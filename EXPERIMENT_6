#include <stdio.h>
#include <stdlib.h>

struct Process {
    int id;
    int burst_time;
    int priority;
};

void sortProcesses(struct Process proc[], int n) {
    struct Process temp;
    for (int i = 0; i < n - 1; i++) {
        for (int j = i + 1; j < n; j++) {
            if (proc[i].priority > proc[j].priority) {
                temp = proc[i];
                proc[i] = proc[j];
                proc[j] = temp;
            }
        }
    }
}

void preemptivePriorityScheduling(struct Process proc[], int n) {
    sortProcesses(proc, n);
    int wait_time[n], turnaround_time[n];
    wait_time[0] = 0;

    for (int i = 1; i < n; i++) {
        wait_time[i] = wait_time[i - 1] + proc[i - 1].burst_time;
    }

    for (int i = 0; i < n; i++) {
        turnaround_time[i] = wait_time[i] + proc[i].burst_time;
    }

    printf("Process ID\tBurst Time\tPriority\tWaiting Time\tTurnaround Time\n");
    for (int i = 0; i < n; i++) {
        printf("%d\t\t%d\t\t%d\t\t%d\t\t%d\n", proc[i].id, proc[i].burst_time, proc[i].priority, wait_time[i], turnaround_time[i]);
    }
}

int main() {
    struct Process proc[] = {
        {1, 10, 2},
        {2, 5, 1},
        {3, 8, 3}
    };
    int n = sizeof(proc) / sizeof(proc[0]);
    preemptivePriorityScheduling(proc, n);
    return 0;
}

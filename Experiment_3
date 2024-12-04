#include <stdio.h>

typedef struct {
    int id;
    int burst_time;
} Process;

void findWaitingTime(Process proc[], int n, int wait_time[]) {
    wait_time[0] = 0;
    for (int i = 1; i < n; i++)
        wait_time[i] = wait_time[i - 1] + proc[i - 1].burst_time;
}

void findTurnAroundTime(Process proc[], int n, int wait_time[], int turn_around_time[]) {
    for (int i = 0; i < n; i++)
        turn_around_time[i] = wait_time[i] + proc[i].burst_time;
}

void findavgTime(Process proc[], int n) {
    int wait_time[n], turn_around_time[n];
    findWaitingTime(proc, n, wait_time);
    findTurnAroundTime(proc, n, wait_time, turn_around_time);
    
    printf("Process\tBurst Time\tWaiting Time\tTurn-Around Time\n");
    for (int i = 0; i < n; i++)
        printf("%d\t%d\t\t%d\t\t%d\n", proc[i].id, proc[i].burst_time, wait_time[i], turn_around_time[i]);
}

int main() {
    Process proc[] = {{1, 5}, {2, 3}, {3, 8}};
    int n = sizeof(proc) / sizeof(proc[0]);
    findavgTime(proc, n);
    return 0;
}

#include <stdio.h>
#include <unistd.h>
#include <sys/types.h>

int main() {
    pid_t pid = fork(); // Create a new process
    if (pid == 0) {
        // Child process
        printf("Child PID: %d\n", getpid());
        printf("Parent PID: %d\n", getppid());
    } else if (pid > 0) {
        // Parent process
        printf("Parent PID: %d\n", getpid());
    } else {
        // Fork failed
        perror("Fork failed");
    }
    return 0;
}

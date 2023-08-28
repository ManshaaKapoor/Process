#include <stdio.h>
#include <stdilib.h>
#include <sys/types.h>
#include <sys/wait.h>
#include <unistd.h>

int main() {
    pid_t pid;
    pid = fork();
    if (pid==0) {
        printf("Child process (PID: %d)\n", getpid());
        printf("My parent id is (PID: %d)\n", getpid());
        char *args[] = {"ls","-l", NULL};
        execvp("ls", args);
        perror("Exec failed");
        return 1;
    } else if (pid >0) {
        printf("Parent process (PID: %d)\n", getpid(), pid);
        wait(NULL); // waiting for child process to complete
        printf("My child process id is (PID: %d)\n", getpid());
    } else {
        perror("Fork Failed!!");
    }
    return 0;
}

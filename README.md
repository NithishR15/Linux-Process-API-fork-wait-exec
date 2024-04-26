## NAME : NITHISH R
## REG NO : 212223040135


# Linux-Process-API-fork-wait-exec-
Ex02-Linux Process API-fork(), wait(), exec()
# Ex02-OS-Linux-Process API - fork(), wait(), exec()
Operating systems Lab exercise


# AIM:
To write C Program that uses Linux Process API - fork(), wait(), exec()

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Write the C Program using Linux Process API - fork(), wait(), exec()

### Step 3:

Test the C Program for the desired output. 

# PROGRAM:

## C Program to print process ID and parent Process ID using Linux API system calls
```c
#include <stdio.h>
#include <sys/types.h>
#include <unistd.h>
int main(void)
{	//variable to store calling function's process id
	pid_t process_id;
	//variable to store parent function's process id
	pid_t p_process_id;
	//getpid() - will return process id of calling function
	process_id = getpid();
	//getppid() - will return process id of parent function
	p_process_id = getppid();
	//printing the process ids

//printing the process ids
	printf("The process id: %d\n",process_id);
	printf("The process id of parent function: %d\n",p_process_id);
	return 0; }
```

## OUTPUT
![Screenshot 2024-03-27 142226](https://github.com/NITHIYANERANJAN/Linux-Process-API-fork-wait-exec/assets/144979351/dcc3f05a-a0d5-42dc-a8b8-4c82bb33c360)


## C Program to create new process using Linux API system calls fork() and exit()
```c
#include <stdio.h>
#include <sys/types.h>
#include <unistd.h>
#include<stdlib.h>
int main()
{ int pid; 
pid=fork(); 
if(pid == 0) 
{ printf("Iam child my pid is %d\n",getpid()); 
printf("My parent pid is:%d\n",getppid()); 
exit(0); } 
else{ 
printf("I am parent, my pid is %d\n",getpid()); 
sleep(100); 
exit(0);} 
}
```

## OUTPUT
![Screenshot 2024-03-27 142249](https://github.com/NITHIYANERANJAN/Linux-Process-API-fork-wait-exec/assets/144979351/777c1275-221f-4827-9074-dd97d6ce66f8)


## C Program to execute Linux system commands using Linux API system calls exec() family
```c
#include <stdio.h>
#include <unistd.h>
#include <stdlib.h>
#include <sys/wait.h>
#include <sys/types.h>
int main()
{       int status;
        printf("Running ps with execlp\n");
        execl("ps", "ps", "ax", NULL);
        wait(&status);
        if (WIFEXITED(status))
                printf("child exited with status of %d\n", WEXITSTATUS(status));
        else
                puts("child did not exit successfully\n");
        printf("Done.\n");
printf("Running ps with execlp. Now with path specified\n");
        execl("/bin/ps", "ps", "ax", NULL);
        wait(&status);
        if (WIFEXITED(status))
                printf("child exited with status of %d\n", WEXITSTATUS(status));
        else
                puts("child did not exit successfully\n");
        printf("Done.\n");
        exit(0);}
```

## OUTPUT
![Screenshot 2024-03-27 142405](https://github.com/NITHIYANERANJAN/Linux-Process-API-fork-wait-exec/assets/144979351/ad7db0a4-e769-46ea-b724-1f5ad9b22ca1)
![Screenshot 2024-03-27 142434](https://github.com/NITHIYANERANJAN/Linux-Process-API-fork-wait-exec/assets/144979351/06e9f646-ed94-4200-a025-b2d024ca38a1)
![Screenshot 2024-03-27 142506](https://github.com/NITHIYANERANJAN/Linux-Process-API-fork-wait-exec/assets/144979351/9be48ca8-1300-4a95-bf4b-6b8f75b2a6c7)


# RESULT:
The programs are executed successfully.














































# RESULT:
The programs are executed successfully.

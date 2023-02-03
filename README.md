# Lab 2
[Fork](https://docs.github.com/en/get-started/quickstart/fork-a-repo) this repo and clone it to your machine to get started!

## Team Members
- 1- Abdelaziz Abdelrhman
- 2- 

## Lab Question Answers

Answer for Question 1: 
 The reliability of the UDP changed by the receiving end of the server having a 50% chance of completely losing the response. This loss occured becuase there's a 50% loss added to the environment. 
 
Answer for Question 2:
The reliability for the TCP changed by the receiving end of the server having a 50% chance of a delayed response! This is because a 50% loss was added to the environment and so the sequence would get resent in the cases they were lost until finally recieved, not caring about any delay.

Answer for Question 3:
The speed of the TCP response changed by having up to around a 10 second delay in response. This might happen because the sending end of the server would keep resending the sequence until it is finally delivered, which would result in a delay.
...
## tcp_server.c Question Answers

  1. What is argc and *argv[]?
  	argc (argument count) = an int that specifies the number of arguments passes to a program (name of program included)
  	*argv[] (argument vector) = an array of character pointers, where the pointers point to the string arguments in the array
  
  2. What is a UNIX file descriptor and file descriptor table?
     	UNIX file descriptor = non-negative int that represents an open file, socket, or other I/O resource
     	File descriptor table = A data struct. that contains the current open file descriptors for a process. 
     	(Discriptors = include info about associated file or I/O resource, such as type, location. and status)
    
  3. What is a struct? What's the structure of sockaddr_in?
     	Struct(structure) = a data type (public by default) that groups zero or more variables with dif data types into a single 		entity
    	struct of sockaddr_in:
     	short int --> address family (should be AF_INET for internet socket addr)
     	unsigned short int --> port number in network byte order
     	struct in_addr --> represents IP address
     	unsigned char --> padding field to align the struct with the 'sockaddr' struct
     	
  4. What are the input parameters and return value of socket()
      	Input paramaters: 1) int domain --> AF_INET --> IPv4 addresses 2) int type --> SOCK_STREAM --> stream sockets 3) int 		protocol --> 0 --> system chooses appropriate protocol
     	Return values: 1) non-negative int (successful)  2) -1 (unsuccessful and tells you the error) 
    
  5. What are the input parameters of bind() and listen()?
  	For bind() : 
     	1) int sockfd --> file descriptor of the socket to be bound
     	2) const struct sockaddr *addr --> address info for the socket, size depends on family specified
      	For listen():
     	1) int sockfd --> file descriptor of the socket to be put in a listening state
      	2) int backlog --> max number of connection that can wait in queue of pending connections (if queue is full, client may 		recieve "connection refused" error)
  
  6.  Why use while(1)? Based on the code below, what problems might occur if there are multiple simultaneous connections to 	handle?
      while(1) is used to continuously accept incoming connections and handle them one at a time.
      If there are multiple simultaneous connections to handle, a problem of the connection being refused or delayed may arise.
  
  7. Research how the command fork() works. How can it be applied here to better handle multiple connections?
     	fork() = a UNIX system call that creates a new process by duplicating the calling process. The original parent process 		and the duplicate child process continue executing from the same point, but with their own separate address spaces
    	This can be applied to handle multiple connections by allowing each incoming connection to be handled (with all their 		processes) independent of other connections
   
  8. This program makes several system calls such as 'bind', and 'listen.' What exactly is a system call?
 	System call = A low level function provided by the OS that allows a program to request a service from the kernel.
    	Provides the interface btwn user-space apps and the kernel. Important part of OS's API, allowing apps to perform tasks 		such as opening or reading files, interacting w/ network, etc.
 
         
  
  
  
  
  
  
  
     

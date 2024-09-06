# Containers

## Container Image

A container image, or most of the time this is simply referred to as an
image, is a read-only template that contains instructions for creating a container. It's a snapshot or blueprint of libraries and dependencies
required inside a container for an application to run.

## Container

A container is the output of a Container Image, and it's a runtime instance; a self-contained software.

## Example: Creating C Podman Container

Directory:
```
.
├── Containerfile
└── main.c
```

Containerfile:
```Dockerfile
# Use Ubuntu as a parent image. 
# This is the OS that the container will run in.
FROM ubuntu:22.04

# Set the working directory in the container.
WORKDIR /usr/src/c-app

# Copy the current directory contents into container's working directory.
COPY main.c .

# RUN tells Docker/Podman what command to run in the CLI.
RUN gcc main.c -o main

# Sets the command to be executed when running a container form an image.
CMD ["./main"]
```

main.c
```c
#include <stdio.h>
#include "DArray/DArray.h"

int AddTwoInts(int x, int y)
{
    return x + y;
}

void print_this()
{
    printf("Printing this!\n");
}

typedef struct {
    void (*print_this_func_ptr)(void);
} ObjOfFun;


int main(void)
{
    int (*func_ptr)(int, int);
    func_ptr = &AddTwoInts;
    int sum = (*func_ptr)(2, 3);
    printf("%d\n", sum);

    // define the pointer.
    void (*print_this_func_ptr)(void);
    // assign the address of the function.
    print_this_func_ptr = &print_this;
    // call the function.
    (*print_this_func_ptr)();

    ObjOfFun o;
    o.print_this_func_ptr = &print_this;
    o.print_this_func_ptr();

    return 0;
}
```

Now, to run this containerfile, we need to do the following:

1. Build the container image.
2. Run the container. 
3. Interact with the container. 

Here is what it looks like from the CLI:
```
# 1. -t is tagging naming our container, and . tells where the Containerfile and other necessary files are.
podman build -t c-app .
# See that the image is built:
podman images
REPOSITORY                            TAG                 IMAGE ID      CREATED        SIZE
localhost/c-app                       latest              dd8a3df89e0a  2 minutes ago  388 MB
# 2. -it where -i keeps the STDIN open (interactive mode) and -t allocates a pseudo terminal allowing us to interact with the container.
# the --rm removes the application after it's done running to keep the background clean.
podman run -it --rm c-app

# 3. If you want to remove the container:
podman rmi c-app
```


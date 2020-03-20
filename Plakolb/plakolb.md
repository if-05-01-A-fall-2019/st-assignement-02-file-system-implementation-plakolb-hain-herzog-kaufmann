# Marcel Plakolb
## What has to be done, when creating a file foo.txt?
Memory has to be allocated.

## What has to be done, when the file size has to be increased? Especially take care if it needs additional blocks
Extra memory has to be allocated and a new has to be too if necessary.

## What has to be done if a file is read sequentially?
read(fd, &buf, all_bytes)

## What has to be done if you want to access foo.txt randomly (seek())?
You need to declare the "whence" in lseek() as a randomly generated location

## What has to be done when the file size decreases? Especially take care if it needs fewer blocks
You need to save free some allocated memory and/or blocks

## What has to be done when a file is deleted?
Free all the allocated memory

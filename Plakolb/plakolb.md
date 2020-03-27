# Marcel Plakolb
## What has to be done, when creating a file foo.txt?
Memory has to be allocated.
In the first few bytes is the name of the file saved.

## What has to be done, when the file size has to be increased? Especially take care if it needs additional blocks
Extra memory has to be allocated and a new has to be too if necessary.

## What has to be done if a file is read sequentially?
We search for the name and read it in the order it's saved.

## What has to be done if you want to access foo.txt randomly (seek())?
Blocksize-bool=size
position/size = nr.block

Is the formula to calculate the wanted position of a file. To enter at a randm location i guess you need to add a rand.

## What has to be done when the file size decreases? Especially take care if it needs fewer blocks
You need to free some allocated memory and/or blocks
That means the blocks just get marked as unused

## What has to be done when a file is deleted?
Free all the allocated memory (it's just getting marked as unused but not overwritten)

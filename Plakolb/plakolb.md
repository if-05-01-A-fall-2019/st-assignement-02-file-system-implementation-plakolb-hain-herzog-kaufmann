# Marcel Plakolb
## What has to be done, when creating a file foo.txt?
Memory has to be allocated.
In the first few bytes is the name of the file saved.
Then we store the location of the other allocated blocks in a metadata file so we know where everything is and in which order.
The path is also saved there.

## What has to be done, when the file size has to be increased? Especially take care if it needs additional blocks
Extra memory has to be allocated if the existing blocks aren't enough.
That means new bytes get allocated and get saved in the metadata file.

## What has to be done if a file is read sequentially?
You want to search for the path which is stored in the metadata file. Then you search for the first allocated block which is stored in said metadata file. That repeats until you are at the end of the file (presumably at '\0').

## What has to be done if you want to access foo.txt randomly (seek())?
Blocksize-bool = size
position/size = nr.block

Is the formula to calculate the wanted position of a file. To enter at a randm location i guess you need to add a rand.

## What has to be done when the file size decreases? Especially take care if it needs fewer blocks
You need to free some allocated memory and/or blocks.
That means the blocks just get marked as unused.
Also everything gets deleted in the metadata file.

## What has to be done when a file is deleted?
Free all the allocated memory (it's just getting marked as unused but not overwritten)

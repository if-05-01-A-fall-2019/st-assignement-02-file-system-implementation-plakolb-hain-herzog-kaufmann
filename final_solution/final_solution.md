# File Systems Implementation
## Own Approach - Kaufmann

### Tasks
#### What has to be done, when creating a file foo.txt?
- The size of the file has to be determined, if it needs multiple blocks or if one is enough. The harddrive controller(Each portion has free space mgmnt) has a table where the address stored -> it can give us the addresses of free space. The space on the disk has to be marked as full. To keep track of the files we need to give each file a unique id. We have to create a lookup table with file name and the unique id from before. So we have on the address specified in the table we have a "metadata" block with all the start and end addresses and the block ids, the path is also saved here
#### What has to be done, when the file size has to be increased? Especially take care if it needs additional blocks
- The blocks where the file is have to be update in the metadata block. The extra space has to be allocated(read the first one)
#### What has to be done if a file is read sequentially?
- With the unique id we can search the addresses in the metadata block. If the file spans across multiple blocks you have jump back to the metadata block to keep track where to read next, or you can write the whole file or the address information to the ram so you don't need to jump to the metadata block, this should save time and should take load of the harddrive
#### What has to be done if you want to access foo.txt randomly (seek())?
- You have to check if the specified address is part of the file with the metadata block of the file name, if it is you can read the address

- Formula
  Blocksize-bool = size

  position/size = nr.block

  blocksize ... all the allocated space

  bool ... the realy used space

  position ... where I want the file

  size ... the real used space
#### What has to be done when the file size decreases? Especially take care if it needs fewer blocks
- We need to make sure that we don't delete the parts of the file that the user wants to keep. The space that is now free has to be released (Marked as free). The addresses in the metadata block have to be updated accordingly
#### What has to be done when a file is deleted?
- All the space has to be marked as unused but we don't want to overwrite the data because that would be to performance heavy and the address have to be removed.

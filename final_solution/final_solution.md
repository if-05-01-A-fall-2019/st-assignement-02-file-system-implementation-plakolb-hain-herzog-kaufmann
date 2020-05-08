# File Systems Implementation
## Own Approach - Kaufmann

### Tasks
#### What has to be done, when creating a file foo.txt?
- The size of the file has to determined, if it needs multiple blocks or if one is enough. The harddrive controller(Each portion has free space mgmnt) has a table where the address stored -> it can give us free addresses. The space on the disk has to be marked as full. To keep track of the files we need to give each file a unique id. We have to create a lookup table with file name and the unique id from before. So we have on the address specified in the table we have a "metadata" block with all the start and end addresses and the block ids, the path is also saved here
#### What has to be done, when the file size has to be increased? Especially take care if it needs additional blocks
- The blocks where the file is have to be update in the metadata block. The extra space has to be allocated(read the first one)
#### What has to be done if a file is read sequentially?
- If the file spans across multiple blocks you have jump back to the metadata block to keep track where to read next, or buffer the whole file in to the ram
#### What has to be done if you want to access foo.txt randomly (seek())?
- You have to check if the specified address is part of the file with the metadata block of the file name, if it is you can read the address
#### What has to be done when the file size decreases? Especially take care if it needs fewer blocks
- We need to make sure that we don't delete the parts of the file that the user wants to keep. The space that is now free has to be released, the addresses in the metadata block have to be update accordingly
#### What has to be done when a file is deleted?
- All the space has to be marked as unused but we don't want to overwrite the data because that would be to performance heavy and the address have to be removed.

# File Systems Implementation
## Own Approach - Kaufmann

### Tasks
- The size of the file has to determined, if it needs multiple blocks or if one is enough. The harddrive controller(Each portion has free space mgmnt) has a table where the address stored -> it can give us free addresses. The space on the disk has to be marked as full. To keep track of the files we need to give each file a unique id. We have to create a lookup table with file name and the unique id from before. So we have on the address specified in the table we have a "metadata" block with all the start and end addresses and the block ids, the path is also saved here
- The blocks where the file is have to be update in the metadata block. The extra space has to be allocated(read the first one)
- If the file spans across multiple blocks you have jump back to the metadata block to keep track where to read next, or buffer the whole file in to the ram
- You have to check if the specified address is part of the file with the metadata block of the file name, if it is you can read the address 
- We need to make sure that we don't delete the parts of the file that the user wants to keep. The space that is now free has to be released, the addresses in the metdata block have to be update accordingly
- All the space has to be marked as unused but we don't want to overwrite the data because that would be to performance and the address have to be removed.

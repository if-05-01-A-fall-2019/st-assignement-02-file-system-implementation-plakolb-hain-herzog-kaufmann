# File Systems Implementation
## Own Approach - Kaufmann

### Tasks
- The size of the file has to determined, if it needs multiple blocks or if one is enough. The harddrive controller has a table where the address stored -> it can give us free addresses. The space on the disk has to be marked as full. The blockids have to be saved in the first block, the start address and end address have to be stored as well.
- The blocks where the file is have to be stored -> addresses. The extra space has to be allocated(read the first one)
- If the file spans across multiple blocks you have to keep track where to read next, or buffer the whole file in to the ram
- You have to keep track of where the start and end is, especially when it is on multiple blocks.
- We need to make sure that we don't delete the parts of the file that the user wants to keep. The space that is now free has to be released, the addresses have to be updated accordingly
- All the space has to be marked as unused but we don't want to overwrite the data because that would be to performance and the address have to be removed.

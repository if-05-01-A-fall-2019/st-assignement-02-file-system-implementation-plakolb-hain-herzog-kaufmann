# File Systems Implementation
## Own Approach - Kaufmann

### Tasks
- The size of the file has to determined, if it needs multiple blocks or if one is enough. The space on the disk has to be allocated. The blocks have to be saved somewhere, the start address and end address have to be stored as well.
- The blocks where the file is have to be stored. The extra space has to be allocated
- If the file spans across multiple blocks you have to keep track where to read next
- You have to keep track of where the start and end is, especially when it is on multiple blocks.
- The space that is now free has to be released, the addresses have to be updated accordingly
- All the space has to be released, and the address have to be removed.

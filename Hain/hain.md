Hain Lukas

- size of the file determined, how many blocks it needs, space on the disk marked as full, blockids saved in the first block, start address and end address stored,
- extra space allocated, bocks stored
- If the file spans across multiple blocks: keep track where to read next,
- keep track of start and end,
- don't delete the parts of the file that the user wants to keep, free space released, addresses updated,
- All space has to be marked unused

# File System Implementation
#### What has to be done, when creating a file foo.txt?
- storage & blocks have to be allocated
<br>&nbsp;&nbsp;&nbsp;infos like the filename and the metadata block of the file are being stored in the first blocks 
- file name entry has to be created
#### What has to be done, when the file size has to be increased? Especially take care if it needs additional blocks
- free blocks have to be found
- info that doesn't fit on the old blocks has to be moved & saved on the free ones
#### What has to be done if a file is read sequentially?
- all blocks with bits of the file have to be found
- return all found bytes (joined)
#### What has to be done if you want to access foo.txt randomly (seek())?
- a block to jump to has to be calculated
  <br>&nbsp;&nbsp;&nbsp;the metadata file helps us with that
- the info of each block has to be taken care of
#### What has to be done when the file size decreases? Especially take care if it needs fewer blocks
- blocks that are not being used anymore have to be marked as 'free' by the system
- those 'free' blocks have to be removed from the file
#### What has to be done when a file is deleted?
- file name entry has to be removed from directory
- unused blocks have to be marked 'free' again, just like when decreasing the size
- it's not being overwritten unless a third-party program is being used to do so

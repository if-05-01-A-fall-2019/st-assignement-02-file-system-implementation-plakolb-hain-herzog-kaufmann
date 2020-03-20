# File System Implementation
## What has to be done, when creating a file foo.txt?
- storage & blocks have to be allocated
<br>&nbsp;&nbsp;&nbsp;infos like the filename are being stored in the first blocks 
- file name entry has to be created
## What has to be done, when the file size has to be increased? Especially take care if it needs additional blocks
## What has to be done if a file is read sequentially?
## What has to be done if you want to access foo.txt randomly (seek())?
## What has to be done when the file size decreases? Especially take care if it needs fewer blocks
## What has to be done when a file is deleted?
- file name entry has to be removed from directory

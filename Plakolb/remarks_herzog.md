# File Systems Implementation - Remarks
#### What has to be done, when creating a file foo.txt?
/
#### What has to be done, when the file size has to be increased? Especially take care if it needs additional blocks
- why do allocated blocks get saved in the metadata file?
#### What has to be done if a file is read sequentially?
/
#### What has to be done if you want to access foo.txt randomly (seek())?
- "Blocksize-bool=size position/size = nr.block" what does that mean exactly?
- are you sure about using random?
#### What has to be done when the file size decreases? Especially take care if it needs fewer blocks
- is really everything deleted in the metadata file? (since it's not being deleted)
- why 'and/or' blocks?
#### What has to be done when a file is deleted?
- why is it not being overwritten?



<br><br><br><br>(typos not corrected)

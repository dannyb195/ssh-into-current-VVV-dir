# ssh-into-current-VVV-dir

In your local user's bin dir add a new file, this file's name will be the name of the command you type. Pasting the following into this file will allow you to run this command from within a VVV install and be taken directly to the same virtual directory. This is helpful as you are not taken to the VVV user's home dir then needing to navigate to the virtual dir as well.

```
#!/bin/bash
local_path=$(pwd);
local_path=${local_path##*www/}; # http://stackoverflow.com/questions/19482123/extract-part-of-a-string-using-bash-cut-split
ssh -t vagrant@vvv.dev "export LOCAL=$local_path; bash"
```

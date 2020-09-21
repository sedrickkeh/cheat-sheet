# cheat-sheet
List of useful commands I've googled way too many times

**Check size of file in command line**

`du -sh (filename)`


**Untar / Unzip**

`tar -zxvf (filename)` 

`tar -C /path/to/save/destination -zxvf yourfile.tar.gz`

`unzip file.zip`

`unzip file.zip -d destination_folder`


**Virtual Environments**

venv:
`python3 -m venv /path/to/new/virtual/environment`

conda:
`conda create -n env python=3.6 pip`

**Github**

Setting username and user email:

`git config user.name (your_username_here)`

`git config user.email (your_email_here)`

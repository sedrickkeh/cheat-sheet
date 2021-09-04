1. Download file from [anaconda website](https://www.anaconda.com/products/individual) using `wget`.
2. You should get the file `Anaconda3-2021.05-Linux-x86_64.sh`. Run `sh Anaconda3-2021.05-Linux-x86_64.sh`
3. Set path: 
```bash 
echo ". /home/(username)/anaconda3/etc/profile.d/conda.sh" >> ~/.bashrc
echo "export PATH="/home/(username)/anaconda3/bin:$PATH"" >> ~/.bashrc
source .bashrc
```
4. `conda init`
5. Reset shell.

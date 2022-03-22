# cheat-sheet
List of useful commands I've googled way too many times


## Linux
**Check size of file in command line**
```bash
du -sh (filename)
```
**Check disk usage**
```bash
df -hl
```
**Check number of files in dir**
```bash
ls -1 | wc -l
```


**Untar / Unzip**
```bash
tar -zxvf (filename)
tar -C /path/to/save/destination -zxvf yourfile.tar.gz
unzip file.zip
unzip file.zip -d destination_folder
```

## Virtual Environments
venv:
```bash
python3 -m venv /path/to/new/virtual/environment
```
conda:
```bash
conda create -n (name) python=3.6 pip`
```

## Git
Setting username and user email:
```bash
git config user.name (your_username_here)
git config user.email (your_email_here)
```

Creating repo:
```bash
git remote add origin [git-url-here]
git push --set-upstream origin master
```

Undo commit: 
```bash
git reset HEAD^
```

Pushing:
```bash
git push --set-upstream origin (branch_name)
```

Delete branches:
```bash
git fetch --prune
git branch -d the_local_branch
```



## Python
Create path if doesn't exist: 
``` bash
if not os.path.exists(savepath):
    os.makedirs(savepath)
```

Read from txt file
```bash
with open("input.txt", "r") as f:
    for line in f.readlines():
        arr.append(line.strip())
```

List to txt file:
```bash
with open("output.txt", "w") as f:
    for line in arr:
        f.write(line+'\n')
```

Read json list of dicts 
```bash
with open("input.json", 'r') as f:
    arr = list(map(json.loads, f))
```

## Wandb
Initialize:
``` bash
wandb.init(project="(project-name)", entity="(user/team-name)")
wandb.config.update(args)
```

Watch model:
``` bash
wandb.watch(model)
```

Logging results:
``` bash
wandb.log(dict_of_results)
```

## Gdown (wget from Google Drive)
```bash
pip install gdown
gdown https://drive.google.com/uc?id=(insert_id_here)
```

## Random shuffle/split 
Torch:
```bash
train_len = train_data.shape[0]
val_len = int(train_len * 0.2)
train_len -= val_len
train_dataset, val_dataset = torch.utils.data.random_split(train_dataset, [train_len, val_len])
```

Lists:
```bash
from sklearn.model_selection import train_test_split
X_train, X_val, y_train, y_val = train_test_split(x, y, test_size=0.2, random_state=42)
```

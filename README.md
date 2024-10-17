# usingazurecli
Commands on using azure command line

# install 

## curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
--
# Login
## az login - login to the account
### here you need verify you account by clicking on the verify link enter the code sign in 
---
# Uploading the folder in azure storage container

## setup 
 ```
 STORAGE_ACCOUNT_NAME=""
 ```
 ``` 
 CONTAINER_NAME=""
```
``` 
LOCAL_FOLDER_PATH="path"
```
### Try creating a new folder for uploading the files if you want it organized because when you type folder/ as local_folder it will upload contents of folder/ not with folder so try creating a folder inside a folder like folder/folder now if you give folder it will also upload folder/
### To upload the folder to storage container
``` 
az storage blob upload-batch --account-name $STORAGE_ACCOUNT_NAME --destination $CONTAINER_NAME --source $LOCAL_FOLDER_PATH --auth-mode login
```


---

# Bonus commands

## To run a command in background like wget or appache serve commands which should makes terminal with continous logs you can use

``` 
nohup wget https://download_link &> wget.log &
```

## To view whats happening with command

``` 
tail -f wget.log
```

## or you can also use screen which open a new session in the terminal to exit you press ctrl+d
``` 
screen
```

## To check available disk or space 

``` 
df -h
```

### for full check

## To check space occupied by the folder you can use

```
du -sh path_to_folder
```

or 

```
du -h /path_to_folder
```

## To delete a set of folder from a txt file the folder will have all the folder names to be deleted we use xargs to pass it to rm -rf
```
xargs rm -rf < folders.txt
```


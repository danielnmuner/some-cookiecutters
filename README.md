![GitHub branch checks state](https://img.shields.io/github/checks-status/darngcode/some-cookiecutters/main?label=Cookiecutter&logo=Cookiecutter)
# Cookiecutters
---
This repo encompasses what I think is relevant and good enough to create personal projects as a future data analyst. All the repositories were cloned and saved on my own. Please take them a look if you want to. 

#### Some links
Here are the links to go through and sure their amazing authors. 
1. [balechon](https://github.com/balechon/cookiecutter-Data_Analysis)
2. [jvelezmagic](https://github.com/jvelezmagic/cookiecutter-conda-data-science)
3. [pjbull](https://github.com/drivendata/cookiecutter-data-science)  
### Python Directory and Files Management [programiz](https://www.programiz.com/python-programming/directory)
---
### OS Module
This package abstracts the functionalities of the platform and provides the python functions to navigate, create, delete and modify files and folders. "[stackabuse](https://stackabuse.com/introduction-to-python-os-module/)"

- [x] Import OS module  
``` import os```
- [x] State variables 
```CURRENT_DIR = os.getcwd()``` Current location  
```DATA_DIR=os.path.join(CURRENT_DIR,os.pardir,'data','raw') ``` os.path.join allow us to join all arguments on that function.
- [x] Confirm ```DATA_DIR``` exist.  
```os.path.exists(DATA_DIR)```  
- [x] Iterate over ```DATA_DIR``` using the next code    
```[os.path.join(DATA_DIR,item) for item in os.listdir(DATA_DIR)]``` The function ```listdir()``` turn ```DATA_DIR``` into a iterable.  
- [x] Create a folder using ```os.mkdir()``` function.  
```os.mkdir(os.path.join(CURRENT_DIR,'folder_name'))``` In doing so we can create the folder in that especific path.

#### As an alternative, we can use the pathlib module that's easier to implement than the os module. 

- [x] import pathlib  
``` 
import pathlib
CURRENT_DIR = pathlib.Path().resolve()
DATA_DIR = CURRENT_DIR.parent.joinpath('data')
```
Functions like ```Path()``` abstract the O.S. path structure and will use ```/``` or ```\``` depending on. ```resolve()``` is a linux function that displays the path to get to current directory. Finally ```parent``` and ```joinpath``` to bring certain path.  

- [x] Creating a folder with pathlib differs from the os module.  Here is the right way with pathlib.

``` DATA_DIR.joinpath('pathlib').mkdir()``` Instead of specifying the path and file or folder name within the ```mkdir()``` function we'll define it before the function. 

- [x] List specific files based on a pattern or wildcards
```list(DATA_DIR.glob(".git*"))``` Globbing is mainly used to match filenames or searching for content in a file. Globbing uses wildcard characters to create the pattern [linuxhint](https://linuxhint.com/bash_globbing_tutorial/)

### PyFilesystem2
PyFilesystem2 stand out from previous modules given that whenever we arrange a path we'll just use ```/``` separately from the O.S. for instance ``` DATA_DIR = fs .open_fs('../data/raw/') ```
It generally resemble to prior modules when it comes to the basic functionalities.
```
import fs
# Open current directory
CURRENT_DIR=fs.open_fs('.')
#Previous function will return a OSFS object so it's no longer a simple str
```  
Now if you want to iterate over pathname we can use the next function ``` walk.files()``` as shown below.

```
for path in DATA_DIR.walk.files():
    print(path)
```



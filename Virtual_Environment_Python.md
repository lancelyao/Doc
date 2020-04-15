# Python Virtual Environment
Virtual environment can help separate projects with dependency on the same pakcage in different version. For instance, two projects need to use the same package numpy but one project needs to use version 2.x, another needs version 3.x.
## Steps
### Create a vitrual environment
1. Install virtualenv
```
$ pip3 install virtualenv
```
2. Create "Environments" folder
```
$ mkdir Environments
$ cd Environments
```
3. Create virtual environment "env1"
```
$ virtualenv env1
```
4. Before activate env1, we can use `pip3 list` to check the installed package list in the global environment, then compare with the package installed later in virutal environment *env1* 
```
$ pip3 list
```
5. Activate vitual environment, now we are in the env1 vitual environment
```
$ source env1/bin/activate
```
6. Install a package in the virtual environment
```
$ pip3 install nltk
```
7. Compare the difference between `pip3 list` in *env1* and the list in global environment in step 4
```
$ pip3 list
...
nltk 3.5 # this package only exists in env1
```
8. Export installed package
```
# -l, --local If in a virtualenv that has global access, do not output globally-installed packages.
$ pip3 freeze --local > requirements.txt 
```
9. Exit *env1* vitual environment
```
$ deactivate
```
### Switch installed pacakges to another virtual environment
1. Remove *env1* environment
```
$ rm -rf env1/
```
2. Use python3 to create virutal environment *env2* and activate
```
$ which python3
$ virtualenv -p .../bin/python3 env2
$ source env2/bin/activate
```
3. Check python verison
```
$ python --version
Python 3.8.2
```
4. Install packages from requirements
```
$ pip3 install -r requirements.txt
$ pip3 list
```
5. Exit *env2*
```
$ deactivate
```
## Caveat
```
$ ls
requirements.txt  env1 env2
```
Python projects should not be placed in folders of virtual environemnts *env1* *env2* , these folders are only for environment separation.
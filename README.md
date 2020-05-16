## Creation Of Virtual environment & Ansible Installation

You can use the [editor on GitHub](https://github.com/rohitthakur2590/cosmosandcode/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Install virtual environment on fedora

```markdown
[rothakur@localhost ~]$ sudo pip install virtualenv
```
### Install python 3.4 , 3.5, 3.6, 3.7, 3.8 

```markdown
[rothakur@localhost ~]$ sudo dnf install python34
[rothakur@localhost ~]$ sudo dnf install python35
[rothakur@localhost ~]$ sudo dnf install python36
[rothakur@localhost ~]$ sudo dnf install python37
[rothakur@localhost ~]$ sudo dnf install python38
```
### Go to the directory

```markdown
[rothakur@localhost ~]$ cd ios-xrv9k
```
### Install virtual environment wrapper

```markdown
[rothakur@localhost]$ sudo pip install virtualenvwrapper 
```
### Edit content of bash_profile file. (you might not have local)### Add upstream and checkout upstream branches in gitcode directory

```markdown

```markdown
 [rothakur@localhost]$ vi ~/.bash_profile
              export WORKON_HOME="~/venvs"
              VIRTUALENVWRAPPER_PYTHON='/usr/local/bin/python'
               source /usr/local/bin/virtualenvwrapper.sh

```
### run bash_profile

```markdown
 [rothakur@localhost]$ source ~/.bash_profile
```
### Make vitual environment for desired python version

```markdown
 [rothakur@localhost]$ mkvirtualenv -p python2.7 ansible27
```
### Create a personal dev-workspace directory and clone the forked git code

```markdown
 [rothakur@localhost]$ cd ~
 [rothakur@localhost]$ mkdir dev-workspace
 [rothakur@localhost dev-workspace]$ git clone https://github.com/rthakur2590/ansible.git
```
### Edit postactivate file in virtual environment

```markdown
 [rothakur@localhost dev-workspace]$ vi ~/venvs/ansible27/bin/postactivate
                       cur_dir=`pwd`
                       cd ~/dev-workspace/ansible
                       pip install -r requirements.txt
                       source hacking/env-setup
                       cd $cur_dir
                       clear
                       out="$(ansible --version)"
                       echo $out
 ```                      
### Add upstreams

```markdown
 [rothakur@localhost dev-workspace]$ cd ~/dev-workspace/ansible/
 [rothakur@localhost dev-workspace ansible]$ git remote add upstream https://github.com/ansible/ansible
 [rothakur@localhost dev-workspace ansible]$ git remote -v
 origin	git@github.com:rohitthakur2590/ansible.git (fetch)
 origin	git@github.com:rohitthakur2590/ansible.git (push)
 upstream	https://github.com/ansible/ansible (fetch)
 upstream	https://github.com/ansible/ansible (push)
 ```
### Checkout upstream branches in gitcode directory

```markdown
 [rothakur@localhost dev-workspace ansible]$ git fetch upstream
 [rothakur@localhost dev-workspace ansible]$ git rebase upstream/devel
 [rothakur@localhost dev-workspace ansible]$ git checkout -b stable-2.8 upstream/stable-2.8
 [rothakur@localhost dev-workspace ansible]$ git checkout -b stable-2.7 upstream/stable-2.7  
 [rothakur@localhost dev-workspace ansible]$ git checkout -b stable-2.6 upstream/stable-2.6 
```
### Set virtual environment with command

```markdown
 [rothakur@localhost dev-workspace ansible]$  workon ansible27
```
### deactivate virtual environment with command

```markdown
 [rothakur@localhost dev-workspace ansible]$  deactivate
```

### Note

```markdown
 Just like we setup environment for python27 we could follow similar steps for other python versions.
```
            


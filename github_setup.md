# github setup via command line for CGLabs

## Step 1: Create SSH key in cglabs with the email associated with your github account; first create a folder with the name ssh
`mkdir ~/.ssh`   
`cd ~/.ssh`   
`ssh-keygen -o -t rsa -C "your_email@gmail.com"`   
 
*you can igonre the following for the default*
`Enter file in which to save the key (/home/jovyan/.ssh/id_rsa):`

This process will create two paired files `id_rsa.pub` and `id_rsa`. Never share `id_rsa`. It remains in the CGLabs only. For any other service that you want to link with CGLabs and that allows SSH access, use the contents of `id_rsa.pub`.

## Step 2: Add the public key to your github account
**get the content of the public SSH key**
`cat id_rsa.pub`
**link it with your github account**
(Needs to be done via the web-browser)Your github account -> Settings -> SSH and GPG Keys -> New ssh key -> paste the content of the public key in there

## Step 3: Now test with a git repo (new or existing)     
**create a folder to keep the codes**   
`cd`   
`mkdir codes`   
`cd codes/`   

**clone an existing repo or even create a new one; make sure to use the git@... url**    
`git clone git@github.com:ani-ghosh/test_repo.git`     

**make some changes/add files and push the changes back**   
`cd test_repo`   

**configure the repo; only for the first time**   
`git config --global user.email "your_email@gmail.com"`     
`git config --global user.name "your_username"`    

**create a new file**
`echo 'git test text' > test.txt`     

`ls`    

**some basic git magic commands**   
`git status`    
`git add *`    
`git push`    

**Check your test repo, all the changes should be updated there**   

#SVN
 problems and solutions 


1. How to get SVN_REVISION number in Jenkins Pipeline 
solution: 
Please use below snippet of code: 
node(){

bat '''@echo off
 
for /f "tokens=2" %%i in (\'svn info -rHEAD https://svn.com/trunk^|find "Revision"\') do SET SVN_REVISION= %%i

echo %SVN_REVISION%

'''

}


If you see these type of problems while getting SVN_REVISION number in Jenkins Pipeline,

svn: E170013: Unable to connect to a repository at URL 'https://<>/trunk'
svn: E215004: No more credentials or we tried too many times.
Authentication failed

Solution: please go to your Jenkins build server and go to any Project Workspace, and 
enter svn up 
Ex: D:\WS\<Any_job>svn up  

here, it will ask for user name and password of your repo like beanstalk, github etc.,

Your problems has solved.  

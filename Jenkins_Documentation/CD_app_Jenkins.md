## Using Jenkins for CD

### Creating a Dev branch

1. We needed to start working from a 'dev' branch as you would never use the main branch accept for when code is ready and tested for production. 
2. In terminal use the 'git checkout dev' to switch to dev branch
3. We then want to use Jenkins to merge the changes to Main branch from the initial dev branch.
4. So we return to our initial job on Jenkins and change the branch specified to 'dev' branch so that it's listening for changes on their.
5. Then we create another 'freestyle' project, with the same configurations except this time in 'post build options' we choose 'git publisher' in the drop down. 
6. In the 'git publisher section' we select 'Push only if build succeeds', 'merge results' and then specify that we want to merge 'main' with 'origin' as the remote target.
7. Once this is complete we can make a change on our local machine on the dev branch and when we push it should also be seen on Jenkins to complete both jobs and have visible changes then on the main branch. 
   
![alt text](<Screenshot 2024-03-22 at 12.03.58-1.png>)

### Deployment of app to production

1. Enter into configure for job 3 (our cd job in this case)
2. In the execute shell we want to add some commands for the app to run in the background and to enable us to make changes to deploy using the jenkins pipeline from one push.
3. To do this we added the below commands 

#Change to app directory   
cd app
#Kill the node.js/npm processes
killall -9 node npm 
#Install the node.js dependencies (ci is clean install)
npm ci
#Start the node.js app in the background (nohup)
nohup node app.js > /dev/null 2>&1 &

4. Now with the build trigger being set to the previous job (the merge job) it means when we push on local machine we can see all of the jobs working and then the changes are visible on port 3000. 
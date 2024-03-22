## Using Jenkins for CD

### Creating a Dev branch

1. We needed to start working from a 'dev' branch as you would never use the main branch accept for when code is ready and tested for production. 
2. In terminal use the 'git checkout dev' to switch to dev branch
3. We then want to use Jenkins to merge the changes to Main branch from the initial dev branch.
4. So we return to our initial job on Jenkins and change the branch specified to 'dev' branch so that it's listening for changes on their.
5. Then we create another 'freestyle' project, with the same configurations except this time in 'post build options' we choose 'git publisher' in the drop down. 
6. In the 'git publisher section' we select 'Push only if build succeeds', 'merge results' and then specify that we want to merge 'main' with 'origin' as the remote target.
7. Once this is complete we can make a change on our local machine on the dev branch and when we push it should also be seen on Jenkins to complete both jobs and have visible changes then on the main branch. 
   

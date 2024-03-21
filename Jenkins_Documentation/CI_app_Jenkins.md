### How to use CI for the app on Jenkins

1. In your Github repo, navigate to 'settings' 
2. In the side panel you will see a section for 'Webhooks'
3. Click on this and select 'Add Webhook' in the top right hand side.
4. In 'Payload URL' paste the public IP to your Jenkins page and then add /github-webhook/
5. Select the content type to 'Application Json'
6. Select 'Just the push event' as the trigger.
7. Ensure it says 'activate webhook' and then create it.
   ![alt text](<Screenshot 2024-03-20 at 17.34.37-1.png>)
8. Then switch over to your Jenkins dashboard on a seperate browser tab.
9.  Create a 'new item', name it (in this instance 'Niamh CI')
10. Choose 'Freestyle project'
![alt text](<Screenshot 2024-03-20 at 17.33.59.png>)

11.  Add a description of what the build is going to do (in this case Test whether a webhook works)
12.  Also select 'Discard old builds' with a Max build of '3' this will delete the oldest builds after three are done.
13.  Link it to your Github Project by ticking 'github project' and then using the https: URL of the github repo you want to link
![alt text](<Screenshot 2024-03-20 at 17.35.51-1.png>) 
    
14.   In the 'Office 365 Connector' select the setting 'Restrict where this project can be run' and in our case enter 'Sparta-ubuntu-node'
   ![alt text](<Screenshot 2024-03-20 at 17.36.54.png>)
15.   For 'Source Control Management' select 'Git'
16.   Paste your repo's SSH Url into the 'repository URL'
17.   Choose the Credentials you want to use (in this case a key) See previous documentation on How to add a key, should you need to.
18.   .   Ensure the 'Branches to build' is configured to the 'main' branch or desired branch
19.  Select 'Github hook trigger for GITScm polling' in build triggers
20.  In "build environment" select 'Provide Node & npm in/folder to PATH'
   
   ![alt text](<Screenshot 2024-03-20 at 17.38.19-1.png>)
   
21. Add build steps required (in our case the cd and comands to install/test)
22. Click save.
23. To test, go to a file you want to make a change to, make the change and push it to your Github repo, you should then see your change visible in the repo but also should see that it has been successful in the build history because it would have turned blue with a sun emoticon next to it. 
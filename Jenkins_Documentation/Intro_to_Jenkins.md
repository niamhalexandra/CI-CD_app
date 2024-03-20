# How to use Jenkins

### Build a Job

* Tasks in jenkins are called 'jobs' we can click on create a new job to make something new for our pipeline
* First you enter a name for the job and the type of project (in our case fresstyle).
* Then you configure the build, we set it up with just a setting to delete after certain amount of builds (discard old builds)
* You can then select to use a build step which is where you'll enter commands. You choose 'execute shell' to run Linux commands. 
* We built one with the 'uname -a' command to check the OS we were using and also another build for 'date' to see what timezone we were operating in
* After these had both ran successful (pressing build now) They showed as blue on the dashboard with a sun. 
* We were then able to enter the configure sessions on the first job to select a 'post-build action' this allowed us to then connect the second job so that once the first was executed sucessfully it would run that second jobs command... this is how you build out a pipeline
* It is important as you build your pipeline you test every job so it's easier to troubleshoot further down the line.

### SSH connection to Jenkins from Github

* Create a 'new item' (job) as you would for a new command, this time, tick the box for 'github project' there you are able to paste the https URL for your github repo
* In 'Office 365 connector' you want to tick 'restrict where this project can be run' and in our case we typed 'sparta-ubuntu-node'
* Then in source code management, tick 'Git', paste your SSH url 
* Then add a key you want to use, click the drop down 'add' then 'jenkins' a seperate configuration box comes up, here you enter what type of key you want to use, give it a name and then paste in the private key that Jenkins needs to use with your github. ENSURE that when pasting you include the -------OPEN------ and ending part too. 
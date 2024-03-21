# CI/CD 

### What is CI?

####  _Continuous_ _Integration_

* Continuous integration by integrating code changes from developers (including multiple) into a shared repo
* This allows for detection of integration errors early on in dev process so software quality can be improved in reduced time with reduced effort to release the software
* In CI a dev will regularly commit changes using version control (e.g git) this triggers an automated build process compiling code, running tests and going through other verification steps
* Tools for CI include, Jenkins, Github Actions and more.
  
  ### When would you use it?

* When there are multiple developers contributing 
* When wanting to optimise time and effort put into release of software
  
  ### Why use it?

* Early detection of errors CI helps catch integration issues, like conflicting changes between different developers code earlier on in the development cycle, minimising the time and effort required to fix them.
* By continuously integrating and testing the code changes, you can maintain a high level of software quality, ensuring that each code commit meets standards and works correctly.
* Feedback to developers about the correctness and stability of their code changes comes more quickly so they can address issues promptly.
* Streamlined Development Process, CI automates the build, tests, and validates process, allowing developers to focus on writing code rather than manual tasks
  
  ### How would you use it?

* Set up a Version Control System such as Git to manage the code changes
* Choose and setup a CI server (e.g., Jenkins, or GitHub Actions) to automatically
* Integrate code analysis tools, linters, and static analysis tools to enforce coding standards and identify potential issues early in the development cycle.
* Configure notifications and alerts to notify developers of build failures or other issues, enabling them to take corrective actions promptly.

### Where would you use CI?

* CI can be used in any software development environment but particularly useful for projects where a lot of developers are involved.
* It is very good for projects with frequent code changes or complex dependencies.
* CI is good for ensuring time is optimised, so if there is deadlines to meat or costs to consider then this optimisation would be really beneficial.
                                                  

Day - 10

Git Branching Strategy

For any organization, Primary Goal is that the customers get the releases on time and promptly.

Deliver Releases with new changes frequently. For this it is very important to have a very efficient branching strategy.

Customer gets releases on time so branching is important for small tasks to be delivered on time.  

What is a Branch ? 
Branch is a separation. 
You have an application named as calculator - v1 and then you have changes which is made and it is called as calculator — v2

After developing and testing, you are confident that it is ready to work, then you just merge into the main application as calculator — v2 and just remove the older one and this starts working as the main application.  

Example(Real Scenario) --> Earlier — Uber was just supporting cab booking and then they wanted to add uber bikes. Uber Cabs functionality was already in production and they wanted to add the bike functionality to their application to attract even more customers. 

Uber people were not confident about the bikes and so they started developing the Bike functionality in a separate branch.

So they create the bike branch and they continue there testing and development and after the team is confident, the bike functionality is added to the main working application and then the Branch which was created for the development and testing of the Bike functionality gets deleted and the main application is working with both cab and bike booking use cases for the end users i.e customers using the Uber application.

CALCULATOR —> Github —> is being developed with the new fixes and creating commits on this existing GITHUB repo —> now they decided to add new features on this application —> So for this adding the new features, a new feature branch is created and after testing and development, this feature branch gets merged to main or master branch.

You have multiple feature branches in an organization, and as the feature gets ready and then it gets merged to the main/master branch.

Release Branch —> To deliver to the customer, we usually build the application from the release branches. You are very satisfied with the application and then you ship this release branch to the customer.

Master is usually being kept for active development 

Release branch is only kept for the final shipping of the new feature or application to the customer. 

Hot fix branches - immediate fixes to be delivered to the customer, this hot fix gets merged with the master and then to the release branches, then the code is shipped from release but the main branch has the up to date codes.  

What is Hot fix branch ? 
What is Feature branch ? 
What is Main branch? 
What is Release branch?  
Answer these questions

11 June -- codebase 
Calculator - Branch - main/master 
Some changes are there which needs to be added to the Calculator application,
So instead of tocuhing the main branch or the production running codebase, 
we create a FEATURE branch for that functionality and when we are confident with the coding and the testing part of the feature branch and then we will merge it with the Main/Master Branch.

Due to many changes being developed simultaneously, many feature brnahces are created for an application to add new functionality.

Any changes which is being developed, needs to be shipped to the customer.
We usually build the application from the Release branches and not from the Main branch.
So to deliver the new functionality, we use release branches for the testing and the shipping of the code to the customer.

So Why we use a Release branch ?
We use the Release Branch because, we want to ship the final production ready code to the customers on time.
So the release branch only has the prod ready changes and nothing else is present in that branch.

Why not directly ship using Main branch ?
Because the main branch will be having active developments going on simultaneouly by other developers, so shippinh use main will also ship the under progress code to the customers which is wrong and shouldn't happen in an organization which sets up pretty bad delivery standards and also if a project is shipping code through the main branch, then only one person can develop that application only or if many people are there, then they will have to wait for the dev who is doing his changes to completely ship it to customer and then a new change will start for that application.
SO this creates delay in the product enhancements and other project releated tasks.


MASTER/MAIN --> Branch
FEATURE     --> Branch
RELEASE     --> Branch
             






 



# Bug Workflow

To meet Moravia standard for quality of software development it is required what each Bug in TargetProcess follows these states and rules

- [Buglog](#buglog)
- [Planning](#planning)
- [Ready](#ready)
- [In Progress](#in-progress)
- [Review](#review)
- [DEV](#dev)
- [TEST](#test)
- [Done](#done)

There are currently three types of bug workflow currently recognized: Live Bug, Hotfix, Development bug.
Bug business value and tags should follow these recommendations [Bug Classification](BUGCLASSIFICATION.md)

## Buglog
General backlog for Bugs should be prioritized by manager/QA.
#####Done/Doing Custom Field
- ######Doing
Any new Bugs should be in this state. Anyone can create new Bugs here.
- ######Done
These Bugs should be prioritized. Only manager or QA should put bugs here.

[Back to top](#bug-workflow)
## Planning
These are Bugs that should be properly planned/groomed.
#####Done/Doing Custom Field
- ######Doing 
These are bugs that should be next on planning/grooming list. manager/scrumMaster move bugs here from Buglog-Done
- ######Done
These bugs are already planned and can be taken to Ready state.

[Back to top](#bug-workflow)
## Ready
Bug in this state should be prioritized and properly prepared so that any developer can start working on these.

++Hotfix++ : These should be added directly here. So that they can be fixed asap
#####Done/Doing Custom Field
- ######Doing 
Anyone can add Bug here but this should be only used for more urgent Bugs. These should not be taken further until properly prioritized by manager/scrummaster
- ######Done
These Should indicated all of the prioritized Bugs and any developer can take these and start implementing them. Only manager/ScrumMaster should move Bugs here.

[Back to top](#bug-workflow)
## In Progress
Bugs that are currently being fixed. Anyone from team can start working on Bugs that were in Ready.
#####Done/Doing Custom Field
- ######Doing
Default state should indicate that developer is currently working on the Bug.
- ######Done
Should indicate that developer's work is done and that the Bug is ready to be taken to next state.

[Back to top](#bug-workflow)
## Review
In this state Bugs should be reviewed that they are fixed.
#####Done/Doing Custom Field
- ######Doing
Default state should indicate that Review is still in progress.
- ######Done
Should indicate that Review is done and Bug is waiting to be merged into appropriate branch.
++Hotfix++ These bug should be merged directly to Live branch so they can be deployed ASAP and after that merged to main development branch, and they should be moved to [TEST](#test)-Done state
++Development Bug++ these should be already merged to whichever branch they were discovered on (ie. Feature Branch, Dev branch...). After Review they can be moved directly to [Done](#done)-Done
++Live Bug++ These should be merged to main development branch and moved to [DEV](#dev)

[Back to top](#bug-workflow)
## DEV
This state mainly indicates that the Bug has been merged to main development branch. Regression tests should be run in this state. Everyone from team should be able to move the bugs here. From here all bugs are considered a single entity as separating since they have to be deployed together (as whole branch).
#####Done/Doing Custom Field
- ######Doing
Default state, test are not complete and/or not passing
- ######Done
Test are passing and Release branch can be created.

[Back to top](#bug-workflow)
## TEST
All bugs in this state should be already merge into release branch(which should be deployed in Test environment). There should be last set of automated tests run here after any new commits.
#####Done/Doing Custom Field
- ######Doing
In this state test are still running/failing, bugs are waiting for deployment to live environment
- ######Done
Done should indicate that Bug has been deployed to Live, What's new can be published and Bug relations should be checked. Only manager should move bugs from this state

[Back to top](#bug-workflow)
## Done
All Bugs are deployed to Live.
#####Done/Doing Custom Field
- ######Doing
Default state, indicates that the Bugs can be demoed in next product demo.
- ######Done
Final state, Bug has been demoed, deployed, done.

[Back to top](#bug-workflow)

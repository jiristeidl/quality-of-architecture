# Process

To meet Moravia standard for quality of software development it is required that 
development process of every project is managed in project management software (PMS).

## Recommended PMS

- [TargetProcess](http://moravia.tpondemand.com)

##Recommended TargetProcess Workflow
- [UserStory](#userstory-workflow)
- [Bug](#bug-workflow)
- [Bug Classification](#bug-classification)

# UserStory Workflow

To meet Moravia standard for quality of software development it is required what each UserStory in TargetProcess follows these states and rules

- [Backlog](#backlog)
- [Planning](#planning)
- [Ready](#ready)
- [In Progress](#in-progress)
- [Review](#review)
- [DEV](#dev)
- [TEST](#test)
- [Done](#done)

UserStories with database migration should be marked with tag *Migration* to indicate that they have to be deployed with Downtime of product.

[Back to top](#process)

## Backlog
General backlog for UserStories should be prioritized by manager
#####Done/Doing Custom Field
- **Doing**
Any new UserStories should be in this state. Anyone can create new UserStories here.
- **Done**
These UserStories should be prioritized. Only manager should put stories here.

[Back to top](#userstory-workflow)
## Planning
These are UserStories that should be properly planned/groomed.
#####Done/Doing Custom Field
- **Doing**
These are stories that should be next on planning/grooming list. manager/scrumMaster move stories here from Backlog-Done
- **Done**
These stories are already planned and can be taken to Ready state.

[Back to top](#userstory-workflow)
## Ready
UserStory in this state should be prioritized and properly prepared so that any developer can start working on these. QA should be verifying that instruction for each user story meets requirements, is understandable and test-able.
#####Done/Doing Custom Field
- **Doing** 
Anyone can add UserStory here but this should be only used for more urgent US. These should not be taken further until properly prioritized by manager/scrummaster
- **Done**
These Should indicated all of the prioritized UserStories and any developer can take these and start implementing them. Only manager/ScrumMaster should move UserStories here.

[Back to top](#userstory-workflow)
## In Progress
UserStories that are currently being implemented. Anyone from team can start working UserStories that were in Ready.
#####Done/Doing Custom Field
- **Doing**
Default state should indicate that developer is currently working on the UserStory.
- **Done**
Should indicate that developer's work is done and that the UserStory is ready to be taken to next state.

[Back to top](#userstory-workflow)
## Review
In this state UserStories should be reviewed (ie. Tested/Code Review/UX review). UserStories should not be merge into main development branch until the review is finished. Everyone from team should be able to do the review.
#####Done/Doing Custom Field
- **Doing**
Default state should indicate that Review is still in progress.
- **Done**
Should indicate that Review is done and UserStory is waiting to be merged into main development branch, once merged the story should be moved to [DEV](#dev). Team can start working on writing User Documentation(Help/What's new).

[Back to top](#userstory-workflow)
## DEV
This state mainly indicates that the UserStory has been merged to main development branch. Regression tests should be run in this state. Everyone from team should be able to move the stories here. From here all stories are considered a single entity as separating since they have to be deployed together (as whole branch).
#####Done/Doing Custom Field
- **Doing**
Default state, test are not complete and/or not passing
- **Done**
Test are passing and Release branch can be created.

[Back to top](#userstory-workflow)
## TEST
All stories in this state should be already merge into release branch(which should be deployed in Test enviroment). There should be last set of automated tests run here after any new commits.
#####Done/Doing Custom Field
- **Doing**
In this state test are still running/failing, stories are waiting for deployment to live environment
- **Done**
Done should indicate that UserStory has been deployed to Live, What's new can be published and UserStory relations should be checked. Only manager should move stories from this state

[Back to top](#userstory-workflow)
## Done
All UserStories are deployed to Live. Only manager should move UserStories here.
#####Done/Doing Custom Field
- **Doing**
Default state, indicates that the UserStories can be demoed in next product demo.
- **Done**
Final state, UserStory has been demoed, deployed, done.

[Back to top](#userstory-workflow)

# Bug Classification

##Business Value:
  * **Urgent** Use only for most severe live bugs, these bugs should be fixed immediately even if that means interrupting current work
  * **Blocking** !!ONLY USE FOR BUGS IN PRODUCTION!! It's a bug that prevents from working. _Should be fixed and deployed as hotfix ASAP_
  * **Critical** The bug affects major functionality or major data. Workaround is not obvious and/or is difficult.
  * **Normal** Workaround for this issue exists and is known and easy to perform or it is User experience issue
  * **Small** Bug does not affect functionality nor Data, no workaround is needed. Does not impact productivity or efficiency
  * **Enhancement** Suggestions or improvements for existing functionality

##Tags:
 * **Live** Should be used on all bugs repro in Live environment, all critical and blocking bugs with this tag are displayed on our monitoring
 * **API** Should be used on all bugs on Symfonie API, all critical and blocking bugs with this tag are displayed on out monitoring
 * **Migration** Indicates that there is Database migration and there will have to be downtime when deploying to live

[Back to top](#process)

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

[Back to top](#process)

## Buglog
General backlog for Bugs should be prioritized by manager/QA.
#####Done/Doing Custom Field
- **Doing**
Any new Bugs should be in this state. Anyone can create new Bugs here.
- **Done**
These Bugs should be prioritized. Only manager or QA should put bugs here.

[Back to top](#bug-workflow)
## Planning
These are Bugs that should be properly planned/groomed.
#####Done/Doing Custom Field
- **Doing** 
These are bugs that should be next on planning/grooming list. manager/scrumMaster move bugs here from Buglog-Done
- **Done**
These bugs are already planned and can be taken to Ready state.

[Back to top](#bug-workflow)
## Ready
Bug in this state should be prioritized and properly prepared so that any developer can start working on these.

++Hotfix++ : These should be added directly here. So that they can be fixed asap
#####Done/Doing Custom Field
- **Doing** 
Anyone can add Bug here but this should be only used for more urgent Bugs. These should not be taken further until properly prioritized by manager/scrummaster
- **Done**
These Should indicated all of the prioritized Bugs and any developer can take these and start implementing them. Only manager/ScrumMaster should move Bugs here.

[Back to top](#bug-workflow)
## In Progress
Bugs that are currently being fixed. Anyone from team can start working on Bugs that were in Ready.
#####Done/Doing Custom Field
- **Doing**
Default state should indicate that developer is currently working on the Bug.
- **Done**
Should indicate that developer's work is done and that the Bug is ready to be taken to next state.

[Back to top](#bug-workflow)
## Review
In this state Bugs should be reviewed that they are fixed.
#####Done/Doing Custom Field
- **Doing**
Default state should indicate that Review is still in progress.
- **Done**
Should indicate that Review is done and Bug is waiting to be merged into appropriate branch.
++Hotfix++ These bug should be merged directly to Live branch so they can be deployed ASAP and after that merged to main development branch, and they should be moved to [TEST](#test)-Done state
++Development Bug++ these should be already merged to whichever branch they were discovered on (ie. Feature Branch, Dev branch...). After Review they can be moved directly to [Done](#done)-Done
++Live Bug++ These should be merged to main development branch and moved to [DEV](#dev)

[Back to top](#bug-workflow)
## DEV
This state mainly indicates that the Bug has been merged to main development branch. Regression tests should be run in this state. Everyone from team should be able to move the bugs here. From here all bugs are considered a single entity as separating since they have to be deployed together (as whole branch).
#####Done/Doing Custom Field
- **Doing**
Default state, test are not complete and/or not passing
- **Done**
Test are passing and Release branch can be created.

[Back to top](#bug-workflow)
## TEST
All bugs in this state should be already merge into release branch(which should be deployed in Test environment). There should be last set of automated tests run here after any new commits.
#####Done/Doing Custom Field
- **Doing**
In this state test are still running/failing, bugs are waiting for deployment to live environment
- **Done**
Done should indicate that Bug has been deployed to Live, What's new can be published and Bug relations should be checked. Only manager should move bugs from this state

[Back to top](#bug-workflow)
## Done
All Bugs are deployed to Live.
#####Done/Doing Custom Field
- **Doing**
Default state, indicates that the Bugs can be demoed in next product demo.
- **Done**
Final state, Bug has been demoed, deployed, done.

[Back to top](#bug-workflow)
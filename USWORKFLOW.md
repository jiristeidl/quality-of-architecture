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

## Backlog
General backlog for UserStories should be prioritized by manager
#####Done/Doing Custom Field
- ######Doing
Any new UserStories should be in this state. Anyone can create new UserStories here.
- ######Done
These UserStories should be prioritized. Only manager should put stories here.

[Back to top](#userstory-workflow)
## Planning
These are UserStories that should be properly planned/groomed.
#####Done/Doing Custom Field
- ######Doing
These are stories that should be next on planning/grooming list. manager/scrumMaster move stories here from Backlog-Done
- ######Done
These stories are already planned and can be taken to Ready state.

[Back to top](#userstory-workflow)
## Ready
UserStory in this state should be prioritized and properly prepared so that any developer can start working on these. QA should be verifying that instruction for each user story meets requirements, is understandable and test-able.
#####Done/Doing Custom Field
- ######Doing 
Anyone can add UserStory here but this should be only used for more urgent US. These should not be taken further until properly prioritized by manager/scrummaster
- ######Done
These Should indicated all of the prioritized UserStories and any developer can take these and start implementing them. Only manager/ScrumMaster should move UserStories here.

[Back to top](#userstory-workflow)
## In Progress
UserStories that are currently being implemented. Anyone from team can start working UserStories that were in Ready.
#####Done/Doing Custom Field
- ######Doing
Default state should indicate that developer is currently working on the UserStory.
- ######Done
Should indicate that developer's work is done and that the UserStory is ready to be taken to next state.

[Back to top](#userstory-workflow)
## Review
In this state UserStories should be reviewed (ie. Tested/Code Review/UX review). UserStories should not be merge into main development branch until the review is finished. Everyone from team should be able to do the review.
#####Done/Doing Custom Field
- ######Doing
Default state should indicate that Review is still in progress.
- ######Done
Should indicate that Review is done and UserStory is waiting to be merged into main development branch, once merged the story should be moved to [DEV](#dev). Team can start working on writing User Documentation(Help/What's new).

[Back to top](#userstory-workflow)
## DEV
This state mainly indicates that the UserStory has been merged to main development branch. Regression tests should be run in this state. Everyone from team should be able to move the stories here. From here all stories are considered a single entity as separating since they have to be deployed together (as whole branch).
#####Done/Doing Custom Field
- ######Doing
Default state, test are not complete and/or not passing
- ######Done
Test are passing and Release branch can be created.

[Back to top](#userstory-workflow)
## TEST
All stories in this state should be already merge into release branch(which should be deployed in Test enviroment). There should be last set of automated tests run here after any new commits.
#####Done/Doing Custom Field
- ######Doing
In this state test are still running/failing, stories are waiting for deployment to live environment
- ######Done
Done should indicate that UserStory has been deployed to Live, What's new can be published and UserStory relations should be checked. Only manager should move stories from this state

[Back to top](#userstory-workflow)
## Done
All UserStories are deployed to Live. Only manager should move UserStories here.
#####Done/Doing Custom Field
- ######Doing
Default state, indicates that the UserStories can be demoed in next product demo.
- ######Done
Final state, UserStory has been demoed, deployed, done.

[Back to top](#userstory-workflow)

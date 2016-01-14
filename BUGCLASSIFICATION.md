#Bug Classification


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


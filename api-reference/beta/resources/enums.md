---
title: "Enum values"
description: "Microsoft Graph enumeration values"
---

### contactRelationship values

|Member|Value|Description|
|:---|:---|:---|
|parent|0|The user's parent.|
|relative|1| The user's relative.|
|aide|2| The user's aide.|
|doctor|3| The user's doctor.|
|guardian|4| The user's guardian.|
|child|5| The user's child.|
|other|6| An unspecified relationship to the user.|
|unknownFutureValue|7| Marker value for future compatibility.|


### scheduleEntityTheme values

| Value
|:-------------------------
| white
| blue
| green
| purple
| pink
| yellow
| gray
| darkBlue
| darkGreen
| darkPurple
| darkPink
| darkYellow
| unknownFutureValue


### timeOffReasonIconType values

|Member|
|:---|
|none|
|car|
|calendar|
|running|
|plane|
|firstAid|
|doctor|
|notWorking|
|clock|
|juryDuty|
|globe|
|cup|
|phone|
|weather|
|umbrella|
|piggyBank|
|dog|
|cake|
|trafficCone|
|pin|
|sunny|
|unknownFutureValue|


### timeZoneStandard values

| Value
|:-----------------
| windows
| iana


### freeBusyStatus values

| Member            |Value
|:------------------|:-------
| free              | 0
| tentative         | 1
| busy              | 2
| oof               | 3
| workingElsewhere  | 4
| unknown           | -1


### physicalAddressType values

| Value
|:-------------------------
| unknown 
| home
| business 
| other


### attendeeType values

| Value
|:-------------------------
| required
| optional
| resource


### externalAudienceScope values

| Value
|:-------------------------
| none
| contactsOnly
| all


### automaticRepliesStatus values

| Value
|:-------------------------
| disabled
| alwaysEnabled
| scheduled


### calendarColor values

| Member     | Value
|:-----------|:----------
| auto       | -1
| lightBlue  | 0
| lightGreen | 1
| lightOrange| 2
| lightGray  | 3
| lightYellow| 4
| lightTeal  | 5
| lightPink  | 6
| lightBrown | 7
| lightRed   | 8
| maxColor   | 9


### educationSynchronizationProfileState values

| Member     | Value
|:-----------|:----------
| deleting          | 2
| deletionFailed    | 3
| provisioningFailed | 5
| provisioned        | 6
| provisioning       | 7
| unknownFutureValue | 8


### educationSynchronizationStatus values

| Member     | Value
|:-----------|:----------
| paused          | 0
| inProgress    | 1
| success | 2
| error        | 3
| validationError | 4
| quarantined       | 5
| unknownFutureValue | 6

### educationExternalSource values

| Value
|:-------------------------
| sis
| manual
| unknownFutureValue


### educationGender values

| Value
|:-------------------------
| female
| male
| other
| unknownFutureValue


### eventType values

| Value
|:-------------------------
| singleInstance
| occurrence
| exception
| seriesMaster


### sensitivity values

| Value
|:-------------------------
| normal
| personal
| private
| confidential


### importance values

| Value
|:-------------------------
| low
| normal
| high


### educationUserRole values
| Value
|:---------------------
| student
| teacher
| faculty


### meetingMessageType values

| Value
|:-----------------
| none
| meetingRequest
| meetingCancelled
| meetingAccepted
| meetingTentativelyAccepted
| meetingDeclined


### followupFlagStatus values

| Value
|:-------------------------
| notFlagged
| complete
| flagged


### inferenceClassificationType values

| Value
|:-----------------
| focused
| other


### iosNotificationAlertType values

| Value
|:-------------------------
| deviceDefault
| banner
| modal
| none

### deviceEnrollmentFailureReason values

| Value
|:-------------
| unknown
| authentication
| authorization
| accountValidation
| userValidation
| deviceNotSupported
| inMaintenance
| badRequest
| featureNotSupported
| enrollmentRestrictionsEnforced
| clientDisconnected


### bodyType values
| Value
|:---------
| text
| html


### locationType values

| Value
|:-------------------------
| default
| conferenceRoom
| homeAddress
| businessAddress
| geoCoordinates
| streetAddress
| hotel
| restaurant
| localBusiness
| postalAddress

### locationUniqueIdType values

| Value
|:-------------------------
| unknown
| locationStore
| directory
| private
| bing


### messageActionFlag values

| Value
|:-------------------------
| any
| call
| doNotForward
| followUp
| fyi
| forward
| noResponseNecessary
| read
| reply
| replyToAll
| review


### onenoteUserRole values

| Member      | Value
|:------------|:------------
| Owner       | 0
| Contributor | 1
| Reader      | 2
| None        | -1


### operationStatus values

| Value
|:-----------------
| NotStarted
| Running
| Completed
| Failed


### onenotePatchActionType values

| Value
|:-------------------------
| Replace
| Append
| Delete
| Insert
| Prepend

### onenotePatchInsertPosition values

| Value
|:-------------------------
| After
| Before


### phoneType values

| Value
|:-------------------------
| home
| business
| mobile
| other
| assistant
| homeFax
| businessFax
| otherFax
| pager
| radio


### plannerPreviewType values

| Value
|:-------------------------
| automatic
| noPreview
| checklist
| description
| reference


### status values

| Value
|:-----------------
| active
| updated
| deleted
| ignored
| unknownFutureValue


### weekIndex values

| Value
|:-------------------------
| first
| second
| third
| fourth
| last


### dayOfWeek values

| Value
|:-------------------------
| sunday
| monday
| tuesday
| wednesday
| thursday
| friday
| saturday

### recurrencePatternType values

| Value
|:-------------------------
| daily
| weekly
| absoluteMonthly
| relativeMonthly
| absoluteYearly
| relativeYearly


### recurrenceRangeType values

| Value
|:-------------------------
| endDate
| noEnd
| numbered


### onenoteSourceService values
| Value
|:---------------------
| Unknown
| OneDrive
| OneDriveForBusiness
| OnPremOneDriveForBusiness


### responseType values

| Value
|:-------------------------
| none
| organizer
| tentativelyAccepted
| accepted
| declined
| notResponded


### activityDomain values

| Value
|:-------------------------
| unknown
| work
| personal
| unrestricted


### websiteType values

| Value
|:-------------------------
| other
| home
| work
| blog
| profile


### categoryColor values

| Member   |Value    
|:---------|:--------
| none     | -1      
| preset0  | 0       
| preset1  | 1       
| preset2  | 2       
| preset3  | 3       
| preset4  | 4       
| preset5  | 5       
| preset6  | 6       
| preset7  | 7       
| preset8  | 8       
| preset9  | 9       
| preset10 | 10      
| preset11 | 11      
| preset12 | 12      
| preset13 | 13      
| preset14 | 14      
| preset15 | 15      
| preset16 | 16      
| preset17 | 17      
| preset18 | 18      
| preset19 | 19      
| preset20 | 20      
| preset21 | 21      
| preset22 | 22      
| preset23 | 23      
| preset24 | 24      

### alertFeedback values

Possible feedback values on the alert provided by an analyst.

|Member|Value|Description|
|:---|:---|:---|
|unknown|0|Unknown.|
|truePositive|1|Alert is true-positive.|
|falsePositive|2| Alert is false-positive.|
|benignPositive|3| Alert is benign-positive.|

### fileHashType values

|Member|Value|Description|
|:---|:---|:---|
|unknown|0|Unknown type.|
|sha1|1|SHA1 hash type.|
|sha256|2| SHA256 hash type.|
|md5|3| MD5 hash type.|
|authenticodeHash256|4| AuthenticodeHash256 hash type.|
|lsHash|5| LsHash hash type.|
|ctph|6| CTPH hash type.|
|peSha1|7| PESHA1 hash type.|
|peSha256|8| PESHA256 hash type.|

### connectionDirection values

|Member|Value|Description|
|:---|:---|:---|
|unknown|0|Unknown connection.|
|inbound|1|Inbound connection.|
|outbound|2| Outbound connection.|

### connectionStatus values

|Member|Value|Description|
|:---|:---|:---|
|unknown|0|Unknown connection status.|
|attempted|1|Connection attempted.|
|succeeded|2| Connection succeeded.|
|blocked|3| Connection blocked.|
|failed|4| Connection failed.|

### processIntegrityLevel values

|Member|Value|Description|
|:---|:---|:---|
|unknown|0|Unknown.|
|untrusted|10|Integrity level is Untrusted.|
|low|20| Integrity level is Low.|
|medium|30| Integrity level is Medium.|
|high|40| Integrity level is High.|
|system|50| Integrity level is System.|

### registryHive values

Enum for registry hives as defined by [https://docs.microsoft.com/en-us/windows/desktop/sysinfo/registry-hives](https://docs.microsoft.com/en-us/windows/desktop/sysinfo/registry-hives).

|Member|Value|Description|
|:---|:---|:---|
|unknown|0|Unknown hive.|
|currentConfig|1|HKEY_CURRENT_CONFIG hive.|
|currentUser|2| HKEY_CURRENT_USER hive.|
|localMachineSam|3| HKEY_LOCAL_MACHINE\SAM hive.|
|localMachineSamSoftware|4| HKEY_LOCAL_MACHINE\Software hive.|
|localMachineSystem|5| HKEY_LOCAL_MACHINE\System hive.|
|usersDefault|6| HKEY_USERS\\.DEFAULT hive.|

### registryOperation values

Operation that changed the registry key name and/or value.

|Member|Value|Description|
|:---|:---|:---|
|unknown|0|Unknown registry value type.|
|create|1|Create registry.|
|modify|2|Modify registry.|
|delete|3|Delete registry.|

### registryValueType values

Enum for registry value types as defined by [https://docs.microsoft.com/en-us/windows/desktop/sysinfo/registry-value-types](https://docs.microsoft.com/en-us/windows/desktop/sysinfo/registry-value-types).

|Member|Value|Description|
|:---|:---|:---|
|unknown|0|Unknown registry value type.|
|binary|1|REG_BINARY registry value type.|
|dword|2| REG_DWORD registry value type.|
|dwordLittleEndian|3| REG_DWORD_LITTLE_ENDIAN registry value type.|
|dwordBigEndian|4| REG_DWORD_BIG_ENDIAN registry value type.|
|expandSz|5| REG_EXPAND_SZ registry value type.|
|link|6| REG_LINK registry value type.|
|multiSz|7| REG_MULTI_SZ registry value type.|
|none|8| REG_NONE registry value type.|
|qword|9| REG_QWORD registry value type.|
|qwordlittleEndian|10| REG_QWORD_LITTLE_ENDIAN registry value type.|
|sz|11| REG_SZ registry value type.|

### alertSeverity values

Enum for severity of alerts.

|Member|Value|Description|
|:---|:---|:---|
|unknown|0|Severity is unknown.|
|informational|1|Severity is only for information.|
|low|2| Severity is low.|
|medium|3| Severity is medium.|
|high|4| Severity is high.|

### alertStatus values

Possible values of an Alert lifecycle status (stage).

|Member|Value|Description|
|:---|:---|:---|
|unknown|0|Unknown status.|
|newAlert|10| Alert is new.|
|inProgress|20|Alert is in progress.|
|resolved|30|Alert is resolved.|

### emailRole values

Possible values for email roles.

|Member|Value|Description|
|:---|:---|:---|
|unknown|0|Unknown Role.|
|sender|1|Sender of the email.|
|recipient|2|Recipient of the email.|

### logonType values

Possible values for the method of user signin.

|Member|Value|Description|
|:---|:---|:---|
|unknown|-1|Unknown.|
|interactive|0|Logon is interactive.|
|remoteInteractive|1| Logon is remote interactive.|
|network|2| Logon is network.|
|batch|3| Logon is batch.|
|service|4| Logon is service.|

### userAccountSecurityType values

Possible values for user account types (group membership), per Windows definition.

|Member|Value|Description|
|:---|:---|:---|
|unknown|-1|Unknown.|
|standard|0|Member of Standard Users group.|
|power|1| Member of Power Users group.|
|administrator|2| Member of Administrators group.|

### scopeOperatorMultiValuedComparisonType values

|Member|
|:---|
|all|
|any|

### riskLevel values

|Member|
|:---|
|low|
|medium|
|high|
|hidden|
|none|
|unknownFutureValue|

### riskState values

|Member|
|:---|
|none|
|confirmedSafe|
|remediated|
|dismissed|
|atRisk|
|confirmedCompromised|
|unknownFutureValue|

### riskDetail values

|Member|
|:---|
|none|
|adminGeneratedTemporaryPassword|
|userPerformedSecuredPasswordChange|
|userPerformedSecuredPasswordReset|
|adminConfirmedSigninSafe|
|aiConfirmedSigninSafe|
|userPassedMFADrivenByRiskBasedPolicy|
|adminDismissedAllRiskForUser|
|adminConfirmedSigninCompromised|
|adminConfirmedUserCompromised|
|hidden|
|unknownFutureValue|

### referenceAttachmentPermission values

|Member|
|:---|
|other|
|view|
|edit|
|anonymousView|
|anonymousEdit|
|organizationView|
|organizationEdit|

### referenceAttachmentProvider values

|Member|
|:---|
|other|
|oneDriveBusiness|
|oneDriveConsumer|
|dropbox|

### riskEventType values

|Member|
|:---|
|unlikelyTravel|
|anonymizedIPAddress|
|maliciousIPAddress|
|unfamiliarFeatures|
|malwareInfectedIPAddress|
|suspiciousIPAddress|
|leakedCredentials|
|investigationsThreatIntelligence|
|generic|
|adminConfirmedUserCompromised|
|mcasImpossibleTravel|
|mcasSuspiciousInboxManipulationRules|
|investigationsThreatIntelligenceSigninLinked|
|maliciousIPAddressValidCredentialsBlockedIP|
|unknownFutureValue|

### networkType values

|Member|
|:---|
|intranet|
|extranet|
|namedNetwork|
|trusted|
|unknownFutureValue|

### exchangeIdFormat values

|Member|
|:---|
|entryId|
|ewsId|
|immutableEntryId|
|restId|
|restImmutableEntryId|

### attributeFlowBehavior values

|Member|
|:---|
|flowWhenChanged|
|flowAlways|

### attributeFlowType values

|Member|
|:---|
|always|
|objectAddOnly|
|multiValueAddOnly|
|restId|

### objectFlowTypes values

|Member| Value|
|:---|:-------|
|None| 0      |
|Add| 1       |
|Update|2     |
|Delete|4     |

### chatMessageType values

|Member|
|:---|
|message|

### chatMessageImportance values

|Member|
|:---|
|normal|
|high|
|urgent|

### tokenIssuerType values

|Member|
|:---|
|AzureAD|
|ADFederationServices|
|unknownFutureValue|

### riskDetectionTimingType values

|Member|
|:---|
|notDefined|
|realtime|
|nearRealtime|
|offline|
|unknownFutureValue|


### activityType values

|Member|
|:---|
|signin|
|user|
|unknownFutureValue|

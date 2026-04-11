# SailPoint Workflow Classes Details

## Class: `AbstractWorkflowHandler`

**Package:** `sailpoint.workflow`

### Inherited Classes/Interfaces
```java
public class AbstractWorkflowHandler extends java.lang.Object implements WorkflowHandler
```

### Description
Skeleton implementation of the WorkflowHandler class.
 Extend this when implementing a custom WorkflowHandler
 since you do not usually want to implement all of the callbacks.

### Attributes
*No attributes found.*

### Methods
- `void archiveWorkItem(WorkflowContext wfc)`
- `void assimilateWorkItem(WorkflowContext wfc)`
- `void backgroundStep(WorkflowContext wfc)`
- `void cancelApproval(WorkflowContext wfc)`
- `void endApproval(WorkflowContext wfc)`
- `void endStep(WorkflowContext wfc)`
- `void endWorkflow(WorkflowContext wfc)`
- `void forwardWorkItem(SailPointContext con, WorkItem item, Identity newOwner)`
- `static java.lang.String getMessage(java.lang.String key, java.lang.Object arg)`
- `protected static java.util.List<java.lang.String> getStringList(java.lang.Object value)`
- `void handleWorkItem(SailPointContext con, WorkItem item, boolean foreground)`
- `void openWorkItem(WorkflowContext wfc)`
- `static void println(java.lang.Object o)`
- `void startApproval(WorkflowContext wfc)`
- `void startStep(WorkflowContext wfc)`
- `void startWorkflow(WorkflowContext wfc)`
- `void validateWorkItem(SailPointContext con, WorkItem item)`
- `void validateWorkItem(WorkflowContext wfc)`

---

## Class: `ApprovalLibrary`

**Package:** `sailpoint.workflow`

### Inherited Classes/Interfaces
```java
public class ApprovalLibrary extends java.lang.Object
```

### Description
*No description available.*

### Attributes
*No attributes found.*

### Methods
- `SailPointObject getCurrentObject(WorkflowContext wfc)`
- `static java.lang.String getMessage(java.lang.String key, java.lang.Object arg)`
- `Identity getNewObjectOwner(WorkflowContext wfc)`
- `java.lang.String getNewObjectOwnerName(WorkflowContext wfc)`
- `SailPointObject getObject(WorkflowContext wfc)`
- `java.lang.String getObjectClass(WorkflowContext wfc)`
- `java.lang.String getObjectName(WorkflowContext wfc)`
- `Identity getObjectOwner(WorkflowContext wfc)`
- `java.lang.String getObjectOwnerName(WorkflowContext wfc)`
- `protected static java.util.List<java.lang.String> getStringList(java.lang.Object value)`
- `boolean isOwnerChange(WorkflowContext wfc)`
- `boolean isSelfApproval(WorkflowContext wfc)`

---

## Class: `BatchRequestLibrary`

**Package:** `sailpoint.workflow`

### Inherited Classes/Interfaces
```java
public class BatchRequestLibrary extends java.lang.Object
```

### Description
Workflow library for processing batch requests

### Attributes
- `static java.util.HashSet<java.lang.String> ACCOUNT_OPS`
- `static java.lang.String ALLOW_SPLIT_BATCH_ENT_REQS`
- `static java.lang.String APP_HEADER`
- `static java.util.HashSet<java.lang.String> ENT_OPS`
- `static java.lang.String ENTNAME_HEADER`
- `static java.lang.String ENTVALUE_HEADER`
- `static java.lang.String IDENTITY_HEADER`
- `static java.lang.String NAME_HEADER`
- `static java.lang.String NATIVE_HEADER`
- `static java.util.HashSet<java.lang.String> NOMIX_OPS`
- `static java.lang.String OP_ADD_ENTITLEMENT`
- `static java.lang.String OP_ADD_ROLE`
- `static java.lang.String OP_CHANGE_PASSWORD`
- `static java.lang.String OP_CREATE_ACCOUNT`
- `static java.lang.String OP_CREATE_IDENTITY`
- `static java.lang.String OP_DELETE_ACCOUNT`
- `static java.lang.String OP_DISABLE_ACCOUNT`
- `static java.lang.String OP_ENABLE_ACCOUNT`
- `static java.lang.String OP_MODIFY_IDENTITY`
- `static java.lang.String OP_REMOVE_ENTITLEMENT`
- `static java.lang.String OP_REMOVE_ROLE`
- `static java.lang.String OP_UNLOCK_ACCOUNT`
- `static java.lang.String OPERATION_HEADER`
- `static java.lang.String PASSWORD_HEADER`
- `static java.lang.String RES_SUCCESS`
- `static java.util.HashSet<java.lang.String> ROLE_OPS`
- `static java.lang.String ROLES_HEADER`
- `static java.lang.String SPLIT_BATCH_ENT_STR`
- `static java.lang.String SUNRISE_HEADER`
- `static java.lang.String SUNSET_HEADER`
- `static java.lang.String VAR_BATCH_ID`
- `static java.lang.String VAR_BATCH_ITEM_ID`
- `static java.lang.String VAR_RESULT`

### Methods
- `ProvisioningPlan.AccountRequest generateRequest(java.lang.String targetId, java.lang.String op, SailPointContext context, ProvisioningPlan plan, java.util.HashMap<java.lang.String, java.lang.String> requestMap)`
- `static java.lang.String getMessage(java.lang.String key, java.lang.Object arg)`
- `protected static java.util.List<java.lang.String> getStringList(java.lang.Object value)`
- `java.lang.String getWorkflowName(SailPointContext ctx, java.lang.String op)`
- `static void initStatic()`
- `void launchBatchWorkflows(WorkflowContext wfc)`
- `void requestRejected(WorkflowContext wfc)`

---

## Class: `GroupLibrary`

**Package:** `sailpoint.workflow`

### Inherited Classes/Interfaces
```java
public class GroupLibrary extends java.lang.Object
```

### Description
Workflow library containing utilities for group management.

### Attributes
- `static java.lang.String ARG_APPLICATION_NAME`
- `static java.lang.String ARG_PROJECT`
- `static java.lang.String CHANGES`
- `static java.lang.String VAR_PLAN`

### Methods
- `static void aggregateSpecificGroup(WorkflowContext wfc)`
- `static void aggregateSpecificTargets(WorkflowContext wfc)`
- `static void approvedAsyncRequest(WorkflowContext wfc)`
- `static java.lang.Object buildGroupChangeSummary(WorkflowContext wfc)`
- `static void checkChanges(WorkflowContext wfc)`
- `static java.lang.Object compileGroupProject(WorkflowContext wfc)`
- `static java.lang.Object getGroupName(WorkflowContext wfc)`
- `staticProvisioningPlan.ObjectRequest getGroupRequest(WorkflowContext wfc)`
- `staticManagedAttribute getManagedAttribute(WorkflowContext wfc)`
- `static java.lang.String getMessage(java.lang.String key, java.lang.Object arg)`
- `protected static java.util.List<java.lang.String> getStringList(java.lang.Object value)`
- `static java.lang.String getSummaryName(WorkflowContext wfc)`
- `static java.lang.Object provisionGroupProject(WorkflowContext wfc)`
- `static void rejectedAsyncRequest(WorkflowContext wfc)`

---

## Class: `IdentityLibrary`

**Package:** `sailpoint.workflow`

### Inherited Classes/Interfaces
```java
public class IdentityLibrary extends java.lang.Object
```

### Description
Workflow library containing utilities for identity management.

### Attributes
- `static java.lang.String ACCOUNT_SELECTOR_CREATE`
- `static java.lang.String ARG_ACCOUNT_SELECTION_OWNER`
- `static java.lang.String ARG_APPROVAL_SET`
- `static java.lang.String ARG_APPROVAL_SET_VARIABLE`
- `static java.lang.String ARG_ASSIGNER`
- `static java.lang.String ARG_CLEAR_APP_DECISIONS`
- `static java.lang.String ARG_DETECTED`
- `static java.lang.String ARG_DISABLE_AUDIT`
- `static java.lang.String ARG_DO_LOCKING`
- `static java.lang.String ARG_DONT_UPDATE_PLAN`
- `static java.lang.String ARG_ENABLE_MANUAL_ACCOUNT_SELECTION`
- `static java.lang.String ARG_FALLBACK_OWNER`
- `static java.lang.String ARG_FILTER_STRING`
- `static java.lang.String ARG_FORM`
- `static java.lang.String ARG_HELP_TEXT`
- `static java.lang.String ARG_IDENTITIES_WITH_ROLES`
- `static java.lang.String ARG_IDENTITY`
- `static java.lang.String ARG_IDENTITY_NAME`
- `static java.lang.String ARG_IDENTITY_NAMES`
- `static java.lang.String ARG_LINKS_TO_ADD`
- `static java.lang.String ARG_LINKS_TO_MOVE`
- `static java.lang.String ARG_LINKS_TO_REMOVE`
- `static java.lang.String ARG_NEW_ROLES_VARIABLE`
- `static java.lang.String ARG_NO_TRIGGERS`
- `static java.lang.String ARG_OLD_ROLES_VARIABLE`
- `static java.lang.String ARG_OWNER`
- `static java.lang.String ARG_PASSWORD`
- `static java.lang.String ARG_PLAN`
- `static java.lang.String ARG_PREFERRED_OWNER`
- `static java.lang.String ARG_PROJECT`
- `static java.lang.String ARG_PROVISION`
- `static java.lang.String ARG_RECOMPILE_BEFORE_PROVISIONING`
- `static java.lang.String ARG_ROLE`
- `static java.lang.String ARG_ROLE_ASSIGNER`
- `static java.lang.String ARG_SOURCE_APPLICATION`
- `static java.lang.String ARG_SPLIT_DISABLE_COMBINE`
- `static java.lang.String ARG_SYNC_ALL`
- `static java.lang.String ARG_TARGET_APPLICATIONS`
- `static java.lang.String ARG_TEMPLATE`
- `static java.lang.String ATT_MAX_RETRIES`
- `static java.lang.String ATT_PROVISIONING_MAX_STATUS_CHECKS`
- `static java.lang.String ATT_PROVISIONING_STATUS_CHECK_INTERVAL`
- `static java.lang.String ATT_RETRY_THRESHOLD`
- `static java.lang.String ATTR_IDENTITY_UPDATE`
- `static java.lang.String FORM_OWNER_APPOWNER`
- `static java.lang.String FORM_OWNER_IDENTITY`
- `static java.lang.String FORM_OWNER_MANAGER`
- `static java.lang.String FORM_OWNER_ROLEOWNER`
- `static java.lang.String IDENTITY_UPDATE_RENDERER`
- `static java.lang.String VAR_APPROVAL_SCHEME`
- `static java.lang.String VAR_APPROVAL_SPLIT_POINT`
- `static java.lang.String VAR_CHANGE_EVENTS`
- `static java.lang.String VAR_DETECTION_DIFFERENCE`
- `static java.lang.String VAR_DO_MANUAL_ACTIONS`
- `static java.lang.String VAR_EVENT`
- `static java.lang.String VAR_FLOW`
- `static java.lang.String VAR_IDENTITIZER`
- `static java.lang.String VAR_IDENTITY`
- `static java.lang.String VAR_IDENTITY_NAME`
- `static java.lang.String VAR_PLAN`
- `static java.lang.String VAR_POLICIES`
- `static java.lang.String VAR_PREVIOUS_VERSION`
- `static java.lang.String VAR_PROJECT`
- `static java.lang.String VAR_REFRESH_OPTIONS`
- `static java.lang.String VAR_SPLIT_APPROVALSETS`
- `static java.lang.String VAR_SPLIT_COMMENTS`
- `static java.lang.String VAR_SPLIT_PROJECTS`
- `static java.lang.String VAR_TRIGGER`
- `static java.lang.String VAR_WORK_ITEM_COMMENTS`

### Methods
- `void activateRoleAssignment(WorkflowContext wfc)`
- `static void addApprovalItem(Identity identity, ProvisioningPlan.AccountRequest account, ApprovalSet set)`
- `static void addApprovalItems(Identity identity, ProvisioningPlan.AccountRequest request, ApprovalSet set)`
- `static void addApprovalItems(Identity identity, ProvisioningPlan.AccountRequest request, ApprovalSet set, SailPointContext ctx)`
- `static void appendNewMessages(WorkflowCase wfCase, java.util.List<Message > messages)`
- `void applyCommittedResults(WorkflowContext wfc)`
- `ProvisioningProject assembleRetryProject(WorkflowContext wfc)`
- `boolean assimilateAccountIdChanges(ProvisioningProject project, ApprovalSet set, IdentityRequest ir)`
- `java.lang.Object assimilateAccountIdChanges(WorkflowContext wfc)`
- `java.lang.Object assimilatePlanApprovalForm(WorkflowContext wfc)`
- `static void assimilateProvisioningErrors(WorkflowContext wfc, ProvisioningProject project)`
- `java.lang.Object assimilateProvisioningForm(WorkflowContext wfc)`
- `void assimilateSplitApprovalSets(WorkflowContext wfc)`
- `void assimilateSplitProjects(WorkflowContext wfc)`
- `void assimilateSplitWorkItemComments(WorkflowContext wfc)`
- `static void auditDecision(WorkflowContext ctx, ApprovalItem item)`
- `java.lang.Object auditLCMCompletion(WorkflowContext wfc)`
- `java.lang.Object auditLCMEvents(java.lang.String eventType, WorkflowContext wfc)`
- `java.lang.Object auditLCMStart(WorkflowContext wfc)`
- `void auditScheduledProject(WorkflowContext wfc)`
- `java.lang.Object buildAccountSelectionForm(WorkflowContext wfc)`
- `ProvisioningPlan buildAlertPlan(WorkflowContext wfc)`
- `java.lang.Object buildApprovalSet(WorkflowContext wfc)`
- `ApprovalSet buildApprovalSetFromNativeChanges(WorkflowContext wfc)`
- `staticAuditEvent buildBaseEvent(WorkflowContext wfc, ApprovalItem item)`
- `java.lang.Object buildCommonApprovals(WorkflowContext wfc)`
- `ProvisioningPlan buildEventPlan(WorkflowContext wfc)`
- `java.lang.Object buildManagerApproval(WorkflowContext wfc)`
- `java.lang.Object buildOwnerApprovals(WorkflowContext wfc)`
- `java.lang.Object buildPlanApprovalForm(WorkflowContext wfc)`
- `ProvisioningPlan buildPlanFromIdentityModel(WorkflowContext wfc)`
- `java.lang.Object buildProvisioningForm(WorkflowContext wfc)`
- `Form buildReadOnlyForm(WorkflowContext wfc)`
- `java.lang.Object buildSecurityOfficerApproval(WorkflowContext wfc)`
- `java.lang.Object buildSplitApprovalSet(WorkflowContext wfc)`
- `java.lang.Object calculateIdentityDifference(WorkflowContext wfc)`
- `void checkAssignedRejection(ApprovalItem rejectedAssignmentApproval, ApprovalSet set, ProvisioningPlan plan, WorkflowContext wfc)`
- `java.util.List<java.util.Map<java.lang.String,​java.lang.Object>> checkPolicyViolations(WorkflowContext wfc)`
- `java.lang.Object checkProvisioningStatus(WorkflowContext wfc)`
- `protected java.util.List<ProvisioningPlan> combineCreatePlans(java.util.List<ProvisioningPlan > splitPlans)`
- `ProvisioningProject compilePasswordInterceptProject(WorkflowContext wfc)`
- `java.lang.Object compileProvisioningProject(WorkflowContext wfc)`
- `ProvisioningProject compileScheduledAssignmentProject(WorkflowContext wfc)`
- `void deactivateRoleAssignment(WorkflowContext wfc)`
- `void deActivateRoleAssignment(WorkflowContext wfc)`
- `void deleteAllAccounts(WorkflowContext wfc)`
- `void disableAllAccounts(WorkflowContext wfc)`
- `void enableAllAccounts(WorkflowContext wfc)`
- `java.lang.Object finishRefresh(WorkflowContext wfc)`
- `java.lang.Object forceRetryTimeoutFailure(WorkflowContext wfc)`
- `ProvisioningPlan generateTicketPlan(WorkflowContext wfc)`
- `java.lang.Object getAccountSelectionOwner(WorkflowContext wfc)`
- `static java.lang.String getAuditEventOperationFromApprovalItem(ApprovalItem item, java.lang.String flow)`
- `java.lang.Object getIdentityCreateUpdateApprovals(WorkflowContext wfc)`
- `java.util.Map<java.lang.String,​java.lang.Object> getIdentityModel(WorkflowContext wfc)`
- `java.lang.String getManager(WorkflowContext wfc)`
- `static java.lang.String getMessage(java.lang.String key, java.lang.Object arg)`
- `staticAttributes<java.lang.String,​java.lang.Object> getProvisionerArguments(Attributes <java.lang.String, java.lang.Object> stepArgs)`
- `java.lang.Integer getProvisioningMaxRetries(WorkflowContext wfc)`
- `java.lang.Integer getProvisioningMaxStatusChecks(WorkflowContext wfc)`
- `java.lang.Integer getProvisioningRetryThreshold(WorkflowContext wfc)`
- `java.lang.Integer getProvisioningStatusCheckInterval(WorkflowContext wfc)`
- `protected static java.util.List<java.lang.String> getStringList(java.lang.Object value)`
- `Identity getTestIdentity(WorkflowContext wfc, java.lang.String name)`
- `Identity getTestIdentityNew(WorkflowContext wfc, java.lang.String name)`
- `static boolean isElectronicSignatureEnabled(WorkflowContext wfc)`
- `void joinLCMProvWorkflowSplits(WorkflowContext wfc)`
- `java.lang.Object mergeRetryProjectResults(WorkflowContext wfc)`
- `boolean outstandingProvisioningFormsForIdentity(WorkflowContext wfc)`
- `java.lang.Object populateRecommendationsInApprovalSet(WorkflowContext wfc)`
- `java.lang.Object processApprovalDecisions(WorkflowContext wfc)`
- `ProvisioningPlan processNativeChangesApprovalDecisions(WorkflowContext wfc)`
- `java.lang.Object processPlanApprovalDecisions(WorkflowContext wfc)`
- `void processProject(WorkflowContext wfc)`
- `void provisionAllAccounts(WorkflowContext wfc, ProvisioningPlan.AccountRequest.Operation op)`
- `java.lang.Object provisionProject(WorkflowContext wfc)`
- `java.lang.Object recompileProject(WorkflowContext wfc)`
- `java.lang.Object recompileProvisioningProject(WorkflowContext wfc)`
- `void refreshIdentities(WorkflowContext wfc)`
- `void refreshIdentity(WorkflowContext wfc)`
- `java.lang.Boolean requiresStatusCheck(WorkflowContext wfc)`
- `java.lang.Object retryProvisionProject(WorkflowContext wfc)`
- `static void saveUnmanagedPlan(WorkflowContext wfc)`
- `static void saveUnmanagedPlan(WorkflowContext wfc, ProvisioningProject project)`
- `java.lang.Object splitProvisioningPlan(WorkflowContext wfc)`
- `void updatePasswordHistory(WorkflowContext wfc)`

---

## Class: `IdentityRequestLibrary.RequestItemizer`

**Package:** `sailpoint.workflow`

### Inherited Classes/Interfaces
```java
public static class IdentityRequestLibrary.RequestItemizer extends java.lang.Object
```

### Description
Utility class to help derive RequestItems from the ProvisioningPlan(s)
 that are passed into the workflow.

### Attributes
*No attributes found.*

### Methods
- `void buildItemsFromMasterPlan(IdentityRequest ir, boolean expandMultiValues)`
- `void refreshItems(IdentityRequest request, boolean expandMultiValues)`
- `void refreshItems(IdentityRequest request, boolean expandMultiValues, boolean detectRemoves)`
- `void setItemLimit(int limit)`

---

## Class: `IdentityRequestLibrary.RequestResultAnnotator`

**Package:** `sailpoint.workflow`

### Inherited Classes/Interfaces
```java
public class IdentityRequestLibrary.RequestResultAnnotator extends java.lang.Object
```

### Description
Class that goes through the plan results and applies them to the
 associated items.

 Results can be returned in a few different ways, so this class has
 the logic necessary to apply the results to each item based on hw
 the result is returned in the project "parts". ( plan, account request
 or attribute request )

### Attributes
*No attributes found.*

### Methods
- `void annotateItems(IdentityRequest ir)`

---

## Class: `IdentityRequestLibrary`

**Package:** `sailpoint.workflow`

### Inherited Classes/Interfaces
```java
public class IdentityRequestLibrary extends java.lang.Object
```

### Description
A Collection of library method designed to handle the create,
 update and complete of an IdentityRequest object as it executes
 through a workflow.

### Attributes
- `static java.lang.String ARG_EXTERNAL_TICKET_ID`
- `static java.lang.String ARG_FLOW`
- `static java.lang.String ARG_IDENTITY_DISABLE_IDENTITY_REQUESTS`
- `static java.lang.String ARG_IDENTITY_DISPLAY_NAME`
- `static java.lang.String ARG_IDENTITY_NAME`
- `static java.lang.String ARG_IDENTITY_REQUEST`
- `static java.lang.String ARG_IDENTITY_REQUEST_ID`
- `static java.lang.String ARG_PROJECT`
- `static java.lang.String ARG_SOURCE`
- `static java.lang.String ARG_SPLIT_PROVISIONING`
- `static java.lang.String ARG_STATE`
- `static java.lang.String CONFIG_IDENTITY_REQUEST_ITEM_LIMIT`
- `static int DEFAULT_IDENTITY_REQUEST_ITEM_LIMIT`
- `static java.lang.String STATE_APPROVE_AND_PROVISION_SPLIT`
- `static java.lang.String STATE_FINISHED`
- `static java.lang.String VAR_APPROVAL_SCHEME`
- `static java.lang.String VAR_BATCH_ITEM_ID`
- `static java.lang.String VAR_IDENTITY_REQUEST_ID`

### Methods
- `static java.lang.Object assimilateWorkItemApprovalSetToIdentityRequest(WorkflowContext wfc, ApprovalSet set)`
- `static java.lang.Object assimilateWorkItemApprovalSetToIdentityRequest(WorkflowContext wfc, ApprovalSet set, boolean updateTaskResult)`
- `java.lang.Object completeIdentityRequest(WorkflowContext wfc)`
- `java.lang.Object createIdentityRequest(WorkflowContext wfc)`
- `staticIdentityRequest getIdentityRequest(WorkflowContext wfc)`
- `java.lang.Object prepareApprovalSetForNotification(WorkflowContext wfc)`
- `void recordBatchItemResult(WorkflowContext wfc)`
- `java.lang.Object refreshIdentityRequestAfterApproval(WorkflowContext wfc)`
- `static void refreshIdentityRequestAfterJoin(WorkflowContext wfc)`
- `java.lang.Object refreshIdentityRequestAfterProvisioning(WorkflowContext wfc)`
- `java.lang.Object refreshIdentityRequestAfterRetry(WorkflowContext wfc)`
- `static void refreshWorkflowSummaries(IdentityRequest ir, TaskResult result)`
- `static void scrubbTaskResultArtifacts(WorkflowContext wfc)`
- `java.lang.Object updateExternalTicketId(WorkflowContext wfc)`
- `static void updateIdentityRequestItemProvisioningState(ApprovalItem approvalItem, WorkflowContext wfc)`
- `java.lang.Object updateIdentityRequestState(WorkflowContext wfc)`

---

## Class: `LCMLibrary`

**Package:** `sailpoint.workflow`

### Inherited Classes/Interfaces
```java
@Deprecated public class LCMLibrary extends java.lang.Object
```

### Description
*No description available.*

### Attributes
*No attributes found.*

### Methods
*No methods found.*

---

## Class: `MFALibrary.DuoCred`

**Package:** `sailpoint.workflow`

### Inherited Classes/Interfaces
```java
protected static class MFALibrary.DuoCred extends java.lang.Object
```

### Description
*No description available.*

### Attributes
*No attributes found.*

### Methods
*No methods found.*

---

## Class: `MFALibrary`

**Package:** `sailpoint.workflow`

### Inherited Classes/Interfaces
```java
public class MFALibrary extends java.lang.Object
```

### Description
Workflow library used in MultiFactor Authentication workflow providers.

### Attributes
- `static java.lang.String CONFIG_DUO_AUTH_API_HOST`
- `static java.lang.String CONFIG_DUO_AUTH_INTEGRATION_KEY`
- `static java.lang.String CONFIG_DUO_AUTH_SECRET_KEY`
- `static java.lang.String RSA_AUTH_CMD`
- `static java.lang.String RSA_AUTH_PARAMS`
- `static java.lang.String USER_NEW_STATIC_PASSCODE`
- `static java.lang.String USER_NEW_STATIC_PASSCODE_CONFIRM`
- `static java.lang.String VAR_APPLICATION_NAME`
- `static java.lang.String VAR_MFA_RESPONSE_MESSAGE`
- `static java.lang.String VAR_NATIVE_USER_ID_ATTRIBUTE`

### Methods
- `void addFieldsToForm(WorkflowContext wfc)`
- `static void addMFAMessage(WorkflowContext wfc)`
- `java.lang.String duoAuthenticate(WorkflowContext wfc)`
- `sailpoint.workflow.MFAAuthResponse duoAuthenticationStatus(WorkflowContext wfc)`
- `static java.lang.String duoGetDevices(SailPointContext context, java.lang.String applicationName, java.lang.String name)`
- `protected staticMFALibrary.DuoCred getDuoCredentials(SailPointContext context, java.lang.String appName)`
- `protected static java.lang.String getIdentityName(WorkflowContext wfc)`
- `static java.lang.String getNativeUserId(WorkflowContext wfc)`
- `void postProcessFormFields(WorkflowContext wfc)`
- `static sailpoint.workflow.MFAAuthResponse responseToAuthResponse(com.fasterxml.jackson.databind.JsonNode obj)`
- `static sailpoint.workflow.MFAAuthResponse responseToAuthResponse(java.lang.String preAuthResponse)`
- `static java.util.List<java.util.List<java.lang.String>> responseToDevice(Field field, java.lang.String preAuthResponse)`
- `static java.util.List<java.util.List<java.lang.String>> responseToMethod(Field field, java.lang.String preAuthResponse, java.lang.String selectedDevice, boolean allowSMSAuth)`
- `sailpoint.workflow.MFAAuthResponse rsaLogin(WorkflowContext wfc)`
- `void rsaLogout(WorkflowContext wfc, java.lang.String sessionId)`
- `protected static void validateField(Field field)`

---

## Class: `PAMLibrary`

**Package:** `sailpoint.workflow`

### Inherited Classes/Interfaces
```java
public class PAMLibrary extends java.lang.Object
```

### Description
A workflow library with methods that are used with PAM workflows.

### Attributes
- `static java.lang.String ARG_APPROVAL_SCHEMA`
- `static java.lang.String ARG_CONTAINER_DISPLAY_NAME`
- `static java.lang.String ARG_CONTAINER_NAME`
- `static java.lang.String ARG_CONTAINER_OWNER_NAME`
- `static java.lang.String ARG_IDENTITY_DISPLAY_NAME`
- `static java.lang.String ARG_IDENTITY_NAME`
- `static java.lang.String ARG_PAM_REQUEST`
- `static java.lang.String ARG_PLAN`

### Methods
- `static void approvalWorkItemCompleted(WorkflowContext wfc, sailpoint.service.pam.PamRequest request, WorkItem item)`
- `static void approvalWorkItemOpened(WorkflowContext wfc, sailpoint.service.pam.PamRequest request, WorkItem item)`
- `void auditApprovalDecision(WorkflowContext wfc)`
- `java.util.List<Workflow.Approval> createApprovals(WorkflowContext wfc)`
- `ApprovalSet createApprovalSetFromPamRequest(WorkflowContext wfc)`
- `sailpoint.service.pam.PamRequest createPamRequest(WorkflowContext wfc)`
- `static void setManagedAttributeOwner(ManagedAttribute attr, SailPointContext context)`

---

## Class: `PolicyViolationLibrary`

**Package:** `sailpoint.workflow`

### Inherited Classes/Interfaces
```java
public class PolicyViolationLibrary extends ApprovalLibrary
```

### Description
A workflow library with methods related to policy violation workflows.

### Attributes
- `static java.lang.String ARG_ACTOR`
- `static java.lang.String ARG_COMMENTS`
- `static java.lang.String ARG_EXPIRATION`
- `static java.lang.String ARG_REMEDIATIONS`
- `static java.lang.String ARG_REMEDIATOR`

### Methods
- `java.lang.Object delete(WorkflowContext wfc)`
- `static java.lang.String getMessage(java.lang.String key, java.lang.Object arg)`
- `java.lang.Object getRemediatables(WorkflowContext wfc)`
- `protected static java.util.List<java.lang.String> getStringList(java.lang.Object value)`
- `java.lang.Object ignore(WorkflowContext wfc)`
- `java.lang.Object mitigateViolation(WorkflowContext wfc)`
- `java.lang.Object remediateViolation(WorkflowContext wfc)`

---

## Class: `RapidSetupLibrary`

**Package:** `sailpoint.workflow`

### Inherited Classes/Interfaces
```java
public class RapidSetupLibrary extends java.lang.Object
```

### Description
*No description available.*

### Attributes
- `static java.lang.String VAR_NAME_REQUEST_TYPE`

### Methods
- `staticProvisioningPlan buildJoinerPlan(WorkflowContext wfc)`
- `staticProvisioningPlan buildLeaverPlan(WorkflowContext wfc)`
- `staticProvisioningPlan buildMoverPlan(WorkflowContext wfc)`
- `static java.util.List<RoleAssignment> calculateBirthrightRoles(WorkflowContext wfc)`
- `static void certWaitExpired(WorkflowContext wfc)`
- `static void clearAuthenticationQuestionsAndPassword(WorkflowContext wfc)`
- `static void executeLeaverDeferActions(WorkflowContext wfc)`
- `static void executeLeaverDeferActions(WorkflowContext wfc, boolean isPam)`
- `static void executeLeaverPamDeferActions(WorkflowContext wfc)`
- `static java.lang.Object executePostJoinerRule(WorkflowContext wfc)`
- `static java.lang.Object executePostLeaverRule(WorkflowContext wfc)`
- `static java.lang.Object executePostMoverRule(WorkflowContext wfc)`
- `static java.util.Map<java.lang.String,​java.util.List<java.lang.String>> executeRemoveIdentityOwnership(WorkflowContext wfc)`
- `staticLeaverPlanBuilder getLeaverPlanBuilder(WorkflowContext wfc)`
- `static java.util.Map<java.lang.String,​java.lang.Object> getMoverCertificationConfiguration(WorkflowContext wfc)`
- `static java.lang.String getRequestType(WorkflowContext wfc)`
- `static boolean isMoverCertificationEnabled(WorkflowContext wfc)`
- `static boolean isMoverJoinerEnabled(WorkflowContext wfc)`
- `static boolean isSendTemporaryPasswordEmailEnabled(WorkflowContext wfc)`
- `static boolean launchCertificationFromTemplate(WorkflowContext wfc)`
- `static void propagateCustomRename(WorkflowContext wfc)`
- `static java.util.Map reassignOwnership(WorkflowContext wfc)`
- `static void rejectApprovalWorkItems(WorkflowContext wfc)`
- `static void repairIdentity(WorkflowContext wfc)`
- `static void updateApprovalScheme(WorkflowContext wfc)`
- `static void updateProcessStatus(WorkflowContext wfc)`

---

## Class: `RoleLibrary`

**Package:** `sailpoint.workflow`

### Inherited Classes/Interfaces
```java
public class RoleLibrary extends ApprovalLibrary
```

### Description
A workflow library with methods related to role model approvals.

### Attributes
- `static java.lang.String APPROVAL_SOURCE_CERTIFICATION`
- `static java.lang.String APPROVAL_SOURCE_DIRECTED`
- `static java.lang.String APPROVAL_SOURCE_MODELER`
- `static java.lang.String APPROVAL_SOURCE_UNDIRECTED`
- `static java.lang.String ARG_DISABLE`
- `static java.lang.String ARG_ROLE`
- `static java.lang.String VAR_APPROVAL_SOURCE`
- `static java.lang.String VAR_IMPACT_ANALYSIS_FILTER`
- `static java.lang.String VAR_IMPACT_ANALYSIS_OWNER`
- `static java.lang.String VAR_IMPACT_ANALYSIS_RESULT`
- `static java.lang.String VAR_NO_ROLE_PROPAGATION`

### Methods
- `java.lang.Object auditRoleDifferences(WorkflowContext wfc)`
- `java.util.List<Workflow.Approval> buildApplicationApprovals(WorkflowContext wfc)`
- `Workflow.Approval buildOwnerApproval(WorkflowContext wfc)`
- `void disableRole(WorkflowContext wfc)`
- `void enableRole(WorkflowContext wfc)`
- `java.lang.String getApprovalAuditAction(WorkflowContext wfc)`
- `java.lang.String getDisplayableRoleName(WorkflowContext wfc)`
- `static java.lang.String getMessage(java.lang.String key, java.lang.Object arg)`
- `java.lang.Object getRoleDifferences(WorkflowContext wfc)`
- `protected static java.util.List<java.lang.String> getStringList(java.lang.Object value)`
- `boolean isSignificantChange(WorkflowContext wfc)`
- `java.lang.Object launchImpactAnalysis(WorkflowContext wfc)`
- `void removeOrphanedRoleRequests(WorkflowContext wfc)`
- `void setRoleDisabledStatus(WorkflowContext wfc)`
- `void updateRolesDisabledFlag(WorkflowContext wfc)`

---

## Class: `SAPGRCIntegrationLibrary`

**Package:** `sailpoint.workflow`

### Inherited Classes/Interfaces
```java
public class SAPGRCIntegrationLibrary extends java.lang.Object
```

### Description
*No description available.*

### Attributes
- `static java.lang.String MSG_CODE_SUCCESS`
- `static java.lang.String RETRY_REQUEST`
- `static java.lang.String SKIP_PROACTIVE_CHECK`

### Methods
- `void addSimulationObject(java.lang.String type, java.lang.String roleName, java.lang.String action, java.lang.String connectorName, mc_style.functions.soap.sap.document.sap_com.GracTWsSimulation simulationGracT)`
- `java.util.Map<java.lang.String,​java.lang.String> buildGRCCredentialMap(WorkflowContext wfc)`
- `void checkEntitlemtDates(WorkflowContext wfc, java.util.Map<java.lang.String, java.util.List> businessRoleMap, java.util.Map roleDates)`
- `boolean checkGRCViolations(WorkflowContext wfc, mc_style.functions.soap.sap.document.sap_com.ServiceStub serviceStub)`
- `java.util.Map<java.lang.String,​java.lang.Object> checkRequestDetails(WorkflowContext wfc)`
- `java.lang.String executeUserAccessRequest(WorkflowContext wfc)`
- `java.util.List<ProvisioningPlan.AccountRequest> filterAccountRequestSAPGRC(WorkflowContext wfc)`
- `java.util.Map<java.lang.String,​java.lang.String> getAppDetailSAPGRC(WorkflowContext wfc, java.util.Map<java.lang.String, java.lang.String> appDetailSAPGRCMap)`
- `java.util.Map<java.lang.String,​java.lang.Object> getAuditLogDetails(WorkflowContext wfc)`
- `java.util.Map<java.lang.String,​java.lang.Object> getAuditLogMap(WorkflowContext wfc)`
- `java.util.Map getBusinessRoleChckngCommonEntl(WorkflowContext wfc)`
- `java.util.Map getBusinessRoleDates(WorkflowContext wfc)`
- `java.util.List<java.lang.String> getBusinessRolesMismachedDates(java.util.Map<java.lang.String, java.util.List> businessRoleMap, java.lang.String entitlement, ProvisioningPlan.AttributeRequest attrReq, java.util.Map roleDates)`
- `java.util.Map<java.lang.String,​java.lang.String> getEffectiveDates(java.util.Date sunriseDate, java.util.Date sunsetDate)`
- `java.util.Map<java.lang.String,​java.lang.String> getEffectiveStartDateEndDates(WorkflowContext wfc)`
- `java.lang.String getGRCConnectorName(java.lang.String appName, SailPointContext context)`
- `mc_style.functions.soap.sap.document.sap_com.GracIdmReqDetailsServicesResponse getRequestDetailResponse(WorkflowContext wfc)`
- `java.lang.String getRequestInitializationSystem(WorkflowContext wfc)`
- `java.util.Map<java.lang.String,​java.lang.Object> getRequestStubDetailsMap(WorkflowContext wfc)`
- `java.util.Map getRoleBusinessMap(WorkflowContext wfc)`
- `java.util.Map getRoleExpansionItems(WorkflowContext wfc)`
- `void getSAPBusinessRoles(WorkflowContext workflowContext)`
- `java.util.Map getSAPEntlBusinessRoleMap(WorkflowContext wfc)`
- `java.util.Map<java.lang.String,​java.util.List> getSAPEntlBusinessRoleMap(WorkflowContext wfc, java.util.List<ExpansionItem > expansionItems, java.util.Map roleDates)`
- `java.lang.String getSAPGRCPollingInterval(WorkflowContext wfc)`
- `boolean isSAPDirectApplication(java.lang.String application, SailPointContext context)`
- `boolean isSAPGRCApplication(java.lang.String application, SailPointContext context)`
- `java.util.Map<java.lang.String,​java.lang.Object> retryError(WorkflowContext wfc, java.lang.Exception ex)`
- `void setAppDetailSAPGRC(WorkflowContext wfc, java.util.Map<java.lang.String, java.lang.String> appDetailSAPGRCMap)`
- `void updateCurrentStep(WorkflowContext wfc, java.lang.String requestNo)`
- `ApprovalSet updateGRCResponse(WorkflowContext wfc)`

---

## Class: `Enum StandardWorkflowHandler.EmailArgument`

**Package:** `sailpoint.workflow`

### Inherited Classes/Interfaces
```java
public static enumStandardWorkflowHandler.EmailArgument extends java.lang.Enum<StandardWorkflowHandler.EmailArgument>
```

### Description
Constants for WorkflowContext arguments when sending an email.

### Attributes
*No attributes found.*

### Methods
- `java.lang.String getValue()`
- `staticStandardWorkflowHandler.EmailArgument valueOf(java.lang.String name)`
- `staticStandardWorkflowHandler.EmailArgument[] values()`

---

## Class: `StandardWorkflowHandler`

**Package:** `sailpoint.workflow`

### Inherited Classes/Interfaces
```java
public class StandardWorkflowHandler extends AbstractWorkflowHandler
```

### Description
Default WorkflowHandler for most IdentityIQ workflows.
 You should not need to replace this but you might want
 to extend it to add custom handler methods.

### Attributes
- `static java.lang.String ARG_ARG1`
- `static java.lang.String ARG_ARG2`
- `static java.lang.String ARG_ARG3`
- `static java.lang.String ARG_ARG4`
- `static java.lang.String ARG_AUDIT_ACTION`
- `static java.lang.String ARG_AUDIT_SOURCE`
- `static java.lang.String ARG_AUDIT_STRING1`
- `static java.lang.String ARG_AUDIT_STRING2`
- `static java.lang.String ARG_AUDIT_STRING3`
- `static java.lang.String ARG_AUDIT_STRING4`
- `static java.lang.String ARG_AUDIT_TARGET`
- `static java.lang.String ARG_CASE_NAME`
- `static java.lang.String ARG_CATCH_EXCEPTIONS`
- `static java.lang.String ARG_COMMIT_ARCHIVE`
- `static java.lang.String ARG_COMMIT_CREATOR`
- `static java.lang.String ARG_IDENTITY_NAME`
- `static java.lang.String ARG_LOG_LEVEL`
- `static java.lang.String ARG_MESSAGE`
- `static java.lang.String ARG_NAME`
- `static java.lang.String ARG_NOTIFICATION_OTHER_EMAIL`
- `static java.lang.String ARG_NOTIFICATION_OTHER_NAMES`
- `static java.lang.String ARG_NOTIFICATION_OTHERS`
- `static java.lang.String ARG_NOTIFICATION_SCHEME`
- `static java.lang.String ARG_OWNER`
- `static java.lang.String ARG_PLAN`
- `static java.lang.String ARG_REQUEST_DEFINITION`
- `static java.lang.String ARG_REQUEST_NAME`
- `static java.lang.String ARG_SCHEDULE_DATE`
- `static java.lang.String ARG_SCHEDULE_DELAY_SECONDS`
- `static java.lang.String ARG_SYNC`
- `static java.lang.String ARG_TASK_DEFINITION`
- `static java.lang.String ARG_TASK_RESULT`
- `static java.lang.String ARG_TYPE`
- `static java.lang.String ARG_WORKFLOW`
- `static java.lang.String VAR_REQUEST_ERROR`
- `static java.lang.String VAR_SCHEDULED_REQUESTS`
- `static java.lang.String VAR_TASK_LAUNCH_ERROR`

### Methods
- `java.lang.Object addLaunchMessage(WorkflowContext wfc)`
- `java.lang.Object addMessage(WorkflowContext wfc)`
- `java.lang.Object audit(WorkflowContext wfc)`
- `void backgroundStep(WorkflowContext wfc)`
- `java.lang.Object commit(WorkflowContext wfc)`
- `void endApproval(WorkflowContext wfc)`
- `void endStep(WorkflowContext wfc)`
- `void endWorkflow(WorkflowContext wfc)`
- `static java.lang.String getMessage(java.lang.String key, java.lang.Object arg)`
- `java.lang.Object getMessage(WorkflowContext wfc)`
- `java.lang.Object getProperty(WorkflowContext wfc)`
- `protected static java.util.List<java.lang.String> getStringList(java.lang.Object value)`
- `java.lang.Object isProperty(WorkflowContext wfc)`
- `java.lang.Object launchTask(WorkflowContext wfc)`
- `java.lang.Object log(WorkflowContext wfc)`
- `java.lang.Object print(WorkflowContext wfc)`
- `java.lang.Object rollback(WorkflowContext wfc)`
- `java.lang.Object scheduleRequest(WorkflowContext wfc)`
- `java.lang.Object scheduleWorkflowEvent(WorkflowContext wfc)`
- `java.lang.Object sendEmail(WorkflowContext wfc)`
- `java.lang.Object sendMultipleNotifications(WorkflowContext wfc)`
- `java.lang.Object setLaunchMessage(WorkflowContext wfc)`
- `void startApproval(WorkflowContext wfc)`
- `void startStep(WorkflowContext wfc)`
- `void startWorkflow(WorkflowContext wfc)`

---

## Class: `WorkflowContext`

**Package:** `sailpoint.workflow`

### Inherited Classes/Interfaces
```java
public class WorkflowContext extends java.lang.Object implements sailpoint.tools.VariableResolver, sailpoint.server.ScriptletEvaluator.ScriptletContext
```

### Description
Runtime information maintained by the workflow engine as
 it advances through a workflow case. Passed into
 rules and scripts in case they need to know where they are,
 and passed to every method in the registered WorkflowHandler.

### Attributes
- `static java.lang.String TRACE_LEVEL_FALSE`
- `static java.lang.String TRACE_LEVEL_TERSE`
- `static java.lang.String TRACE_LEVEL_TRUE`
- `static java.lang.String WORKFLOW_TRACE_LOG`

### Methods
- `java.lang.Object get(java.lang.String name)`
- `Workflow.Approval getApproval()`
- `Attributes<java.lang.String,​java.lang.Object> getApprovalArguments()`
- `Attributes<java.lang.String,​java.lang.Object> getArguments()`
- `boolean getBoolean(java.lang.String name)`
- `java.util.List<java.lang.Object> getCallLibraries(Scriptlet s)`
- `java.lang.Object[] getCallParamaters(Scriptlet s)`
- `java.lang.Object getHierararchical(java.lang.String argName)`
- `int getInt(java.lang.String name)`
- `java.util.List<java.lang.Object> getLibraries()`
- `WorkflowContext getParent()`
- `java.lang.Object getReference(Scriptlet s)`
- `WorkflowContext getRootContext()`
- `WorkflowCase getRootWorkflowCase()`
- `java.util.Map getRuleArgs(Scriptlet s)`
- `java.util.List<Rule> getRuleLibraries(Scriptlet s)`
- `SailPointContext getSailPointContext()`
- `java.util.List<Rule> getScriptLibraries(Scriptlet s)`
- `java.util.Map getScriptParameters(Scriptlet s)`
- `Workflow.Step getStep()`
- `Attributes<java.lang.String,​java.lang.Object> getStepArguments()`
- `java.lang.String getString(java.lang.String name)`
- `java.lang.Object getString(Scriptlet s)`
- `TaskResult getTaskResult()`
- `java.lang.String getTrace()`
- `java.lang.Object getVariable(java.lang.String name)`
- `protected org.apache.commons.logging.Log getWfLogger()`
- `Workflow getWorkflow()`
- `WorkflowCase getWorkflowCase()`
- `Workflower getWorkflower()`
- `WorkflowHandler getWorkflowHandler()`
- `WorkflowLaunch getWorkflowLaunch()`
- `WorkItem getWorkItem()`
- `WorkItemArchive getWorkItemArchive()`
- `WorkItem.Level getWorkItemPriority()`
- `boolean isForeground()`
- `boolean isTrace()`
- `boolean isTransient()`
- `void queueProcessLog(ProcessLog pl)`
- `void setApproval(Workflow.Approval app)`
- `void setArgument(java.lang.String name, java.lang.Object value)`
- `void setArguments(Attributes <java.lang.String, java.lang.Object> args)`
- `void setLibraries(java.util.List<java.lang.Object> libs)`
- `void setParent(WorkflowContext wfc)`
- `void setSailPointContext(SailPointContext con)`
- `void setStep(Workflow.Step step)`
- `void setTrace(java.lang.String level)`
- `void setVariable(java.lang.String name, java.lang.Object value)`
- `void setWorkflow(Workflow wf)`
- `void setWorkflowCase(WorkflowCase wfc)`
- `void setWorkflower(Workflower wf)`
- `void setWorkflowHandler(WorkflowHandler h)`
- `void setWorkflowLaunch(WorkflowLaunch wfl)`
- `void setWorkItem(WorkItem item)`
- `void setWorkItemArchive(WorkItemArchive archive)`
- `void trace(java.lang.String msg)`
- `void traceMap(java.util.Map map)`
- `void traceObject(java.lang.Object o)`

---

## Class: `WorkflowHandler`

**Package:** `sailpoint.workflow`

### Inherited Classes/Interfaces
```java
public interface WorkflowHandler extends WorkItemHandler
```

### Description
The interface of a class that can be registered to handle
 notifications of progress through a workflow.

 The handler can have side effects such as modifying the
 workflow variables or even modifying the process model itself.

 Note that this extends WorkItemHandler. This is necessary
 for validateWorkItem, but handleWorkItem logic can be accomplished
 with endApproval as well.

 Since we have a lot of state to convey, this is all encapsulated
 in the WorkflowContext to make it easier to extend.

### Attributes
*No attributes found.*

### Methods
- `void archiveWorkItem(WorkflowContext wfc)`
- `void assimilateWorkItem(WorkflowContext wfc)`
- `void backgroundStep(WorkflowContext wfc)`
- `void cancelApproval(WorkflowContext wfc)`
- `void endApproval(WorkflowContext wfc)`
- `void endStep(WorkflowContext wfc)`
- `void endWorkflow(WorkflowContext wfc)`
- `void openWorkItem(WorkflowContext wfc)`
- `void startApproval(WorkflowContext wfc)`
- `void startStep(WorkflowContext wfc)`
- `void startWorkflow(WorkflowContext wfc)`
- `void validateWorkItem(WorkflowContext wfc)`

---

# SailPoint API Classes Details

## AccountGroupService

**Package:** `sailpoint.api`

**Description:** A service class for dealing with AccountGroups.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.AccountGroupService`

**Attributes:** N/A

**Methods:**
- `ManagedAttribute getAccountGroup (java.lang.String appName, java.lang.String groupAttr, java.lang.String groupVal)`
- `ManagedAttribute getAccountGroup (java.lang.String appName, java.lang.String groupAttr, java.lang.String groupVal, java.lang.String objectType)`
- `java.lang.String getGroupDisplayableName (java.lang.String appName, java.lang.String attr, java.lang.String val)`
- `java.util.List<java.lang.String> getGroupDisplayableNames (java.lang.String appName, java.lang.String attr, java.lang.Object vals)`
- `Filter getGroupMemberFilter ( Application app, java.lang.String attrName, java.lang.String groupIdentity)`
- `int getMemberCount ( ManagedAttribute entitlement)`
- `java.util.List<java.lang.String> getMemberNames ( ManagedAttribute group, java.lang.String memberNameAttribute)`
- `Filter getMembershipfilter ( Application app, java.lang.String attrName, java.lang.String groupIdentity)`
- `QueryOptions getMembersQueryOptions ( ManagedAttribute group)`
- `QueryOptions getMembersQueryOptions ( ManagedAttribute group, boolean connectedOnly)`
- `boolean isGroupAttribute (java.lang.String appName, java.lang.String attrName)`
- `boolean isGroupAttribute (java.lang.String appName, java.lang.String attrName, java.lang.String schemaName)`
- `static boolean isProvisioningEnabled (java.util.List< Capability > capabilities, java.util.Collection<java.lang.String> rights)`
- `static sailpoint.api.WorkflowSession launchWorkflow (sailpoint.web.group.AccountGroupDTO groupDTO, ProvisioningPlan plan, sailpoint.web.BaseBean launchingPage)`
- `static sailpoint.api.WorkflowSession launchWorkflowForAPIFlow (sailpoint.web.group.AccountGroupDTO groupDTO, ProvisioningPlan plan, SailPointContext sailPointContext, java.lang.String loggedInUserName, boolean skipApprovalFlag)`

---

## Correlator

**Package:** `sailpoint.api`

**Description:** A class to help in finding Link and Identity Objects.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Correlator`

**Attributes:**
- `static java.lang.String MULTI_MATCHMODE`
- `static java.lang.String MULTI_OPERATOR`
- `static java.lang.String RULE_RETURN_APPLICATIONS`
- `static java.lang.String RULE_RETURN_CORRELATION_ATTRIBUTE`
- `static java.lang.String RULE_RETURN_GROUP`
- `static java.lang.String RULE_RETURN_GROUP_ATTRIBUTE`
- `static java.lang.String RULE_RETURN_GROUP_ATTRIBUTE_VALUE`
- `static java.lang.String RULE_RETURN_GROUP_TYPE`
- `static java.lang.String RULE_RETURN_IDENTITY`
- `static java.lang.String RULE_RETURN_IDENTITY_ATTRIBUTE`
- `static java.lang.String RULE_RETURN_IDENTITY_ATTRIBUTE_VALUE`
- `static java.lang.String RULE_RETURN_IDENTITY_NAME`
- `static java.lang.String RULE_RETURN_LINK_ATTRIBUTE`
- `static java.lang.String RULE_RETURN_LINK_ATTRIBUTE_VALUE`
- `static java.lang.String RULE_RETURN_LINK_DISPLAYNAME`
- `static java.lang.String RULE_RETURN_LINK_IDENTITY`
- `static java.lang.String RULE_RETURN_LINK_INSTANCE`

**Methods:**
- `Identity correlateIdentity ( CorrelationConfig config, ResourceObject account)`
- `ManagedAttribute findAccountGroupByAttribute ( Application app, java.lang.String attrName, java.lang.String attrValue)`
- `ManagedAttribute findAccountGroupByAttribute ( Application app, java.lang.String attrName, java.lang.String attrValue, java.lang.String objectType)`
- `Identity findIdentityByAttribute (java.lang.String attrName, java.lang.String attrValue)`
- `Link findLink ( Application app, java.lang.String instance, java.lang.String byNativeIdentity, java.lang.String byDisplayName)`
- `Link findLinkByAttribute ( Application app, java.lang.String instance, java.lang.String attrName, java.lang.String attrValue)`
- `Link findLinkByDisplayName ( Application app, java.lang.String instance, java.lang.String displayName)`
- `Link findLinkByIdentityOrDisplayName ( Application app, java.lang.String instance, java.lang.String attrValue)`
- `Link findLinkByNativeIdentity ( Application app, java.lang.String instance, java.lang.String nativeIdentity)`
- `Link findLinkByUuid ( Application app, java.lang.String instance, java.lang.String uuid)`
- `java.lang.String getCorrelationAttribute ()`
- `void prepare ()`
- `protectedIdentity processIdentityRuleResult (java.lang.Object result)`
- `protectedSailPointObject processLinkRuleResult ( Application app, java.lang.Object result)`
- `protectedSailPointObject processTargetRuleResult (java.util.List< Application > apps, java.lang.Object result)`
- `Identity runIdentityCorrelationRules (java.util.Map<java.lang.String,java.lang.Object> inputs, java.util.List< Rule > rules)`
- `SailPointObject runLinkCorrelationRules ( Application app, java.util.Map<java.lang.String,java.lang.Object> inputs, java.util.List< Rule > rules)`
- `SailPointObject runTargetCorrelationRule (java.util.List< Application > apps, java.util.Map<java.lang.String,java.lang.Object> inputs, Rule rule)`
- `void setContext ( SailPointContext context)`
- `void setDoLocking (boolean b)`

---

## Describer

**Package:** `sailpoint.api`

**Description:** This utility enables Describable objects to handle descriptions consistently. Prior to 6.0 we took a simple approach to storing descriptions and stored a single description on its object. Due to high demand for internationalized descriptions we took an alternate approach and moved the descriptions into a separate table. This came with its own set of problems because exported objects no longer contained their own descriptions and versioned/transient objects had no means of hanging on to descriptions across multiple versions. In 6.2 we are taking a hybrid approach: descriptions still exist in the LocalizedAttributes table but they are also available inside of a Map that each object maintains among its attributes. The methods in this utility class facilitate setting and/or retrieving descriptions from Describable objects. Currently these include Application, Policy, and Bundle. sailpoint.api.Explanator contains similar utilities for ManagedAttributes.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Describer`

**Attributes:** N/A

**Methods:**
- `void addDescriptions (java.util.Map<java.lang.String,java.lang.String> descriptions)`
- `java.lang.String getDefaultDescription ( SailPointContext context)`
- `void removeDescription ( SailPointContext context, java.lang.String locale)`
- `void removeDescription ( SailPointContext context, java.util.Locale locale)`
- `staticDescribable removeDescription ( SailPointContext context, LocalizedAttribute attribute)`
- `int saveLocalizedAttributes ( SailPointContext context)`
- `void setDefaultDescription ( SailPointContext context, java.lang.String description)`
- `staticDescribable updateDescription ( SailPointContext context, LocalizedAttribute attribute)`

---

## Differencer.AccountItemComparator

**Package:** `sailpoint.api`

**Description:** Return whether the given objects are equal.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Differencer.BaseComparator`
- `sailpoint.api.Differencer.AccountItemComparator`
- `java.util.Comparator<AccountItem>`

**Attributes:** N/A

**Methods:**
- `boolean areEqual ( AccountItem item1, AccountItem item2)`

---

## Differencer.BaseComparator<T>

**Package:** `sailpoint.api`

**Description:** Common comparator implementation shared by the class-specific comparators. Subclass this and implement the areEqual() method.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Differencer.BaseComparator<T>`
- `java.util.Comparator<T>`

**Attributes:** N/A

**Methods:**
- `abstract boolean areEqual ( T o1, T o2)`
- `int compare ( T o1, T o2)`
- `boolean equals (java.lang.Object o)`

---

## Differencer.BundleListFilter

**Package:** `sailpoint.api`

**Description:** A ListFilter that only includes bundles that reference the application passed into the constructor.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Differencer.BundleListFilter`
- `Util.ListFilter<java.lang.String>`

**Attributes:** N/A

**Methods:**
- `boolean removeFromList (java.lang.String bundleName)`

---

## Differencer.BundleSnapshotComparator

**Package:** `sailpoint.api`

**Description:** Deep equality comparison for BundleSnapshots.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Differencer.BaseComparator`
- `sailpoint.api.Differencer.BundleSnapshotComparator`
- `java.util.Comparator<BundleSnapshot>`

**Attributes:** N/A

**Methods:**
- `boolean areEqual ( BundleSnapshot snap1, BundleSnapshot snap2)`

---

## Differencer.EntitlementGroupComparator

**Package:** `sailpoint.api`

**Description:** Deep equality comparison for EntitlementGroups.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Differencer.BaseComparator`
- `sailpoint.api.Differencer.EntitlementGroupComparator`
- `java.util.Comparator<EntitlementGroup>`

**Attributes:** N/A

**Methods:**
- `boolean areEqual ( EntitlementGroup group1, EntitlementGroup group2)`

---

## Differencer.EntitlementSnapshotComparator

**Package:** `sailpoint.api`

**Description:** Deep equality comparison for EntitlementSnapshots.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Differencer.BaseComparator`
- `sailpoint.api.Differencer.EntitlementSnapshotComparator`
- `java.util.Comparator<EntitlementSnapshot>`

**Attributes:** N/A

**Methods:**
- `boolean areEqual ( EntitlementSnapshot snap1, EntitlementSnapshot snap2)`

---

## Differencer.IdentitySnapshotComparator

**Package:** `sailpoint.api`

**Description:** Deep equality comparison for IdentitySnapshots.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Differencer.BaseComparator`
- `sailpoint.api.Differencer.IdentitySnapshotComparator`
- `java.util.Comparator<IdentitySnapshot>`

**Attributes:** N/A

**Methods:**
- `boolean areEqual ( IdentitySnapshot snap1, IdentitySnapshot snap2)`

---

## Differencer.LinkSnapshotComparator

**Package:** `sailpoint.api`

**Description:** Deep equality comparison for LinkSnapshots.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Differencer.BaseComparator`
- `sailpoint.api.Differencer.LinkSnapshotComparator`
- `java.util.Comparator<LinkSnapshot>`

**Attributes:** N/A

**Methods:**
- `boolean areEqual ( LinkSnapshot snap1, LinkSnapshot snap2)`

---

## Differencer.LinkSnapshotListFilter

**Package:** `sailpoint.api`

**Description:** A ListFilter that only includes LinkSnapshots for the application passed into the constructor.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Differencer.LinkSnapshotListFilter`
- `Util.ListFilter<LinkSnapshot>`

**Attributes:** N/A

**Methods:**
- `boolean removeFromList ( LinkSnapshot ls)`

---

## Differencer.PermissionComparator

**Package:** `sailpoint.api`

**Description:** Deep equality comparison for Permissions.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Differencer.BaseComparator`
- `sailpoint.api.Differencer.PermissionComparator`
- `java.util.Comparator<Permission>`

**Attributes:** N/A

**Methods:**
- `boolean areEqual ( Permission p1, Permission p2)`

---

## Differencer.PolicyViolationSnapshotComparator

**Package:** `sailpoint.api`

**Description:** Return whether the given objects are equal.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Differencer.BaseComparator`
- `sailpoint.api.Differencer.PolicyViolationSnapshotComparator`
- `java.util.Comparator<PolicyViolation>`

**Attributes:** N/A

**Methods:**
- `boolean areEqual ( PolicyViolation violation1, PolicyViolation violation2)`

---

## Differencer.RoleAssignmentSnapshotComparator

**Package:** `sailpoint.api`

**Description:** Return whether the given objects are equal.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Differencer.BaseComparator`
- `sailpoint.api.Differencer.RoleAssignmentSnapshotComparator`
- `java.util.Comparator<RoleAssignmentSnapshot>`

**Attributes:** N/A

**Methods:**
- `boolean areEqual ( RoleAssignmentSnapshot snapshot1, RoleAssignmentSnapshot snapshot2)`

---

## Differencer.RoleTargetComparator

**Package:** `sailpoint.api`

**Description:** Return whether the given objects are equal.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Differencer.BaseComparator`
- `sailpoint.api.Differencer.RoleTargetComparator`
- `java.util.Comparator<RoleTarget>`

**Attributes:** N/A

**Methods:**
- `boolean areEqual ( RoleTarget target1, RoleTarget target2)`

---

## Differencer.ScorecardComparator

**Package:** `sailpoint.api`

**Description:** Deep equality comparison for Scorecards.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Differencer.BaseComparator`
- `sailpoint.api.Differencer.ScorecardComparator`
- `java.util.Comparator<Scorecard>`

**Attributes:** N/A

**Methods:**
- `boolean areEqual ( Scorecard sc1, Scorecard sc2)`

---

## Differencer

**Package:** `sailpoint.api`

**Description:** Utility class to compare various objects and generate a summary of the differences. Used by the Aggregator to determine when to generate identity snapshots, and can be of general use in custom workflows. There are two sets of methods in here, those that calculate Difference objects that describe the differences between two objects, and those that return a boolean value to indicate whether there are any differences between two objects. The later methods are used in places where the generation of something (like an IdentitySnapshot) needs to be triggered but all the specific differences do not matter.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Differencer`

**Attributes:** N/A

**Methods:**
- `static boolean contains (java.util.List l, java.lang.Object el, java.util.Comparator c)`
- `IdentityDifference diff ( IdentitySnapshot prev, IdentitySnapshot current, Application app, boolean includePolicyViolations)`
- `static boolean equal (java.lang.String s1, java.lang.String s2)`
- `static boolean equal (java.util.Collection list1, java.util.Collection list2)`
- `static boolean equal (java.util.Date d1, java.util.Date d2)`
- `static boolean equal (java.util.List l1, java.util.List l2, java.util.Comparator c)`
- `boolean equal ( IdentitySnapshot snap1, IdentitySnapshot snap2)`
- `static boolean equal ( SailPointObject o1, SailPointObject o2)`
- `static boolean objectsEqual (java.lang.Object o1, java.lang.Object o2)`
- `static boolean objectsEqual (java.lang.Object o1, java.lang.Object o2, boolean nullAndEmptyStrEqual)`
- `static boolean objectsEqualOrContains (java.lang.Object o1, java.lang.Object o2, boolean nullAndEmptyStrEqual)`
- `void setIncludeNativeIdentity (boolean b)`
- `void setMaxStringLength (int maxStringLength)`

---

## DynamicScopeMatchmaker

**Package:** `sailpoint.api`

**Description:** This class centralizes the business logic that determines if a DynamicScope applies to an Identity.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.DynamicScopeMatchmaker`

**Attributes:** N/A

**Methods:**
- `java.util.List<java.lang.String> getMatches ( Identity identity)`
- `boolean isMatch ( DynamicScope dynamicScope, Identity identity)`
- `boolean isMatch ( DynamicScope dynamicScope, Identity identity, boolean includeAllSystemAdmins)`
- `boolean isMember ( Identity currUser, Identity ident, DynamicScope.PopulationRequestAuthority authority)`

---

## EmailNotifier

**Package:** `sailpoint.api`

**Description:** The interface of an object that can send notifications.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `void sendEmailNotification ( SailPointContext context, EmailTemplate template, EmailOptions options)`
- `java.lang.Boolean sendImmediate ()`
- `void setSendImmediate (java.lang.Boolean b)`

---

## EmailSuppressor

**Package:** `sailpoint.api`

**Description:** The EmailSuppressor can be used to track who has received an email of a particular type within a logical "session". This can then be used to suppress sending duplicate emails to the same person.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.EmailSuppressor`

**Attributes:** N/A

**Methods:**
- `int getEmailsSuppressed ()`
- `boolean shouldSend ( EmailTemplate template, java.lang.String recipient)`

---

## Emailer

**Package:** `sailpoint.api`

**Description:** A service that can send emails and capture error messages.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Emailer`

**Attributes:** N/A

**Methods:**
- `EmailTemplate compileAccessRequestReminderEmail ( EmailTemplate template, java.lang.String workItemId, java.lang.String recipientId, java.lang.String comment)`
- `EmailTemplate compileCertReminderEmail ( EmailTemplate template, java.lang.String certId, java.lang.String recipientId, Identity sender, java.lang.String comment)`
- `Identity getCertReminderEmailRecipient (java.lang.String certId)`
- `void sendEmailNotification ( EmailTemplate email, EmailOptions ops)`

---

## EncodingUtil

**Package:** `sailpoint.api`

**Description:** Utility class for hash or encrypt Identity secret, based on setting in system configuration. It should be only applied to IdentityIQ Identity password, password history, Link password history, and authentication question answers.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.EncodingUtil`

**Attributes:** N/A

**Methods:**
- `static java.lang.String decrypt (java.lang.String src)`
- `static java.lang.String encode (java.lang.String secret, SailPointContext context)`
- `static java.lang.String encrypt (java.lang.String src)`
- `static boolean isEncrypted (java.lang.String secret)`
- `static boolean isHashed (java.lang.String secret)`
- `static boolean isHashingEnabled ( SailPointContext context)`
- `static boolean isMatch (java.lang.String secret, java.lang.String encryptedOrHashedValue, SailPointContext context)`

---

## EntitlementCorrelator

**Package:** `sailpoint.api`

**Description:** The EntitlementCorrelator inspects identities and calculates assigned and detected roles and entitlement exceptions based on the attributes on the links. The identity can be updated with the roles and exceptions that are found or the results can be retrieved from the EntitlementCorrelator using the various getters. Entitlement correlation can be performed for "impact analysis" to show how modifications to the role model would change role assignments and detections. This is enabled by setting the candidate roles and enabling the useCandidates flag before analyzing an identity. The assignment and detection process has these steps for each identity: Find all "top level" roles, those with no super roles For each top level role, do a depth first traversal For each traversed role evaluate the assignment selector or try to match the profiles. If the assignment selector or profiles matched, check that all super roles also match to account for multiple inheritance. If the role and its supers match mark the role as matched and descend, otherwise stop traversing this path. This process is repeated for top-level assignable roles, top-level detectable roles, and then for roles that are required/permitted by the assigned role (if there are any noDetectionUnlessAssigned role types).

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.EntitlementCorrelator`

**Attributes:**
- `static java.lang.String ARG_DEMOTE_SOFT_PERMITS`
- `static java.lang.String ARG_PROMOTE_SOFT_PERMITS`
- `static java.lang.String LINK_LOAD_CONFIG_KEY`
- `static java.lang.String RET_ASSIGNED_ROLE_CHANGES`
- `static java.lang.String RET_DETECTED_ROLE_CHANGES`
- `static java.lang.String RET_EXCEPTION_CHANGES`
- `static java.lang.String RULE_ARGUMENT_ROLE_NAME`
- `static java.lang.String STRATEGY_CACHE`
- `static java.lang.String STRATEGY_ITERATE`
- `static java.lang.String STRATEGY_SEARCH`

**Methods:**
- `void analyzeContributingEntitlements ( Identity identity)`
- `void analyzeContributingEntitlements ( Identity identity, RoleAssignment assignment)`
- `void analyzeIdentity ( Identity identity)`
- `void analyzeIdentity ( Identity identity, boolean strictIdentityComparison)`
- `staticEntitlementCorrelator createDefaultEntitlementCorrelator ( SailPointContext context)`
- `void detectAssignment ( Identity identity, RoleAssignment assignment)`
- `void detectDeassignment ( Identity identity, RoleAssignment assignment)`
- `void dump ()`
- `java.util.List<Bundle> getAutoAssignedRoles ()`
- `java.util.List<EntitlementGroup> getContributingEntitlements ( Identity identity, RoleAssignment assignment, Bundle detectedRole, boolean flattened)`
- `java.util.Map<Bundle,​java.util.List<EntitlementGroup>> getContributingEntitlements ( RoleAssignment assignment, boolean flattened)`
- `java.util.List<EntitlementGroup> getContributingEntitlements ( RoleAssignment assignment, Bundle detectedRole, boolean flattened)`
- `java.util.List<EntitlementGroup> getContributingListEntitlements ( RoleAssignment assignment, Bundle detectedRole, boolean flattened)`
- `sailpoint.api.CorrelationModel getCorrelationModel ()`
- `java.util.List<Bundle> getDetectedRoles ()`
- `java.util.List<EntitlementGroup> getEntitlementExceptions ()`
- `java.util.Map<Bundle,​java.util.List<EntitlementGroup>> getEntitlementMappings ()`
- `java.util.Map<Bundle,​java.util.List<EntitlementGroup>> getEntitlementMappings (boolean flattened)`
- `java.util.Map<Bundle,​java.util.List<EntitlementGroup>> getEntitlementMappings ( Identity identity)`
- `java.util.List<RoleAssignment> getNewRoleAssignments ()`
- `java.util.Map<sailpoint.api.CorrelationModel.CorrelationRole,​java.util.List<EntitlementGroup>> getRoleEnititlementMapping (boolean flattened)`
- `void prepare ()`
- `void printStats ()`
- `void processBirthrightRoles ( Identity identity)`
- `void processIdentity ( Identity identity)`
- `void redetect ( Identity identity)`
- `void refreshGroupDefinitions ()`
- `void saveAnalysis ( Identity identity)`
- `void saveAssignmentAnalysis ( Identity identity)`
- `void saveDetectionAnalysis ( Identity identity)`
- `void saveResults ( TaskResult result)`
- `void setCandidates (java.util.List< Bundle > roles)`
- `void setDeletes (java.util.List< Bundle > roles)`
- `void setDemoteSoftPermits (boolean b)`
- `void setDoRoleAssignment (boolean b)`
- `void setNoPersistentIdentity (boolean notPersistent)`
- `void setPromoteSoftPermits (boolean b)`
- `void setSourceRoles (java.util.List< Bundle > roles)`
- `void setUseCandidates (boolean b)`

---

## Entitlizer.RoleData

**Package:** `sailpoint.api`

**Description:** Helper class to hold data around for each of the entitlements. We turn the entitlementmapping from the entitlement correlation around so it's entitlement-centric to allow us to update the links as they are visited when possible.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Entitlizer.RoleData`

**Attributes:** N/A

**Methods:**
- `void addSourceAssignable (java.lang.String roleName)`
- `void addSourceAssignables (java.util.List<java.lang.String> roles)`
- `void addSourceDetectable (java.lang.String roleName)`
- `java.lang.String getSourceAssignablesCsv ()`
- `java.util.List<java.lang.String> getSourceDetectables ()`
- `java.lang.String getSourceDetectablesCsv ()`
- `void setSourceDetectables (java.util.List<java.lang.String> sourceDetectables)`
- `boolean updatedDuringLinkRefresh ()`
- `void updateDuringLinkRefresh (boolean b)`

---

## Entitlizer

**Package:** `sailpoint.api`

**Description:** An API class that handles the create/update/delete of IdentityEntitlement objects as they pertain to Link attribute assignment. Mainly in charge of promoting entitlement attributes from links during the aggregation and also optionally during the refresh process. There is no optimization code here, we always fetch and update all of the entitlement on a link. Up front we query for all of the IdentityEntitlement for the identity on a given app and stores them in a map keyed by the attribute name and attribute value concatenated together. This class delegates the promotion of detected and assigned roles the RoleEntitlizer.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.AbstractEntitlizer`
- `sailpoint.api.Entitlizer`

**Attributes:**
- `static java.lang.String ARG_DISABLE_IDENTITY_ENTITLEMENT_CHECK`
- `static java.lang.String ARG_DISABLE_IDENTITY_ENTITLEMENT_PROMOTION`
- `static java.lang.String ARG_FORCE_IDENTITY_ENTITLEMENT_REFRESH`
- `static java.lang.String ARG_REFRESH_IDENTITY_ENTITLEMENTS`
- `static java.lang.String ARG_RENAMES_MAP`
- `static java.lang.String RET_CREATED`
- `static java.lang.String RET_REMOVED`
- `static java.lang.String RET_UPDATED`

**Methods:**
- `protected java.lang.String buildKey (java.lang.String attrName, java.lang.String value)`
- `void finish ( Identity identity)`
- `protected static java.lang.String getKey ( Entitlements group, java.lang.String attrName, java.lang.String value)`
- `protected java.util.HashMap<java.lang.String,​IdentityEntitlement> getLinkEntitlements ( Link link)`
- `protected boolean isCandidateForRemoval ( IdentityRequestItem item)`
- `boolean isForcePromotion ()`
- `void moveLinkEntitlements ( Link link, Identity source, Identity destination)`
- `void promoteLinkEntitlements ( Link link)`
- `void promoteRoleAssignments ( Identity identity)`
- `void promoteRoleDetections ( Identity identity)`
- `void refreshAttributeAssignmentEntitlements (java.util.List< AttributeAssignment > assignments, Identity identity)`
- `void refreshEntitlements ( Identity identity, java.util.List< Application > sources, EntitlementCorrelator correlator)`
- `void refreshTargetPermissions ( Link link, java.util.List< Permission > permissions)`
- `void restoreFromTaskResult ( TaskResult result)`
- `void saveResults ( TaskResult result)`
- `void setCorrelationModel (sailpoint.api.CorrelationModel model)`
- `void setEntitlementMapping ( Identity id, java.util.Map< Bundle ,java.util.List< EntitlementGroup >> map)`
- `void setForcePromotion (boolean forceIdentityEntitlementPromotion)`
- `void traceStatistics ()`

---

## IdentityHistoryService

**Package:** `sailpoint.api`

**Description:** Service class used to query for identity history items.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.service.BaseListService<sailpoint.service.BaseListServiceContext>`
- `sailpoint.api.IdentityHistoryService`

**Attributes:**
- `static java.lang.String COL_COMMENTS`
- `static java.lang.String COL_ID`

**Methods:**
- `staticQueryOptions buildQuery ( QueryOptions ops, IdentityHistoryItem.Type type, java.lang.String identityId, CertificationItem item)`
- `protected java.lang.Object convertColumn (java.util.Map.Entry<java.lang.String,java.lang.Object> entry, ColumnConfig config, java.util.Map<java.lang.String,java.lang.Object> rawObject)`
- `int countComments (java.lang.String identityId, java.lang.String role)`
- `int countComments (java.lang.String identityId, EntitlementSnapshot entitlements, Certification.EntitlementGranularity granularity)`
- `int countComments (java.lang.String identityId, PolicyViolation violation)`
- `int countEntitlementDecisions (java.lang.String identityId)`
- `int countRoleDecisions (java.lang.String identityId)`
- `int countViolationDecisions (java.lang.String identityId)`
- `java.util.List<IdentityHistoryItem> getComments (java.lang.String identityId, CertificationItem item)`
- `java.util.List<IdentityHistoryItem> getDecisions (java.lang.String identityId)`
- `ListResult getIdentityHistory (java.lang.String identityId, CertificationItem item)`
- `java.util.List<IdentityHistoryItem> getItems ( IdentityHistoryItem.Type type, java.lang.String identityId, EntitlementSnapshot entitlements, Certification.EntitlementGranularity granularity)`
- `IdentityHistoryItem getLastDecision (java.lang.String identityId, CertificationItem item)`
- `IdentityHistoryItem getLastEntitlementDecision (java.lang.String identityId, EntitlementSnapshot snapshot, Certification.EntitlementGranularity granularity)`
- `IdentityHistoryItem getLastRoleDecision (java.lang.String identityId, java.lang.String roleName)`
- `IdentityHistoryItem getLastViolationDecision (java.lang.String identityId, PolicyViolation violation)`
- `java.util.List<IdentityHistoryItem> getMostRecentAccountDecisions (java.lang.String identityId, java.lang.String app, java.lang.String instance, java.lang.String nativeIdentity)`
- `java.util.Map<java.lang.String,​java.lang.Object> getPendingDecision (java.lang.String identityId, CertificationItem item)`

---

## IdentityService

**Package:** `sailpoint.api`

**Description:** A service layer that deals with identities.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.IdentityService`

**Attributes:**
- `static java.lang.String COMBO_BOX_PREFIX`
- `static java.lang.String SUGGEST_CONTEXT`
- `static java.lang.String SUGGEST_ID`

**Methods:**
- `int countLinks ( Identity identity)`
- `int countLinks ( Identity identity, Application application)`
- `staticQueryOptions getDelegationRecipientSuggestQueryOptions ( SailPointContext context, java.lang.String certificationItemId, java.lang.String query)`
- `GridState getGridState ( Identity ident, java.lang.String stateName)`
- `java.util.List<GridState> getGridStates ( Identity ident)`
- `java.util.List<Identity> getIdentitiesWithViolationsOwnedByIdentity ( Identity owner)`
- `Identity getIdentityFromIdOrName (java.lang.String id, java.lang.String name)`
- `Identity getIdentityFromPolicyViolation (java.lang.String policyViolationId)`
- `QueryOptions getIdentitySuggestQueryOptions (java.util.Map<java.lang.String,?> requestParams, Identity loggedInUser)`
- `Link getLink ( Identity identity, Application application, java.lang.String instance, java.lang.String nativeIdentity)`
- `Link getLink ( Identity identity, Application application, java.lang.String instance, java.lang.String nativeIdentity, java.lang.String uuid)`
- `Link getLink ( Identity identity, Application application, ResourceObject obj)`
- `Link getLinkById ( Identity identity, java.lang.String id)`
- `java.util.List<Link> getLinks ( Identity identity, int start, int limit)`
- `java.util.List<Link> getLinks ( Identity identity, java.util.List< Application > apps, java.lang.String instance)`
- `java.util.List<Link> getLinks ( Identity identity, Application application)`
- `java.util.List<Link> getLinks ( Identity identity, Application application, java.lang.String instance)`
- `ExtState getState ( Identity ident, java.lang.String name)`
- `java.util.List<Identity> getSubordinatesWithViolations ( Identity manager)`
- `boolean hasAccounts ( Identity identity, java.util.List< Application > apps)`
- `java.lang.String resolveIdentityDisplayName (java.lang.String name)`
- `void saveGridState ( Identity ident, GridState state)`
- `void saveState ( Identity ident, ExtState state)`

---

## Localizer

**Package:** `sailpoint.api`

**Description:** Utility for dealing with localized attributes.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Localizer`

**Attributes:**
- `static java.lang.String ATTR_DESCRIPTION`
- `static java.lang.String LOCALE_DEFAULT`
- `static java.lang.String LOCALE_DEFAULT_DISPLAY_NAME`
- `static java.lang.String MAP_LOCALE`
- `static java.lang.String MAP_LOCALE_DISPLAY_NAME`
- `static java.lang.String MAP_VALUE`

**Methods:**
- `void addLocalizedAttribute (java.lang.String attribute, java.lang.String locale, java.lang.String value, java.lang.String name, java.lang.String simpleClassName)`
- `void buildAttributes (java.lang.String attribute, java.util.Map<java.lang.String,java.lang.String> localizedValues, java.lang.String name, java.lang.String simpleClassName)`
- `LocalizedAttribute buildLocalizedAttribute (java.lang.String attribute, java.lang.String locale, java.lang.String name, java.lang.String simpleClassName)`
- `void commitAttributes (java.lang.String targetId)`
- `void commitAttributes ( SailPointObject obj)`
- `LocalizedAttribute findAttribute (java.lang.String attribute, java.lang.String locale)`
- `LocalizedAttribute findAttribute (java.lang.String attribute, java.lang.String locale, boolean findDefaultLocale)`
- `java.util.List<LocalizedAttribute> findAttributes (java.lang.String attribute)`
- `java.util.List<LocalizedAttribute> findAttributes (java.lang.String attribute, boolean checkNames)`
- `java.lang.String getAttributesJSON ()`
- `java.lang.String getAttributesJSON (java.lang.String attribute)`
- `java.util.Map<java.lang.String,​java.lang.String> getAttributesMap (java.lang.String attribute)`
- `java.util.Locale[] getAvailableLocales ()`
- `Configuration getConfig ()`
- `java.util.Locale getDefaultLocale ()`
- `java.lang.String getDefaultLocaleName ()`
- `static java.lang.String getDefaultLocaleName ( Configuration systemConfig)`
- `java.lang.String getDefaultLocalizedValue (java.lang.String targetId, java.lang.String attribute)`
- `protected java.util.Comparator<java.util.Locale> getLocaleComparator ()`
- `java.util.List<java.util.Map<java.lang.String,​java.lang.String>> getLocaleList ()`
- `java.util.List<LocalizedAttribute> getLocalizedAttributes ()`
- `java.lang.String getLocalizedValue (java.lang.String targetId, java.lang.String attribute, java.util.Locale locale)`
- `java.lang.String getLocalizedValue (java.lang.String targetId, java.lang.String attribute, java.util.Locale locale, boolean sanitizeValue)`
- `java.lang.String getLocalizedValue (java.lang.String attribute, java.util.Locale locale)`
- `java.lang.String getLocalizedValue ( SailPointObject object, java.lang.String attribute, java.util.Locale locale)`
- `java.lang.String getTargetId ()`
- `java.util.Map<java.lang.String,​java.lang.String> getTransientAttributesMap (java.lang.String attribute)`
- `int importFile (org.primefaces.model.file.UploadedFile importFile, java.lang.String objectType, java.lang.String language, sailpoint.server.Importer.Monitor monitor)`
- `boolean isLocaleSupported (java.lang.String locale)`
- `static java.util.Locale localeStringToLocale (java.lang.String localeString)`
- `java.util.List<java.util.Map<java.lang.String,​java.lang.Object>> localeValueMapToLanguageList (java.util.Map<java.lang.String,java.lang.String> valuesByLocale, java.util.Locale userLocale)`
- `void setLocalizedAttributes (java.util.List< LocalizedAttribute > localizedAttributes)`
- `void setTargetId (java.lang.String targetId)`

---

## ManagedAttributer

**Package:** `sailpoint.api`

**Description:** The ManagedAttributer provides utility methods for searching, reading, and creating ManagedAttribute objects. It is also used by the Identitizer to promote attribute values from links into ManagedAttributes.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.ManagedAttributer`

**Attributes:**
- `static java.lang.String RET_CREATED`
- `static java.lang.String RET_CREATED_BY_APP`

**Methods:**
- `ManagedAttribute bootstrapIfNew ( ManagedAttribute src)`
- `static java.lang.String checkValidity ( ManagedAttribute att)`
- `static int count ( SailPointContext con, Application app, java.lang.String objectType)`
- `static int count ( SailPointContext con, Application app, java.lang.String name, java.lang.String value)`
- `static int count ( SailPointContext con, Application app, java.lang.String name, java.lang.String value, java.lang.String objectType)`
- `static int count ( SailPointContext con, ManagedAttribute src)`
- `staticManagedAttribute get ( SailPointContext con, java.lang.String appid, boolean permission, java.lang.String name, java.lang.String value)`
- `staticManagedAttribute get ( SailPointContext con, java.lang.String appid, boolean permission, java.lang.String name, java.lang.String value, java.lang.String objectType)`
- `staticManagedAttribute get ( SailPointContext con, java.lang.String appid, java.lang.String target)`
- `staticManagedAttribute get ( SailPointContext con, java.lang.String appid, java.lang.String name, java.lang.String value)`
- `staticManagedAttribute get ( SailPointContext con, Application app, boolean permission, java.lang.String name, java.lang.String value)`
- `staticManagedAttribute get ( SailPointContext con, Application app, boolean permission, java.lang.String name, java.lang.String value, java.lang.String objectType)`
- `staticManagedAttribute get ( SailPointContext con, Application app, java.lang.String name, java.lang.String value)`
- `staticManagedAttribute get ( SailPointContext con, Application app, java.lang.String groupAttribute, ResourceObject obj)`
- `staticManagedAttribute get ( SailPointContext con, ProvisioningPlan.ObjectRequest req)`
- `staticManagedAttribute get ( SailPointContext con, ProvisioningPlan.ObjectRequest req, Application app)`
- `static java.util.List<ManagedAttribute> getAll ( SailPointContext con, java.lang.String appid, boolean permission, java.lang.String name, java.lang.String value)`
- `static java.util.List<ManagedAttribute> getAll ( SailPointContext con, java.lang.String appid, boolean permission, java.lang.String name, java.lang.String value, java.lang.String objectType)`
- `static java.util.List<ManagedAttribute> getAll ( SailPointContext con, ManagedAttribute src)`
- `static java.lang.Object[] getAttr ( SailPointContext con, java.lang.String appid, boolean permission, java.lang.String name, java.lang.String value, java.util.List<java.lang.String> properties)`
- `staticManagedAttribute getByDisplayName ( SailPointContext con, Application app, java.lang.String name)`
- `java.util.Map<java.lang.String,​java.lang.Integer> getCreatedByApp ()`
- `static java.lang.String getDescription ( ManagedAttribute att)`
- `static java.lang.String getEntitlementHash ( Application app, java.lang.String attName, java.lang.String value)`
- `staticManagedAttribute getEntitlementOrObject ( SailPointContext context, java.lang.String uuid, Application app, java.lang.String groupAttribute, java.lang.String type)`
- `staticManagedAttribute getEntitlementOrObject ( SailPointContext ctx, Application app, java.lang.String groupAttribute, java.lang.String value, java.lang.String type)`
- `static java.lang.String getHash (java.lang.String appId, java.lang.String type, java.lang.String attribute, java.lang.String value)`
- `static java.lang.String getHash ( ManagedAttribute attr)`
- `static java.lang.String getObjectIdentity ( SailPointContext con, ProvisioningPlan.ObjectRequest req)`
- `static java.lang.String getObjectIdentity ( ProvisioningPlan.ObjectRequest req, Application app)`
- `static java.lang.String getObjectIdentity ( ProvisioningPlan.ObjectRequest req, Application app, Schema schema)`
- `static java.lang.String getPermissionHash ( Application app, java.lang.String target)`
- `static java.lang.String getReferenceAttribute ( ProvisioningPlan.ObjectRequest req, Application app)`
- `staticSchema getTargetSchema ( ProvisioningPlan.ObjectRequest req, Application app)`
- `int getTotalCreated ()`
- `static boolean isPermissionRequest ( ProvisioningPlan.ObjectRequest req)`
- `java.util.List<ManagedAttribute> promoteManagedAttributes ( Link link)`
- `java.util.List<ManagedAttribute> promoteManagedAttributes ( ManagedAttribute group)`
- `void restoreFromTaskResult ( TaskResult result)`

---

## Matchmaker.CubeMatcher

**Package:** `sailpoint.api`

**Description:** Extension of JavaMatcher used with Filter evaluation. Here the target object is expected to be an Identity and compound filter prefixes are recognized. If property has a prefix of this form: target:property then this must be a compound filter and the target identifies an Application. The target can either be an application name or a numeric index into the the application list of the CompoundFilter. Find the Link for that Application and go from there. If there is no prefix this must be an Identity property. After stripping the prefix a property can either be a simple property name or a path such as: manager.name application.owner.name All but the final token on the path are assumed to be Java bean properties that can be accessed by reflection. The values of these properties must be SailPointObject. The final token can either be a bean property or an extended attribute name. If there is no bean property with that name use the SailPointObject.getExtendedAttributes method to get the extended attribute map.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Filter.BaseFilterVisitor`
- `sailpoint.search.JavaMatcher`
- `sailpoint.api.Matchmaker.CubeMatcher`
- `Filter.FilterVisitor`
- `sailpoint.search.Matcher`

**Attributes:** N/A

**Methods:**
- `java.lang.Object getPropertyValue ( Filter.LeafFilter leaf, java.lang.Object o)`

---

## Matchmaker.ExpressionMatcher.TermMatcher

**Package:** `sailpoint.api`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Matchmaker.ExpressionMatcher.TermMatcher`
- `sailpoint.search.Matcher`

**Attributes:** N/A

**Methods:**
- `java.util.List<IdentitySelector.MatchTerm> getMatches ( Identity ident, Application defaultApp, SailPointContext ctx)`
- `boolean matches (java.lang.Object o)`

---

## Matchmaker.ExpressionMatcher

**Package:** `sailpoint.api`

**Description:** Return true if the identity matches this selector.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Matchmaker.ExpressionMatcher`
- `sailpoint.search.Matcher`

**Attributes:** N/A

**Methods:**
- `java.util.List<IdentitySelector.MatchTerm> getMatches ( Identity identity)`
- `boolean match ( Identity ident)`
- `boolean matches (java.lang.Object o)`

---

## Matchmaker

**Package:** `sailpoint.api`

**Description:** The evaluation engine for the IdentitySelector object.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Matchmaker`
- `IdentityMatcher`
- `IdentitySelector.MatchMonitor`

**Attributes:**
- `static java.lang.String ARG_APPLICATION_CACHE`
- `static java.lang.String ARG_ENTITLEMENT_SELECTORS`
- `static java.lang.String ARG_IDENTITY`
- `static java.lang.String ARG_ROLE_SELECTORS`
- `static java.lang.String PRAGMA_RELEVANT_APPS`

**Methods:**
- `java.util.List<Application> getLastMatchApplications ()`
- `void getLastMatchApplications (java.util.List<java.lang.String> names)`
- `java.util.List<IdentityItem> getLastMatchItems ()`
- `java.lang.Object getLastMatchValue ()`
- `boolean isMatch (@NotNull IdentitySelector selector, @NotNull Identity identity)`
- `void matchMonitorApplication ( Application app)`
- `void matchMonitorAttribute ( Link link, java.lang.String name, java.lang.Object value)`
- `void matchMonitorPermission ( Link link, Permission p, java.lang.Object value)`
- `void removeArgument (java.lang.String name)`
- `void setArgument (java.lang.String name, java.lang.Object value)`
- `void setArguments (java.util.Map<java.lang.String,java.lang.Object> args)`

---

## ObjectUtil

**Package:** `sailpoint.api`

**Description:** Utility class providing methods to load and analyze SailPointObject subclasses.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.ObjectUtil`

**Attributes:**
- `static int DEFAULT_LOCK_TIMEOUT`
- `static java.lang.String DEFAULT_NAME_DELIMITER`
- `static char ENCODING_DELIMITER`
- `static int MAX_IN_QUERY_SIZE`
- `static int MINIMUM_ENCODED_LENGTH`
- `static java.lang.String SECRET_DUMMY_VALUE`
- `static int VALID_ID_LEN`

**Methods:**
- `static <T extendsSailPointObject>void breakLock ( SailPointContext con, java.lang.Class<T> cls, java.lang.String id)`
- `static <T extendsSailPointObject>void breakLock ( SailPointContext con, T obj)`
- `staticFilter buildWorkgroupInclusiveIdentityFilter ()`
- `static void checkIllegalRename ( SailPointContext context, SailPointObject obj)`
- `static void checkIllegalRenameOrNewName ( SailPointContext context, SailPointObject obj)`
- `static java.lang.Object convertIdsToNames ( SailPointContext context, java.lang.Class<?> clazz, java.lang.Object value)`
- `static java.util.List<java.lang.String> convertToIds ( SailPointContext ctx, java.lang.Class clazz, java.util.List<java.lang.String> names)`
- `static java.util.List<java.lang.String> convertToNames ( SailPointContext ctx, java.lang.Class clazz, java.util.List<java.lang.String> idsOrNames)`
- `static int countDistinctAttributeValues ( SailPointContext ctx, java.lang.Class<? extends SailPointObject > clazz, QueryOptions qo, java.lang.String attrName)`
- `static int countLinkAttributeValues ( SailPointContext ctx, java.lang.String appName, java.lang.String attrName, java.lang.String prefix)`
- `static void deleteObject ( SailPointContext context, SailPointObject spObj)`
- `static <T> sailpoint.tools.Pair<java.lang.Boolean,​T> doWithCertLock ( SailPointContext context, Certification certification, java.util.concurrent.Callable<T> doWhat, boolean shouldUnlock, int lockTimeout)`
- `static void editObjectAttribute ( SailPointObject object, ObjectAttribute attr, java.lang.Object newValue, java.lang.String user)`
- `static void encryptIdentity ( Identity user, SailPointContext context)`
- `static void encryptLink ( Link link, SailPointContext context)`
- `protected static java.util.List<java.lang.String> encryptPasswordHistory (java.util.List<java.lang.String> oldList, SailPointContext context)`
- `static void encryptPasswordsInApplication ( Application application, SailPointContext context)`
- `static java.lang.String extractName (java.lang.String compoundName)`
- `static java.lang.String extractName (java.lang.String compoundName, java.lang.String delimiter)`
- `static java.lang.String generateUniqueName ( SailPointContext ctx, java.lang.String id, java.lang.String name, java.lang.Class clazz, int count)`
- `static java.lang.String getAccountId ( SailPointContext ctx, java.lang.String identityName, java.lang.String appName, java.lang.String instance, java.lang.String nativeIdentity)`
- `staticApplication getApplicationByAttribute (java.lang.String attrKey, java.lang.String attrValue, java.util.List<java.lang.String> appTypes, SailPointContext ctx)`
- `staticCertification getCertification ( SailPointContext context, CertificationLink link)`
- `staticCertificationArchive getCertificationArchive ( SailPointContext context, java.lang.String certId)`
- `staticIdentity getContextIdentity ( SailPointContext context)`
- `static java.util.List<java.lang.String> getEffectiveEmails ( SailPointContext ctx, Identity identity)`
- `static java.lang.Class getExtendedAttributeClass (java.lang.Class clazz, java.lang.String attributeName)`
- `staticFilter getFilter ( SailPointContext con, java.lang.Object something)`
- `static <T extendsSailPointObject>T getFirstObject ( SailPointContext context, java.lang.Class<T> cls, Filter filter)`
- `static java.lang.String getId ( SailPointContext ctx, java.lang.Class clazz, java.lang.String name)`
- `static java.util.List<Identity> getIdentitiesToNotifyFromEmail ( SailPointContext ctx, java.lang.String emailArg)`
- `static java.lang.String getIdentityFromLink ( SailPointContext ctx, Application app, java.lang.String instance, java.lang.String nativeId)`
- `staticIdentity getIdentityOrWorkgroup ( SailPointContext ctx, java.lang.String idOrName)`
- `static java.util.List<java.lang.String> getInvalidAttributes ( Attributes <java.lang.String,java.lang.Object> attributes, java.util.List< ObjectAttribute > validAttributeDefinitions, ObjectConfig config, java.util.Locale locale)`
- `static java.lang.String getLCMWorkflowName ( SailPointContext ctx, java.lang.String flowName)`
- `static java.util.List<java.lang.Object> getLinkAttributeValues ( SailPointContext ctx, java.lang.String appName, java.lang.String attrName, java.lang.String prefix, int start, int limit)`
- `static java.util.List<java.lang.Object> getLinkPermissionRights ( SailPointContext ctx, java.util.Locale locale, java.lang.String appName, java.lang.String targetName, java.lang.String prefix, int start, int limit)`
- `staticApplication getLocalApplication ( Connector conn)`
- `static java.lang.Class getMajorClass (java.lang.String className)`
- `static java.lang.String getName ( SailPointContext ctx, java.lang.Class clazz, java.lang.String id)`
- `staticNamedTimestamp getNamedTimestamp ( SailPointContext ctx, java.lang.String namedTimestampName)`
- `static <T extendsSailPointObject>T getObject ( SailPointContext context, java.lang.Class<T> cls, java.lang.Object something)`
- `static <T extendsSailPointObject>T getObject ( SailPointContext context, java.lang.Class<T> cls, java.lang.Object something, boolean trustRuleReturns, boolean throwExceptions)`
- `staticSailPointObject getObject ( SailPointContext con, java.lang.String className, java.lang.String id)`
- `static java.lang.Object getObjectAttributeValue ( SailPointObject object, ObjectAttribute attr)`
- `static <T extendsSailPointObject>java.util.List<java.lang.String> getObjectIds (java.util.List<T> objects)`
- `static java.util.List<java.lang.String> getObjectIds ( SailPointContext con, java.lang.Class clazz, QueryOptions ops)`
- `static <T extendsSailPointObject>java.util.List<java.lang.String> getObjectNames (java.util.List<T> objects)`
- `static <T extendsSailPointObject>java.util.List<java.lang.String> getObjectNames (java.util.Set<T> objects)`
- `static <T extendsSailPointObject>java.util.List<T> getObjects ( SailPointContext context, java.lang.Class<T> cls, java.lang.Object something)`
- `static <T extendsSailPointObject>java.util.List<T> getObjects ( SailPointContext context, java.lang.Class<T> cls, java.lang.Object something, boolean trustRuleReturns)`
- `static <T extendsSailPointObject>java.util.List<T> getObjects ( SailPointContext context, java.lang.Class<T> cls, java.lang.Object something, boolean trustRuleReturns, boolean throwExceptions)`
- `static <T extendsSailPointObject>java.util.List<T> getObjects ( SailPointContext context, java.lang.Class<T> cls, java.lang.Object something, boolean trustRuleReturns, boolean throwExceptions, boolean convertCSVToList)`
- `static <T extendsSailPointObject>java.util.List<T> getObjects ( SailPointContext context, java.lang.Class<T> cls, java.lang.Object something, boolean trustRuleReturns, boolean throwExceptions, boolean convertCSVToList, java.util.List<java.lang.String> notFoundNames)`
- `static <T extendsSailPointObject>java.util.List<T> getObjects ( SailPointContext context, java.lang.Class<T> cls, java.lang.Object something, boolean trustRuleReturns, boolean throwExceptions, java.util.List<java.lang.String> notFoundNames)`
- `static java.util.Map<java.lang.String,​? extendsSailPointObject> getObjectsMappedById (java.util.Collection<? extends SailPointObject > objectsToMap)`
- `staticIdentity getOriginator ( SailPointContext context, java.lang.String launcher)`
- `staticIdentity getOriginator ( SailPointContext context, java.lang.String launcher, Attributes <java.lang.String,java.lang.Object> arguments)`
- `staticIdentity getOriginator ( SailPointContext context, java.lang.String launcher, Attributes <java.lang.String,java.lang.Object> arguments, TaskResult result)`
- `staticFilter getOwnerFilterForIdentity ( Identity identity)`
- `staticFilter getOwnerNameArchiveFilterForIdentity ( Identity identity)`
- `static java.util.List<Filter> getPartitionedInFilters (java.lang.String propertyName, java.util.List<java.lang.String> values)`
- `static java.util.List<Filter> getPartitionedInFilters (java.lang.String propertyName, java.util.List<java.lang.String> values, int partitionSize)`
- `staticAttributeDefinition.UserInterfaceInputType getPermissionRemediationInputType ( SailPointContext ctx, java.lang.String appName, java.lang.String schemaName)`
- `static java.util.List<PolicyViolation> getPolicyViolations ( SailPointContext context, Identity identity)`
- `staticIdentitySnapshot getRecentSnapshot ( SailPointContext context, Identity identity)`
- `static java.lang.Object[] getRecentSnapshotInfo ( SailPointContext context, Identity identity)`
- `staticAttributeDefinition.UserInterfaceInputType getRemediationInputType ( SailPointContext ctx, java.lang.String appName, java.lang.String schemaName, java.lang.String attrName)`
- `static java.util.List<Rule> getRules ( SailPointContext context, java.lang.Object something)`
- `static java.lang.Class getSailPointClass (java.lang.String className)`
- `static java.util.List<IdentitySnapshot> getSnapshots ( SailPointContext context, Identity identity)`
- `static <T extendsSailPointObject>java.lang.String getStringPropertyFromObject ( Filter filter, java.lang.String returnProperty, SailPointContext context, java.lang.Class<T> clazz)`
- `static java.util.List<java.lang.String> getStrings (java.util.List objects)`
- `staticAdaptiveCardNotificationTemplate getSysConfigAdaptiveCardNotificationTemplate ( SailPointContext ctx, java.lang.String key)`
- `staticEmailTemplate getSysConfigEmailTemplate ( SailPointContext ctx, java.lang.String key)`
- `staticPermission getTargetPermission ( SailPointContext context, Link link, java.lang.String target)`
- `static java.util.List<Permission> getTargetPermissions ( SailPointContext context, Link link)`
- `static java.util.List<Permission> getTargetPermissions ( SailPointContext context, Link link, java.lang.String target)`
- `static java.util.List<Permission> getTargetPermissions ( SailPointContext context, Link link, java.lang.String target, Filter targetAssociationFilter)`
- `static java.lang.String getTempDir ( SailPointContext ctx)`
- `static java.util.List<Identity> getTrustedIdentities ( SailPointContext context, java.lang.Object something)`
- `static java.util.Iterator<java.lang.Object[]> getWorkgroupMembers ( SailPointContext ctx, Identity identity, java.util.List<java.lang.String> props)`
- `static boolean hasName (java.lang.Class<? extends SailPointObject > clazz)`
- `static boolean hasName ( SailPointContext context, java.lang.Class<? extends SailPointObject > clazz)`
- `static boolean hasTargetPermissions ( SailPointContext context, Link link, java.lang.String target)`
- `static boolean isEncoded (java.lang.String src)`
- `static boolean isIdentifiedBy ( SailPointObject obj, java.lang.String id)`
- `static boolean isIllegalRename ( SailPointContext context, SailPointObject obj)`
- `static boolean isInitialized (java.lang.Object object)`
- `static boolean isLocked ( SailPointContext con, java.lang.Class<? extends SailPointObject > cls, java.lang.String name)`
- `static boolean isLockedById ( SailPointContext con, java.lang.Class<? extends SailPointObject > cls, java.lang.String id)`
- `static boolean isPermissionRemediationModifiable ( SailPointContext ctx, java.lang.String appName, java.lang.String schemaName)`
- `static boolean isRemediationModifiable ( SailPointContext ctx, java.lang.String appName, java.lang.String schemaName, java.lang.String attrName)`
- `static boolean isReservedAttributeName ( SailPointContext context, java.lang.Class<? extends SailPointObject > clazz, java.lang.String attributeName)`
- `static boolean isSecret (java.lang.String name)`
- `static boolean isSecret ( IdentityRequestItem item)`
- `static boolean isSimple ( CorrelationConfig corrConfig)`
- `static boolean isUniqueId (java.lang.String id)`
- `static boolean isValidHexDigit (char ch)`
- `static boolean isValidId (java.lang.String id)`
- `static void iterateAndAddDummyPassword (java.util.Map<java.lang.String,java.lang.Object> attributes)`
- `staticCertification lockCert ( SailPointContext context, Certification certification, int lockTimeout)`
- `staticCertification lockCertificationById ( SailPointContext context, java.lang.String id, int lockTimeout)`
- `staticIdentity lockIdentity ( SailPointContext con, java.lang.String identifier)`
- `staticIdentity lockIdentity ( SailPointContext con, java.lang.String identifier, int timeout)`
- `staticIdentity lockIdentity ( SailPointContext con, Identity src)`
- `staticIdentity lockIdentityById ( SailPointContext ctx, java.lang.String id)`
- `staticIdentity lockIdentityById ( SailPointContext ctx, java.lang.String id, int timeout)`
- `staticIdentity lockIdentityByName ( SailPointContext ctx, java.lang.String name)`
- `staticIdentity lockIdentityByName ( SailPointContext ctx, java.lang.String name, int timeout)`
- `staticIdentity lockIfNecessary ( SailPointContext con, java.lang.String idOrName)`
- `staticNamedTimestamp lockNamedTimestamp ( SailPointContext ctx, NamedTimestamp namedTimestamp, java.lang.String lockName)`
- `staticNamedTimestamp lockNamedTimestamp ( SailPointContext ctx, NamedTimestamp namedTimestamp, java.lang.String lockName, int timeout)`
- `static <T extendsSailPointObject>T lockObject ( SailPointContext con, java.lang.Class<T> cls, java.lang.String id, java.lang.String name, java.lang.String lockMode)`
- `static <T extendsSailPointObject>T lockObject ( SailPointContext con, java.lang.Class<T> cls, java.lang.String id, java.lang.String name, java.lang.String lockMode, int lockTimeout)`
- `static <T extendsSailPointObject>T lockObject ( SailPointContext con, java.lang.Class<T> cls, PersistenceManager.LockParameters params)`
- `staticRule lookupRule ( SailPointContext context, java.lang.String abstractName)`
- `static java.util.List<Permission> mergePermissions (java.util.List< Permission > currentPerms, java.util.List< Permission > newPerms)`
- `static boolean objectExistsById ( SailPointContext context, java.lang.Class<? extends SailPointObject > clazz, java.lang.String id)`
- `static java.util.List<java.util.Map<java.lang.String,​java.lang.Object>> objectsToMap (java.util.List<? extends java.lang.Object> objects, java.util.List<java.lang.String> properties)`
- `static java.util.Map<java.lang.String,​java.lang.Object> objectToMap (java.lang.Object object, java.util.List<java.lang.String> properties)`
- `static java.lang.Object objectToPropertyValue (java.lang.Object object, java.lang.String property)`
- `static <T extendsSailPointObject>T reattach ( SailPointContext ctx, T o)`
- `static <T extendsSailPointObject>T reattachWithPrejudice ( SailPointContext ctx, java.lang.Class<T> objClass, T o)`
- `staticSailPointObject recache ( SailPointContext con, SailPointObject src)`
- `staticSailPointObject recache ( SailPointContext con, SailPointObject src, boolean doAttach)`
- `static <T extendsSailPointObject>T relockObject ( SailPointContext con, java.lang.Class<T> cls, T object, java.lang.String lockMode, int lockTimeout)`
- `static <T extendsSailPointObject>int removeObjects ( SailPointContext context, java.lang.Class<T> cls, QueryOptions ops)`
- `static <T extendsSailPointObject>void saveDecacheAttach ( SailPointContext ctx, T object)`
- `static void scrubPasswords ( ApprovalSet approvalSet)`
- `static void scrubPasswords ( Attributes <java.lang.String,java.lang.Object> attrs)`
- `static void scrubPasswords ( ProvisioningPlan plan)`
- `static void scrubPasswords ( ProvisioningPlan.AttributeRequest attributeRequest)`
- `static void scrubPasswords ( ProvisioningProject project)`
- `static void scrubPasswords ( WorkItem workitem)`
- `staticApprovalSet scrubPasswordsAndClone ( ApprovalSet approvalSet)`
- `static sailpoint.api.SearchResultsIterator searchAcrossIds ( SailPointContext context, java.lang.Class clazz, java.util.List<java.lang.String> ids, java.util.List< Filter > otherFilters, java.util.List<java.lang.String> properties)`
- `static sailpoint.api.SearchResultsIterator searchAcrossIds ( SailPointContext context, java.lang.Class clazz, java.util.List<java.lang.String> ids, java.util.List< Filter > otherFilters, java.util.List<java.lang.String> properties, java.lang.String idPropertyName)`
- `static sailpoint.api.SearchResultsIterator searchAcrossIds ( SailPointContext context, java.lang.Class clazz, java.util.List<java.lang.String> ids, java.util.List< Filter > otherFilters, java.util.List<java.lang.String> properties, java.lang.String idPropertyName, boolean isDistinct)`
- `static void setTargetPermission ( SailPointContext context, Link link, Permission perm)`
- `static <T extendsSailPointObject>void sortByName (java.util.List<T> objects)`
- `static <T extendsSailPointObject>T transactionLock ( SailPointContext con, java.lang.Class<T> cls, java.lang.String identifier)`
- `static <T extendsSailPointObject>T transactionLockById ( SailPointContext con, java.lang.Class<T> cls, java.lang.String identifier)`
- `static <T extendsSailPointObject>T transactionLockByName ( SailPointContext con, java.lang.Class<T> cls, java.lang.String identifier)`
- `static void unlockAndUpdateNamedTimestamp ( SailPointContext ctx, NamedTimestamp namedTimestamp)`
- `static void unlockAndUpdateNamedTimestamp ( SailPointContext ctx, NamedTimestamp namedTimestamp, java.util.Date timestamp)`
- `static void unlockCert ( SailPointContext context, Certification certification)`
- `static void unlockCert ( SailPointContext context, Certification certification, boolean setImmutable)`
- `static void unlockIdentity ( SailPointContext con, Identity id)`
- `static void unlockIfNecessary ( SailPointContext con, Identity ident)`
- `static void unlockObject ( SailPointContext con, SailPointObject object, java.lang.String lockMode)`
- `static void updateApplicationConfig ( SailPointContext spContext, Application app)`
- `static void updateApplicationConfig ( SailPointContext spContext, Application app, boolean isCG)`
- `static void updateUnSavedApplicationConfig ( Application app)`
- `static void validateDependencies ( Application app)`

---

## PasswordGenerator

**Package:** `sailpoint.api`

**Description:** Generate a password based on policies.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.PasswordGenerator`

**Attributes:** N/A

**Methods:**
- `java.lang.String generateDefaultPassword ()`
- `java.lang.String generatePassword ()`
- `java.lang.String generatePassword ( Identity identity, Application app)`
- `java.lang.String generatePassword ( Link link)`
- `java.lang.String generatePassword ( PasswordPolicy policy)`

---

## PasswordPolice.Expiry

**Package:** `sailpoint.api`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `PasswordPolice.Expiry`
- `sailpoint.api.PasswordPolice.Expiry`
- `java.io.Serializable`
- `java.lang.Comparable<PasswordPolice.Expiry>`

**Attributes:** N/A

**Methods:**
- `staticPasswordPolice.Expiry valueOf (java.lang.String name)`
- `staticPasswordPolice.Expiry[] values ()`

---

## PasswordPolice

**Package:** `sailpoint.api`

**Description:** Value we always return for the password and password confirmation properties to prevent the actual password from appearing on the wire.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.PasswordPolice`

**Attributes:**
- `static java.lang.String EXPIRATION_DAYS`
- `static java.lang.String FAKE_PASSWORD`
- `static java.lang.String PASSWORD_CHANGE_MIN_DURATION`
- `static java.lang.String RESET_EXPIRATION_DAYS`

**Methods:**
- `void addPasswordHistory ( Identity identity, java.lang.String password)`
- `void addPasswordHistory ( Link link, java.lang.String password)`
- `static void auditExpiredPasswordChange ( Identity ident)`
- `static void auditPasswordChangefailure ( Identity identity, java.util.List< Message > errors)`
- `void checkCurrentPassword ( Identity identity, java.lang.String currentPassword)`
- `void checkExpiration ( Identity identity)`
- `void checkPassword ( Application app, Identity identity, java.lang.String password)`
- `void checkPassword ( Identity identity, java.lang.String password, boolean isSystemAdmin)`
- `void checkPassword ( Identity identity, PasswordPolicy passwordPolicy, java.lang.String password, java.lang.String passwordHistory)`
- `void checkPassword ( Identity identity, PasswordPolicy passwordPolicy, java.lang.String password, java.lang.String passwordHistory, java.util.List< Link > links)`
- `void checkPassword ( Link link, java.lang.String password)`
- `void checkPasswordWithHistory ( Link link, java.lang.String password, boolean ignoreHistory)`
- `java.util.List<java.lang.String> findInvalidHashingPolicies ()`
- `PasswordPolicy getEffectivePolicy ( Application app, Identity identity)`
- `PasswordPolicy getEffectivePolicy ( Link link)`
- `java.util.List<java.lang.String> getIIQPasswordConstraints ()`
- `java.util.List<java.lang.String> getIIQPasswordConstraints (java.util.Locale locale, java.util.TimeZone timeZone)`
- `java.util.List<java.lang.String> getIIQPasswordConstraints (java.util.Locale locale, java.util.TimeZone timeZone, boolean showNoConstraintMessage)`
- `void setConstraints (java.util.Map<java.lang.String,java.lang.Object> policy)`
- `void setPassword (java.lang.String pass)`
- `void setPassword ( Identity ident, java.lang.String password, java.lang.String currentPassword, PasswordPolice.Expiry expires, boolean isSystemAdmin)`
- `void setPassword ( Identity ident, java.lang.String password, java.lang.String currentPassword, PasswordPolice.Expiry expires, boolean isSystemAdmin, boolean isPasswordAdmin)`
- `void setPassword ( Identity ident, java.lang.String password, PasswordPolice.Expiry expires, boolean isSystemAdmin)`
- `void setPassword ( Identity ident, java.lang.String password, PasswordPolice.Expiry expires, boolean isSystemAdmin, boolean isPasswordAdmin)`
- `void setPasswordExpiration ( Identity identity, PasswordPolice.Expiry expires)`
- `void setPasswordNoCheck ( Identity ident, java.lang.String password, PasswordPolice.Expiry expires, boolean isPasswordAdmin)`
- `void validate ()`
- `void validatePasswordFields (java.lang.String password, java.lang.String confirmation, boolean requireCurrentPassword, java.lang.String currentPassword)`
- `boolean validatePasswordPolicy ( Configuration config, sailpoint.api.MessageAccumulator msgs)`

---

## PersistenceManager.LockParameters

**Package:** `sailpoint.api`

**Description:** Encapsulation of lock parameters.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.PersistenceManager.LockParameters`

**Attributes:** N/A

**Methods:**
- `staticPersistenceManager.LockParameters createById (java.lang.String id, java.lang.String lockType)`
- `staticPersistenceManager.LockParameters createByName (java.lang.String name, java.lang.String lockType)`
- `java.lang.String getColumn ()`
- `int getLockDuration ()`
- `int getLockTimeout ()`
- `java.lang.String getLockType ()`
- `java.lang.String getValue ()`
- `boolean isTransactionLock ()`
- `void setColumn (java.lang.String val)`
- `void setId (java.lang.String id)`
- `void setLockDuration (int val)`
- `void setLockTimeout (int val)`
- `void setLockType (java.lang.String val)`
- `void setName (java.lang.String name)`
- `void setValue (java.lang.String val)`

---

## PersistenceManager

**Package:** `sailpoint.api`

**Description:** Interface implemented by classes that provide persistence services.

**Inherited Classes/Interfaces:**
- `Resolver`

**Attributes:**
- `static java.lang.String LOCK_TYPE`
- `static java.lang.String LOCK_TYPE_PERSISTENT`
- `static java.lang.String LOCK_TYPE_TRANSACTION`

**Methods:**
- `void attach ( SailPointObject object)`
- `void clearHighLevelCache ()`
- `java.lang.Object clone ()`
- `void close ()`
- `void commitTransaction ()`
- `int countObjects (java.lang.Class cls, QueryOptions options)`
- `void decache ()`
- `void decache ( SailPointObject obj)`
- `void enableStatistics (boolean b)`
- `<T extendsSailPointObject>T getObject (java.lang.Class<T> cls, QueryOptions queryOptions)`
- `<T extendsSailPointObject>T getObjectById (java.lang.Class<T> cls, java.lang.String id)`
- `<T extendsSailPointObject>T getObjectByName (java.lang.Class<T> cls, java.lang.String name)`
- `<T extendsSailPointObject>java.util.List<T> getObjects (java.lang.Class<T> cls)`
- `<T extendsSailPointObject>java.util.List<T> getObjects (java.lang.Class<T> cls, QueryOptions ops)`
- `PersistenceOptions getPersistenceOptions ()`
- `<T extendsSailPointObject>T getUniqueObject (java.lang.Class<T> cls, Filter f)`
- `<T extendsSailPointObject>T getUniqueObject (T example)`
- `void importObject ( SailPointObject obj)`
- `<T extendsSailPointObject>T lockObject (java.lang.Class<T> clazz, PersistenceManager.LockParameters params)`
- `<T extendsSailPointObject>T lockObjectById (java.lang.Class<T> cls, java.lang.String id, java.util.Map<java.lang.String,java.lang.Object> options)`
- `<T extendsSailPointObject>T lockObjectByName (java.lang.Class<T> cls, java.lang.String name, java.util.Map<java.lang.String,java.lang.Object> options)`
- `void printStatistics ()`
- `void reconnect ()`
- `void removeObject ( SailPointObject obj)`
- `<T extendsSailPointObject>void removeObjects (java.lang.Class<T> cls, QueryOptions ops)`
- `void rollbackTransaction ()`
- `void saveObject ( SailPointObject obj)`
- `default void saveObject ( SailPointObject obj, SaveObjectOptions options)`
- `<T extendsSailPointObject>java.util.Iterator<T> search (java.lang.Class<T> cls, QueryOptions options)`
- `<T extendsSailPointObject>java.util.Iterator<java.lang.Object[]> search (java.lang.Class<T> cls, QueryOptions options, java.lang.String properties)`
- `<T extendsSailPointObject>java.util.Iterator<java.lang.Object[]> search (java.lang.Class<T> cls, QueryOptions options, java.util.List<java.lang.String> properties)`
- `java.util.Iterator search (java.lang.String query, java.util.Map<java.lang.String,java.lang.Object> args, QueryOptions ops)`
- `void setPersistenceOptions ( PersistenceOptions ops)`
- `void startTransaction ()`
- `<T extendsSailPointObject>void unlockObject (T object)`
- `int update (java.lang.String query, java.util.Map<java.lang.String,java.lang.Object> args)`

---

## PolicyUtil.ApplicationSummary

**Package:** `sailpoint.api`

**Description:** Model for entitlements on a specific application account. While the attribute/permission models are similar, it is nice to render them in slightly different ways so keep them on different lists.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.PolicyUtil.ApplicationSummary`

**Attributes:**
- `java.util.List<PolicyUtil.ItemSummary> attributes`
- `java.lang.String name`
- `java.util.List<PolicyUtil.ItemSummary> permissions`

**Methods:**
- `void assimilate (boolean permission, java.lang.String name, java.lang.Object value)`
- `void assimilate (java.util.List< PolicyUtil.ItemSummary > items, boolean permission, java.lang.String name, java.lang.Object value)`
- `PolicyUtil.ItemSummary getItem (java.util.List< PolicyUtil.ItemSummary > items, java.lang.String name)`

---

## PolicyUtil.EntitlementSummary

**Package:** `sailpoint.api`

**Description:** Model for representing entitlements related to SOD violations. This is returned by summarizeViolationEntitlements and is intended to be easy to use from Beanshell rules. Keep lists non-null and use .length regularly in the JSf pages. Use the same model to convey information about both Role SOD violations and Entitlement SOD violations. In practice there will only be one RoleSummary on each list because we always OR the roles in the SOD constraint sides, even though the model supports ANDing. So the first one that correlates becomes the one for the violation. For Entitlement SOD there is one RoleSummary on each list but the role name will be null to indicate they are "free" entitlements. The rendering rule needs to check this to avoid omitting a Role: label.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.PolicyUtil.EntitlementSummary`

**Attributes:**
- `java.util.List<PolicyUtil.RoleSummary> left`
- `java.util.List<PolicyUtil.RoleSummary> right`

**Methods:**
- `void assimilate (boolean bleft, java.lang.String appname, boolean permission, java.lang.String name, java.lang.Object value)`
- `PolicyUtil.RoleSummary getRoleSummary (boolean bleft, java.lang.String name)`

---

## PolicyUtil.ItemSummary

**Package:** `sailpoint.api`

**Description:** Model for one entitlement in an application. Values will be unique.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.PolicyUtil.ItemSummary`

**Attributes:**
- `java.lang.String name`
- `java.util.List<java.lang.String> values`

**Methods:**
- `void assimilate (java.lang.Object value)`
- `java.lang.String getCsv ()`

---

## PolicyUtil.RoleSummary

**Package:** `sailpoint.api`

**Description:** Represents a collection of application-specific entitlements, either "free" (the name is null) or associated with a role. We provide construction utilities to collapse entitlements for the same application, attributes, and permission into the same summary objects to reduce clutter in the UI.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.PolicyUtil.RoleSummary`

**Attributes:**
- `java.util.List<PolicyUtil.ApplicationSummary> applications`
- `java.lang.String name`

**Methods:**
- `void assimilate (java.lang.String appname, boolean permission, java.lang.String name, java.lang.Object value)`

---

## PolicyUtil

**Package:** `sailpoint.api`

**Description:** Utilities for analyzing policies and policy violations.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.PolicyUtil`

**Attributes:**
- `static java.lang.String ATT_APPLICATION`
- `static java.lang.String ATT_NAME`
- `static java.lang.String ATT_PERMISSION`
- `static java.lang.String ATT_VALUE`
- `static java.lang.String PRAGMA_SOD`
- `static java.lang.String PRAGMA_SOD_LEFT`
- `static java.lang.String PRAGMA_SOD_RIGHT`

**Methods:**
- `static java.util.List<IdentityItem.Path> getRolePath ( Bundle src, Bundle target)`
- `static java.util.Map<java.lang.String,​java.lang.String> parsePragma (java.lang.String pragma)`
- `staticPolicyUtil.EntitlementSummary summarizeViolationEntitlements ( SailPointContext context, Identity identity, PolicyViolation pv, EntitlementCorrelator correlator)`

---

## Provisioner

**Package:** `sailpoint.api`

**Description:** Utility class to process ProvisioningProjects and ProvisioningPlans.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Provisioner`

**Attributes:**
- `static java.lang.String ARG_DETECTED_ROLE_RECONCILIATION`
- `static java.lang.String ARG_FULL_RECONCILIATION`
- `static java.lang.String[] ARG_NAMES`
- `static java.lang.String ARG_OPTIMIZE_RECONCILIATION`
- `static java.lang.String ARG_PROVISION_ROLES_IF_CHANGED`
- `static java.lang.String ARG_RESET_PERMITTED_ROLES`
- `static java.lang.String RET_ASSIGNMENTS_RECONCILED`

**Methods:**
- `ProvisioningProject compile ( Identity identity, ProvisioningPlan masterPlan, boolean forceAll)`
- `ProvisioningProject compile ( ProvisioningPlan masterPlan)`
- `ProvisioningProject compile ( ProvisioningPlan masterPlan, Attributes <java.lang.String,java.lang.Object> scriptArgs)`
- `ProvisioningProject compileOld ( Identity identity, ProvisioningPlan masterPlan, boolean forceAll)`
- `void execute ()`
- `void execute ( ProvisioningPlan masterPlan)`
- `void execute ( ProvisioningPlan masterPlan, Attributes <java.lang.String,java.lang.Object> scriptArgs)`
- `void execute ( ProvisioningProject project)`
- `ProvisioningPlan getItemizedPlan (java.lang.String key)`
- `java.util.Map<java.lang.String,​ProvisioningPlan> getItemizedPlans ()`
- `ProvisioningProject getProject ()`
- `IntegrationConfig getResourceManager ( ProvisioningPlan.AccountRequest req)`
- `ProvisioningPlan getUnmanagedPlan ()`
- `ProvisioningPlan getUnmanagedPlan (java.lang.String trackingId)`
- `Identity impactAnalysis ( Identity ident)`
- `Identity impactAnalysis ( Identity ident, ProvisioningPlan plan)`
- `Identity impactAnalysis ( Identity ident, ProvisioningProject project)`
- `static boolean isArgument (java.lang.String name)`
- `java.util.Map<java.lang.String,​ProvisioningPlan> itemize (boolean simplifyItems)`
- `void prepare ()`
- `void processWithoutFiltering ( Identity identity, ProvisioningPlan masterPlan)`
- `void processWithoutFiltering ( ProvisioningPlan masterPlan)`
- `ProvisioningProject recompile ( ProvisioningProject project, Attributes <java.lang.String,java.lang.Object> scriptArgs)`
- `ProvisioningProject reconcile ( Identity ident, Attributes <java.lang.String,java.lang.Object> scriptArgs)`
- `ProvisioningProject reconcileAutoAssignments ( Identity ident, java.util.List< RoleAssignment > newAssignments, Attributes <java.lang.String,java.lang.Object> scriptArgs)`
- `ProvisioningProject reconcileManualAssignments ( Identity ident, java.util.List< Bundle > newRoles, Attributes <java.lang.String,java.lang.Object> scriptArgs)`
- `ProvisioningProject reconcileUnitTestRoles ( Identity ident, java.util.List< Bundle > roles, Attributes <java.lang.String,java.lang.Object> scriptArgs)`
- `void saveResults ( TaskResult result)`
- `void setArgument (java.lang.String name, java.lang.Object o)`
- `void setAssigner (java.lang.String s)`
- `void setDetectedRoleReconciliation (boolean b)`
- `void setDoRefresh (boolean b)`
- `void setLocalUpdate (boolean b)`
- `void setNativeChange (boolean b)`
- `void setNoCreateTemplates (boolean b)`
- `void setNoInheritedRoleDeprovisioning (boolean b)`
- `void setNoLinkUpdate (boolean b)`
- `void setNoLocking (boolean b)`
- `void setNoRoleExpansion (boolean b)`
- `void setOptimisticProvisioning (boolean b)`
- `void setPreserveDetectedRoles (boolean b)`
- `void setRefreshOptions (java.util.Map options)`
- `void setRequester (java.lang.String s)`
- `void setSource (java.lang.String s)`
- `void setSource ( Source s)`
- `void setTransactionLock (boolean b)`
- `void setTriggerSnapshots (boolean b)`
- `void simplify ()`

---

## RequestManager

**Package:** `sailpoint.api`

**Description:** A class providing an API for managing the request processor and submitting asynchronous requests.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.RequestManager`

**Attributes:** N/A

**Methods:**
- `static void addRequest ( SailPointContext context, Request request)`
- `void addRequest ( Request request)`
- `static void addRequestNoCommit ( SailPointContext context, Request request)`
- `void addRequestNoCommit ( Request request)`
- `sailpoint.request.RequestProcessor getRequestProcessor ()`
- `boolean pingProcessor ()`
- `void resetRequests (java.lang.String host)`
- `void resetRequests (java.util.Set<java.lang.String> requestIds)`
- `void restart ( TaskResult res)`
- `static void scheduleRequest ( SailPointContext context, RequestDefinition def, java.util.Map<java.lang.String,java.lang.Object> arguments, java.lang.String name, java.util.Date when, Identity owner)`
- `void scheduleRequest ( RequestDefinition def, java.util.Map<java.lang.String,java.lang.Object> arguments, java.lang.String name, java.util.Date when, Identity owner)`
- `static void scheduleWorkflow ( SailPointContext context, Workflow wf, java.lang.String caseName, java.util.Map<java.lang.String,java.lang.Object> arguments, java.util.Date when, Identity owner)`
- `void scheduleWorkflow ( Workflow wf, java.lang.String caseName, java.util.Map<java.lang.String,java.lang.Object> arguments, java.util.Date when, Identity owner)`
- `void startProcessor ()`
- `void suspendProcessor ()`
- `void terminate ( Request req)`
- `void terminatePartitionedTask ( TaskResult res)`
- `void terminatePartitionThreads ( TaskResult res)`
- `void wakeProcessor ()`

---

## RoleChangeAnalyzer

**Package:** `sailpoint.api`

**Description:** RoleChangeAnalyzer is a utility class to calculate provisioning items before and after changes done to a role. This class is influenced from the RoleDifferencer class authored by Jeff. To avoid any modifications on the RoleDifferencer class which has been implemented for a specific customer resulting a different behaviour, the RoleChangeAnalyzer class is introduced. RoleDifferencer used to calculate list of identity items for the modified role and the list of identity items for the unmodified role. These lists were used to calculate removals and were local variables in the calculateRemovals method. In order to support calculateAdditions and to avoid recalculating the list of identity items, the before and after lists are made as members of the RoleChangeAnalyzer class and gets populated once within the calculateBeforeAfterChanges() method which populates the beforeList and afterList only once during a call to either calculateRemovals or calculateAdditions. Besides, the buildDeProvisioningPlan() method is modified to buildPlan() as the buildDeProvisioningPlan() method does was hardcoded to only create remove provisioning plans. buildPlan() accepts an operation as the parameter and which accepts operation as one of the parameter and can be invoked by calculateRemovals and calculateAdditions to build a provisioning plan depending upon the operation in concern. Author: Alevi

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.RoleChangeAnalyzer`

**Attributes:** N/A

**Methods:**
- `java.util.List<RoleChangeEvent> calculateRoleChanges ( Bundle role)`

---

## SailPointContext

**Package:** `sailpoint.api`

**Description:** The primary API for accessing the persistent store and performing core system operations.

**Inherited Classes/Interfaces:**
- `PersistenceManager`
- `Resolver`
- `RuleRunner`
- `sailpoint.tools.xml.XMLReferenceResolver`

**Attributes:** N/A

**Methods:**
- `Identity authenticate (java.lang.String accountId, java.lang.String password)`
- `Identity authenticate (java.lang.String accountId, java.util.Map<java.lang.String,java.lang.Object> options)`
- `java.lang.String decrypt (java.lang.String src)`
- `java.lang.String encrypt (java.lang.String src)`
- `java.lang.String encrypt (java.lang.String src, boolean checkForEncrypted)`
- `Configuration getConfiguration ()`
- `java.sql.Connection getConnection ()`
- `SailPointContext getContext ()`
- `default sailpoint.api.DatabaseInstance getDatabaseInstance ()`
- `java.sql.Connection getJdbcConnection ()`
- `java.lang.Object getProperty (java.lang.String name)`
- `boolean getScopeResults ()`
- `java.lang.String getUserName ()`
- `void impersonate ( Identity identity)`
- `boolean isClosed ()`
- `void prepare ()`
- `void sendEmailNotification ( EmailTemplate template, EmailOptions options)`
- `void setProperty (java.lang.String name, java.lang.Object value)`
- `void setScopeResults (boolean scopeResults)`
- `void setUserName (java.lang.String name)`

---

## SailPointFactory

**Package:** `sailpoint.api`

**Description:** Factory service for SailPointContexts. The SailPointContext is the primary API that most of the system code should use to access core services like the persistent store, the task scheduler, and the email notifier. A SailPointContext must be obtained by calling this factory which knows how to create them from a prototype instances injected by Spring. Once created, contexts are placed in thread local storage so they can be accessed from any level of the code, though the convention we usually follow is to pass a context to the constructor of a business logic class which then uses it internally, and passes it along to any classes it might create.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.SailPointFactory`

**Attributes:** N/A

**Methods:**
- `staticSailPointContext createContext ()`
- `staticSailPointContext createContext (java.lang.Class<? extends SailPointObject > scope)`
- `staticSailPointContext createContext (java.lang.String user)`
- `staticSailPointContext createContext (sailpoint.api.DatabaseInstance databaseInstance)`
- `staticSailPointContext createContext (sailpoint.api.DatabaseInstance databaseInstance, java.lang.String user)`
- `staticSailPointContext createPrivateContext ()`
- `staticSailPointContext createPrivateContext (java.lang.Class<? extends SailPointObject > scope)`
- `staticSailPointContext createPrivateContext (sailpoint.api.DatabaseInstance databaseInstance)`
- `static void dumpUnreleased ()`
- `static void dumpUnreleased (sailpoint.api.DatabaseInstance databaseInstance)`
- `java.util.Map<java.lang.String,​SailPointContext> getContextPrototypes ()`
- `staticSailPointContext getCurrentContext ()`
- `staticSailPointContext getCurrentContext (sailpoint.api.DatabaseInstance databaseInstance)`
- `staticSailPointContext getCurrentContextForClass (java.lang.Class<? extends SailPointObject > scope)`
- `staticSailPointContext peekCurrentContext ()`
- `staticSailPointContext peekCurrentContext (sailpoint.api.DatabaseInstance databaseInstance)`
- `static void popContext (sailpoint.api.DatabaseInstance databaseInstance, SailPointContext prev)`
- `static void popContext ( SailPointContext prev)`
- `staticSailPointContext pushContext ()`
- `staticSailPointContext pushContext (sailpoint.api.DatabaseInstance databaseInstance)`
- `static void releaseContext (sailpoint.api.DatabaseInstance databaseInstance, SailPointContext context, boolean publishMeters)`
- `static void releaseContext ( SailPointContext context)`
- `static void releaseContext ( SailPointContext context, boolean publishMeters)`
- `static void releaseContextNoMeters (sailpoint.api.DatabaseInstance databaseInstance, SailPointContext context)`
- `static void releaseContextNoMeters ( SailPointContext context)`
- `static void releasePrivateContext (sailpoint.api.DatabaseInstance databaseInstance, SailPointContext context)`
- `static void releasePrivateContext ( SailPointContext context)`
- `static void restoreContext (sailpoint.api.DatabaseInstance databaseInstance, SailPointContext con)`
- `static void restoreContext ( SailPointContext con)`
- `static void setContext (sailpoint.api.DatabaseInstance databaseInstance, SailPointContext ctxt)`
- `static void setContext ( SailPointContext ctxt)`
- `void setContextPrototype ( SailPointContext c)`

---

## ScopeService.DeletionOptions

**Package:** `sailpoint.api`

**Description:** DeletionOptions provide information about what to do with scope references when a scope is deleted.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.ScopeService.DeletionOptions`

**Attributes:** N/A

**Methods:**
- `boolean deleteChildren ()`
- `Scope getAssignedScopeReplacement ()`
- `Scope getControlledScopeReplacement ()`

---

## ScopeService

**Package:** `sailpoint.api`

**Description:** Service to deal with scopes. While the Scoper is more aimed at scope services as they relate to identities, this provides methods to deal with scopes from a more interactive perspective.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.ScopeService`

**Attributes:** N/A

**Methods:**
- `void applyScopingOptionsToContext ( Identity userBeingScoped)`
- `boolean controlsScope ( Identity user, Scope scope)`
- `void deleteScope ( Scope scope, ScopeService.DeletionOptions options)`
- `int denormalizePaths ()`
- `Filter getAssignedScopeFilter ( Identity user)`
- `QueryInfo getAssignedScopeQueryInfo ( Identity user)`
- `Filter getControlledScopesFilter ( Identity user)`
- `QueryInfo getControlledScopesQueryInfo ( Identity user)`
- `sailpoint.task.TaskMonitor getTaskMonitor (sailpoint.task.TaskMonitor monitor)`
- `boolean getTrace ()`
- `boolean hasAssignedScope (java.lang.Class<? extends SailPointObject > clazz)`
- `boolean isScopingEnabled ()`
- `boolean isUnscopedGloballyAccessible ()`
- `void moveScope ( Scope toMove, Scope oldParent, Scope newParent)`
- `static void println (java.lang.Object o)`
- `void queueDirtyScope ( Scope scope, boolean commit)`
- `void save ( Scope scope)`
- `void setTaskMonitor (sailpoint.task.TaskMonitor monitor)`
- `void setTrace (boolean b)`
- `void terminateDenormalization ()`

---

## TaskManager

**Package:** `sailpoint.api`

**Description:** A utility class providing task management services.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.TaskManager`
- `WorkItemHandler`

**Attributes:**
- `static java.lang.String ARG_EXIT_ON_ERROR`
- `static java.lang.String ARG_SEQUENTIAL_TASK_LIST`
- `static java.lang.String ARG_TASK_TIME_OUT`
- `static java.lang.String ARG_TASKS_RUN_MSG`
- `static boolean DisableTaskRunStatistics`
- `static java.lang.String IMMEDIATE_SCHEDULE`
- `static int MAX_TASK_NAME_LEN`

**Methods:**
- `TaskResult awaitTask (java.lang.String resultName, int seconds)`
- `TaskResult awaitTask ( TaskSchedule sched, int seconds)`
- `TaskResult createResult ( TaskSchedule sched, TaskDefinition def, Attributes <java.lang.String,java.lang.Object> args, boolean launching)`
- `void expireSequentialTask ( Request request, TaskResult expiredResult)`
- `TaskResult finalizeTask ( TaskResult result)`
- `int getSuggestedPartitionCount (java.lang.String requestDefinitionName)`
- `int getSuggestedPartitionCount (java.lang.String requestDefinitionName, java.util.List< Server > returnServers)`
- `TaskDefinition getTaskDefinition (java.lang.String name)`
- `TaskDefinition getTaskDefinition ( TaskSchedule sched)`
- `TaskExecutor getTaskExecutor ( TaskDefinition def)`
- `TaskExecutor getTaskExecutor ( TaskDefinition def, Attributes <java.lang.String,java.lang.Object> args)`
- `boolean isSchedulerRunning ()`
- `boolean isTaskRunning (java.lang.String taskName, java.lang.String resultName)`
- `static void pause (int seconds)`
- `void restart ( TaskResult result)`
- `void run (java.lang.String name, Attributes <java.lang.String,java.lang.Object> args)`
- `TaskSchedule run ( TaskDefinition def, java.util.Map<java.lang.String,java.lang.Object> args)`
- `void runNow ( TaskSchedule sched)`
- `TaskResult runSync (java.lang.String defName, java.util.Map<java.lang.String,java.lang.Object> args)`
- `TaskResult runSync ( TaskDefinition def, java.util.Map<java.lang.String,java.lang.Object> args)`
- `TaskResult runSync ( TaskSchedule schedule, java.util.Map<java.lang.String,java.lang.Object> schedArgs)`
- `TaskResult runSync ( TaskSchedule schedule, TaskDefinition definition, TaskResult result, Attributes <java.lang.String,java.lang.Object> args)`
- `TaskResult runWithResult ( TaskDefinition def, java.util.Map<java.lang.String,java.lang.Object> args)`
- `void saveQualifiedResult ( TaskResult result, boolean tryUnqualified, boolean useNewContext)`
- `void saveQualifiedResult ( TaskResult result, boolean tryUnqualified, boolean useNewContext, TaskDefinition.ResultAction resultAction)`
- `void sendCommand ( TaskResult result, java.lang.String command, Attributes <java.lang.String,java.lang.Object> args)`
- `void sendStackCommand ( TaskResult result)`
- `void sendTerminateCommand ( TaskResult result)`
- `static void setDisableTaskRunStatistics (boolean b)`
- `void setLauncher (java.lang.String s)`
- `void startScheduler ()`
- `void suspendScheduler ()`
- `boolean terminate ( TaskResult result)`
- `void terminate ( TaskSchedule sched)`
- `void terminateTasks (java.util.Set<java.lang.String> taskResultIds)`

---

## Terminator

**Package:** `sailpoint.api`

**Description:** Utility class that can delete SailPointObject subclasses while carefully pruning references to them from other objects. This is necessary to avoid foreign key constraint violations.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Visitor`
- `sailpoint.api.Terminator`

**Attributes:** N/A

**Methods:**
- `void deleteObject ( SailPointObject obj)`
- `void deleteObjects (java.lang.Class<? extends SailPointObject > cls, QueryOptions ops)`
- `<T extendsSailPointObject>java.util.Iterator<java.lang.String> getIds (java.lang.Class<T> cls, QueryOptions ops)`
- `void setNoDecache (boolean b)`
- `void setNoLocking (boolean b)`
- `void setTerminate (boolean b)`
- `void setTrace (boolean b)`
- `void visitClassification ( Classification classification)`
- `void visitIdentityEntitlement ( IdentityEntitlement entitlement)`
- `void visitMonitoringStatistic ( MonitoringStatistic stat)`
- `void visitRequest ( Request req)`
- `void visitWorkflow ( Workflow workflow)`

---

## Workflower.AssignmentAudit

**Package:** `sailpoint.api`

**Description:** A representation of a work item assignment audit event. This class is a wrapper around AuditEvents that allows convenient construction and retrieval of assignment audit-related information.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Workflower.AssignmentAudit`

**Attributes:** N/A

**Methods:**
- `java.util.Date getDate ()`
- `AuditEvent getEvent ()`
- `java.lang.String getItemOrCertificationId ()`
- `java.lang.String getNewAssignee ()`
- `java.lang.String getOldAssignee ()`
- `java.lang.String getSource ()`
- `java.lang.String getWorkgroup ()`
- `void setItemOrCertificationId (java.lang.String itemOrCertificationId)`
- `void setNewAssignee (java.lang.String newAssignee)`
- `void setOldAssignee (java.lang.String oldAssignee)`
- `void setWorkgroup (java.lang.String workgroup)`

---

## Workflower.ForwardAudit

**Package:** `sailpoint.api`

**Description:** A representation of a forwarding audit event. This class is a wrapper around AuditEvents that allows convenient construction and retrieval of forwarding audit-related information.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Workflower.ForwardAudit`

**Attributes:**
- `static java.lang.String ATTR_COMMENT`

**Methods:**
- `java.lang.String getComment ()`
- `java.util.Date getDate ()`
- `AuditEvent getEvent ()`
- `Workflower.ForwardType getForwardType ()`
- `java.lang.String getNewOwner ()`
- `java.lang.String getOldOwner ()`
- `java.lang.String getSource ()`

---

## Workflower.ForwardType

**Package:** `sailpoint.api`

**Description:** Enumeration of types of forwards.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Workflower.ForwardType`
- `sailpoint.api.Workflower.ForwardType`
- `java.io.Serializable`
- `java.lang.Comparable<Workflower.ForwardType>`

**Attributes:** N/A

**Methods:**
- `staticWorkflower.ForwardType valueOf (java.lang.String name)`
- `staticWorkflower.ForwardType[] values ()`

---

## Workflower

**Package:** `sailpoint.api`

**Description:** A class for managing the lifecycle and side effects of Workflows and WorkItems. For developers outside of SailPoint, the primary methods that should be used are the ones for launching workflows. The methods for manging the lifecycle of WorkItems are normally only used by the UI, though it is permissible to finish WorkItems in custom code.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.api.Workflower`
- `WorkItemHandler`

**Attributes:**
- `static java.lang.String ACCESS_REQUEST`
- `static java.lang.String ARG_BACKGROUND`
- `static java.lang.String ATTACHMENTS`
- `static java.lang.String EMAIL_TEMPLATE_AUTHOR`
- `static java.lang.String EMAIL_TEMPLATE_COMMENT`
- `static java.lang.String EMAIL_TEMPLATE_COMMENT_TEXT`
- `static java.lang.String EMAIL_TEMPLATE_DATE`
- `static java.lang.String EMAIL_TEMPLATE_FORWARD_DATE`
- `static java.lang.String EMAIL_TEMPLATE_NEW_OWNER`
- `static java.lang.String EMAIL_TEMPLATE_PREV_OWNER`
- `static java.lang.String EMAIL_TEMPLATE_REMED_ITEM`
- `static java.lang.String EMAIL_TEMPLATE_REMED_ITEM_NAME`
- `static java.lang.String EMAIL_TEMPLATE_REQUESTER`
- `static java.lang.String EMAIL_TEMPLATE_WORK_ITEM`
- `static java.lang.String EMAIL_TEMPLATE_WORK_ITEM_NAME`
- `static java.lang.String FLOW`
- `static java.lang.String IS_ADAPTIVE_CARD`
- `static java.lang.String SYSTEM_RULE_LIBRARY`
- `static java.lang.String TASK_WORKFLOW_LAUNCHER`
- `static java.lang.String VAR_TASK_TYPE`
- `static java.lang.String WORK_ITEM`

**Methods:**
- `void addComment ( WorkItem item, Identity requester, java.lang.String comment)`
- `WorkItemArchive archive ( WorkItem item)`
- `WorkItemArchive archiveIfNecessary ( WorkItem item)`
- `void auditForward ( WorkItem item, Identity requester, Identity oldOwner, Identity newOwner, java.lang.String comment, Workflower.ForwardType type)`
- `void auditForward ( WorkItem item, Identity requester, Identity oldOwner, Identity newOwner, java.lang.String comment, Workflower.ForwardType type, java.lang.String integration)`
- `Identity checkForward ( Identity src)`
- `Identity checkForward ( Identity src, WorkItem item)`
- `Identity checkForward ( Identity src, WorkItem item, boolean audit, Identity requester)`
- `void finish ( WorkItem item)`
- `void forward ( WorkItem item, Identity requester, Identity newOwner, java.lang.String comment, boolean notify)`
- `void forward ( WorkItem item, Identity requester, Identity newOwner, java.lang.String comment, boolean notify, java.lang.String integration)`
- `void forward ( WorkItem item, Identity requester, Identity newOwner, java.lang.String comment, boolean notify, Workflower.ForwardType type)`
- `void forward ( WorkItem item, Identity requester, Identity newOwner, java.lang.String comment, boolean notify, Workflower.ForwardType type, java.lang.String integration)`
- `void forwardWorkItem ( SailPointContext context, WorkItem item, Identity newOwner)`
- `java.util.List<Identity> getEffectiveOwners ( WorkItemConfig config, java.lang.Object def)`
- `Form getForm (java.lang.Object formArg)`
- `java.util.List<Workflower.ForwardAudit> getForwardAudits (java.lang.String objectId, java.util.Date before)`
- `java.util.List<Workflower.ForwardAudit> getForwardAudits ( WorkItem item, java.util.Date before)`
- `int getNotificationErrors ()`
- `int getNotifications ()`
- `void handleWorkItem ( SailPointContext con, WorkItem item, boolean foreground)`
- `void initStatistics ()`
- `boolean isArchivable ( WorkItem item)`
- `boolean isForeground ()`
- `boolean isTransient ()`
- `static boolean isTruthy (java.lang.Object o)`
- `WorkflowLaunch launch (java.lang.String workflowRef, java.lang.String caseName, java.util.Map<java.lang.String,java.lang.Object> invars)`
- `WorkflowLaunch launch ( WorkflowLaunch wflaunch)`
- `WorkflowLaunch launch ( Workflow wf, java.lang.String caseName, java.util.Map<java.lang.String,java.lang.Object> vars)`
- `java.lang.String launchApproval (java.lang.String workflowRef, java.lang.String caseName, SailPointObject object, java.util.Map<java.lang.String,java.lang.Object> invars)`
- `java.lang.String launchDeleteApproval (java.lang.String workflowRef, java.lang.String caseName, SailPointObject object, java.util.Map<java.lang.String,java.lang.Object> invars)`
- `WorkflowLaunch launchSafely ( Workflow wf, java.lang.String caseName, java.util.Map<java.lang.String,java.lang.Object> vars)`
- `sailpoint.api.WorkflowSession launchSession ( WorkflowLaunch wflaunch)`
- `static java.lang.Object mergeValues (java.lang.Object old, java.lang.Object neu)`
- `void notify ( Identity ident, boolean checkForwarding, EmailTemplate template, java.util.Map<java.lang.String,java.lang.Object> args, sailpoint.api.MessageAccumulator accumulator)`
- `void notify ( Identity ident, EmailTemplate template, java.util.Map<java.lang.String,java.lang.Object> args, sailpoint.api.MessageAccumulator accumulator)`
- `void notify ( Identity ident, WorkItemConfig config, java.util.Map<java.lang.String,java.lang.Object> args, sailpoint.api.MessageAccumulator accumulator)`
- `void open ( WorkItem item)`
- `void open ( WorkItem item, java.lang.String defaultTemplate, java.lang.String configProperty, java.util.Map<java.lang.String,java.lang.Object> args)`
- `void open ( WorkItem item, java.lang.String configProperty, java.util.Map<java.lang.String,java.lang.Object> args)`
- `void open ( WorkItem item, EmailTemplate email, java.util.Map<java.lang.String,java.lang.Object> args)`
- `void open ( WorkItem item, WorkItemConfig config, java.util.Map<java.lang.String,java.lang.Object> args, sailpoint.api.MessageAccumulator accumulator)`
- `void persistCase ( WorkflowContext wfc)`
- `void println (java.lang.Object o)`
- `void process (sailpoint.api.WorkflowSession ses, WorkItem item)`
- `void process ( WorkItem item, boolean foreground)`
- `void processEvent ( WorkItem item)`
- `void processEvent ( WorkItem item, boolean foreground)`
- `void reject ( WorkItem item)`
- `void removeAssignee ( Identity requester, AssignableItem item)`
- `void removeAssignee ( Identity requester, AssignableItem item, java.lang.String integration)`
- `java.lang.Object resolveVariable ( WorkflowContext context, java.lang.String name)`
- `Identity runFallbackForwardRule ( Identity src, WorkItem item, java.util.HashMap<java.lang.String,java.lang.Object> additionalParams, boolean audit, Identity requester, Workflower.ForwardType forwardType)`
- `void setAssignee ( Identity requester, AssignableItem item, Identity assignee)`
- `void setAssignee ( Identity requester, AssignableItem item, Identity assignee, java.lang.String integration)`
- `void setDefaultApprovalOwner (java.lang.String s)`
- `void setEmailSuppressor ( EmailSuppressor emailSuppressor)`
- `void setSessionOwner (java.lang.String s)`
- `void setTestHarness (sailpoint.workflow.WorkflowTestHarness h)`
- `void terminate ( WorkflowCase wfcase)`
- `void udpateApprovalObject (java.lang.String id, SailPointObject obj)`
- `void updateApprovalObject ( WorkflowCase wfcase, SailPointObject obj)`
- `void updateTaskResult ( WorkflowContext wfc, TaskResult result)`
- `void validateWorkItem ( SailPointContext con, WorkItem item)`

---

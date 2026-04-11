# SailPoint Object Classes Details

## AbstractCertifiableEntity

**Package:** `sailpoint.object`

**Description:** This abstract class includes all of the methods needed for classes that undergo certification. This base class provides the methods that the generic certification classes need, while properties specific to any subclasses are only referenced in the CertificationContext implementation specific to the subclass type.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.AbstractCertifiableEntity`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.util.List<Bundle> getAssignedRoles ()`
- `java.util.List<Bundle> getBundles ()`
- `java.util.List<Bundle> getBundles (java.util.List< Application > apps)`
- `java.util.List<Bundle> getBundles ( Application app)`
- `java.util.List<EntitlementGroup> getExceptions (java.util.List< Application > apps)`
- `abstract java.lang.String getFullName ()`
- `CertificationLink getLatestCertification ( Certification.Type type)`
- `java.util.List<RoleAssignment> getRoleAssignments ()`
- `java.util.List<RoleDetection> getRoleDetections ()`
- `java.util.Collection<RoleDetection> getRoleDetections (java.util.List< Application > apps)`
- `java.util.List<RoleDetection> getRoleDetections ( Application app)`
- `abstract java.lang.String getTypeName (boolean plural)`
- `abstract boolean isDifferencable ()`
- `boolean isInactive ()`
- `void remove ( CertificationLink link)`

---

## AbstractCertificationItem.ContinuousState

**Package:** `sailpoint.object`

**Description:** An enumeration of possible continuous certification states that indicate the timeliness of certification for an AbstractCertificationItem.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `AbstractCertificationItem.ContinuousState`
- `sailpoint.object.AbstractCertificationItem.ContinuousState`
- `java.io.Serializable`
- `java.lang.Comparable<AbstractCertificationItem.ContinuousState>`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:**
- `protected abstract void enterEntity ( Certification cert)`
- `protected abstract void enterItem ( Certification cert)`
- `java.lang.String getLocalizedMessage ()`
- `java.lang.String getLocalizedMessage (java.util.Locale locale, java.util.TimeZone timezone)`
- `java.lang.String getMessageKey ()`
- `protected abstract void leaveEntity ( Certification cert)`
- `protected abstract void leaveItem ( Certification cert)`
- `void transitionEntityTo ( AbstractCertificationItem.ContinuousState from, Certification cert)`
- `void transitionItemTo ( AbstractCertificationItem.ContinuousState from, Certification cert)`
- `staticAbstractCertificationItem.ContinuousState valueOf (java.lang.String name)`
- `staticAbstractCertificationItem.ContinuousState[] values ()`

---

## AbstractCertificationItem.Status

**Package:** `sailpoint.object`

**Description:** An enumeration of possible statuses for an AbstractCertificationItem.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `AbstractCertificationItem.Status`
- `sailpoint.object.AbstractCertificationItem.Status`
- `java.io.Serializable`
- `java.lang.Comparable<AbstractCertificationItem.Status>`
- `sailpoint.tools.Localizable`
- `sailpoint.tools.MessageKeyHolder`

**Attributes:** N/A

**Methods:**
- `java.lang.String getLocalizedMessage ()`
- `java.lang.String getLocalizedMessage (java.util.Locale locale, java.util.TimeZone timezone)`
- `java.lang.String getMessageKey ()`
- `boolean isComplete ()`
- `staticAbstractCertificationItem.Status valueOf (java.lang.String name)`
- `staticAbstractCertificationItem.Status[] values ()`

---

## AbstractCertificationItem

**Package:** `sailpoint.object`

**Description:** Abstract superclass for a certifiable item in a certification. In some customer situations, customers will want to add additional behavior and information to the certification model. The "custom" fields in CertificationItem can be used to store this information. Certificationer provides hooks during generation, refresh, etc... to insert custom behavior.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.AbstractCertificationItem`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `WorkItemOwnerChangeListener`
- `sailpoint.tools.WatchableMap.Watcher<java.lang.String,​java.lang.Object>`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `abstract java.util.List<CertificationItem> bulkCertify ( Identity who, java.lang.String workItem, CertificationAction bulkAction, CertificationItemSelector selector, boolean force)`
- `void clearIds ()`
- `void delegate ( Identity requester, java.lang.String workItem, java.lang.String recipient, java.lang.String description, java.lang.String comments)`
- `CertificationAction getAction ()`
- `abstract java.util.List<Application> getApplications ( CertificationAction action, boolean isBulkCertified, Resolver resolver)`
- `abstractCertification getCertification ()`
- `abstractCertificationEntity getCertificationEntity ()`
- `java.util.Date getCompleted ()`
- `AbstractCertificationItem.ContinuousState getContinuousState ()`
- `java.lang.String getCustom1 ()`
- `java.lang.String getCustom2 ()`
- `java.util.Map<java.lang.String,​java.lang.Object> getCustomMap ()`
- `abstractIdentity getDefaultRemediator ( Resolver resolver)`
- `CertificationDelegation getDelegation ()`
- `boolean getHasDifferences ()`
- `java.lang.String getHibernateCustom1 ()`
- `java.lang.String getHibernateCustom2 ()`
- `java.util.Map<java.lang.String,​java.lang.Object> getHibernateCustomMap ()`
- `abstract java.lang.String getIdentity ()`
- `java.util.List<CertificationItem> getItems ()`
- `java.util.Date getLastDecision ()`
- `java.util.Date getNextContinuousStateChange ()`
- `java.util.Date getOverdueDate ()`
- `AbstractCertificationItem.Status getSummaryStatus ()`
- `java.lang.String getTargetDisplayName ()`
- `java.lang.String getTargetId ()`
- `java.lang.String getTargetName ()`
- `boolean hasName ()`
- `boolean isActionRequired ()`
- `boolean isComplete ()`
- `void mapChanged (java.util.Map<java.lang.String,java.lang.Object> m)`
- `abstract void markForContinuousFlush ()`
- `abstract void markForRefresh ()`
- `abstract void refreshActionRequired ()`
- `abstract boolean refreshHasDifferences ( IdentityDifference diff, Resolver resolver)`
- `void refreshSummaryStatus ()`
- `abstract void refreshSummaryStatus (java.lang.Boolean completeOverride)`
- `void revokeDelegation ()`
- `boolean rollbackChanges (java.lang.String workItemId)`
- `void setAction ( CertificationAction a)`
- `void setActionRequired (boolean actionRequired)`
- `void setCompleted (java.util.Date d)`
- `void setContinuousState ( AbstractCertificationItem.ContinuousState state)`
- `void setCustom1 (java.lang.String s)`
- `void setCustom2 (java.lang.String s)`
- `void setCustomMap (java.util.Map<java.lang.String,java.lang.Object> m)`
- `void setDelegation ( CertificationDelegation a)`
- `void setHasDifferences (boolean hasDifferences)`
- `void setHibernateCustom1 (java.lang.String s)`
- `void setHibernateCustom2 (java.lang.String s)`
- `void setHibernateCustomMap (java.util.Map<java.lang.String,java.lang.Object> m)`
- `void setLastDecision (java.util.Date lastDecision)`
- `void setNextContinuousStateChange (java.util.Date nextChange)`
- `void setOverdueDate (java.util.Date overdueDate)`
- `void setSummaryStatus ( AbstractCertificationItem.Status summaryStatus)`
- `void setTargetDisplayName (java.lang.String targetDisplayName)`
- `void setTargetId (java.lang.String targetId)`
- `void setTargetName (java.lang.String targetName)`
- `void workItemOwnerChanged ( Resolver resolver, WorkItem item, Identity newOwner, Identity prevOwner)`

---

## AbstractChangeEvent.Operation

**Package:** `sailpoint.object`

**Description:** Enumeration of operations on the identity.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `AbstractChangeEvent.Operation`
- `sailpoint.object.AbstractChangeEvent.Operation`
- `java.io.Serializable`
- `java.lang.Comparable<AbstractChangeEvent.Operation>`

**Attributes:** N/A

**Methods:**
- `staticAbstractChangeEvent.Operation valueOf (java.lang.String name)`
- `staticAbstractChangeEvent.Operation[] values ()`

---

## AbstractChangeEvent<T>

**Package:** `sailpoint.object`

**Description:** An event that gets fired when an object is created/update/deleted.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.AbstractChangeEvent<T>`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getDeletedObjectName ()`
- `T getNewObject ()`
- `T getObject ()`
- `java.lang.String getObjectName ()`
- `T getOldObject ()`
- `AbstractChangeEvent.Operation getOperation ()`

---

## AccessMapping

**Package:** `sailpoint.object`

**Description:** The database id.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.AccessMapping`

**Attributes:** N/A

**Methods:**
- `void addNativeId (java.lang.String id)`
- `java.lang.Object getAttribute (java.lang.String name)`
- `java.util.Map<java.lang.String,​java.lang.Object> getAttributes ()`
- `int getEffective ()`
- `java.lang.String getId ()`
- `java.util.List<java.lang.String> getNativeIds ()`
- `java.lang.String getRights ()`
- `java.util.List<java.lang.String> getRightsList ()`
- `boolean isAllow ()`
- `boolean isInherited ()`
- `void setAllow (boolean _isAllow)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes (java.util.Map<java.lang.String,java.lang.Object> attrs)`
- `void setEffective (int _effective)`
- `void setId (java.lang.String id)`
- `void setInherited (boolean _inherited)`
- `void setNativeIds (java.util.List<java.lang.String> nativeIds)`
- `void setRights (java.lang.String rights)`
- `void setRightsList (java.util.List<java.lang.String> rights)`

---

## AccessRequestAccountInfo

**Package:** `sailpoint.object`

**Description:** Simple class to hold some account information for access requests. It is useful for bulk requests when you need to select native identity or instance.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.AccessRequestAccountInfo`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String NEW_ACCOUNT_SELECTION`

**Methods:**
- `java.lang.String getApplicationName ()`
- `java.lang.String getId ()`
- `java.lang.String getIdentityId ()`
- `java.lang.String getInstance ()`
- `java.lang.String getNativeIdentity ()`
- `java.lang.String getRoleName ()`
- `boolean isCreateAccount ()`
- `boolean isInAssigments (java.util.List< RoleAssignment > assignments)`
- `void setApplicationName (java.lang.String applicationName)`
- `void setId (java.lang.String accountRequestId)`
- `void setIdentityId (java.lang.String identityId)`
- `void setInstance (java.lang.String instance)`
- `void setNativeIdentity (java.lang.String nativeIdentity)`
- `void setRoleName (java.lang.String roleName)`

---

## AccountGroup.NoMemberAttributeException

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `java.lang.Throwable`
- `java.lang.Exception`
- `sailpoint.tools.AbstractLocalizableException`
- `sailpoint.tools.GeneralException`
- `sailpoint.object.AccountGroup.NoMemberAttributeException`
- `java.io.Serializable`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:** N/A

---

## AccountGroup

**Package:** `sailpoint.object`

**Description:** NOTE: As of 6.0 this class was merged with ManagedEntitlement. Account groups are modeled as "group" flagged Managed attributes. This class is provided only to facilitate the upgrade process it must no longer be used by system or custom code. An object representing a "group" defined in an application. Groups in our context are used to assign permissions indirectly to accounts. Note that the term group is generic, some applications might call the concept something else, like "role". Account groups are discovered dynamically during identity aggregation. In our model, they are very similar to Link objects, but are not owned by another object. In theory a group can have arbitrary attributes but in practice they are brought over primarily to hold a list of Permission objects representing the entitlements granted by the group. On the application they logically contain a set of "members" but modelign that is not attempted here. The SailPointObject._name field is used to hold the "display name" which is an alternative to the nativeIdentity for display. This is not a unique key.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.AbstractCertifiableEntity`
- `sailpoint.object.AccountGroup`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.util.Comparator<AccountGroup> SP_ACCOUNTGROUP_BY_MODIFIED`
- `static java.util.Comparator<AccountGroup> SP_ACCOUNTGROUP_BY_NAME`
- `static java.util.Comparator<AccountGroup> SP_ACCOUNTGROUP_BY_NATIVE_IDENTITY`
- `static java.util.Comparator<AccountGroup> SP_ACCOUNTGROUP_BY_OWNER`

**Methods:**
- `void add ( Permission p)`
- `java.lang.Object clone ()`
- `java.util.List<Permission> getAllPermissions ()`
- `Application getApplication ()`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getDisplayableName ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `java.util.List<EntitlementGroup> getExceptions (java.util.List< Application > apps)`
- `java.lang.String getFullName ()`
- `java.util.List<AccountGroup> getInheritance ()`
- `java.lang.String getInstance ()`
- `java.lang.String getKey1 ()`
- `java.lang.String getKey2 ()`
- `java.lang.String getKey3 ()`
- `java.lang.String getKey4 ()`
- `java.util.Date getLastRefresh ()`
- `java.util.Date getLastTargetAggregation ()`
- `java.lang.String getMemberAttribute ()`
- `java.lang.String getNativeIdentity ()`
- `java.util.List<Permission> getPermissions ()`
- `java.lang.String getReferenceAttribute ()`
- `Permission getSinglePermission (java.lang.String target)`
- `java.util.List<Permission> getTargetPermissions ()`
- `java.lang.String getTypeName (boolean plural)`
- `boolean isDifferencable ()`
- `boolean isUncorrelated ()`
- `void setApplication ( Application res)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> a)`
- `void setInheritance (java.util.List< AccountGroup > groups)`
- `void setInstance (java.lang.String ins)`
- `void setKey1 (java.lang.String s)`
- `void setKey2 (java.lang.String s)`
- `void setKey3 (java.lang.String s)`
- `void setKey4 (java.lang.String s)`
- `void setLastRefresh (java.util.Date d)`
- `void setLastTargetAggregation (java.util.Date d)`
- `void setMemberAttribute (java.lang.String attr)`
- `void setNativeIdentity (java.lang.String id)`
- `void setPermissions (java.util.List< Permission > perms)`
- `void setReferenceAttribute (java.lang.String s)`
- `void setSinglePermission ( Permission single)`
- `void setTargetPermissions (java.util.List< Permission > perms)`
- `void setUncorrelated (boolean b)`
- `void visit ( Visitor v)`

---

## AccountIconConfig

**Package:** `sailpoint.object`

**Description:** A class to encapsulate the configuration to drive the icons that are displayed when displaying accounts in the identities page and certification pages.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.AccountIconConfig`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `boolean equals (java.lang.Object obj)`
- `java.lang.String getAttribute ()`
- `java.lang.String getSource ()`
- `java.lang.String getTitle ()`
- `java.lang.String getValue ()`
- `void setAttribute (java.lang.String attribute)`
- `void setSource (java.lang.String icon)`
- `void setTitle (java.lang.String title)`
- `void setValue (java.lang.String value)`

---

## AccountItem

**Package:** `sailpoint.object`

**Description:** A class used to represent a single item (attribute or entitlement) from an application account.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.AccountItem`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void assimilate (java.lang.Object value)`
- `boolean equal (java.lang.String s1, java.lang.String s2)`
- `java.lang.String getAnnotation ()`
- `java.lang.String getCsv ()`
- `java.lang.String getDisplayName ()`
- `java.lang.String getName ()`
- `Permission getPermissionObject ()`
- `java.lang.Object getValue ()`
- `java.util.List<java.lang.String> getValueList ()`
- `boolean isEqual ( AccountItem other)`
- `boolean isPermission ()`
- `void setAnnotation (java.lang.String s)`
- `void setDisplayName (java.lang.String displayName)`
- `void setName (java.lang.String s)`
- `void setPermission (boolean b)`
- `void setPermission ( Permission perm)`
- `void setPermission ( Permission perm, java.lang.Object value)`
- `void setValue (java.lang.Object o)`
- `void setValue (java.lang.String name, java.lang.Object value)`

---

## AccountScopeData

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.AccountScopeData`

**Attributes:** N/A

**Methods:**
- `java.lang.String getGroupMemberFilterString ()`
- `java.lang.String getGroupMembershipSearchDN ()`
- `java.util.List<java.util.Map<java.lang.Object,​java.lang.Object>> getGroupMembershipSearchScope ()`
- `java.lang.String getIterateSearchFilter ()`
- `java.lang.String getPrimaryGroupSearchDN ()`
- `java.lang.String getSearchDN ()`
- `java.lang.String getSearchScope ()`
- `void setGroupMemberFilterString (java.lang.String groupMemberFilterString)`
- `void setGroupMembershipSearchDN (java.lang.String groupMembershipSearchDN)`
- `void setGroupMembershipSearchScope (java.util.List<java.util.Map<java.lang.Object,java.lang.Object>> groupMembershipSearchScope)`
- `void setIterateSearchFilter (java.lang.String iterateSearchFilter)`
- `void setPrimaryGroupSearchDN (java.lang.String primaryGroupSearchDN)`
- `void setSearchDN (java.lang.String searchDN)`
- `void setSearchScope (java.lang.String searchScope)`

---

## AccountSelection.AccountInfo

**Package:** `sailpoint.object`

**Description:** The distinguishing information about an account. This is stored in the AccountSelection rather than calculated on the fly to allow a relatively dumb form to be able to consume it. A list of these represents the possible target accounts that can be selected.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.AccountSelection.AccountInfo`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getDisplayName ()`
- `java.lang.String getInstance ()`
- `java.lang.String getNativeIdentity ()`

---

## AccountSelection

**Package:** `sailpoint.object`

**Description:** AccountSelection holds information used to select one or more accounts for an operation when an identity has multiple accounts on the same applicationId.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.AccountSelection`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void addAccountInfo ( AccountSelection.AccountInfo info)`
- `void addAccountInfo ( Link link)`
- `void addAccountInfo ( RoleTarget targ)`
- `void addFollower (java.lang.String roleName)`
- `java.util.List<AccountSelection.AccountInfo> getAccounts ()`
- `java.lang.String getApplicationId ()`
- `java.lang.String getApplicationName ()`
- `java.util.List<java.lang.String> getFollowers ()`
- `java.lang.String getInstance ()`
- `java.lang.String getOrigin ()`
- `ProvisioningPlan getPlan ()`
- `java.lang.String getRoleName ()`
- `java.util.List<java.lang.String> getSelectedNativeIdentities ()`
- `java.util.List<java.lang.String> getSelectedNativeIdentitiesXml ()`
- `java.lang.String getSelectedNativeIdentity ()`
- `java.lang.String getSelection ()`
- `java.lang.String getSelectionXml ()`
- `boolean isAllowCreate ()`
- `boolean isAnswered ()`
- `boolean isDoCreate ()`
- `boolean isImplicitCreate ()`
- `boolean onApplication ( Application app)`
- `void setAllowCreate (boolean b)`
- `void setDoCreate (boolean b)`
- `void setFollowers (java.util.List<java.lang.String> followers)`
- `void setImplicitCreate (boolean b)`
- `void setOrigin (java.lang.String origin)`
- `void setPlan ( ProvisioningPlan plan)`
- `void setRoleName (java.lang.String name)`
- `void setSelectedNativeIdentities (java.util.List<java.lang.String> selected)`
- `void setSelectedNativeIdentitiesXml (java.util.List<java.lang.String> selected)`
- `void setSelectedNativeIdentity (java.lang.String selected)`
- `void setSelection (java.lang.String s)`
- `void setSelectionXml (java.lang.String s)`

---

## AccountSelectorRules

**Package:** `sailpoint.object`

**Description:** Optional rule for selecting target account for the bundle.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.AccountSelectorRules`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.util.List<ApplicationAccountSelectorRule> getApplicationAccountSelectorRules ()`
- `Rule getBundleLevelAccountSelectorRule ()`
- `void setApplicationAccountSelectorRules (java.util.List< ApplicationAccountSelectorRule > _applicationAccountSelectorRules)`
- `void setBundleLevelAccountSelectorRule ( Rule r)`

---

## ActivityConfig

**Package:** `sailpoint.object`

**Description:** An object that describes activity monitoring configuration. There are two levels of enablement, a global "all ON" flag and enablement at the application level. One of these objects can be assigned to either the individual Identity or to a role.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ActivityConfig`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void addApplication (java.lang.String id)`
- `void clearApplications ()`
- `void disableApplication ( Application app)`
- `boolean enableAll ()`
- `void enableApplication ( Application app)`
- `boolean enabled ()`
- `boolean enabled ( Application application)`
- `boolean equals (java.lang.Object o)`
- `java.util.Set<java.lang.String> getEnabledApplications ()`
- `boolean isAllEnabled ()`
- `boolean isEnabled (java.lang.String id)`
- `boolean isEnabled ( Application application)`
- `void removeApplication (java.lang.String id)`
- `void setAllEnabled (boolean enableAll)`
- `void setEnabledApplications (java.util.Set<java.lang.String> enabled)`

---

## ActivityConstraint

**Package:** `sailpoint.object`

**Description:** The model for a constraint within an activity policy.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.BaseConstraint`
- `sailpoint.object.ActivityConstraint`
- `java.io.Serializable`
- `PolicyViolation.IPolicyViolationOwnerSource`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.util.List<Filter> getActivityFilters ()`
- `java.util.List<Filter> getIdentityFilters ()`
- `java.util.List<TimePeriod> getTimePeriods ()`
- `void setActivityFilters (java.util.List< Filter > filters)`
- `void setIdentityFilters (java.util.List< Filter > filters)`
- `void setTimePeriods (java.util.List< TimePeriod > periods)`

---

## ActivityDataSource

**Package:** `sailpoint.object`

**Description:** Clone this object.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.ActivityDataSource`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `void addTarget (java.lang.String target)`
- `java.lang.Object clone ()`
- `java.lang.Object getAttributeValue (java.lang.String name)`
- `java.lang.String getCollector ()`
- `Attributes<java.lang.String,​java.lang.Object> getConfiguration ()`
- `Rule getCorrelationRule ()`
- `java.util.Date getLastRefresh ()`
- `java.util.List<java.lang.String> getTargets ()`
- `Rule getTransformationRule ()`
- `java.lang.String getType ()`
- `void load ()`
- `void removeTarget (java.lang.String target)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setCollector (java.lang.String collector)`
- `void setConfiguration ( Attributes <java.lang.String,java.lang.Object> config)`
- `void setCorrelationRule ( Rule rule)`
- `void setLastRefresh (java.util.Date date)`
- `void setTargets (java.util.List<java.lang.String> targets)`
- `void setTransformationRule ( Rule rule)`
- `void setType (java.lang.String type)`

---

## ActivityFieldMap.ActivityField

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ActivityFieldMap.ActivityField`
- `sailpoint.object.ActivityFieldMap.ActivityField`
- `java.io.Serializable`
- `java.lang.Comparable<ActivityFieldMap.ActivityField>`

**Attributes:** N/A

**Methods:**
- `staticActivityFieldMap.ActivityField valueOf (java.lang.String name)`
- `staticActivityFieldMap.ActivityField[] values ()`

---

## ActivityFieldMap.TransformationType

**Package:** `sailpoint.object`

**Description:** Enumeration which specifies the types of transformations that can be used for a field. None : No transformation, use the raw value Rule : Rule a rule to transform the value DateConverter : Use a specialized date converter Script : Some script value

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ActivityFieldMap.TransformationType`
- `sailpoint.object.ActivityFieldMap.TransformationType`
- `java.io.Serializable`
- `java.lang.Comparable<ActivityFieldMap.TransformationType>`

**Attributes:** N/A

**Methods:**
- `staticActivityFieldMap.TransformationType valueOf (java.lang.String name)`
- `staticActivityFieldMap.TransformationType[] values ()`

---

## ActivityFieldMap

**Package:** `sailpoint.object`

**Description:** Enumeration which specifies the types of transformations that can be used for a field.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ActivityFieldMap`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getDateFormat ()`
- `ActivityFieldMap.ActivityField getField ()`
- `Rule getRule ()`
- `Script getScript ()`
- `java.lang.String getSource ()`
- `java.lang.String getTimeZone ()`
- `ActivityFieldMap.TransformationType getTransformationType ()`
- `void setDateFormat (java.lang.String dateFormat)`
- `void setField ( ActivityFieldMap.ActivityField field)`
- `void setRule ( Rule rule)`
- `void setScript ( Script script)`
- `void setSource (java.lang.String field)`
- `void setTimeZone (java.lang.String timeZone)`
- `void setTransformationType ( ActivityFieldMap.TransformationType type)`

---

## AdaptiveCardNotificationTemplate

**Package:** `sailpoint.object`

**Description:** Class containing information required to send an adaptive card notification.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.AdaptiveCardNotificationTemplate`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `NotificationTemplate`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `AdaptiveCardNotificationTemplate compile ( Resolver resolver, EmailOptions options)`
- `java.lang.String getBody ()`
- `java.lang.String getTo ()`
- `void setBody (java.lang.String body)`
- `void setTo (java.lang.String _to)`

---

## Alert

**Package:** `sailpoint.object`

**Description:** Created by ryan.pickens on 6/16/16.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Alert`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `void addAction ( AlertAction action)`
- `java.util.List<AlertAction> getActions ()`
- `java.util.Date getAlertDate ()`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getDisplayName ()`
- `Attributes<java.lang.String,​java.lang.Object> getExtendedAttributes ()`
- `java.util.Date getLastProcessed ()`
- `java.lang.String getNativeId ()`
- `staticObjectConfig getObjectConfig ()`
- `Application getSource ()`
- `java.lang.String getTargetDisplayName ()`
- `java.lang.String getTargetId ()`
- `java.lang.String getTargetType ()`
- `java.lang.String getType ()`
- `boolean hasAssignedScope ()`
- `void load ()`
- `void setActions (java.util.List< AlertAction > actions)`
- `void setAlertDate (java.util.Date d)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> atts)`
- `void setDisplayName (java.lang.String s)`
- `void setLastProcessed (java.util.Date d)`
- `void setNativeId (java.lang.String id)`
- `void setSource ( Application app)`
- `void setTargetDisplayName (java.lang.String s)`
- `void setTargetId (java.lang.String _targetId)`
- `void setTargetType (java.lang.String _targetType)`
- `void setType (java.lang.String s)`

---

## AlertAction.AlertActionResult

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.AlertAction.AlertActionResult`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.util.List<AlertAction.AlertNotification> getNotifications ()`
- `java.lang.String getResultId ()`
- `java.lang.String getResultName ()`
- `java.lang.String getWorkflowName ()`
- `void setNotifications (java.util.List< AlertAction.AlertNotification > notified)`
- `void setResultId (java.lang.String s)`
- `void setResultName (java.lang.String s)`
- `void setWorkflowName (java.lang.String s)`

---

## AlertAction.AlertNotification

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.AlertAction.AlertNotification`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getDisplayName ()`
- `java.util.List<java.lang.String> getEmailAddresses ()`
- `java.lang.String getName ()`
- `void setDisplayName (java.lang.String displayName)`
- `void setEmailAddresses (java.util.List<java.lang.String> emailAddress)`
- `void setName (java.lang.String name)`

---

## AlertAction

**Package:** `sailpoint.object`

**Description:** Created by ryan.pickens on 6/16/16.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.AlertAction`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `AlertDefinition.ActionType getActionType ()`
- `AlertDefinition getAlertDef ()`
- `AlertAction.AlertActionResult getResult ()`
- `java.lang.String getResultId ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `void setActionType ( AlertDefinition.ActionType action)`
- `void setAlertDef ( AlertDefinition def)`
- `void setResult ( AlertAction.AlertActionResult res)`
- `void setResultId (java.lang.String s)`

---

## AlertDefinition.ActionConfig

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.AlertDefinition.ActionConfig`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String ARG_CERT_TRIGGER`
- `static java.lang.String ARG_EMAIL_TEMPLATE`
- `static java.lang.String ARG_EMAIL_VARS`
- `static java.lang.String ARG_IDENTITY_EMAIL_RECIP`
- `static java.lang.String ARG_WORKFLOW_ARGS`
- `static java.lang.String ARG_WORKFLOW_NAME`

**Methods:**
- `AlertDefinition.ActionType getActionType ()`
- `Attributes getAttributes ()`
- `java.lang.String getCertificationTrigger ()`
- `java.util.List<java.lang.String> getEmailRecipients ()`
- `java.lang.String getEmailTemplate ()`
- `java.lang.String getStringAttributeValue (java.lang.String name)`
- `java.util.List getStringListAttributeValue (java.lang.String name)`
- `java.lang.String getWorkflowName ()`
- `void setActionType ( AlertDefinition.ActionType actionType)`
- `void setAttributes ( Attributes atts)`
- `void setCertificationTrigger (java.lang.String s)`
- `void setEmailRecipients (java.util.List<java.lang.String> recips)`
- `void setEmailTemplate (java.lang.String s)`
- `void setWorkflowName (java.lang.String s)`

---

## AlertDefinition.ActionType

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `AlertDefinition.ActionType`
- `sailpoint.object.AlertDefinition.ActionType`
- `java.io.Serializable`
- `java.lang.Comparable<AlertDefinition.ActionType>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticAlertDefinition.ActionType valueOf (java.lang.String name)`
- `staticAlertDefinition.ActionType[] values ()`

---

## AlertDefinition

**Package:** `sailpoint.object`

**Description:** Created by ryan.pickens on 6/16/16.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.AlertDefinition`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `AlertDefinition.ActionConfig getActionConfig ()`
- `java.lang.String getDisplayName ()`
- `AlertMatchConfig getMatchConfig ()`
- `void load ()`
- `void setActionConfig ( AlertDefinition.ActionConfig cnfg)`
- `void setDisplayName (java.lang.String s)`
- `void setMatchConfig ( AlertMatchConfig cnfg)`
- `boolean shouldNotify ()`

---

## AlertMatchConfig.AlertMatchExpression

**Package:** `sailpoint.object`

**Description:** Expression to match alerts. This will be composed of

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.AlertMatchConfig.AlertMatchExpression`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void addMatchTerm ( AlertMatchConfig.AlertMatchTerm term)`
- `java.util.List<AlertMatchConfig.AlertMatchTerm> getMatchTerms ()`
- `boolean isAnd ()`
- `void load ()`
- `boolean match ( Alert alert)`
- `void setAnd (boolean b)`
- `void setMatchTerms (java.util.List< AlertMatchConfig.AlertMatchTerm > terms)`

---

## AlertMatchConfig.AlertMatchTerm

**Package:** `sailpoint.object`

**Description:** Load the term and all term children

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.AlertMatchConfig.AlertMatchTerm`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void addChild ( AlertMatchConfig.AlertMatchTerm term)`
- `java.util.List<AlertMatchConfig.AlertMatchTerm> getChildren ()`
- `java.lang.String getName ()`
- `Application getSource ()`
- `java.lang.String getValue ()`
- `boolean isAnd ()`
- `boolean isContainer ()`
- `void load ()`
- `boolean match ( Alert alert)`
- `void setAnd (boolean b)`
- `void setChildren (java.util.List< AlertMatchConfig.AlertMatchTerm > children)`
- `void setContainer (boolean b)`
- `void setName (java.lang.String _name)`
- `void setSource ( Application _source)`
- `void setValue (java.lang.String _value)`

---

## AlertMatchConfig

**Package:** `sailpoint.object`

**Description:** Created by ryan.pickens on 6/22/16.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.AlertMatchConfig`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `AlertMatchConfig.AlertMatchExpression getMatchExpression ()`
- `Rule getMatchRule ()`
- `void load ()`
- `void setMatchExpression ( AlertMatchConfig.AlertMatchExpression _matchExpression)`
- `void setMatchRule ( Rule _matchRule)`

---

## AllowableActivity

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.AllowableActivity`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `ApplicationActivity.Action getAction ()`
- `java.util.List<ApplicationActivity.Result> getResults ()`
- `java.util.List<java.lang.String> getTargets ()`
- `void setAction ( ApplicationActivity.Action action)`
- `void setResults (java.util.List< ApplicationActivity.Result > results)`
- `void setTargets (java.util.List<java.lang.String> targets)`

---

## Application.Feature

**Package:** `sailpoint.object`

**Description:** Optional features that can be supported by an application.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Application.Feature`
- `sailpoint.object.Application.Feature`
- `java.io.Serializable`
- `java.lang.Comparable<Application.Feature>`

**Attributes:** N/A

**Methods:**
- `staticApplication.Feature valueOf (java.lang.String name)`
- `staticApplication.Feature[] values ()`

---

## Application.NotRequestableEntsLvl

**Package:** `sailpoint.object`

**Description:** Enum that helps to identify the level of not requestable entitlements configuration. The level could be: Application and Schema.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Application.NotRequestableEntsLvl`
- `sailpoint.object.Application.NotRequestableEntsLvl`
- `java.io.Serializable`
- `java.lang.Comparable<Application.NotRequestableEntsLvl>`

**Attributes:** N/A

**Methods:**
- `staticApplication.NotRequestableEntsLvl getEnum (java.lang.String value)`
- `java.lang.String getText ()`
- `staticApplication.NotRequestableEntsLvl valueOf (java.lang.String name)`
- `staticApplication.NotRequestableEntsLvl[] values ()`

---

## Application

**Package:** `sailpoint.object`

**Description:** The definition of an application.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Application`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `Describable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATTR_ACCOUNT_DISABLE_FILTER`
- `static java.lang.String ATTR_ACCOUNT_LOCK_FILTER`
- `static java.lang.String ATTR_ACCT_AGGREGATION_END`
- `static java.lang.String ATTR_ACCT_AGGREGATION_START`
- `static java.lang.String ATTR_AFTER_PROV_RULE_LOCATION`
- `static java.lang.String ATTR_AFTER_PROVISIONING_RULE`
- `static java.lang.String ATTR_AGGREGATION_PARTITIONED`
- `static java.lang.String ATTR_AGGREGATION_TYPE`
- `static java.lang.String ATTR_BEFORE_PROV_RULE_LOCATION`
- `static java.lang.String ATTR_BEFORE_PROVISIONING_RULE`
- `static java.lang.String ATTR_COMPOSITE_DEFINITION`
- `static java.lang.String ATTR_CUSTOMIZATION_RULE_LOCATION`
- `static java.lang.String ATTR_DELTA_AGGREGATION`
- `static java.lang.String ATTR_FORM_PATH`
- `static java.lang.String ATTR_FORM_PATH_RULES`
- `static java.lang.String ATTR_GROUP_MEMBER_ATTRIBUTE`
- `static java.lang.String ATTR_MANAGER_FILTER`
- `static java.lang.String ATTR_NATIVE_CHANGE_ATTRIBUTE_SCOPE`
- `static java.lang.String ATTR_NATIVE_CHANGE_ATTRIBUTES`
- `static java.lang.String ATTR_NATIVE_CHANGE_DETECTION_ENABLED`
- `static java.lang.String ATTR_NATIVE_CHANGE_OPERATIONS`
- `static java.lang.String ATTR_NATIVE_RULES`
- `static java.lang.String ATTR_NOT_REQUESTABLE_ENTITLEMENTS`
- `static java.lang.String ATTR_REFERENCE_APPS`
- `static java.lang.String ATTR_RPA_ACCOUNT_FILTER`
- `static java.lang.String ATTR_SERVICE_ACCOUNT_FILTER`
- `static java.lang.String ATTR_TEMPLATE_APPLICATION`
- `static java.lang.String CONFIG_ENCRYPTED_CONFIG_ATTRIBUTES`
- `static java.lang.String CONNECTOR_STATE_MAP`
- `static java.lang.String RULE_LOCATION_BOTH`
- `static java.lang.String RULE_LOCATION_LOCAL`
- `static java.lang.String RULE_LOCATION_PROXY`
- `static java.lang.String SCHEMA_ACCOUNT`
- `static java.lang.String SCHEMA_GROUP`
- `static java.lang.String[] SECRET_ATTRIBUTES`

**Methods:**
- `void add ( TargetSource source)`
- `void addActivityDataSource ( ActivityDataSource ads)`
- `void addDependency ( Application dependency)`
- `void addDescription (java.lang.String locale, java.lang.String desc)`
- `void addFeature ( Application.Feature feature)`
- `void addPasswordPolicy ( PasswordPolicyHolder pp)`
- `void addSchema ( Schema sch)`
- `void addScorecard ( ApplicationScorecard c)`
- `void assimilate ( Application app)`
- `java.lang.Object clone ()`
- `java.lang.Object derive ( Resolver res)`
- `CorrelationConfig getAccountCorrelationConfig ()`
- `Schema getAccountSchema ()`
- `ActivityDataSource getActivityDataSource (java.lang.String name)`
- `ActivityDataSource getActivityDataSourceById (java.lang.String id)`
- `java.util.List<ActivityDataSource> getActivityDataSources ()`
- `int getActivityDataSourcesCount ()`
- `java.lang.String getAfterProvisioningRule ()`
- `java.lang.String getAggregationTypes ()`
- `Schema getAssociationSchema ( Schema s)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.Object getAttributeValue (java.lang.String name)`
- `java.lang.String getBeforeProvisioningRule ()`
- `boolean getBooleanAttributeValue (java.lang.String name)`
- `java.lang.String getCluster ()`
- `CompositeDefinition getCompositeDefinition ()`
- `java.lang.String getConnector ()`
- `Rule getCorrelationRule ()`
- `Rule getCorrelationRule (java.lang.String objectType)`
- `Rule getCreationRule ()`
- `Rule getCreationRule (java.lang.String objectType)`
- `Rule getCustomizationRule ()`
- `Rule getCustomizationRule (java.lang.String objectType)`
- `java.util.Date getDateAttributeValue (java.lang.String name)`
- `java.util.List<Application> getDependencies ()`
- `java.lang.String getDescription ()`
- `java.lang.String getDescription (java.lang.String locale)`
- `java.lang.String getDescription (java.util.Locale locale)`
- `java.util.Map<java.lang.String,​java.lang.String> getDescriptions ()`
- `java.util.List<sailpoint.service.listfilter.ListFilterValue> getDisableAccountFilter ()`
- `java.util.List<java.lang.String> getEncrpytedConfigAttributes ()`
- `java.util.List<java.lang.String> getEncryptedAndSecretAttrList ()`
- `java.util.List<java.lang.String> getEntitlementAttributeNames ()`
- `java.util.Map<java.lang.String,​java.lang.String> getEntitlements (java.util.Locale locale)`
- `java.util.Map<java.lang.String,​java.lang.Object> getExtendedAttributes ()`
- `java.util.List<Application.Feature> getFeatures ()`
- `java.lang.String getFeaturesString ()`
- `java.util.List<sailpoint.service.listfilter.ListFilterValue> getFilterValueForType (java.lang.String type)`
- `java.lang.String getFormPath ()`
- `java.lang.String getFormPathRules ()`
- `AttributeDefinition getGroupAttribute ()`
- `AttributeDefinition getGroupAttribute (java.lang.String objectType)`
- `java.util.List<AttributeDefinition> getGroupAttributes ()`
- `java.lang.String getGroupHierarchyAttribute ()`
- `java.lang.String getGroupHierarchyAttribute (java.lang.String objectType)`
- `Schema getGroupSchema ()`
- `java.util.List<java.lang.String> getGroupSchemaObjectTypes ()`
- `java.util.List<Schema> getGroupSchemas ()`
- `java.util.List<Schema> getGroupsHaveMembersSchemas ()`
- `java.util.List<Form> getHibernateProvisioningForms ()`
- `java.lang.String getIcon ()`
- `int getIntAttributeValue (java.lang.String name)`
- `java.util.List getListAttributeValue (java.lang.String name)`
- `java.util.List<sailpoint.service.listfilter.ListFilterValue> getLockAccountFilter ()`
- `staticApplication getLoggingApp ( Application src)`
- `java.lang.Long getLongAttributeValue (java.lang.String name)`
- `long getMaintenanceExpiration ()`
- `Rule getManagedAttributeCustomizationRule ()`
- `Filter.LeafFilter getManagerCorrelationFilter ()`
- `Rule getManagerCorrelationRule ()`
- `java.util.List<java.lang.String> getNativeChangeAttributes ()`
- `java.lang.String getNativeChangeAttributeScope ()`
- `java.util.List<java.lang.String> getNativeChangeOperations ()`
- `java.util.List<java.lang.String> getNativeRules ()`
- `Application.NotRequestableEntsLvl getNotCreateRequestableEntitlements ()`
- `staticObjectConfig getObjectConfig ()`
- `java.lang.String getObjectTypeForAttribute (java.lang.String attributeName)`
- `Template getOldTemplate ( Template.Usage usage, java.lang.String objectType)`
- `java.util.List<Template> getOldTemplates ()`
- `java.util.List<Template> getOldTemplates (java.lang.String objectType)`
- `java.util.List<PasswordPolicyHolder> getPasswordPolicies ()`
- `PasswordPolicyHolder getPasswordPolicyHolderById (java.lang.String id)`
- `java.lang.String getProfileClass ()`
- `ProvisioningConfig getProvisioningConfig ()`
- `Form getProvisioningForm ( Form.Type type, java.lang.String objectType)`
- `java.util.List<Form> getProvisioningForms ()`
- `java.util.List<Form> getProvisioningForms (java.lang.String objectType)`
- `java.lang.String getProxiedName ()`
- `Application getProxy ()`
- `Rule getRefreshRule (java.lang.String schemaName)`
- `java.util.List<Identity> getRemediators ()`
- `java.util.List<sailpoint.service.listfilter.ListFilterValue> getRpaAccountFilter ()`
- `Schema getSchema (java.lang.String name)`
- `java.util.List<Schema> getSchemas ()`
- `int getScore ()`
- `ApplicationScorecard getScorecard ()`
- `java.util.List<Identity> getSecondaryOwners ()`
- `java.util.List<sailpoint.service.listfilter.ListFilterValue> getServiceAccountFilter ()`
- `java.lang.String getSettings ()`
- `java.lang.String getStringAttributeValue (java.lang.String name)`
- `TargetSource getTargetSource ()`
- `TargetSource getTargetSource (java.lang.String name)`
- `TargetSource getTargetSourceById (java.lang.String id)`
- `java.util.List<TargetSource> getTargetSources ()`
- `int getTargetSourcesCount ()`
- `java.lang.String getTemplateApplication ()`
- `java.util.List<Template> getTemplates ()`
- `java.lang.String getType ()`
- `ApplicationScorecard getXmlScorecard ()`
- `java.util.List<Template> getXmlTemplates ()`
- `boolean hasGroupSchema (java.lang.String objectType)`
- `boolean isActivityEnabled ()`
- `boolean isAuthenticationResource ()`
- `boolean isAuthoritative ()`
- `boolean isAutoPromotion ()`
- `boolean isCaseInsensitive ()`
- `boolean isComposite ()`
- `boolean isDirectlyAssignable (java.lang.String objectType)`
- `boolean isInMaintenance ()`
- `boolean isLogical ()`
- `boolean isManagesOtherApps ()`
- `boolean isNativeChangeDetectionEnabled ()`
- `boolean isNoAggregation ()`
- `boolean isNoAggregation (java.lang.String objectType)`
- `boolean isSchemaRequestable (java.lang.String name)`
- `boolean isSupportsAccountOnly ()`
- `boolean isSupportsAdditionalAccounts ()`
- `boolean isSupportsAuthenticate ()`
- `boolean isSupportsDirectPermissions ()`
- `boolean isSupportsGroupProvisioning ()`
- `boolean isSupportsProvisioning ()`
- `boolean isSyncProvisioning ()`
- `void load ()`
- `void notifyListeners ()`
- `void pruneUnloadedReferences ()`
- `void registerListener (sailpoint.api.ApplicationConfigChangeListener listener)`
- `void remove ( TargetSource targetSource)`
- `void removeActivityDataSource ( ActivityDataSource activityDS)`
- `void removeAttribute (java.lang.String name)`
- `boolean removeFeature ( Application.Feature feature)`
- `PasswordPolicyHolder removePasswordPolicy (java.lang.String ppName)`
- `void removeRemediator ( Identity remediator)`
- `void setAccountCorrelationConfig ( CorrelationConfig config)`
- `void setActivityDataSources (java.util.List< ActivityDataSource > dataSources)`
- `void setAfterProvisioningRule (java.lang.String afterRule)`
- `void setAggregationTypes (java.lang.String types)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> config)`
- `void setAuthenticationResource (boolean isAuthentication)`
- `void setAuthoritative (boolean authoritative)`
- `void setBeforeProvisioningRule (java.lang.String beforeRule)`
- `void setCaseInsensitive (boolean b)`
- `void setCluster (java.lang.String s)`
- `void setCompositeDefinition ( CompositeDefinition definition)`
- `void setConnector (java.lang.String className)`
- `void setCorrelationRule ( Rule r)`
- `void setCreationRule ( Rule r)`
- `void setCustomizationRule ( Rule r)`
- `void setDependencies (java.util.List< Application > dependencies)`
- `void setDescription (java.lang.String s)`
- `void setDescriptions (java.util.Map<java.lang.String,java.lang.String> map)`
- `void setDisableAccountFilter (java.util.List<sailpoint.service.listfilter.ListFilterValue> filter)`
- `void setFeatures (java.util.List< Application.Feature > features)`
- `void setFeaturesString (java.lang.String features)`
- `void setFormPath (java.lang.String key)`
- `void setFormPathRules (java.lang.String key)`
- `void setHibernateProvisioningForms (java.util.List< Form > l)`
- `void setIcon (java.lang.String icon)`
- `void setLockAccountFilter (java.util.List<sailpoint.service.listfilter.ListFilterValue> filter)`
- `void setMaintenanceExpiration (long i)`
- `void setMaintenanceExpirationDate (java.util.Date d)`
- `void setManagedAttributeCustomizationRule ( Rule rule)`
- `void setManagerCorrelationFilter ( Filter.LeafFilter filter)`
- `void setManagerCorrelationRule ( Rule r)`
- `void setNativeChangeAttributes (java.util.List<java.lang.String> ops)`
- `void setNativeChangeAttributeScope (java.lang.String scope)`
- `void setNativeChangeDetectionEnabled (boolean enabled)`
- `void setNativeChangeOperations (java.util.List<java.lang.String> ops)`
- `void setNativeRules (java.util.List<java.lang.String> nativeRules)`
- `void setOldTemplates (java.util.List< Template > l)`
- `void setPasswordPolicies (java.util.List< PasswordPolicyHolder > passwordPolicies)`
- `void setProfileClass (java.lang.String s)`
- `void setProvisioningConfig ( ProvisioningConfig c)`
- `void setProvisioningForms (java.util.List< Form > l)`
- `void setProxiedName (java.lang.String name)`
- `void setProxy ( Application app)`
- `void setRemediators (java.util.List< Identity > remediators)`
- `void setRpaAccountFilter (java.util.List<sailpoint.service.listfilter.ListFilterValue> filter)`
- `void setSchema ( Schema schema)`
- `void setSchemas (java.util.List< Schema > schemas)`
- `void setScorecard ( ApplicationScorecard c)`
- `void setSecondaryOwners (java.util.List< Identity > owners)`
- `void setServiceAccountFilter (java.util.List<sailpoint.service.listfilter.ListFilterValue> filter)`
- `void setSettings (java.lang.String settings)`
- `void setTargetSource ( TargetSource source)`
- `void setTargetSources (java.util.List< TargetSource > sources)`
- `void setTemplateApplication (java.lang.String key)`
- `void setType (java.lang.String type)`
- `void setXmlScorecard ( ApplicationScorecard c)`
- `void setXmlTemplates (java.util.List< Template > l)`
- `boolean supportsFeature ( Application.Feature feature)`
- `boolean supportsGroupProvisioning (java.lang.String schemaObjectType)`
- `void unRegisterListener ()`
- `void visit ( Visitor v)`

---

## ApplicationAccountSelectorRule

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ApplicationAccountSelectorRule`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `Application getApplication ()`
- `Rule getRule ()`
- `void setApplication ( Application _application)`
- `void setRule ( Rule _rule)`

---

## ApplicationActivity.Action

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ApplicationActivity.Action`
- `sailpoint.object.ApplicationActivity.Action`
- `java.io.Serializable`
- `java.lang.Comparable<ApplicationActivity.Action>`
- `sailpoint.tools.MessageKeyHolder`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticApplicationActivity.Action valueOf (java.lang.String name)`
- `staticApplicationActivity.Action[] values ()`

---

## ApplicationActivity.Result

**Package:** `sailpoint.object`

**Description:** An enumeration of states the job can be in. Used to both return the current state, and request a new state.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ApplicationActivity.Result`
- `sailpoint.object.ApplicationActivity.Result`
- `java.io.Serializable`
- `java.lang.Comparable<ApplicationActivity.Result>`
- `sailpoint.tools.MessageKeyHolder`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticApplicationActivity.Result valueOf (java.lang.String name)`
- `staticApplicationActivity.Result[] values ()`

---

## ApplicationActivity

**Package:** `sailpoint.object`

**Description:** The definition of an ApplicationActivity event that comes from underlying applications and will be stored into the database.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.ApplicationActivity`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `void addTimePeriod ( TimePeriod tp)`
- `void addTimePeriods (java.util.Collection< TimePeriod > tps)`
- `ApplicationActivity.Action getAction ()`
- `java.util.Date getCreated ()`
- `java.lang.String getDataSource ()`
- `java.lang.String getDescription ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `java.lang.String getEvent ()`
- `java.lang.String getIdentityId ()`
- `java.lang.String getIdentityName ()`
- `java.lang.String getInfo ()`
- `java.lang.String getInstance ()`
- `java.util.Date getModified ()`
- `java.lang.String getName ()`
- `Identity getOwner ()`
- `ApplicationActivity.Result getResult ()`
- `java.lang.String getSourceApplication ()`
- `java.lang.String getTarget ()`
- `java.util.List<TimePeriod> getTimePeriods ()`
- `java.util.Date getTimeStamp ()`
- `java.lang.String getUser ()`
- `boolean hasName ()`
- `void setAction ( ApplicationActivity.Action action)`
- `void setApplication ( Application app)`
- `void setCreated (java.util.Date created)`
- `void setDataSource (java.lang.String dataSource)`
- `void setDataSourceObject ( ActivityDataSource datasource)`
- `void setDescription (java.lang.String description)`
- `void setIdentity ( Identity identity)`
- `void setIdentityId (java.lang.String identityId)`
- `void setIdentityName (java.lang.String identityName)`
- `void setInfo (java.lang.String info)`
- `void setInstance (java.lang.String ins)`
- `void setModified (java.util.Date modified)`
- `void setName (java.lang.String name)`
- `void setOwner ( Identity owner)`
- `void setResult ( ApplicationActivity.Result status)`
- `void setSourceApplication (java.lang.String source)`
- `void setTarget (java.lang.String target)`
- `void setTimePeriods (java.util.List< TimePeriod > timePeriods)`
- `void setTimeStamp (java.util.Date date)`
- `void setUser (java.lang.String nativeIdentifier)`
- `java.lang.String toString ()`

---

## ApplicationChangeEvent

**Package:** `sailpoint.object`

**Description:** An event that gets fired when an application is created/update/deleted.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.AbstractChangeEvent`
- `sailpoint.object.ApplicationChangeEvent`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:** N/A

---

## ApplicationConfig

**Package:** `sailpoint.object`

**Description:** This class holds data related to the referenced application's impact on risk scoring

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ApplicationConfig`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getActivityMonitoringFactor ()`
- `Application getApplication ()`
- `java.lang.String getUiActivityMonitoringFactor ()`
- `void setActivityMonitoringFactor (java.lang.String activityMonitoringFactor)`
- `void setApplication ( Application application)`
- `void setUiActivityMonitoringFactor (java.lang.String uiFactor)`

---

## ApplicationEntitlementWeights

**Package:** `sailpoint.object`

**Description:** ApplicationEntitlementWeights holds a collection of EntitlementWeights for the specified application.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.ApplicationEntitlementWeights`
- `java.io.Serializable`
- `java.lang.Cloneable`

**Attributes:** N/A

**Methods:**
- `void addWeight ( EntitlementWeight weight)`
- `void addWeights (java.util.Collection< EntitlementWeight > weights)`
- `void clearWeights ()`
- `java.lang.Object clone ()`
- `int getAccountWeight ()`
- `Application getApplication ()`
- `java.util.List<EntitlementWeight> getWeights ()`
- `boolean isEmpty ()`
- `void setAccountWeight (int i)`
- `void setApplication ( Application app)`
- `void setWeights (java.util.List< EntitlementWeight > weights)`

---

## ApplicationScorecard

**Package:** `sailpoint.object`

**Description:** A class holding various scores and statistics calculated from application accounts.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.GenericIndex`
- `sailpoint.object.ApplicationScorecard`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATT_TOTAL_ENTITLEMENTS`
- `static java.lang.String ATT_TOTAL_LINKS`

**Methods:**
- `Application getApplication ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `int getTotalEntitlements ()`
- `int getTotalLinks ()`
- `boolean hasName ()`
- `void setApplication ( Application app)`
- `void setTotalEntitlements (int i)`
- `void setTotalLinks (int i)`
- `void visit ( Visitor v)`

---

## ApprovalItem.ProvisioningState

**Package:** `sailpoint.object`

**Description:** The plan has been executed and successfully applied by an integration.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ApprovalItem.ProvisioningState`
- `sailpoint.object.ApprovalItem.ProvisioningState`
- `java.io.Serializable`
- `java.lang.Comparable<ApprovalItem.ProvisioningState>`
- `sailpoint.tools.MessageKeyHolder`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticApprovalItem.ProvisioningState valueOf (java.lang.String name)`
- `staticApprovalItem.ProvisioningState[] values ()`

---

## ApprovalItem

**Package:** `sailpoint.object`

**Description:** A class used during the approval process. This class will represent a line item in an approval workitem, or business process. These objects are typically contained by an ApprovalSet. ApprovalSets. Which typically live in the attributes map of an Approval WorkItem. In 5.5 the ProvisioningPlan field was deprecated. This is used to use the approvalItems as the basis for Provisioning Checking, but this is now happening using the new IdentityRequest objects.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.AccountItem`
- `sailpoint.object.IdentityItem`
- `sailpoint.object.ApprovalItem`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String ATT_UPDATED_NATIVE_ID`

**Methods:**
- `void add ( Comment comment)`
- `void addRejecter (java.lang.String rejecter)`
- `void approve ()`
- `ApprovalItem clone ()`
- `java.lang.String getApplicationName ()`
- `java.lang.String getApprover ()`
- `java.lang.String getAssignmentId ()`
- `java.lang.Object getAttribute (java.lang.String key)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.util.List<Comment> getComments ()`
- `java.lang.String getDisplayableValue ()`
- `java.lang.String getDisplayName ()`
- `java.lang.String getDisplayValue ()`
- `java.util.Date getEndDate ()`
- `java.lang.String getId ()`
- `java.util.List<ProvisioningPlan.AttributeRequest> getIIQAttributes ()`
- `java.lang.String getOperation ()`
- `java.lang.String getOwner ()`
- `ProvisioningPlan getProvisioningPlan ()`
- `ApprovalItem.ProvisioningState getProvisioningState ()`
- `Recommendation getRecommendation ()`
- `java.lang.String getRejecters ()`
- `java.lang.String getRequesterComments ()`
- `java.util.Date getStartDate ()`
- `WorkItem.State getState ()`
- `boolean isApproved ()`
- `boolean isComplete ()`
- `boolean isProvisioningComplete ()`
- `boolean isRejected ()`
- `boolean matches ( ApprovalItem item)`
- `static java.lang.String parseApprovalItemName (java.lang.String value)`
- `static java.lang.String parseAprovalItemValue (java.lang.String value)`
- `void reject ()`
- `void setApprover (java.lang.String approver)`
- `void setAssignmentId (java.lang.String _assignmentId)`
- `void setAttribute (java.lang.String key, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attrs)`
- `void setComments (java.util.List< Comment > comments)`
- `void setDisplayName (java.lang.String name)`
- `void setDisplayValue (java.lang.String displayValue)`
- `void setEndDate (java.util.Date d)`
- `void setId (java.lang.String id)`
- `void setOperation (java.lang.String op)`
- `void setOwner (java.lang.String owner)`
- `void setProvisioningPlan ( ProvisioningPlan plan)`
- `void setProvisioningState ( ApprovalItem.ProvisioningState provisioningState)`
- `void setRecommendation ( Recommendation recommendation)`
- `void setRejecters (java.lang.String csv)`
- `void setRequesterComments (java.lang.String comments)`
- `void setStartDate (java.util.Date d)`
- `void setState ( WorkItem.State state)`
- `void undo ()`

---

## ApprovalSet

**Package:** `sailpoint.object`

**Description:** A class used during the approval process. This is an object that can be used to examine the items contained in a set. These typically live in the attributes map of an Approval WorkItem.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ApprovalSet`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void add ( ApprovalItem item)`
- `void assimilate ( ApprovalSet set, java.lang.String owner, java.lang.String globalSignOffComments, boolean keepRejected)`
- `staticApprovalSet castApprovalSet (java.lang.Object o)`
- `ApprovalSet clone ()`
- `ApprovalItem find ( ApprovalItem item)`
- `void findAndMergeItem ( ApprovalItem item, java.lang.String owner, java.lang.String globalSignOffComments, boolean keepRejected)`
- `java.util.List<ApprovalItem> getApproved ()`
- `java.util.List<ApprovalItem> getItems ()`
- `java.util.List<ApprovalItem> getRejected ()`
- `boolean hasApproved ()`
- `boolean hasRejected ()`
- `void initializeProvisioningState ()`
- `boolean isAllApproved ()`
- `boolean isAllProvisioned ()`
- `boolean isAllRejected ()`
- `boolean isEmpty ()`
- `void remove ( ApprovalItem item)`
- `void setAllProvisioned ()`
- `void setItems (java.util.List< ApprovalItem > items)`

---

## Archive

**Package:** `sailpoint.object`

**Description:** A base class used to maintain an "archived version" of an object. An archive is simply a copy of an object saved as XML with some extra metadata. The object must be saved as XML so references to other objects are "soft" and do not cause the creation of foreign key constraints that prevent the referenced objects from being deleted. When an archive is "rehydrated" references to objects that no longer exist are pruned. This is intended to be subclassed to provide a different table for each versioned class. SailPointObject.id will be the unique id for this archive. SailPointObject.name will be the name of the archived object at the time the archive was created. SailPointObject.created will be the date the archive was created and must not be changed.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Archive`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.String getArchive ()`
- `java.lang.String getCreator ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `java.lang.String getSourceId ()`
- `int getVersion ()`
- `boolean isNameUnique ()`
- `void setArchive (java.lang.String s)`
- `void setCreator (java.lang.String s)`
- `void setSourceId (java.lang.String s)`
- `void setVersion (int i)`

---

## ArchivedCertificationEntity.Reason

**Package:** `sailpoint.object`

**Description:** Enumeration of reasons an entity is archived in a certification.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ArchivedCertificationEntity.Reason`
- `sailpoint.object.ArchivedCertificationEntity.Reason`
- `java.io.Serializable`
- `java.lang.Comparable<ArchivedCertificationEntity.Reason>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticArchivedCertificationEntity.Reason valueOf (java.lang.String name)`
- `staticArchivedCertificationEntity.Reason[] values ()`

---

## ArchivedCertificationEntity

**Package:** `sailpoint.object`

**Description:** An ArchivedCertificationEntity is a CertificationEntity that is not a part of the live, operational model of a certification. These cannot be acted upon (approved, delegated, etc...) but are retained for reporting and historical purposes.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.ArchivedCertificationEntity`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `void addItem ( CertificationItem item)`
- `java.lang.String getAccountGroup ()`
- `java.lang.String getApplication ()`
- `Certification getCertification ()`
- `CertificationEntity getEntity ()`
- `java.lang.String getEntityName ()`
- `java.lang.String getExplanation ()`
- `java.lang.String getIdentity ()`
- `java.util.List<ArchivedCertificationItem> getItems ()`
- `java.lang.String getNativeIdentity ()`
- `ArchivedCertificationEntity.Reason getReason ()`
- `java.lang.String getReferenceAttribute ()`
- `java.lang.String getSchemaObjectType ()`
- `java.lang.String getTargetDisplayName ()`
- `java.lang.String getTargetId ()`
- `java.lang.String getTargetName ()`
- `boolean hasName ()`
- `void setAccountGroup (java.lang.String accountGroup)`
- `void setApplication (java.lang.String application)`
- `void setCertification ( Certification certification)`
- `void setEntity ( CertificationEntity entity)`
- `void setExplanation (java.lang.String explanation)`
- `void setIdentity (java.lang.String name)`
- `void setItems (java.util.List< ArchivedCertificationItem > items)`
- `void setNativeIdentity (java.lang.String nativeIdentity)`
- `void setReason ( ArchivedCertificationEntity.Reason reason)`
- `void setReferenceAttribute (java.lang.String referenceAttribute)`
- `void setSchemaObjectType (java.lang.String schemaObjectType)`
- `void setTargetDisplayName (java.lang.String targetDisplayName)`
- `void setTargetId (java.lang.String targetId)`
- `void setTargetName (java.lang.String targetName)`

---

## ArchivedCertificationItem

**Package:** `sailpoint.object`

**Description:** Archived record of a CertificationItem which has been excluded from a Certification. The full xml CertificationItem is stored in a clob on the parent ArchivedCertificationEntity. The purpose of this record is really to make the archived data searchable.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.ArchivedCertificationItem`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.util.List<java.lang.String> getApplicationNames ()`
- `java.lang.String getBundle ()`
- `CertificationItem getCertificationItem ()`
- `java.lang.String getConstraintName ()`
- `java.util.List<EntitlementSnapshot> getEntitlements ()`
- `java.lang.String getExceptionApplication ()`
- `java.lang.String getExceptionAttributeName ()`
- `java.lang.String getExceptionAttributeValue ()`
- `java.lang.String getExceptionNativeIdentity ()`
- `java.lang.String getExceptionPermissionRight ()`
- `java.lang.String getExceptionPermissionTarget ()`
- `java.lang.String getItemId ()`
- `ArchivedCertificationEntity getParent ()`
- `java.lang.String getPolicy ()`
- `CertificationItem.SubType getSubType ()`
- `java.lang.String getTargetDisplayName ()`
- `java.lang.String getTargetId ()`
- `java.lang.String getTargetName ()`
- `CertificationItem.Type getType ()`
- `java.lang.String getViolationSummary ()`
- `boolean hasName ()`
- `void setApplicationNames (java.util.List<java.lang.String> applicationNames)`
- `void setBundle (java.lang.String bundle)`
- `void setConstraintName (java.lang.String constraintName)`
- `void setEntitlements (java.util.List< EntitlementSnapshot > entitlements)`
- `void setExceptionApplication (java.lang.String exceptionApplication)`
- `void setExceptionAttributeName (java.lang.String exceptionAttributeName)`
- `void setExceptionAttributeValue (java.lang.String exceptionAttributeValue)`
- `void setExceptionNativeIdentity (java.lang.String exceptionNativeIdentity)`
- `void setExceptionPermissionRight (java.lang.String exceptionPermissionRight)`
- `void setExceptionPermissionTarget (java.lang.String exceptionPermissionTarget)`
- `void setItemId (java.lang.String itemId)`
- `void setParent ( ArchivedCertificationEntity parent)`
- `void setPolicy (java.lang.String policy)`
- `void setSubType ( CertificationItem.SubType subType)`
- `void setTargetDisplayName (java.lang.String targetDisplayName)`
- `void setTargetId (java.lang.String targetId)`
- `void setTargetName (java.lang.String targetName)`
- `void setType ( CertificationItem.Type type)`
- `void setViolationSummary (java.lang.String violationSummary)`

---

## Argument

**Package:** `sailpoint.object`

**Description:** A subcomponent of the Signature model, an object describing the arguments and return values of an abstract function.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.BaseAttributeDefinition`
- `sailpoint.object.Argument`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `boolean equals (java.lang.Object obj)`
- `java.lang.String getDisplayLabel ()`
- `java.lang.String getFilterString ()`
- `java.lang.String getHelpKey ()`
- `java.lang.String getInputTemplate ()`
- `java.lang.String getPrompt ()`
- `java.lang.String getSection ()`
- `boolean isHidden ()`
- `void setFilterString (java.lang.String s)`
- `void setHelpKey (java.lang.String s)`
- `void setHidden (boolean hidden)`
- `void setInputTemplate (java.lang.String inputTemplate)`
- `void setPrompt (java.lang.String s)`
- `void setSection (java.lang.String section)`

---

## AssignableItem

**Package:** `sailpoint.object`

**Description:** Simple interface used on WorkItems and RemediationItems to handle both classes using the same Workflower methods.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `Identity getAssignee ()`
- `java.lang.String getId ()`
- `Identity getOwner ()`
- `void setAssignee ( Identity assignee)`

---

## Assignment

**Package:** `sailpoint.object`

**Description:** Used to record information about assignments and revocations. A list of these will be stored in the preferences area of the identity cube. In 6.0 this was factored out of RoleAssignment so it could spawn AttributeAssignment.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Assignment`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String ASSIGNER_SYSTEM`

**Methods:**
- `java.lang.String getAssigner ()`
- `java.lang.String getAssignmentId ()`
- `java.util.Date getDate ()`
- `java.util.Date getEndDate ()`
- `Request getEndRequest ()`
- `java.lang.String getSource ()`
- `java.util.Date getStartDate ()`
- `Request getStartRequest ()`
- `boolean hasTimeFrame ()`
- `boolean isManual ()`
- `boolean isNegative ()`
- `void setAssigner (java.lang.String s)`
- `void setAssignmentId (java.lang.String s)`
- `void setDate (java.util.Date d)`
- `void setEndDate (java.util.Date end)`
- `void setEndRequest ( Request req)`
- `void setNegative (boolean b)`
- `void setSource (java.lang.String s)`
- `void setSource ( Source s)`
- `void setStartDate (java.util.Date start)`
- `void setStartRequest ( Request req)`

---

## AsyncRequest

**Package:** `sailpoint.object`

**Description:** Represents an asynchronous request in the system. This object encapsulates the details of an asynchronous request, including its status, type, result, and other related information such as reference and batch ID.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.AsyncRequest`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.String getBatchId ()`
- `java.lang.Integer getPollInterval ()`
- `java.lang.String getReference ()`
- `java.lang.String getReferenceType ()`
- `java.lang.String getResult ()`
- `java.lang.String getStatus ()`
- `java.lang.String getType ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `void setBatchId (java.lang.String batchId)`
- `void setPollInterval (java.lang.Integer pollInterval)`
- `void setReference (java.lang.String reference)`
- `void setReferenceType (java.lang.String referenceType)`
- `void setResult (java.lang.String result)`
- `void setStatus (java.lang.String status)`
- `void setType (java.lang.String type)`

---

## Attachment

**Package:** `sailpoint.object`

**Description:** (c) Copyright 2018 SailPoint Technologies, Inc., All Rights Reserved. Used to represent a file that can be attached to other objects in IdentityIQ. Initially this will be used for LCM Requests.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Attachment`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `byte[] getContent ()`
- `boolean isInUse ( SailPointContext context)`
- `void setContent (byte[] content)`

---

## AttributeAssignment

**Package:** `sailpoint.object`

**Description:** List of assignments that are assigned to an identity, typically through the Lifecycle Manager interface. A list of these will be stored in the preferences area of the identity cube. When comparing or using the application stored on this object be careful as these applications can fail to be resolved. Either call resolveApplication or use the ID when trying to resolve the application instance. Since these are stored in an XML blob on the identity these can get stale so consumers make sure they are valid. IdentityIQ does not go through them during refresh to make sure they contain valid attributes and applications.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Assignment`
- `sailpoint.object.AttributeAssignment`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `boolean equals (java.lang.Object o)`
- `java.lang.String getAnnotation ()`
- `java.lang.String getApplicationId ()`
- `java.lang.String getApplicationName ()`
- `java.lang.String getInstance ()`
- `java.util.List<java.lang.Object> getListValue ()`
- `java.lang.String getName ()`
- `java.lang.String getNativeIdentity ()`
- `java.lang.String getStringValue ()`
- `java.lang.String getTargetCollector ()`
- `ManagedAttribute.Type getType ()`
- `java.lang.Object getValue ()`
- `int hashCode ()`
- `boolean isApplicationCaseInsensitive ()`
- `boolean isPermission ()`
- `boolean isValid ( Resolver resolver)`
- `boolean matches ( AttributeAssignment obj)`
- `Application resolveApplication ( Resolver resolver)`
- `void setAnnotation (java.lang.String annotation)`
- `void setApplicationCaseInsensitive (boolean applicationCaseInsensitive)`
- `void setApplicationId (java.lang.String applicationId)`
- `void setApplicationName (java.lang.String applicationName)`
- `void setInstance (java.lang.String instance)`
- `void setName (java.lang.String name)`
- `void setNativeIdentity (java.lang.String nativeIdentity)`
- `void setTargetCollector (java.lang.String targetCollector)`
- `void setType ( ManagedAttribute.Type type)`
- `void setValue (java.lang.Object value)`
- `ProvisioningPlan.AccountRequest toAccountRequest ( ProvisioningPlan.AccountRequest.Operation acctReqOp, ProvisioningPlan.Operation attrReqOp)`

---

## AttributeDefinition.AttributeType

**Package:** `sailpoint.object`

**Description:** Enum for the Primitive types for Account Schema Attribute Definitions

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `AttributeDefinition.AttributeType`
- `sailpoint.object.AttributeDefinition.AttributeType`
- `java.io.Serializable`
- `java.lang.Comparable<AttributeDefinition.AttributeType>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getDisplayName ()`
- `java.lang.String getDisplayName (java.util.Locale loc, java.util.TimeZone tz)`
- `java.lang.String getValue ()`
- `static boolean hasValue (java.lang.String value)`
- `staticAttributeDefinition.AttributeType valueOf (java.lang.String name)`
- `staticAttributeDefinition.AttributeType[] values ()`

---

## AttributeDefinition.CloudAccessManagementType

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `AttributeDefinition.CloudAccessManagementType`
- `sailpoint.object.AttributeDefinition.CloudAccessManagementType`
- `java.io.Serializable`
- `java.lang.Comparable<AttributeDefinition.CloudAccessManagementType>`

**Attributes:** N/A

**Methods:**
- `staticAttributeDefinition.CloudAccessManagementType valueOf (java.lang.String name)`
- `staticAttributeDefinition.CloudAccessManagementType[] values ()`

---

## AttributeDefinition.UserInterfaceInputType

**Package:** `sailpoint.object`

**Description:** The UserInterfaceInputType enumeration specifies how an attribute should be edited in the user interface. A null value means that the attribute cannot be edited.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `AttributeDefinition.UserInterfaceInputType`
- `sailpoint.object.AttributeDefinition.UserInterfaceInputType`
- `java.io.Serializable`
- `java.lang.Comparable<AttributeDefinition.UserInterfaceInputType>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticAttributeDefinition.UserInterfaceInputType valueOf (java.lang.String name)`
- `staticAttributeDefinition.UserInterfaceInputType[] values ()`

---

## AttributeDefinition

**Package:** `sailpoint.object`

**Description:** The definition of an application schema attribute.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.BaseAttributeDefinition`
- `sailpoint.object.AttributeDefinition`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getCompositeSourceApplication ()`
- `java.lang.String getCompositeSourceAttribute ()`
- `int getCorrelationKey ()`
- `java.lang.String getInternalName ()`
- `java.lang.String getInternalOrName ()`
- `java.lang.String getObjectMapping ()`
- `AttributeDefinition.UserInterfaceInputType getRemediationModificationType ()`
- `java.lang.String getSchemaObjectType ()`
- `java.lang.String getSource ()`
- `boolean isCorrelationKeyAssigned ()`
- `boolean isEditable ()`
- `boolean isEntitlement ()`
- `boolean isGroup ()`
- `boolean isGroupAttribute ()`
- `boolean isIndexed ()`
- `boolean isManaged ()`
- `boolean isMinable ()`
- `boolean isRemediationModifiable ()`
- `void setCompositeSource (java.lang.String application, java.lang.String attribute)`
- `void setCorrelationKey (int i)`
- `void setCorrelationKeyAssigned (boolean b)`
- `void setEntitlement (boolean entitlement)`
- `void setGroup (boolean b)`
- `void setIndexed (boolean b)`
- `void setInternalName (java.lang.String s)`
- `void setManaged (boolean b)`
- `void setMinable (boolean _minable)`
- `void setObjectMapping (java.lang.String s)`
- `void setRemediationModificationType ( AttributeDefinition.UserInterfaceInputType type)`
- `void setSchemaObjectType (java.lang.String _objectType)`
- `void setSource (java.lang.String source)`
- `static java.lang.String[] tokenizeSource (java.lang.String source)`

---

## AttributeMetaData

**Package:** `sailpoint.object`

**Description:** A class encapsulating information about how an extended attribute got its value. Originally this was designed to track manual modifications to the attribute made from the UI so they could be preserved on the next aggregation or refresh. It was later extended to track of the source of an attribute in cases where there is more than one AttributeSource (in practice only for identities). These two uses are mutually exclusive, when "userName" is non-null this represents the state of a manual edit. The "modified" property will have the data of that edit and "lastValue" will hold the previous value. When "userName" is null this means that the attribute was derived automatically from an AttributeSource and the "source" property will have a description of that source. This is only used in cases where there are multiple sources and you need to know when you can null the value. With multiple sources a null value is only promoted if the current value was promoted from the same source that is now providing a null value. The value for "source" will be the derived "key" property of the AttributeSource that supplied the value for this attribute.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.AttributeMetaData`
- `java.io.Serializable`
- `sailpoint.tools.xml.IXmlEqualable<AttributeMetaData>`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `boolean contentEquals ( AttributeMetaData other)`
- `java.lang.String getAttribute ()`
- `java.lang.Object getLastValue ()`
- `java.util.Date getModified ()`
- `java.lang.String getSource ()`
- `java.lang.String getUser ()`
- `void incrementModified ()`
- `void setAttribute (java.lang.String name)`
- `void setLastValue (java.lang.Object val)`
- `void setModified (java.util.Date mod)`
- `void setSource (java.lang.String s)`
- `void setUser (java.lang.String userName)`

---

## AttributeSource

**Package:** `sailpoint.object`

**Description:** Part of the ObjectAttribute model. Used for attributes whose values can be derived from one of several sources. In practice these are used only for Identity attributes. The attribute can be sourced from one of three places: An application account attribute A rule applied to an application account link A rule applied to the entire identity cube When sourcing directly from an account attribute the application and name properties must be set and the instance can optionally be set if using template applications. When sourcing from an account rule the application and rule properties must be set, the instance is optional. The rule is passed the Link object representing the account, as well as the Identity, the AttributeDefinition, and this AttributeSource. The name property is optional but can be set if the rule is a generic formatting rule that can be used with several attributes. If no application is specified, then this represents a "global rule" that is applied to the entire identity cube. The rule property must be set to a Rule that will receive the Identity, the AttributeDefinition, and this AttributeSource. The instance and name properties are normally ignored by the rule. In theory you could use these to pass arguments to the rule but since these are not settable in the UI this is not recommended.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.AttributeSource`
- `java.io.Serializable`

**Attributes:** N/A

**Methods:**
- `Application getApplication ()`
- `java.lang.String getInstance ()`
- `java.lang.String getKey ()`
- `java.lang.String getName ()`
- `Rule getRule ()`
- `boolean isMatch ( AttributeSource other)`
- `void load ()`
- `void setApplication ( Application a)`
- `void setInstance (java.lang.String inst)`
- `void setName (java.lang.String name)`
- `void setRule ( Rule r)`

---

## AttributeTarget

**Package:** `sailpoint.object`

**Description:** Part of the ObjectAttribute model. Used for attribute synchronization to push attribute values to other target applications. In practice these are used only for Identity attributes. These must contain at least an application and attribute name to specify where the value will be pushed. Additionally, a rule can be specified to transform the value being pushed to the target. When an identity has multiple accounts on the same application, the provisionAllAccounts flag indicates whether to push the value to all accounts or require account selection.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.AttributeSource`
- `sailpoint.object.AttributeTarget`
- `java.io.Serializable`

**Attributes:** N/A

**Methods:**
- `boolean isProvisionAllAccounts ()`
- `void setProvisionAllAccounts (boolean provisionAll)`

---

## Attributes<K,​V>

**Package:** `sailpoint.object`

**Description:** An extension of HashMap that adds convenience coercion methods. This class is used throughout the model to represent collections of dynamic attributes.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `java.util.AbstractMap<K,​V>`
- `java.util.HashMap<K,​V>`
- `sailpoint.object.Attributes<K,​V>`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `java.util.Map<K,​V>`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `staticAttributes<?,​?> castAttributes (java.lang.Object o)`
- `boolean getBoolean (java.lang.String attributeName)`
- `boolean getBoolean (java.lang.String attributeName, boolean defaultValue)`
- `java.lang.Boolean getBooleanObject (java.lang.String attributeName)`
- `java.util.Date getDate (java.lang.String attributeName)`
- `float getFloat (java.lang.String attributeName)`
- `float getFloat (java.lang.String attributeName, float defaultValue)`
- `int getInt (java.lang.String attributeName)`
- `int getInt (java.lang.String attributeName, int defaultValue)`
- `java.lang.Integer getInteger (java.lang.String attributeName)`
- `java.util.List<java.lang.String> getKeys ()`
- `java.util.List getList (java.lang.String attributeName)`
- `java.util.List getList (java.lang.String attributeName, boolean csvToList)`
- `long getLng (java.lang.String attributeName)`
- `long getLng (java.lang.String attributeName, long defaultValue)`
- `java.lang.Long getLong (java.lang.String attributeName)`
- `java.util.Map<K,​V> getMap ()`
- `java.lang.String getOriginalXml ()`
- `java.lang.String getString (java.lang.String attributeName)`
- `java.util.List<java.lang.String> getStringList (java.lang.String name)`
- `Attributes<K,​V> mediumClone ()`
- `void putClean ( K key, V value)`
- `void setMap (java.util.Map< K , V > map)`
- `void setOriginalXml (java.lang.String xml)`

---

## AuditConfig.AuditAction

**Package:** `sailpoint.object`

**Description:** These are simpler than AuditClass since they have only one boolean enable flag, but it also serves as a container for other metadata like displayName and the list itself determines what is displayed in the configuration UI.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.AuditConfig.AuditAction`

**Attributes:** N/A

**Methods:**
- `java.lang.String getDisplayableName ()`
- `java.lang.String getDisplayName ()`
- `java.lang.String getName ()`
- `boolean isEnabled ()`
- `boolean isObsolete ()`
- `void setDisplayName (java.lang.String s)`
- `void setEnabled (boolean b)`
- `void setName (java.lang.String s)`
- `void setObsolete (boolean b)`
- `java.lang.String toString ()`

---

## AuditConfig.AuditAttribute

**Package:** `sailpoint.object`

**Description:** Audit configuration for individual attributes. The action for these will be "change". The target will be formatted as : string1 is the attribute name string2 is the operation: set, add, remove string3 is a CSV of the values

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.AuditConfig.AuditAttribute`
- `sailpoint.tools.xml.IXmlEqualable<AuditConfig.AuditAttribute>`

**Attributes:** N/A

**Methods:**
- `boolean contentEquals ( AuditConfig.AuditAttribute other)`
- `java.lang.String getClassName ()`
- `java.lang.String getDisplayableName ()`
- `java.lang.String getDisplayName ()`
- `java.lang.String getName ()`
- `boolean isEnabled ()`
- `boolean isObsolete ()`
- `void setClassName (java.lang.String s)`
- `void setDisplayName (java.lang.String s)`
- `void setEnabled (boolean b)`
- `void setName (java.lang.String s)`
- `void setObsolete (boolean b)`
- `java.lang.String toString ()`

---

## AuditConfig.AuditClass

**Package:** `sailpoint.object`

**Description:** Each of the major SailPointObject classes can have a different audit configuration. Might be nice to have a global default.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.AuditConfig.AuditClass`

**Attributes:** N/A

**Methods:**
- `protected java.util.Map<java.lang.String,​java.lang.String> getActionMap ()`
- `java.lang.String getDisplayableName ()`
- `java.lang.String getDisplayName ()`
- `java.lang.String getName ()`
- `boolean isCreate ()`
- `boolean isDelete ()`
- `boolean isEnabled (java.lang.String action)`
- `boolean isInvisible ()`
- `boolean isObsolete ()`
- `boolean isUpdate ()`
- `void setCreate (boolean b)`
- `void setDelete (boolean b)`
- `void setDisplayName (java.lang.String s)`
- `void setName (java.lang.String s)`
- `void setObsolete (boolean b)`
- `void setUpdate (boolean b)`
- `java.lang.String toString ()`

---

## AuditConfig.AuditSCIMResource

**Package:** `sailpoint.object`

**Description:** Audit configuration for CRUD operations on SCIM endpoints.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.AuditConfig.AuditClass`
- `sailpoint.object.AuditConfig.AuditSCIMResource`

**Attributes:** N/A

**Methods:**
- `protected java.util.Map<java.lang.String,​java.lang.String> getActionMap ()`
- `boolean isInvisible ()`
- `boolean isRead ()`
- `void setRead (boolean b)`
- `java.lang.String toString ()`

---

## AuditConfig

**Package:** `sailpoint.object`

**Description:** Configuration for the internal audit log. There are four lists of config objects, one for general operations not associated with any particular model class, one for CRUD operations on model classes, one for CRUD operations on SCIM Rest Resources and one for changes to individual attributes. The objects in the lists serve both to hold the audit selections, as well as give the UI the list of all things that can be audited. In other words, if something does not appear on the list it will not appear in the UI. If you write AuditConfig classes in XML this cannot be a "sparse" list, you need to include an entry for all general operations and all classes that can be audited even if auditing will be disabled.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.AuditConfig`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `Cacheable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String OBJ_NAME`

**Methods:**
- `void add ( AuditConfig.AuditAttribute att)`
- `java.util.List<AuditConfig.AuditAction> getActions ()`
- `java.util.List<AuditConfig.AuditAttribute> getAttributes ()`
- `AuditConfig.AuditAction getAuditAction (java.lang.String name)`
- `AuditConfig.AuditAttribute getAuditAttribute (java.lang.Class cls, java.lang.String name)`
- `AuditConfig.AuditAttribute getAuditAttribute (java.lang.String cls, java.lang.String name)`
- `AuditConfig.AuditClass getAuditClass (java.lang.String name)`
- `staticAuditConfig getAuditConfig ()`
- `AuditConfig.AuditSCIMResource getAuditSCIMResource (java.lang.String resourceName)`
- `protectedAuditConfig.AuditSCIMResource getAuditSCIMResource ( AuditEvent.SCIMResource resource)`
- `java.util.List<AuditConfig.AuditClass> getClasses ()`
- `java.util.List<AuditConfig.AuditSCIMResource> getResources ()`
- `protected java.util.Map<AuditEvent.SCIMResource,​AuditConfig.AuditSCIMResource> getSCIMResourceMap ()`
- `boolean isAudited ( SailPointObject obj)`
- `boolean isEnabled (java.lang.Class cls, java.lang.String name)`
- `boolean isEnabled (java.lang.String action)`
- `boolean isEnabled (java.lang.String action, AuditEvent.SCIMResource resource)`
- `boolean isEnabled (java.lang.String action, SailPointObject obj)`
- `void remove ( AuditConfig.AuditAttribute att)`
- `void setActions (java.util.List< AuditConfig.AuditAction > actions)`
- `void setAttributes (java.util.List< AuditConfig.AuditAttribute > attributes)`
- `void setClasses (java.util.List< AuditConfig.AuditClass > classes)`
- `void setResources (java.util.List< AuditConfig.AuditSCIMResource > resources)`

---

## AuditEvent.SCIMResource

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `AuditEvent.SCIMResource`
- `sailpoint.object.AuditEvent.SCIMResource`
- `java.io.Serializable`
- `java.lang.Comparable<AuditEvent.SCIMResource>`

**Attributes:** N/A

**Methods:**
- `staticAuditEvent.SCIMResource valueOf (java.lang.String name)`
- `staticAuditEvent.SCIMResource[] values ()`

---

## AuditEvent

**Package:** `sailpoint.object`

**Description:** Class used for the audit log of internal system events. Actions are extensible and defined in the AuditConfig. Some name constants are defined here for use in system code.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.AuditEvent`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String AccessHistoryRemoveEvents`
- `static java.lang.String AccessRequestStart`
- `static java.lang.String AccountsRequestStart`
- `static java.lang.String ActionApprove`
- `static java.lang.String ActionApproveLineItem`
- `static java.lang.String ActionApprovePamRequest`
- `static java.lang.String ActionAssignment`
- `static java.lang.String ActionAttachmentsPruned`
- `static java.lang.String ActionAttributeSync`
- `static java.lang.String ActionCertificationArchivesPruned`
- `static java.lang.String ActionCertificationItemsAutomaticallyDecided`
- `static java.lang.String ActionCertificationItemsPhased`
- `static java.lang.String ActionCertificationsArchived`
- `static java.lang.String ActionCertificationsAutomaticallyClosed`
- `static java.lang.String ActionCertificationsFinished`
- `static java.lang.String ActionCertificationsPhased`
- `static java.lang.String ActionCertificationsPruned`
- `static java.lang.String ActionChange`
- `static java.lang.String ActionCompleteDelegation`
- `static java.lang.String ActionContinuousCertItemsOverdue`
- `static java.lang.String ActionContinuousCertItemsRequired`
- `static java.lang.String ActionContinuousCertsProcessed`
- `static java.lang.String ActionCreate`
- `static java.lang.String ActionDelegate`
- `static java.lang.String ActionDelete`
- `static java.lang.String ActionDisableRole`
- `static java.lang.String ActionEmailFailure`
- `static java.lang.String ActionEmailSent`
- `static java.lang.String ActionEscalate`
- `static java.lang.String ActionException`
- `static java.lang.String ActionExpansion`
- `static java.lang.String ActionExpire`
- `static java.lang.String ActionForward`
- `static java.lang.String ActionHistoriesPruned`
- `static java.lang.String ActionIdentityCorrelation`
- `static java.lang.String ActionIdentityRequestPruned`
- `static java.lang.String ActionIdentityTriggerEvent`
- `static java.lang.String ActionImport`
- `static java.lang.String ActionInactiveWorkItemsForwarded`
- `static java.lang.String ActionInterceptedDeletePruned`
- `static java.lang.String ActionLinkMoved`
- `static java.lang.String ActionLogin`
- `static java.lang.String ActionLoginFailure`
- `static java.lang.String ActionLogout`
- `static java.lang.String ActionNativeIdentityChangeDetected`
- `static java.lang.String ActionNativeIdentityChangeEventsPruned`
- `static java.lang.String ActionPendingAttachmentsPruned`
- `static java.lang.String ActionPostCommitNotificationObjectsPruned`
- `static java.lang.String ActionProvision`
- `static java.lang.String ActionProvisioningTransactionsPruned`
- `static java.lang.String ActionRead`
- `static java.lang.String ActionReassign`
- `static java.lang.String ActionReject`
- `static java.lang.String ActionRejectLineItem`
- `static java.lang.String ActionRejectPamRequest`
- `static java.lang.String ActionRemediate`
- `static java.lang.String ActionRemediationAssignment`
- `static java.lang.String ActionRemediationsScanned`
- `static java.lang.String ActionRequestsPruned`
- `static java.lang.String ActionRescindCertification`
- `static java.lang.String ActionRevokeDelegation`
- `static java.lang.String ActionRoleSunrise`
- `static java.lang.String ActionRoleSunset`
- `static java.lang.String ActionRun`
- `static java.lang.String ActionScopesDenormalized`
- `static java.lang.String ActionSignoff`
- `static java.lang.String ActionSignoffEscalation`
- `static java.lang.String ActionStartWorkflow`
- `static java.lang.String ActionSyslogEventsPruned`
- `static java.lang.String ActionTaskResultsPruned`
- `static java.lang.String ActionUpdate`
- `static java.lang.String ActionUpdateRole`
- `static java.lang.String ActionViolationAcknowledge`
- `static java.lang.String ActionViolationAllowException`
- `static java.lang.String ActionViolationCorrection`
- `static java.lang.String ActionViolationDelegate`
- `static java.lang.String AlertActionCreated`
- `static java.lang.String AlertProcessed`
- `static java.lang.String APIConfigurationChange`
- `static java.lang.String ATT_ESIG_SIGNER`
- `static java.lang.String ATT_ESIG_TEXT`
- `static java.lang.String AttAssignedRoles`
- `static java.lang.String AttCapabilities`
- `static java.lang.String AttControlledScopes`
- `static java.lang.String AttCorrelationStatus`
- `static java.lang.String AttPassword`
- `static java.lang.String AttScope`
- `static java.lang.String AuditConfigChange`
- `static java.lang.String AuthAnswerIncorrect`
- `static java.lang.String CancelWorkflow`
- `static java.lang.String ChangeAdd`
- `static java.lang.String ChangeRemove`
- `static java.lang.String ChangeSet`
- `static java.lang.String ChatNotificationFailure`
- `static java.lang.String ChatNotificationSuccess`
- `static java.lang.String Comment`
- `static java.lang.String DebugObjectBrowserChange`
- `static java.lang.String Disable`
- `static java.lang.String Enable`
- `static java.lang.String EntitlementAdd`
- `static java.lang.String EntitlementRemove`
- `static java.lang.String EntitlementsRequestStart`
- `static java.lang.String ExpiredPasswordChange`
- `static java.lang.String ForgotPasswordChange`
- `static java.lang.String Forward`
- `static java.lang.String[] IdentityAttributes`
- `static java.lang.String IdentityCreateRequestStart`
- `static java.lang.String IdentityEditRequestStart`
- `static java.lang.String IdentityLocked`
- `static java.lang.String IdentityUnlocked`
- `static java.lang.String IdentityWorkgroupAdd`
- `static java.lang.String IdentityWorkgroupRemove`
- `static java.lang.String LoginConfigChange`
- `static java.lang.String ManualChange`
- `static java.lang.String PasswordChange`
- `static java.lang.String PasswordChangeFailure`
- `static java.lang.String PasswordPolicyChange`
- `static java.lang.String PluginConfigurationChanged`
- `static java.lang.String PluginDisabled`
- `static java.lang.String PluginEnabled`
- `static java.lang.String PluginInstalled`
- `static java.lang.String PluginUninstalled`
- `static java.lang.String PluginUpgraded`
- `static java.lang.String ProvisioningComplete`
- `static java.lang.String ProvisioningFailure`
- `static java.lang.String RoleAdd`
- `static java.lang.String RoleRemove`
- `static java.lang.String RolesRequestStart`
- `static java.lang.String SessionTimeout`
- `static java.lang.String SeverUpDown`
- `static java.lang.String SourceViolationCertification`
- `static java.lang.String SourceViolationManage`
- `static java.lang.String Unlock`

**Methods:**
- `void checkLimits ()`
- `java.lang.String getAccountName ()`
- `java.lang.String getAction ()`
- `java.lang.String getApplication ()`
- `java.lang.Object getAttribute (java.lang.String name)`
- `java.lang.String getAttributeName ()`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getAttributeValue ()`
- `java.lang.String getClientHost ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `java.lang.String getInstance ()`
- `java.lang.String getInterface ()`
- `int getPseudoCreated ()`
- `java.lang.String getSailPointObjectName ()`
- `java.lang.String getServerHost ()`
- `java.lang.String getSource ()`
- `java.lang.String getString (java.lang.String name)`
- `java.lang.String getString1 ()`
- `java.lang.String getString2 ()`
- `java.lang.String getString3 ()`
- `java.lang.String getString4 ()`
- `java.lang.String getTarget ()`
- `java.lang.String getTrackingId ()`
- `boolean hasName ()`
- `static java.lang.String limit (java.lang.String src, int max)`
- `static java.lang.String limitArg (java.lang.String src)`
- `static java.lang.String limitTarget (java.lang.String src)`
- `void setAccountName (java.lang.String accountName)`
- `void setAction (java.lang.String action)`
- `void setApplication (java.lang.String app)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributeName (java.lang.String attribute)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attr)`
- `void setAttributeValue (java.lang.String value)`
- `void setClientHost (java.lang.String host)`
- `void setInstance (java.lang.String instance)`
- `void setInterface (java.lang.String s)`
- `void setServerHost (java.lang.String host)`
- `void setSource (java.lang.String source)`
- `void setString1 (java.lang.String string)`
- `void setString2 (java.lang.String string)`
- `void setString3 (java.lang.String string)`
- `void setString4 (java.lang.String string)`
- `void setTarget (java.lang.String s)`
- `void setTrackingId (java.lang.String trackingId)`
- `java.lang.String toString ()`

---

## AuthenticationAnswer

**Package:** `sailpoint.object`

**Description:** An answer to an authentication question for an identity.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.AuthenticationAnswer`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.String getAnswer ()`
- `Identity getIdentity ()`
- `AuthenticationQuestion getQuestion ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `void setAnswer (java.lang.String answer)`
- `void setIdentity ( Identity identity)`
- `void setQuestion ( AuthenticationQuestion question)`
- `void visit ( Visitor v)`

---

## AuthenticationQuestion

**Package:** `sailpoint.object`

**Description:** An authentication question is a question that can be answered by users that are attempting to authenticate without a password (for example, when a password is forgotten).

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.AuthenticationQuestion`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `java.lang.String getQuestion ()`
- `java.lang.String getQuestion (java.util.Locale locale)`
- `java.lang.String[] getUniqueKeyProperties ()`
- `boolean hasName ()`
- `void setQuestion (java.lang.String question)`
- `void visit ( Visitor v)`

---

## BaseAttributeDefinition

**Package:** `sailpoint.object`

**Description:** The fundamental properties required for the definition of an attribute.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.BaseAttributeDefinition`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `protected java.util.List<java.lang.Object> _allowedValues`
- `protected java.lang.String _categoryName`
- `protected boolean _required`
- `static java.lang.String TYPE_BOOLEAN`
- `static java.lang.String TYPE_COMPLEX`
- `static java.lang.String TYPE_DATE`
- `static java.lang.String TYPE_IDENTITY`
- `static java.lang.String TYPE_INT`
- `static java.lang.String TYPE_LONG`
- `static java.lang.String TYPE_PERMISSION`
- `static java.lang.String TYPE_RULE`
- `static java.lang.String TYPE_SCOPE`
- `static java.lang.String TYPE_SECRET`
- `static java.lang.String TYPE_STRING`

**Methods:**
- `void assimilate ( BaseAttributeDefinition src)`
- `java.util.List<Filter.LogicalOperation> getAllowedOperations ()`
- `java.util.List<java.lang.Object> getAllowedValues ()`
- `static java.util.Comparator<BaseAttributeDefinition> getByDisplayableNameComparator ()`
- `static java.util.Comparator<BaseAttributeDefinition> getByDisplayableNameComparator (java.util.Locale locale)`
- `java.lang.String getCategoryName ()`
- `java.lang.Object getDefaultValue ()`
- `java.lang.String getDescription ()`
- `java.lang.String getDisplayableName ()`
- `java.lang.String getDisplayableName (java.util.Locale locale)`
- `java.lang.String getDisplayName ()`
- `java.lang.String getName ()`
- `java.lang.String getType ()`
- `boolean isComplex ()`
- `boolean isMulti ()`
- `boolean isMultiValued ()`
- `boolean isRequired ()`
- `boolean isType (java.lang.String type)`
- `void setAllowedValues (java.util.List<java.lang.Object> val)`
- `void setCategoryName (java.lang.String categoryName)`
- `void setDefaultValue (java.lang.Object defaultValue)`
- `void setDescription (java.lang.String description)`
- `void setDisplayName (java.lang.String name)`
- `void setMulti (boolean b)`
- `void setMultiValued (boolean b)`
- `void setName (java.lang.String name)`
- `void setRequired (boolean required)`
- `void setType (java.lang.String type)`

---

## BaseConstraint

**Package:** `sailpoint.object`

**Description:** Base class for all Policy constraints, also known as "policy rules" in the UI. SailPointObject.name is used as the "short name". SailPointObject.description is used as the "long name". SailPointobject.disabled is used to mark disabled constraints.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.BaseConstraint`
- `java.io.Serializable`
- `PolicyViolation.IPolicyViolationOwnerSource`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ARG_VIOLATION_RULE`
- `static java.lang.String ARG_VIOLATION_WORKFLOW`

**Methods:**
- `java.lang.Object getArgument (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getArguments ()`
- `java.lang.String getCompensatingControl ()`
- `java.lang.String getDisplayableName ()`
- `Policy getPolicy ()`
- `java.lang.String getRemediationAdvice ()`
- `java.lang.String getString (java.lang.String name)`
- `Identity getViolationOwner ()`
- `Rule getViolationOwnerRule ()`
- `Policy.ViolationOwnerType getViolationOwnerType ()`
- `java.lang.String getViolationRule ()`
- `Rule getViolationRuleObject ( Resolver r)`
- `java.lang.String getViolationWorkflow ()`
- `Workflow getViolationWorkflow ( Resolver r)`
- `int getWeight ()`
- `void load ()`
- `void setArgument (java.lang.String name, java.lang.Object value)`
- `void setArguments ( Attributes <java.lang.String,java.lang.Object> args)`
- `void setCompensatingControl (java.lang.String cc)`
- `void setPolicy ( Policy p)`
- `void setRemediationAdvice (java.lang.String s)`
- `void setViolationOwner ( Identity val)`
- `void setViolationOwnerRule ( Rule val)`
- `void setViolationOwnerType ( Policy.ViolationOwnerType val)`
- `void setViolationRule (java.lang.String s)`
- `void setViolationWorkflow (java.lang.String s)`
- `void setWeight (int weight)`

---

## BaseExecutor

**Package:** `sailpoint.object`

**Description:** Ask the executor to perform a command encapsulated in a Request.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `void processCommand ( Request cmd)`
- `boolean terminate ()`

---

## BaseIdentityIndex

**Package:** `sailpoint.object`

**Description:** A class holding various scores and statistics calculated for identities or groups of identities. This is the base class for both GroupIndex and Scorecard.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.GenericIndex`
- `sailpoint.object.BaseIdentityIndex`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `void assimilate ( BaseIdentityIndex src)`
- `int getBusinessRoleScore ()`
- `int getCertificationScore ()`
- `int getEntitlementScore ()`
- `int getGenericScore (java.lang.String name)`
- `int getPolicyScore ()`
- `int getRawBusinessRoleScore ()`
- `int getRawEntitlementScore ()`
- `int getRawPolicyScore ()`
- `int getScore (java.lang.String name)`
- `int getTotalApprovals ()`
- `int getTotalDelegations ()`
- `int getTotalMitigations ()`
- `int getTotalRemediations ()`
- `int getTotalViolations ()`
- `boolean isDifferent ( BaseIdentityIndex other)`
- `boolean isDifferentCompositeScore ( Scorecard other)`
- `void reset ()`
- `void setBusinessRoleScore (int i)`
- `void setCertificationScore (int i)`
- `void setEntitlementScore (int i)`
- `void setPolicyScore (int i)`
- `void setRawBusinessRoleScore (int i)`
- `void setRawEntitlementScore (int i)`
- `void setRawPolicyScore (int i)`
- `void setTotalApprovals (int totalApprovals)`
- `void setTotalDelegations (int totalDelegations)`
- `void setTotalMitigations (int totalMitigations)`
- `void setTotalRemediations (int TotalRemediations)`
- `void setTotalViolations (int i)`

---

## BatchRequest.Status

**Package:** `sailpoint.object`

**Description:** Batch request completion states.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `BatchRequest.Status`
- `sailpoint.object.BatchRequest.Status`
- `java.io.Serializable`
- `java.lang.Comparable<BatchRequest.Status>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticBatchRequest.Status valueOf (java.lang.String name)`
- `staticBatchRequest.Status[] values ()`

---

## BatchRequest

**Package:** `sailpoint.object`

**Description:** This class represents the batch request file. It contains the actual file contents for use later by the task scheduler. This object will also track the request execution status.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.BatchRequest`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.util.List<BatchRequestItem> getBatchRequestItems ()`
- `int getCompletedCount ()`
- `java.util.Date getCompletedDate ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `int getErrorCount ()`
- `Message getErrorMessage ()`
- `java.lang.String getFileContents ()`
- `java.lang.String getFileName ()`
- `java.lang.String getHeader ()`
- `int getInvalidCount ()`
- `java.lang.String getMessage ()`
- `int getRecordCount ()`
- `Attributes<java.lang.String,​java.lang.Object> getRunConfig ()`
- `java.util.Date getRunDate ()`
- `BatchRequest.Status getStatus ()`
- `java.lang.String[] getUniqueKeyProperties ()`
- `boolean hasName ()`
- `void setBatchRequestItems (java.util.List< BatchRequestItem > items)`
- `void setCompletedCount (int cc)`
- `void setCompletedDate (java.util.Date d)`
- `void setErrorCount (int rc)`
- `void setErrorMessage ( Message msg)`
- `void setFileContents (java.lang.String fc)`
- `void setFileName (java.lang.String fname)`
- `void setHeader (java.lang.String hdr)`
- `void setInvalidCount (int rc)`
- `void setMessage (java.lang.String msg)`
- `void setRecordCount (int rc)`
- `void setRunConfig ( Attributes <java.lang.String,java.lang.Object> st)`
- `void setRunDate (java.util.Date d)`
- `void setStatus ( BatchRequest.Status st)`
- `void updateStats ( BatchRequestItem.Result result)`
- `void visit ( Visitor v)`

---

## BatchRequestItem.Result

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `BatchRequestItem.Result`
- `sailpoint.object.BatchRequestItem.Result`
- `java.io.Serializable`
- `java.lang.Comparable<BatchRequestItem.Result>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticBatchRequestItem.Result valueOf (java.lang.String name)`
- `staticBatchRequestItem.Result[] values ()`

---

## BatchRequestItem.Status

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `BatchRequestItem.Status`
- `sailpoint.object.BatchRequestItem.Status`
- `java.io.Serializable`
- `java.lang.Comparable<BatchRequestItem.Status>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticBatchRequestItem.Status valueOf (java.lang.String name)`
- `staticBatchRequestItem.Status[] values ()`

---

## BatchRequestItem

**Package:** `sailpoint.object`

**Description:** Object that represents one line in a batch request file

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.BatchRequestItem`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `BatchRequest getBatchRequest ()`
- `Message getErrorMessage ()`
- `java.lang.String getIdentityRequestId ()`
- `java.lang.String getMessage ()`
- `java.lang.String getRequestData ()`
- `BatchRequestItem.Result getResult ()`
- `BatchRequestItem.Status getStatus ()`
- `java.lang.String getTargetIdentityId ()`
- `boolean hasName ()`
- `void setBatchRequest ( BatchRequest br)`
- `void setErrorMessage ( Message msg)`
- `void setIdentityRequestId (java.lang.String rq)`
- `void setMessage (java.lang.String msg)`
- `void setRequestData (java.lang.String rq)`
- `void setResult ( BatchRequestItem.Result s)`
- `void setStatus ( BatchRequestItem.Status s)`
- `void setTargetIdentityId (java.lang.String s)`
- `void visit ( Visitor v)`

---

## BulkIdJoin

**Package:** `sailpoint.object`

**Description:** Utility table for helping with bulk IN queries. Sqlserver IN query parameters maxes out at 2100 so we need to move the IN params into a join table and use a subquery to join the params. For example, Filter.in("manager.id", managerIds) would be converted to Filter.subquery("manager.id", BulkJoinId.class, "joinId", Filter.eq("joinProperty", "manager.id") The list of manager ids needs to be loaded into the BulkJoinId table first. Its possible to have multiple IN filters but not recommended for performance reasons. Currently, this is only being used by the LCMConfigService but could be generalized into the persistence manager.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.BulkIdJoin`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.String getJoinId ()`
- `java.lang.String getJoinProperty ()`
- `java.lang.String getUserId ()`
- `boolean hasName ()`
- `void setJoinId (java.lang.String joinId)`
- `void setJoinProperty (java.lang.String joinProperty)`
- `void setUserId (java.lang.String userId)`

---

## Bundle

**Package:** `sailpoint.object`

**Description:** A class used to represent roles. The class name is Bundle for historical reasons (representing bundles of entitlements). You can assume that "bundle" is synonymous with "role" throughout the model.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.AbstractCertifiableEntity`
- `sailpoint.object.Bundle`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `Certifiable`
- `Classifiable`
- `Describable`
- `RoleContainer`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATT_ACCOUNT_SELECTOR_RULES`
- `static java.lang.String ATT_ALLOW_MULTIPLE_ASSIGNMENTS`
- `static java.lang.String ATT_DUPLICATE_ACCOUNTS`
- `static java.lang.String ATT_MERGE_TEMPLATES`

**Methods:**
- `void add ( Bundle b)`
- `void add ( Profile m)`
- `void add ( RoleScorecard scorecard)`
- `void addDescription (java.lang.String locale, java.lang.String desc)`
- `void addInheritance ( Bundle b)`
- `void addPermit ( Bundle b)`
- `void addRequirement ( Bundle b)`
- `void addRoleIndex ( RoleIndex roleIndex)`
- `void assignProfiles (java.util.List< Profile > profiles)`
- `Profile findProfile (java.lang.String name)`
- `Rule getAccountSelectorRule ()`
- `Rule getAccountSelectorRule (java.lang.String appname)`
- `AccountSelectorRules getAccountSelectorRules ()`
- `java.util.Date getActivationDate ()`
- `ActivityConfig getActivityConfig ()`
- `java.util.List<ApplicationAccountSelectorRule> getApplicationAccountSelectorRules ()`
- `java.util.Set<Application> getApplications ()`
- `java.lang.String getAssignmentId ()`
- `java.util.List<TargetAssociation> getAssociations ()`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getAuditClassName ()`
- `java.util.Date getDeactivationDate ()`
- `java.lang.String getDescription ()`
- `java.lang.String getDescription (java.lang.String locale)`
- `java.lang.String getDescription (java.util.Locale locale)`
- `java.util.Map<java.lang.String,​java.lang.String> getDescriptions ()`
- `java.lang.String getDisplayableName ()`
- `java.lang.String getDisplayName ()`
- `java.util.Map<java.lang.String,​java.lang.Object> getExtendedAttributes ()`
- `java.util.Collection<Bundle> getFlattenedInheritance ()`
- `java.util.Collection<Bundle> getFlattenedPermits ()`
- `java.util.Collection<Bundle> getFlattenedPermits (java.util.Set<java.lang.String> examinedRoles)`
- `java.util.Collection<Bundle> getFlattenedRequirements ()`
- `java.util.Collection<Bundle> getFlattenedRequirements (java.util.Set<java.lang.String> examinedRoles)`
- `java.lang.String getFullName ()`
- `java.util.List<Form> getHibernateProvisioningForms ()`
- `java.util.List<Bundle> getHierarchy ( Resolver r)`
- `java.util.List<Bundle> getInheritance ()`
- `Rule getJoinRule ()`
- `MiningStatistics getMiningStatistics ()`
- `java.util.Set<Application> getMonitoredApplications ()`
- `staticObjectConfig getObjectConfig ()`
- `java.util.List<Template> getOldTemplates ()`
- `java.util.List<Bundle> getPermits ()`
- `java.util.List<Profile> getProfiles ()`
- `java.util.List<Profile> getProfilesForApplications (java.util.List< Application > apps)`
- `java.util.List<Form> getProvisioningForms ()`
- `ProvisioningPlan getProvisioningPlan ()`
- `java.util.List<Bundle> getRequirements ()`
- `int getRiskScoreWeight ()`
- `RoleIndex getRoleIndex ()`
- `java.util.List<Bundle> getRoles ()`
- `RoleTypeDefinition getRoleTypeDefinition ()`
- `RoleScorecard getScorecard ()`
- `IdentitySelector getSelector ()`
- `java.lang.String getType ()`
- `java.lang.String getTypeName (boolean plural)`
- `RoleIndex getXmlRoleIndex ()`
- `java.util.List<Template> getXmlTemplates ()`
- `boolean hasAccountSelectorRules ()`
- `boolean isActivityEnabled ()`
- `boolean isAllowDuplicateAccounts ()`
- `boolean isAllowMultipleAssignments ()`
- `boolean isAutoPromotion ()`
- `boolean isDifferencable ()`
- `boolean isIiqElevatedAccess ()`
- `boolean isMergeTemplates ()`
- `boolean isOrProfiles ()`
- `boolean isPendingDelete ()`
- `void load ()`
- `boolean permits ( Bundle bundle)`
- `boolean referencesAnyApplication (java.util.List< Application > apps)`
- `boolean referencesApplication ( Application app)`
- `boolean remove ( Bundle b)`
- `boolean remove ( Profile profile)`
- `boolean removeInheritance ( Bundle b)`
- `boolean removePermit ( Bundle b)`
- `boolean removeRequirement ( Bundle b)`
- `boolean requires ( Bundle bundle)`
- `void setAccountSelectorRule ( Rule r)`
- `void setAccountSelectorRules ( AccountSelectorRules rules)`
- `void setActivationDate (java.util.Date activationDate)`
- `void setActivityConfig ( ActivityConfig activityConfig)`
- `void setAllowDuplicateAccounts (boolean b)`
- `void setAllowMultipleAssignments (boolean b)`
- `void setApplicationAccountSelectorRules (java.util.List< ApplicationAccountSelectorRule > rules)`
- `void setAssignmentId (java.lang.String assignId)`
- `void setAssociations (java.util.List< TargetAssociation > assocs)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> a)`
- `void setDeactivationDate (java.util.Date deactivationDate)`
- `void setDescription (java.lang.String s)`
- `void setDescriptions (java.util.Map<java.lang.String,java.lang.String> map)`
- `void setDisplayName (java.lang.String displayName)`
- `void setHibernateProvisioningForms (java.util.List< Form > l)`
- `void setIiqElevatedAccess (boolean b)`
- `void setInheritance (java.util.List< Bundle > bundles)`
- `void setJoinRule ( Rule r)`
- `void setMergeTemplates (boolean b)`
- `void setMiningStatistics ( MiningStatistics stats)`
- `void setOldTemplates (java.util.List< Template > l)`
- `void setOrProfiles (boolean orProfiles)`
- `void setPendingDelete (boolean b)`
- `void setPermits (java.util.List< Bundle > bundles)`
- `void setProvisioningForms (java.util.List< Form > l)`
- `void setProvisioningPlan ( ProvisioningPlan plan)`
- `void setRequirements (java.util.List< Bundle > bundles)`
- `void setRiskScoreWeight (int scoreWeight)`
- `void setRoleIndex ( RoleIndex roleIndex)`
- `void setSelector ( IdentitySelector sel)`
- `void setType (java.lang.String type)`
- `void setXmlRoleIndex ( RoleIndex c)`
- `void setXmlTemplates (java.util.List< Template > l)`
- `void visit ( Visitor v)`

---

## BundleArchive

**Package:** `sailpoint.object`

**Description:** Extension of Archive to represent archived versions of Bundles.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Archive`
- `sailpoint.object.BundleArchive`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:** N/A

---

## BundleDifference

**Package:** `sailpoint.object`

**Description:** Class used to contain the results of a comparison between two Bundle objects. These are calculated by the RoleLifecycler and displayed in role approval work items.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.BundleDifference`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String ATT_PERMITS`
- `static java.lang.String ATT_REQUIREMENTS`

**Methods:**
- `void add ( Difference diff)`
- `void add ( ProfileDifference diff)`
- `java.util.List<Difference> getAttributeDifferences ()`
- `Difference getDifference (java.lang.String name)`
- `Difference getPermitsDifference ()`
- `java.util.List<ProfileDifference> getProfileDifferences ()`
- `Difference getRequirementsDifference ()`
- `Difference getSelectorDifference ()`
- `boolean hasDifferences ()`
- `void setAttributeDifferences (java.util.List< Difference > diffs)`
- `void setProfileDifferences (java.util.List< ProfileDifference > diffs)`
- `void setSelectorDifference ( Difference diff)`

---

## BundleProfileRelation

**Package:** `sailpoint.object`

**Description:** BundleProfileRelations represent the effective entitlements and permissions that a Bundle has, as determined by analyzing the Bundle's profiles and the profiles of its inheritance and permitted/required graphs.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.BundleProfileRelation`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.String getAppStatus ()`
- `java.lang.String getAttribute ()`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getBundleId ()`
- `java.util.List<BundleProfileRelationStep> getBundleProfileRelationSteps ()`
- `java.lang.String getDisplayableValue ()`
- `java.lang.String getDisplayValue ()`
- `java.lang.String getHash ()`
- `int getHashCode ()`
- `Application getSourceApplication ()`
- `java.lang.String getSourceBundleId ()`
- `java.lang.String getSourceProfileId ()`
- `java.lang.String getType ()`
- `java.lang.String getValue ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `boolean isInherited ()`
- `boolean isOrMember ()`
- `boolean isPermitted ()`
- `boolean isRequired ()`
- `void setAppStatus (java.lang.String appStatus)`
- `void setAttribute (java.lang.String attribute)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> atts)`
- `void setBundleId (java.lang.String bundleId)`
- `void setBundleProfileRelationSteps (java.util.List< BundleProfileRelationStep > bundleProfileRelationSteps)`
- `void setDisplayValue (java.lang.String displayValue)`
- `void setHash (java.lang.String hash)`
- `void setHashCode (int hashCode)`
- `void setInherited (boolean inherited)`
- `void setOrMember (boolean orMember)`
- `void setPermitted (boolean permitted)`
- `void setRequired (boolean required)`
- `void setSourceApplication ( Application sourceApplication)`
- `void setSourceBundleId (java.lang.String sourceBundleId)`
- `void setSourceProfileId (java.lang.String sourceProfileId)`
- `void setType (java.lang.String type)`
- `void setValue (java.lang.String value)`

---

## BundleProfileRelationObject.Type

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `BundleProfileRelationObject.Type`
- `sailpoint.object.BundleProfileRelationObject.Type`
- `java.io.Serializable`
- `java.lang.Comparable<BundleProfileRelationObject.Type>`

**Attributes:** N/A

**Methods:**
- `staticBundleProfileRelationObject.Type valueOf (java.lang.String name)`
- `staticBundleProfileRelationObject.Type[] values ()`

---

## BundleProfileRelationObject

**Package:** `sailpoint.object`

**Description:** Let the ScopeService know this class does not have a scope.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.BundleProfileRelationObject`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `int getHashCode ()`
- `java.lang.String getModifiedId ()`
- `BundleProfileRelationObject.Type getType ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `void setHashCode (int hashCode)`
- `void setModifiedId (java.lang.String modifiedId)`
- `void setType ( BundleProfileRelationObject.Type type)`

---

## BundleProfileRelationStep

**Package:** `sailpoint.object`

**Description:** Let the ScopeService know this class does not have a scope.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.BundleProfileRelationStep`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.Object clone ()`
- `java.lang.String getBundleId ()`
- `java.lang.String getBundleProfileRelationId ()`
- `java.lang.String getStepType ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `void setBundleId (java.lang.String bundleId)`
- `void setBundleProfileRelationId (java.lang.String bundleProfileRelationId)`
- `void setStepType (java.lang.String stepType)`

---

## BundleSnapshot

**Package:** `sailpoint.object`

**Description:** An object which represents a definition of a Bundle as it applies to a given Identity at a given point in time. This object retains the bundle name and a snapshot of the entitlements that caused this bundle to be correlated to the Identity. This object is serialized as xml and is a private object of IdentitySnapshot object.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.BundleSnapshot`
- `java.io.Serializable`
- `NamedSnapshot`

**Attributes:** N/A

**Methods:**
- `java.util.List<EntitlementSnapshot> getEntitlements ()`
- `java.lang.String getName ()`
- `boolean referencesLink (java.util.List<? extends LinkInterface > links)`
- `void setEntitlements (java.util.List< EntitlementSnapshot > entitlements)`
- `void setName (java.lang.String name)`

---

## Cacheable

**Package:** `sailpoint.object`

**Description:** Allows a cached object to be removed by name.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `default boolean decache (java.lang.String className)`
- `boolean isCacheable ( SailPointObject obj)`
- `void setCache ( CacheReference obj)`

---

## CandidateRole

**Package:** `sailpoint.object`

**Description:** The definition of a role produced by role mining. This is a simplification of the Bundle and Profile models to make it easier to represent role mining results without having to generate a lot of transient Bundles and Profiles (all with unique names), cluttering up the business modeler. It also gives a place to hang transient statistics like the matching identities. The classes are intended to be stored as XML until they are "promoted" so they do not require a Hibernate mapping. When a candidate role is promoted, it becomes an actual Bundle/Profile set and is visible in the modeler for further editing and approvals. Like Bundles these can be organized into a hierarchy but in current practice these should be limited to two levels, the topmost representing Bundles and the second the Profiles. Hierarchical roles will be generated only when you are mining for patterns of roles rather than raw entitlements, or in constrained cases where cross-application clusters are discovered.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.CandidateRole`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `Describable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static int MAX_MATCHES`

**Methods:**
- `void add ( CandidateRole r)`
- `void add ( Filter c)`
- `void add ( Permission p)`
- `void addDescription (java.lang.String locale, java.lang.String desc)`
- `void addMatch (java.lang.String name)`
- `Application getApplication ()`
- `java.lang.Object getAttribute (java.lang.String name)`
- `java.util.List<CandidateRole> getCandidateProfiles ()`
- `java.util.List<CandidateRole> getChildren ()`
- `java.lang.String getDescription (java.lang.String locale)`
- `java.lang.String getDescription (java.util.Locale locale)`
- `java.util.Map<java.lang.String,​java.lang.String> getDescriptions ()`
- `java.util.List<Filter> getFilters ()`
- `int getMatchCount ()`
- `java.util.List<java.lang.String> getMatches ()`
- `MiningStatistics getMiningStatistics ()`
- `java.util.List<Permission> getPermissions ()`
- `java.lang.String getRoleType ()`
- `java.lang.String getRuleExpression ()`
- `java.lang.String getRuleSummary ()`
- `boolean isDefaultName ()`
- `void setApplication ( Application r)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setChildren (java.util.List< CandidateRole > roles)`
- `void setDescriptions (java.util.Map<java.lang.String,java.lang.String> map)`
- `void setFilters (java.util.List< Filter > filters)`
- `void setMatches (java.util.List<java.lang.String> matches)`
- `void setMiningStatistics ( MiningStatistics stats)`
- `void setPermissions (java.util.List< Permission > perms)`
- `void setRoleType (java.lang.String roleType)`

---

## Capability

**Package:** `sailpoint.object`

**Description:** A capability is a logical grouping of rights within IdentityIQ. These can inherit rights from other capabilities to allow a hierarchy of capabilities. Authorization in IdentityIQ will be checked against the SPRights rather than the capabilities. A capability simply serves as a container of rights that can be assigned to an Identity. There is one special capability called SystemAdministrator that gets full access to everything in the system.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Capability`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String DEBUG_PAGES_READ_ONLY_ACCESS`
- `static java.lang.String FORM_ADMINISTRATOR`
- `static java.lang.String HELP_DESK`
- `static java.lang.String IDENTITY_OPERATIONS_ADMIN`
- `static java.lang.String SYSTEM_ADMINISTRATOR`

**Methods:**
- `void addInheritedCapability ( Capability cap)`
- `java.util.List<SPRight> getAllRights ()`
- `boolean getAppliesToAnalyzer ()`
- `java.lang.String getDisplayableName ()`
- `java.lang.String getDisplayableName (java.util.Locale locale)`
- `java.lang.String getDisplayName ()`
- `java.util.List<Capability> getInheritedCapabilities ()`
- `java.util.List<SPRight> getRights ()`
- `static boolean hasCapability (java.lang.String name, java.util.List< Capability > caps)`
- `static boolean hasSystemAdministrator (java.util.List< Capability > caps)`
- `static boolean hasSystemAdministratorInWorkGroups ( Identity identity)`
- `void setAppliesToAnalyzer (boolean b)`
- `void setDisplayName (java.lang.String displayName)`
- `void setInheritedCapabilities (java.util.List< Capability > caps)`
- `void setRights (java.util.List< SPRight > rights)`

---

## Category

**Package:** `sailpoint.object`

**Description:** Represents a category of permission targets within an application. Used in the configuration of activity policy.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Category`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.String getName ()`
- `java.util.List<java.lang.String> getTargets ()`
- `java.lang.String getTargetsAsCSV ()`
- `void setName (java.lang.String name)`
- `void setTargets (java.util.List<java.lang.String> _targets)`

---

## Certifiable

**Package:** `sailpoint.object`

**Description:** Marker interface for any object that can be certified.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:** N/A

---

## CertifiableDescriptor

**Package:** `sailpoint.object`

**Description:** A CertifiableDescriptor holds information that can uniquely identify a Certifiable object or an object holding information about a Certifiable object (such as a CertificationItem).

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.CertifiableDescriptor`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `boolean equals (java.lang.Object o)`
- `java.util.List<EntitlementSnapshot> getAttributeSources ()`
- `java.lang.String getBusinessRole ()`
- `Bundle getBusinessRole ( Resolver resolver)`
- `EntitlementSnapshot getExceptionEntitlements ()`
- `PolicyViolation getPolicyViolation ()`
- `int hashCode ()`
- `boolean isSimiliarViolation ( PolicyViolation otherViolation)`
- `boolean matches ( CertifiableDescriptor other)`
- `void setBusinessRole (java.lang.String businessRole)`
- `void setConstraintId (java.lang.String constraintId)`
- `void setConstraintRuleName (java.lang.String constraintRuleName)`
- `void setExceptionEntitlements ( EntitlementSnapshot exceptionEntitlements)`
- `void setPolicyId (java.lang.String policyId)`
- `void setPolicyName (java.lang.String policyName)`
- `void setPolicyViolation ( PolicyViolation policyViolation)`

---

## Certification.CertificationStatistics

**Package:** `sailpoint.object`

**Description:** Calculate the item and entity percent complete and store them on this certification.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Certification.CertificationStatistics`

**Attributes:** N/A

**Methods:**
- `void decCertificationRequiredEntities ()`
- `void decCertificationRequiredItems ()`
- `void decCertifiedEntities ()`
- `void decCertifiedItems ()`
- `void decOverdueEntities ()`
- `void decOverdueItems ()`
- `int getAccountGroupMembershipsApproved ()`
- `int getAccountGroupMembershipsRemediated ()`
- `int getAccountGroupPermissionsApproved ()`
- `int getAccountGroupPermissionsRemediated ()`
- `int getAccountsAllowed ()`
- `int getAccountsApproved ()`
- `int getAccountsRemediated ()`
- `int getCapabilitiesApproved ()`
- `int getCapabilitiesRemediated ()`
- `int getCertificationRequiredEntities ()`
- `int getCertificationRequiredItems ()`
- `int getCertifiedEntities ()`
- `int getCertifiedItems ()`
- `int getCompletedEntities ()`
- `int getCompletedItems ()`
- `int getDelegatedEntities ()`
- `int getDelegatedItems ()`
- `int getExceptionsAllowed ()`
- `int getExceptionsApproved ()`
- `int getExceptionsRemediated ()`
- `int getExcludedEntities ()`
- `int getExcludedItems ()`
- `int getItemPercentComplete ()`
- `int getOpenAccountGroupMemberships ()`
- `int getOpenAccountGroupPermissions ()`
- `int getOpenAccounts ()`
- `int getOpenCapabilities ()`
- `int getOpenEntities ()`
- `int getOpenExceptions ()`
- `int getOpenItems ()`
- `int getOpenPermits ()`
- `int getOpenProfiles ()`
- `int getOpenRequirements ()`
- `int getOpenRoleHierarchies ()`
- `int getOpenRoles ()`
- `int getOpenScopes ()`
- `int getOpenViolations ()`
- `int getOverdueEntities ()`
- `int getOverdueItems ()`
- `int getPercentComplete ()`
- `int getPermitsApproved ()`
- `int getPermitsRemediated ()`
- `int getProfilesApproved ()`
- `int getProfilesRemediated ()`
- `int getRemediationsCompleted ()`
- `int getRemediationsKickedOff ()`
- `int getRequirementsApproved ()`
- `int getRequirementsRemediated ()`
- `int getRoleHierarchiesApproved ()`
- `int getRoleHierarchiesRemediated ()`
- `int getRolesAllowed ()`
- `int getRolesApproved ()`
- `int getRolesRemediated ()`
- `int getScopesApproved ()`
- `int getScopesRemediated ()`
- `int getTotalAccountGroupMemberships ()`
- `int getTotalAccountGroupPermissions ()`
- `int getTotalAccounts ()`
- `int getTotalCapabilities ()`
- `int getTotalEntities ()`
- `int getTotalExceptions ()`
- `int getTotalItems ()`
- `int getTotalPermits ()`
- `int getTotalProfiles ()`
- `int getTotalRequirements ()`
- `int getTotalRoleHierarchies ()`
- `int getTotalRoles ()`
- `int getTotalScopes ()`
- `int getTotalViolations ()`
- `int getViolationsAcknowledged ()`
- `int getViolationsAllowed ()`
- `int getViolationsRemediated ()`
- `void incCertificationRequiredEntities ()`
- `void incCertificationRequiredItems ()`
- `void incCertifiedEntities ()`
- `void incCertifiedItems ()`
- `void incOverdueEntities ()`
- `void incOverdueItems ()`
- `void incrementDecisionCount ( Certification.Type certType, CertificationItem.Type type, CertificationAction.Status status, int count)`
- `void reset ()`
- `void savePercentComplete ()`
- `void setAccountGroupMembershipsApproved (int accountGroupMembershipsApproved)`
- `void setAccountGroupMembershipsRemediated (int accountGroupMembershipsRemediated)`
- `void setAccountGroupPermissionsApproved (int accountGroupPermissionsApproved)`
- `void setAccountGroupPermissionsRemediated (int accountGroupPermissionsRemediated)`
- `void setAccountsAllowed (int accountsAllowed)`
- `void setAccountsApproved (int accountsApproved)`
- `void setAccountsRemediated (int accountsRemediated)`
- `void setCapabilitiesApproved (int capabilitiesApproved)`
- `void setCapabilitiesRemediated (int capabilitiesRemediated)`
- `void setCertificationRequiredEntities (int certificationRequiredEntities)`
- `void setCertificationRequiredItems (int certificationRequiredItems)`
- `void setCertifiedEntities (int certifiedEntities)`
- `void setCertifiedItems (int certifiedItems)`
- `void setCompletedEntities (int completedEntities)`
- `void setCompletedItems (int completedItems)`
- `void setDelegatedEntities (int delegatedEntities)`
- `void setDelegatedItems (int delegatedItems)`
- `void setExceptionsAllowed (int exceptionsAllowed)`
- `void setExceptionsApproved (int exceptionsApproved)`
- `void setExceptionsRemediated (int exceptionsRemediated)`
- `void setExcludedEntities (int excludedEntities)`
- `void setExcludedItems (int excludedItems)`
- `void setItemPercentComplete (int itemPercentComplete)`
- `void setOverdueEntities (int overdueEntities)`
- `void setOverdueItems (int overdueItems)`
- `void setPercentComplete (int percentComplete)`
- `void setPermitsApproved (int permitsApproved)`
- `void setPermitsRemediated (int permitsRemediated)`
- `void setProfilesApproved (int profilesApproved)`
- `void setProfilesRemediated (int profilesRemediated)`
- `void setRemediationsCompleted (int remediationsCompleted)`
- `void setRemediationsKickedOff (int remediationsKickedOff)`
- `void setRequirementsApproved (int requirementsApproved)`
- `void setRequirementsRemediated (int requirementsRemediated)`
- `void setRoleHierarchiesApproved (int roleHierarchiesApproved)`
- `void setRoleHierarchiesRemediated (int roleHierarchiesRemediated)`
- `void setRolesAllowed (int rolesAllowed)`
- `void setRolesApproved (int rolesApproved)`
- `void setRolesRemediated (int rolesRemediated)`
- `void setScopesApproved (int scopesApproved)`
- `void setScopesRemediated (int scopesRemediated)`
- `void setTotalAccountGroupMemberships (int totalAccountGroupMemberships)`
- `void setTotalAccountGroupPermissions (int totalAccountGroupPermissions)`
- `void setTotalAccounts (int totalAccounts)`
- `void setTotalCapabilities (int totalCapabilities)`
- `void setTotalEntities (int totalEntities)`
- `void setTotalExceptions (int totalExceptions)`
- `void setTotalItems (int totalItems)`
- `void setTotalPermits (int totalPermits)`
- `void setTotalProfiles (int totalProfiles)`
- `void setTotalRequirements (int totalRequirements)`
- `void setTotalRoleHierarchies (int totalRoleHierarchies)`
- `void setTotalRoles (int totalRoles)`
- `void setTotalScopes (int totalScopes)`
- `void setTotalViolations (int totalViolations)`
- `void setViolationsAcknowledged (int violationsAcknowledged)`
- `void setViolationsAllowed (int violationsAllowed)`
- `void setViolationsRemediated (int violationsRemediated)`

---

## Certification.EntitlementGranularity

**Package:** `sailpoint.object`

**Description:** Enumeration of granularities at which additional entitlement certification items can be generated. The default is Application.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Certification.EntitlementGranularity`
- `sailpoint.object.Certification.EntitlementGranularity`
- `java.io.Serializable`
- `java.lang.Comparable<Certification.EntitlementGranularity>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticCertification.EntitlementGranularity valueOf (java.lang.String name)`
- `staticCertification.EntitlementGranularity[] values ()`

---

## Certification.Phase

**Package:** `sailpoint.object`

**Description:** An enumeration of Phases or States that a certification can be in.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Certification.Phase`
- `sailpoint.object.Certification.Phase`
- `java.io.Serializable`
- `java.lang.Comparable<Certification.Phase>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticCertification.Phase valueOf (java.lang.String name)`
- `staticCertification.Phase[] values ()`

---

## Certification.SelfCertificationAllowedLevel

**Package:** `sailpoint.object`

**Description:** Enumeration of levels of allowing self certification

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Certification.SelfCertificationAllowedLevel`
- `sailpoint.object.Certification.SelfCertificationAllowedLevel`
- `java.io.Serializable`
- `java.lang.Comparable<Certification.SelfCertificationAllowedLevel>`
- `sailpoint.tools.MessageKeyHolder`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticCertification.SelfCertificationAllowedLevel valueOf (java.lang.String name)`
- `staticCertification.SelfCertificationAllowedLevel[] values ()`

---

## Certification.Type

**Package:** `sailpoint.object`

**Description:** Styles of certification.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Certification.Type`
- `sailpoint.object.Certification.Type`
- `java.io.Serializable`
- `java.lang.Comparable<Certification.Type>`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:**
- `java.util.List<AbstractCertificationItem.Status> getAllowedEntityStatuses ()`
- `staticCertification.Type getDefaultType ()`
- `CertificationEntity.Type getEntityType ()`
- `java.lang.String getLocalizedMessage ()`
- `java.lang.String getLocalizedMessage (java.util.Locale locale, java.util.TimeZone timezone)`
- `java.lang.String getMessageKey ()`
- `boolean isAllowedEntityStatus ( AbstractCertificationItem.Status status)`
- `boolean isIdentity ()`
- `boolean isObjectType ()`
- `boolean isType ( Certification.Type ... types)`
- `boolean supportsRecommendations ()`
- `staticCertification.Type valueOf (java.lang.String name)`
- `staticCertification.Type[] values ()`

---

## Certification

**Package:** `sailpoint.object`

**Description:** The representation for one certification process. This class is different from most in that is "archival", meaning it has a potentially infinite lifespan. References to object objects such as Identities are made by name rather than through direct references so that they do not introduce foreign key constraints on the referenced objects.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Certification`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `Phaseable`
- `WorkItemOwnerChangeListener`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATT_REASSIGNMENT_DESCRIPTION`
- `static java.lang.String ATT_SIGNATURE_TYPE`
- `static java.lang.String ATTR_ALLOW_PROVISIONING`
- `static java.lang.String ATTR_DISP_ENTS_DESC`
- `static java.lang.String ATTR_EMAIL_TEMPLATE_PREFIX`
- `static java.lang.String ATTR_REQ_APPROVAL_COMMENTS`
- `static java.lang.String IIQ_APPLICATION`
- `static java.lang.String IIQ_ATTR_CAPABILITIES`
- `static java.lang.String IIQ_ATTR_SCOPES`
- `static int NAME_MAX_LENGTH`
- `static int SHORT_NAME_MAX_LENGTH`

**Methods:**
- `void add ( Certification cert)`
- `void add ( CertificationEntity id)`
- `void addAll (java.util.Collection< CertificationEntity > ids)`
- `void addCertificationGroup ( CertificationGroup group)`
- `void addCertificationGroups (java.util.List< CertificationGroup > groups)`
- `void addCommand ( CertificationCommand command)`
- `void addEntityToRefresh ( CertificationEntity id)`
- `void addSignOff ( SignOffHistory signOff)`
- `void addSignOffHistory ( Identity signer)`
- `void addWorkItem ( WorkItem item)`
- `void bulkReassign ( Identity requester, java.util.List< AbstractCertificationItem > items, Identity recipient, java.lang.String certName, java.lang.String description, java.lang.String comments, Configuration sysConfig)`
- `void bulkReassign ( Identity requester, java.util.List< AbstractCertificationItem > items, Identity recipient, java.lang.String certName, java.lang.String description, java.lang.String comments, Configuration sysConfig, boolean checkSelfCertify)`
- `void bulkReassign ( Identity requester, java.util.List< AbstractCertificationItem > items, Identity recipient, java.lang.String certName, java.lang.String description, java.lang.String comments, Configuration sysConfig, boolean checkSelfCertify, boolean checkLimitReassignment)`
- `void bulkReassign ( Identity requester, java.util.List< AbstractCertificationItem > items, Identity recipient, java.lang.String description, java.lang.String comments, Configuration sysConfig)`
- `void bulkReassignEntities ( Identity requester, java.util.List<java.lang.String> entityIds, Identity recipient, java.lang.String description, java.lang.String comments)`
- `void bulkReassignEntities ( Identity requester, java.util.List<java.lang.String> entityIds, Identity recipient, java.lang.String certName, java.lang.String description, java.lang.String comments)`
- `void bulkReassignEntities ( Identity requester, java.util.List<java.lang.String> entityIds, Identity recipient, java.lang.String certName, java.lang.String description, java.lang.String comments, boolean checkSelfCertify)`
- `void bulkReassignEntities ( Identity requester, java.util.List<java.lang.String> entityIds, Identity recipient, java.lang.String certName, java.lang.String description, java.lang.String comments, boolean checkSelfCertify, boolean checkLimitReassignment)`
- `void bulkReassignItems ( Identity requester, java.util.List<java.lang.String> itemIds, Identity recipient, java.lang.String description, java.lang.String comments)`
- `void bulkReassignItems ( Identity requester, java.util.List<java.lang.String> itemIds, Identity recipient, java.lang.String certName, java.lang.String description, java.lang.String comments)`
- `void bulkReassignItems ( Identity requester, java.util.List<java.lang.String> itemIds, Identity recipient, java.lang.String certName, java.lang.String description, java.lang.String comments, boolean checkSelfCertify)`
- `void bulkReassignItems ( Identity requester, java.util.List<java.lang.String> itemIds, Identity recipient, java.lang.String certName, java.lang.String description, java.lang.String comments, boolean checkSelfCertify, boolean checkLimitReassignment)`
- `java.util.Date calculateAutomaticClosingDate ( Resolver resolver)`
- `java.util.Date calculateExpirationDate ()`
- `java.util.Date calculateExpirationDate (java.util.Date startDate)`
- `java.util.Date calculatePhaseEndDate ( Certification.Phase phase)`
- `void clearCommands ()`
- `void clearEntitiesToRefresh ()`
- `void decCertificationRequiredEntities ()`
- `void decCertificationRequiredItems ()`
- `void decCertifiedEntities ()`
- `void decCertifiedItems ()`
- `void decOverdueEntities ()`
- `void decOverdueItems ()`
- `java.util.List<ArchivedCertificationEntity> fetchArchivedEntities ( SailPointContext context)`
- `ArchivedCertificationEntity findArchivedEntity ( CertificationEntity entity, Resolver resolver)`
- `CertificationCommand findCommandForUnpersistedItem ( AbstractCertificationItem item)`
- `AbstractCertificationItem findUnpersistedItemInCommands ( AbstractCertificationItem item)`
- `void flushFullEntitiesToRefresh ()`
- `void flushUnpersistedCommands ()`
- `java.util.Date getActivated ()`
- `java.util.List<AbstractCertificationItem.Status> getAllowedStatuses ()`
- `Application getApplication ( Resolver r)`
- `java.lang.String getApplicationId ()`
- `Reference getApproverRule ()`
- `Rule getApproverRule ( Resolver resolver)`
- `int getArchivedEntityCount ( SailPointContext ctx)`
- `java.lang.Object getAttribute (java.lang.String attrName, Attributes <java.lang.String,java.lang.Object> systemDefaults)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.util.Date getAutomaticClosingDate ()`
- `Certification getCertification ()`
- `Certification getCertification (java.lang.String certId)`
- `int getCertificationCount ( SailPointContext ctx)`
- `CertificationDefinition getCertificationDefinition ( Resolver resolver)`
- `java.lang.String getCertificationDefinitionId ()`
- `java.util.List<CertificationGroup> getCertificationGroups ()`
- `java.util.List<CertificationGroup> getCertificationGroupsByType ( CertificationGroup.Type type)`
- `java.lang.String getCertificationName ()`
- `int getCertificationRequiredEntities ()`
- `int getCertificationRequiredItems ()`
- `java.util.List<Certification> getCertifications ()`
- `int getCertifiedEntities ()`
- `int getCertifiedItems ()`
- `java.util.List<java.lang.String> getCertifiers ()`
- `java.util.List<CertificationCommand> getCommands ()`
- `java.lang.String getComments ()`
- `int getCompletedEntities ()`
- `int getCompletedItems ()`
- `java.util.List<ContinuousStateConfig> getContinuousConfig ()`
- `ContinuousStateConfig getContinuousConfig ( AbstractCertificationItem.ContinuousState state)`
- `java.lang.String getCreator ()`
- `Identity getCreator ( Resolver r)`
- `int getDelegatedEntities ()`
- `int getDelegatedItems ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `java.lang.Boolean getDisplayEntitlementDescription ()`
- `static java.lang.String getDisplayFormat ()`
- `java.lang.String getEmailTemplatePrefix ()`
- `java.util.List<CertificationEntity> getEntities ()`
- `java.util.Set<java.lang.String> getEntitiesToRefresh ()`
- `Certification.EntitlementGranularity getEntitlementGranularity ()`
- `CertificationEntity getEntity (java.lang.String idOrName)`
- `CertificationEntity getEntity ( AbstractCertifiableEntity entity)`
- `java.lang.String getError ()`
- `java.util.Date getExpiration ()`
- `java.util.Date getFinished ()`
- `java.util.Set<CertificationEntity> getFullEntitiesToRefresh ()`
- `Reference getGroupDefinition ()`
- `java.lang.String getGroupDefinitionId ()`
- `java.lang.String getGroupDefinitionName ()`
- `java.lang.String getIdentityProperty ()`
- `IdentityTrigger getIdentityTrigger ( Resolver resolver)`
- `CertificationItem getItem (java.lang.String itemId)`
- `int getItemPercentComplete ()`
- `java.lang.String getManager ()`
- `Identity getManager ( Resolver r)`
- `java.util.Date getNextCertificationRequiredScan ()`
- `java.util.Date getNextOverdueScan ()`
- `Certification.Phase getNextPhase ()`
- `java.util.Date getNextPhaseTransition ()`
- `java.util.Date getNextRemediationScan ()`
- `int getOpenEntities ()`
- `int getOpenItems ()`
- `java.util.Date getOverdueDate ( AbstractCertificationItem.ContinuousState startState, java.util.Date start)`
- `int getOverdueEntities ()`
- `int getOverdueItems ()`
- `Certification getParent ()`
- `int getPercentComplete ()`
- `Certification.Phase getPhase ()`
- `java.util.List<CertificationPhaseConfig> getPhaseConfig ()`
- `CertificationPhaseConfig getPhaseConfig ( Certification.Phase phase)`
- `AbstractCertificationItem.ContinuousState getPreviousContinuousState ( AbstractCertificationItem.ContinuousState current)`
- `Certification.Phase getPreviousPhase ()`
- `int getReassignmentLimit ( SailPointContext ctx)`
- `int getRemainingEntities ()`
- `float getRemediationPercentComplete ()`
- `int getRemediationsCompleted ()`
- `int getRemediationsKickedOff ()`
- `java.lang.String getShortName ()`
- `java.util.Date getSigned ()`
- `java.util.List<SignOffHistory> getSignOffHistory ()`
- `java.util.List<SignOffHistory> getSignOffs ()`
- `Certification.CertificationStatistics getStatistics ()`
- `java.util.List<Tag> getTags ()`
- `TaskSchedule getTaskSchedule ( Resolver resolver)`
- `java.lang.String getTaskScheduleId ()`
- `int getTotalEntities ()`
- `int getTotalItems ()`
- `java.lang.String getTriggerId ()`
- `Certification.Type getType ()`
- `java.util.List<WorkItem> getWorkItems ()`
- `boolean hasBeenSigned ()`
- `boolean hasBulkReassignments ()`
- `void incCertificationRequiredEntities ()`
- `void incCertificationRequiredItems ()`
- `void incCertifiedEntities ()`
- `void incCertifiedItems ()`
- `void incOverdueEntities ()`
- `void incOverdueItems ()`
- `void inlineChildCertifications ()`
- `boolean isAllowProvisioningRequirements ()`
- `boolean isAssimilateBulkReassignments ( Attributes <java.lang.String,java.lang.Object> dflts)`
- `boolean isAutoSignoffOnReassignment ()`
- `boolean isBulkReassignment ()`
- `boolean isCertifyingGroups ()`
- `boolean isCertifyingIdentities ()`
- `static boolean isChildCertificationsComplete ( SailPointContext ctx, java.lang.String certId)`
- `boolean isComplete ()`
- `boolean isCompleteHierarchy ()`
- `boolean isContinuous ()`
- `boolean isElectronicallySigned ()`
- `boolean isExcludeInactive ()`
- `boolean isExpired ()`
- `boolean isInlineChildCertifications ()`
- `boolean isLimitReassignments ( SailPointContext ctx)`
- `static boolean isLockedAndActionable ( SailPointContext context, java.lang.String id)`
- `boolean isNameUnique ()`
- `boolean isOnOrPastRemediationPhase ()`
- `boolean isOnTime ()`
- `boolean isPhaseEnabled ( Certification.Phase phase)`
- `boolean isProcessRevokesImmediately ()`
- `boolean isRemediationPhaseEnabled ()`
- `boolean isRequireApprovalComments ()`
- `boolean isRequireReassignmentCompletion ( Attributes <java.lang.String,java.lang.Object> dflts)`
- `boolean isSelfCertificationReassignment ()`
- `boolean isUseRollingPhases ()`
- `boolean limitCertReassignment ( SailPointContext context)`
- `boolean mergeArchivedEntity ( ArchivedCertificationEntity entity, Resolver resolver)`
- `void mergeCommand ( CertificationCommand cmd)`
- `void removeCommand ( CertificationCommand cmd)`
- `void removeEntity ( CertificationEntity entity)`
- `void removeWorkItem ( WorkItem item)`
- `void resetStatistics ()`
- `void savePercentComplete ()`
- `void setActivated (java.util.Date activated)`
- `void setAllowProvisioningRequirements (boolean allowProvisioningRequirements)`
- `void setApplicationId (java.lang.String applicationId)`
- `void setApproverRule ( Reference rule)`
- `void setApproverRule ( Rule rule)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attributes)`
- `void setAutomaticClosingDate (java.util.Date automaticClosingDate)`
- `void setBulkReassignment (boolean bulkReassignment)`
- `void setCertificationDefinitionId (java.lang.String id)`
- `void setCertificationGroups (java.util.List< CertificationGroup > certificationGroups)`
- `void setCertificationRequiredEntities (int certReqEntities)`
- `void setCertificationRequiredItems (int certReqItems)`
- `void setCertifications (java.util.List< Certification > certs)`
- `void setCertifiedEntities (int certifiedEntities)`
- `void setCertifiedItems (int certifiedItems)`
- `void setCertifierIdentities (java.util.List< Identity > identities)`
- `void setCertifierNames (java.util.List<java.lang.String> identities)`
- `void setCommands (java.util.List< CertificationCommand > commands)`
- `void setComments (java.lang.String s)`
- `void setComplete (boolean b)`
- `void setCompletedEntities (int i)`
- `void setCompletedItems (int completedItems)`
- `void setCompleteHierarchy (boolean b)`
- `void setContinuous (boolean continuous)`
- `void setContinuousConfig (java.util.List< ContinuousStateConfig > config)`
- `void setCreator (java.lang.String s)`
- `void setCreator ( Identity u)`
- `void setDelegatedEntities (int i)`
- `void setDelegatedItems (int delegatedItems)`
- `void setDisplayEntitlementDescription (java.lang.Boolean displayEntitlementDescription)`
- `void setElectronicallySigned (boolean _electronicallySigned)`
- `void setEmailTemplatePrefix (java.lang.String prefix)`
- `void setEntities (java.util.List< CertificationEntity > entities)`
- `void setEntitiesToRefresh (java.util.Set<java.lang.String> ids)`
- `void setEntitlementGranularity ( Certification.EntitlementGranularity eg)`
- `void setError (java.lang.String s)`
- `void setExcludeInactive (boolean exclude)`
- `void setExpiration (java.util.Date expiration)`
- `void setFinished (java.util.Date d)`
- `void setGroupDefinition ( GroupDefinition def)`
- `void setGroupDefinition ( Reference groupDefinition)`
- `void setGroupDefinitionId (java.lang.String groupDefinitionId)`
- `void setGroupDefinitionName (java.lang.String groupDefinitionName)`
- `void setInlineChildCertifications (boolean inline)`
- `void setItemPercentComplete (int itemPercentComplete)`
- `void setManager (java.lang.String manager)`
- `void setManager ( Identity manager)`
- `void setNextCertificationRequiredScan (java.util.Date next)`
- `void setNextOverdueScan (java.util.Date next)`
- `void setNextPhaseTransition (java.util.Date phaseTransition)`
- `void setNextRemediationScan (java.util.Date next)`
- `void setOverdueEntities (int overdueEntities)`
- `void setOverdueItems (int overdueItems)`
- `void setParent ( Certification cert)`
- `void setPercentComplete (int complete)`
- `void setPhase ( Certification.Phase p)`
- `void setPhaseConfig (java.util.List< CertificationPhaseConfig > phaseConfig)`
- `void setProcessRevokesImmediately (boolean useRollingPhases)`
- `void setRemediationsCompleted (int i)`
- `void setRemediationsKickedOff (int i)`
- `void setRequireApprovalComments (boolean requireApprovalComments)`
- `void setSelfCertificationReassignment (boolean selfCertificationReassignment)`
- `void setShortName (java.lang.String s)`
- `void setSigned (java.util.Date d)`
- `void setStatistics ( Certification.CertificationStatistics statistics)`
- `void setTags (java.util.List< Tag > tags)`
- `void setTaskScheduleId (java.lang.String scheduleId)`
- `void setTotalEntities (int i)`
- `void setTotalItems (int totalItems)`
- `void setTriggerId (java.lang.String id)`
- `void setType ( Certification.Type t)`
- `void setupWorkItemNotifications ( Resolver resolver, WorkItem item)`
- `void setWorkItems (java.util.List< WorkItem > items)`
- `void sort ()`
- `void sort (boolean useComparable)`
- `void sort (boolean useComparable, boolean secondarySort)`
- `java.lang.String toString ()`
- `void visit ( Visitor v)`
- `void workItemOwnerChanged ( Resolver resolver, WorkItem item, Identity newOwner, Identity prevOwner)`

---

## CertificationAction.RemediationAction

**Package:** `sailpoint.object`

**Description:** The actions that can occur in response to a remediation request.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `CertificationAction.RemediationAction`
- `sailpoint.object.CertificationAction.RemediationAction`
- `java.io.Serializable`
- `java.lang.Comparable<CertificationAction.RemediationAction>`
- `sailpoint.tools.MessageKeyHolder`

**Attributes:** N/A

**Methods:**
- `java.lang.String getDisplayName ()`
- `java.lang.String getMessageKey ()`
- `staticCertificationAction.RemediationAction valueOf (java.lang.String name)`
- `staticCertificationAction.RemediationAction[] values ()`

---

## CertificationAction.Status

**Package:** `sailpoint.object`

**Description:** The states an certification item might be in. Approved indicates that the item was unconditionally approved. Mitigated indicates that the item was approved, but with conditions. A WorkItem can be assigned to to track the mitigation process. Remediated indicates that the item was rejected, and a remediation process was launched. A WorkItem can be assigned to track the remediation process. Delegated is not used in the persistent model, it is only used at runtime when calculating status summaries for the UI. In the model, an item considered delegated if it has a non-null CertificationDelegation object. For UI convenience the presence of this object is converted to the Delegated state by *insert method name here*. Similarly, RevokeAccount is not used in the persistence model, but only at runtime in the UI. In the CertificationAction, a revoke account is modeled as a Remediated status with the revokeAccount flag set to true. The messageKey is used in certifications and reports to convey the decision that was made and it will be past tense (Approved, Revoked, etc.) The promptKey is used in the UI when *making* the decision and it will be present tense (Approve, Revoke), etc.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `CertificationAction.Status`
- `sailpoint.object.CertificationAction.Status`
- `java.io.Serializable`
- `java.lang.Comparable<CertificationAction.Status>`
- `sailpoint.tools.Localizable`
- `sailpoint.tools.MessageKeyHolder`

**Attributes:** N/A

**Methods:**
- `java.lang.String getDisplayName ()`
- `java.lang.String getLocalizedMessage ()`
- `java.lang.String getLocalizedMessage (java.util.Locale locale, java.util.TimeZone timezone)`
- `java.lang.String getMessageKey ()`
- `java.lang.String getPromptKey ()`
- `void setDisplayName (java.lang.String name)`
- `void setMessageKey (java.lang.String key)`
- `void setPromptKey (java.lang.String key)`
- `staticCertificationAction.Status valueOf (java.lang.String name)`
- `staticCertificationAction.Status[] values ()`

---

## CertificationAction

**Package:** `sailpoint.object`

**Description:** An object that represents an certification decision. These can be stored on both CertificationEntity and CertificationItem, though currently the UI only exposes actions on items. A null action implies that the item is still "open". The class extends WorkItemMonitor whose fields are used only if the action type is Remediate.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.WorkItemMonitor`
- `sailpoint.object.CertificationAction`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String CERT_BULK_DECISION_REASSIGN`

**Methods:**
- `void acknowledge (java.lang.String certId, Identity who, java.lang.String workItem, java.lang.String comments)`
- `void acknowledge ( Identity who, java.lang.String workItem, java.lang.String comments)`
- `void addChildAction ( CertificationAction newAction)`
- `void addParentAction ( CertificationAction newAction)`
- `void approve (java.lang.String certId, Identity who, java.lang.String workItem, java.lang.String comments)`
- `void approve (java.lang.String certId, Identity who, java.lang.String workItem, java.lang.String comments, boolean isAutoDecision)`
- `void approve (java.lang.String certId, Identity who, java.lang.String workItem, ProvisioningPlan additionalActions, java.lang.String additionalActionOwner, java.lang.String additionalActionDesc, java.lang.String additionalActionComments)`
- `void approve ( Identity who, java.lang.String workItem)`
- `void approve ( Identity who, java.lang.String workItem, java.lang.String comments)`
- `void approve ( Identity who, java.lang.String workItem, ProvisioningPlan additionalActions, java.lang.String additionalActionOwner, java.lang.String additionalActionDesc, java.lang.String additionalActionComments)`
- `void bulkCertify (java.lang.String certId, Identity who, java.lang.String workItem, CertificationAction bulkAction)`
- `void bulkCertify ( Identity who, java.lang.String workItem, CertificationAction bulkAction)`
- `void clear (java.lang.String certId, Identity who, java.lang.String workItem, java.lang.String comments)`
- `protected void clearData ()`
- `ProvisioningPlan getAdditionalActions ()`
- `java.util.List<java.lang.String> getAdditionalRemediations ()`
- `java.util.List<CertificationAction> getChildActions ()`
- `java.lang.String getDecisionCertificationId ()`
- `java.util.Date getDecisionDate ()`
- `java.util.Date getMitigationExpiration ()`
- `java.util.List<CertificationAction> getParentActions ()`
- `CertificationAction.RemediationAction getRemediationAction ()`
- `ProvisioningPlan getRemediationDetails ()`
- `CertificationAction getSourceAction ()`
- `CertificationAction.Status getStatus ()`
- `boolean hasFilteredRemediations ()`
- `boolean isAcknowledgment ()`
- `boolean isApproved ()`
- `boolean isAutoDecision ()`
- `boolean isBulkCertified ()`
- `boolean isDelegation ()`
- `boolean isMitigation ()`
- `boolean isReadyForRemediation ()`
- `boolean isRemediation ()`
- `boolean isRemediationCompleted ()`
- `boolean isRemediationKickedOff ()`
- `boolean isReviewed ()`
- `boolean isRevokeAccount ()`
- `void mitigate (java.lang.String certId, Identity who, java.lang.String workItem, java.util.Date mitigationExpiration, java.lang.String comments)`
- `void mitigate ( Identity who, java.lang.String workItem, java.util.Date mitigationExpiration, java.lang.String comments)`
- `void remediate (java.lang.String certId, Identity who, java.lang.String workItem, CertificationAction.RemediationAction action, java.lang.String ownerName, java.lang.String description, java.lang.String comments, ProvisioningPlan details, ProvisioningPlan additionalActions)`
- `void remediate ( Identity who, java.lang.String workItem, CertificationAction.RemediationAction action, java.lang.String ownerName, java.lang.String description, java.lang.String comments, ProvisioningPlan details, ProvisioningPlan additionalActions)`
- `void removeChildAction ( CertificationAction action)`
- `void removeParentAction ( CertificationAction action)`
- `void revokeAccount (java.lang.String certId, Identity who, java.lang.String workItem, CertificationAction.RemediationAction action, java.lang.String ownerName, java.lang.String description, java.lang.String comments)`
- `void revokeAccount ( Identity who, java.lang.String workItem, CertificationAction.RemediationAction action, java.lang.String ownerName, java.lang.String description, java.lang.String comments)`
- `void setAdditionalActions ( ProvisioningPlan additionalActions)`
- `void setAutoDecision (boolean autoDecision)`
- `void setBulkCertified (boolean b)`
- `void setChildActions (java.util.List< CertificationAction > requiredActions)`
- `void setDecisionCertificationId (java.lang.String decisionCertificationId)`
- `void setDecisionDate (java.util.Date date)`
- `void setMitigationExpiration (java.util.Date d)`
- `void setParentActions (java.util.List< CertificationAction > parentActions)`
- `void setReadyForRemediation (boolean readyForRemediation)`
- `void setRemediationAction ( CertificationAction.RemediationAction action)`
- `void setRemediationCompleted (boolean remediationCompleted)`
- `void setRemediationDetails ( ProvisioningPlan plan)`
- `void setRemediationKickedOff (boolean remediationKickedOff)`
- `void setReviewed (boolean b)`
- `void setRevokeAccount (boolean revokeAccount)`
- `void setSourceAction ( CertificationAction sourceAction)`
- `void setStatus ( CertificationAction.Status s)`
- `java.lang.String toString ()`

---

## CertificationArchive

**Package:** `sailpoint.object`

**Description:** The representation for one archived certification process.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.CertificationArchive`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `Certification decompress (sailpoint.tools.xml.XMLReferenceResolver r, java.lang.String certId)`
- `java.lang.String getArchive ()`
- `java.lang.String getCertificationGroupId ()`
- `java.lang.String getCertificationId ()`
- `java.util.List<java.lang.String> getChildCertificationIds ()`
- `java.lang.String getComments ()`
- `java.lang.String getCreatorName ()`
- `java.util.Date getExpiration ()`
- `java.lang.String getOwnerName ()`
- `java.util.Date getSigned ()`
- `void rezipCertification (sailpoint.tools.xml.XMLReferenceResolver r, Certification cert)`
- `void setArchive (java.lang.String s)`
- `void setArchive ( Certification cert)`
- `void setCertificationGroupId (java.lang.String certificationGroupId)`
- `void setCertificationId (java.lang.String s)`
- `void setChildCertificationIds (java.util.List<java.lang.String> ids)`
- `void setComments (java.lang.String s)`
- `void setCreatorName (java.lang.String s)`
- `void setExpiration (java.util.Date expiration)`
- `void setOwnerName (java.lang.String s)`
- `void setSigned (java.util.Date d)`

---

## CertificationChallenge.Decision

**Package:** `sailpoint.object`

**Description:** Decisions that a certifier can make on a challenged item.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `CertificationChallenge.Decision`
- `sailpoint.object.CertificationChallenge.Decision`
- `java.io.Serializable`
- `java.lang.Comparable<CertificationChallenge.Decision>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticCertificationChallenge.Decision valueOf (java.lang.String name)`
- `staticCertificationChallenge.Decision[] values ()`

---

## CertificationChallenge

**Package:** `sailpoint.object`

**Description:** A CertificationChallenge holds challenge information when a third-party (currently, the person that a certification decision will affect) wishes to refute a certification decision. In practice, this is currently being used to let a user challenge a remediation decision in a certification so that they can keep the entitlement being remediated. This can also be used to challenge mitigations, but for now it is just remediations. When challenged, the challenge work item is deleted and the fate of the challenge lies in the hands of the certifier. The certifier can choose to approve or reject a challenge request. Approving a challenge request requires the certifier to choose another decision - the challenge will remain with an Accepted Decision and optional comments. Rejecting marks the challenge as rejected with optional comments. Challenges are created at the start of the "challenge period". The challenge lifecycle is largely maintained by the ChallengePhaseHandler and the Certificationer through WorkItem assimilation. This extends WorkItemMonitor since it can trigger creation of a WorkItem and can have the WorkItem changes assimilated back into it. For a challenge, the WorkItemMonitor fields are used as follows: ownerName: Name of the challenger. completionState: Whether the challenge WorkItem was finished (either as challenged or accepted) or expired. completionComments: The comments from the challenger regarding the reason for a challenge.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.WorkItemMonitor`
- `sailpoint.object.CertificationChallenge`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `void acceptDecision ( Identity challenger, java.lang.String workItem)`
- `void challenge ( Identity challenger, java.lang.String workItem, java.lang.String comments)`
- `boolean didChallengerAct ()`
- `java.lang.String getDeciderName ()`
- `CertificationChallenge.Decision getDecision ()`
- `java.lang.String getDecisionComments ()`
- `boolean hasBeenDecidedUpon ()`
- `boolean isActive ()`
- `boolean isChallenged ()`
- `boolean isChallengeDecisionExpired ()`
- `boolean isRejected ()`
- `boolean requiresDecision ()`

---

## CertificationCommand.BulkReassignment

**Package:** `sailpoint.object`

**Description:** A concrete CertificationCommand that request a bulk re-assignment of multiple CertificationIdentities.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.CertificationCommand`
- `sailpoint.object.CertificationCommand.BulkReassignment`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `boolean equals (java.lang.Object obj)`
- `java.lang.String getCertificationName ()`
- `java.lang.String getComments ()`
- `java.lang.String getDescription ()`
- `Identity getRecipient ()`
- `protected java.util.Comparator<CertificationCommand> getSimilarComparator ()`
- `int hashCode ()`
- `boolean isCheckLimitReassignments ()`
- `boolean isCheckSelfCertification ()`
- `boolean isSelfCertificationReassignment ()`
- `void setCertificationName (java.lang.String certificationName)`
- `void setCheckLimitReassignments (boolean checkLimitReassignments)`
- `void setCheckSelfCertification (boolean checkSelfCertification)`
- `void setComments (java.lang.String comments)`
- `void setDescription (java.lang.String description)`
- `void setRecipient ( Identity recipient)`
- `void setSelfCertificationReassignment (boolean selfCertificationReassignment)`

---

## CertificationCommand.FlushUnPersistedCommandsException

**Package:** `sailpoint.object`

**Description:** This is an exception that will get thrown if there are commands that are in queue to be merged, but have not been persisted yet. This exception is broken out of GeneralException because in some cases it represents a problem that does not need to be worried about. So this is an attempt to be more specific about which exceptions are allowed.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `java.lang.Throwable`
- `java.lang.Exception`
- `sailpoint.tools.AbstractLocalizableException`
- `sailpoint.tools.GeneralException`
- `sailpoint.object.CertificationCommand.FlushUnPersistedCommandsException`
- `java.io.Serializable`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:** N/A

---

## CertificationCommand

**Package:** `sailpoint.object`

**Description:** A CertificationCommand encapsulates a request to modify a certification in some way. These are intended to be left on the Certification and consumed by the Certificationer during refresh to trigger some behavior, and are used instead of just decorating specific CertificationItems and CertificationIdentities with actions because the command spans many elements in the Certification. This is a very weak GoF command pattern in that the command itself is not responsible for the execution logic - it merely serves as a trigger with some information about the command to be processed. The reason for this is that all business logic dealing with certifications has been externalized into the Certificationer. If more commands are created it might make sense to move the execution logic into the command class, but this would require the object package to have some interaction with the Certificationer. Not a bad thing really (objects already load other objects through a Resolver interface), but not yet necessary.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.CertificationCommand`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void addUnpersistedItem ( AbstractCertificationItem item)`
- `boolean equals (java.lang.Object obj)`
- `staticCertificationCommand findSimilar ( CertificationCommand cmd, java.util.List< CertificationCommand > cmds)`
- `AbstractCertificationItem findUnpersistedItem ( AbstractCertificationItem item)`
- `void flushUnpersistedItems ()`
- `java.lang.Class<? extendsAbstractCertificationItem> getItemClass ()`
- `java.util.List<java.lang.String> getItemIds ()`
- `Identity getRequester ()`
- `protected java.util.Comparator<CertificationCommand> getSimilarComparator ()`
- `int hashCode ()`
- `boolean isEmpty ()`
- `void mergeItems (java.util.Collection<java.lang.String> itemIds)`
- `void remove (java.lang.String id)`
- `void setItemClass (java.lang.Class<? extends AbstractCertificationItem > itemClass)`
- `void setItemIds (java.util.List<java.lang.String> itemIds)`
- `void setRequester ( Identity requester)`

---

## CertificationDecision

**Package:** `sailpoint.object`

**Description:** Stores the decision details for a given certifiable.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.CertificationDecision`
- `java.io.Serializable`
- `EntitlementHistoryItem`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `CertificationAction getAction ()`
- `java.lang.String getBusinessRole ()`
- `CertifiableDescriptor getCertifiableDescriptor ()`
- `CertificationLink getCertificationLink ()`
- `EntitlementSnapshot getExceptionEntitlements ()`
- `PolicyViolation getPolicyViolation ()`
- `boolean isSimiliarViolation ( PolicyViolation otherViolation)`
- `void setAction ( CertificationAction action)`
- `void setCertifiableDescriptor ( CertifiableDescriptor desc)`
- `void setCertificationLink ( CertificationLink certificationLink)`

---

## CertificationDefinition.ApplicationGroup

**Package:** `sailpoint.object`

**Description:** This class holds information about which groups to certify for AccountGroupPermission and AccountGroupMembership certs.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.CertificationDefinition.ApplicationGroup`

**Attributes:** N/A

**Methods:**
- `java.lang.String getApplicationName ()`
- `java.lang.String getSchemaObjectType ()`
- `void setApplicationName (java.lang.String applicationName)`
- `void setSchemaObjectType (java.lang.String schemaObjectType)`

---

## CertificationDefinition.CertifierSelectionType

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `CertificationDefinition.CertifierSelectionType`
- `sailpoint.object.CertificationDefinition.CertifierSelectionType`
- `java.io.Serializable`
- `java.lang.Comparable<CertificationDefinition.CertifierSelectionType>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getName ()`
- `staticCertificationDefinition.CertifierSelectionType valueOf (java.lang.String name)`
- `staticCertificationDefinition.CertifierSelectionType[] values ()`

---

## CertificationDefinition.FactoryBean

**Package:** `sailpoint.object`

**Description:** Inner class that holds information about the group factories and associated certifier rules when certifying factories.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.CertificationDefinition.FactoryBean`
- `java.io.Serializable`

**Attributes:** N/A

**Methods:**
- `java.lang.String getCertifierRuleName ()`
- `java.lang.String getId ()`
- `java.lang.String getName ()`
- `boolean isChecked ()`
- `void setCertifierRuleName (java.lang.String ruleName)`
- `void setChecked (boolean checked)`

---

## CertificationDefinition.GroupBean

**Package:** `sailpoint.object`

**Description:** Inner class that holds information about the group definitions and associated certifiers when certifying with an iPOP population.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.CertificationDefinition.GroupBean`
- `java.io.Serializable`

**Attributes:** N/A

**Methods:**
- `java.util.List<Identity> getCertifiers ()`
- `GroupDefinition getGroupDefinition ()`
- `boolean isChecked ()`
- `void setCertifiers (java.util.List< Identity > certifiers)`
- `void setChecked (boolean checked)`

---

## CertificationDefinition.NotificationConfig.ConfigBase

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.CertificationDefinition.NotificationConfig.ConfigBase`
- `CertificationDefinition.NotificationConfig.IConfig`

**Attributes:** N/A

**Methods:**
- `java.util.List<CertificationDefinition.NotificationConfig.RecipientInfo> getAdditionalRecipients ()`
- `int getCount ()`
- `java.lang.String getEmailTemplateId ()`
- `int getOnceEveryHowManyDays ()`
- `java.lang.String getRecipientsRuleName ()`
- `int getStartHowManyDays ()`
- `boolean isAdditionalEmailRecipientsPresent ()`
- `boolean isBefore ()`
- `boolean isEnabled ()`
- `boolean isFromDb ()`
- `void setAdditionalEmailRecipientsPresent (boolean val)`
- `void setAdditionalRecipients (java.util.List< CertificationDefinition.NotificationConfig.RecipientInfo > val)`
- `void setBefore (boolean val)`
- `void setCount (int val)`
- `void setEmailTemplateId (java.lang.String val)`
- `void setEnabled (boolean val)`
- `void setFromDb (boolean val)`
- `void setOnceEveryHowManyDays (int val)`
- `void setRecipientsRuleName (java.lang.String val)`
- `void setStartHowManyDays (int val)`

---

## CertificationDefinition.NotificationConfig.EscalationConfig

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.CertificationDefinition.NotificationConfig.ConfigBase`
- `sailpoint.object.CertificationDefinition.NotificationConfig.EscalationConfig`
- `CertificationDefinition.NotificationConfig.IConfig`

**Attributes:**
- `static java.lang.String TYPE_STRING`

**Methods:**
- `java.lang.String getEscalationRuleId ()`
- `int getMaxReminders ()`
- `java.lang.String getType ()`
- `void setEscalationRuleId (java.lang.String val)`
- `void setMaxReminders (int val)`
- `void setType (java.lang.String val)`

---

## CertificationDefinition.NotificationConfig.IConfig

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `java.util.List<CertificationDefinition.NotificationConfig.RecipientInfo> getAdditionalRecipients ()`
- `int getCount ()`
- `java.lang.String getEmailTemplateId ()`
- `int getOnceEveryHowManyDays ()`
- `java.lang.String getRecipientsRuleName ()`
- `int getStartHowManyDays ()`
- `java.lang.String getType ()`
- `boolean isAdditionalEmailRecipientsPresent ()`
- `boolean isBefore ()`
- `boolean isEnabled ()`
- `boolean isFromDb ()`
- `void setAdditionalEmailRecipientsPresent (boolean val)`
- `void setAdditionalRecipients (java.util.List< CertificationDefinition.NotificationConfig.RecipientInfo > val)`
- `void setBefore (boolean val)`
- `void setCount (int val)`
- `void setEmailTemplateId (java.lang.String val)`
- `void setEnabled (boolean val)`
- `void setFromDb (boolean val)`
- `void setOnceEveryHowManyDays (int val)`
- `void setRecipientsRuleName (java.lang.String val)`
- `void setStartHowManyDays (int val)`
- `void setType (java.lang.String val)`

---

## CertificationDefinition.NotificationConfig.RecipientInfo

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.CertificationDefinition.NotificationConfig.RecipientInfo`

**Attributes:** N/A

**Methods:**
- `java.lang.String getDisplayField ()`
- `java.lang.String getIcon ()`
- `java.lang.String getId ()`
- `void setDisplayField (java.lang.String val)`
- `void setIcon (java.lang.String val)`
- `void setId (java.lang.String val)`

---

## CertificationDefinition.NotificationConfig.ReminderConfig

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.CertificationDefinition.NotificationConfig.ConfigBase`
- `sailpoint.object.CertificationDefinition.NotificationConfig.ReminderConfig`
- `CertificationDefinition.NotificationConfig.IConfig`

**Attributes:**
- `static java.lang.String TYPE_STRING`

**Methods:**
- `java.lang.String getType ()`
- `boolean isOnce ()`
- `void setOnce (boolean val)`
- `void setType (java.lang.String val)`

---

## CertificationDefinition.NotificationConfig

**Package:** `sailpoint.object`

**Description:** This class holds information about notifications. There can be multiple notifications and escalations in a notification. This is a more UI Friendly version of NotificationConfig class

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.CertificationDefinition.NotificationConfig`
- `java.io.Serializable`

**Attributes:** N/A

**Methods:**
- `java.util.List<CertificationDefinition.NotificationConfig.IConfig> getConfigs ()`
- `CertificationDefinition.NotificationConfig.EscalationConfig getDefaultEscalationConfig ()`
- `CertificationDefinition.NotificationConfig.EscalationConfig getDefaultEscalationConfigForNew ()`
- `CertificationDefinition.NotificationConfig.ReminderConfig getDefaultReminderConfig ()`
- `CertificationDefinition.NotificationConfig.ReminderConfig getDefaultReminderConfigForNew ()`
- `java.util.Date getEndDate ()`
- `java.lang.String getEscalationEmailTemplate ()`
- `java.lang.String getEscalationFrequency ()`
- `java.lang.Long getEscalationFrequencyMillis ()`
- `java.lang.String getEscalationRule ()`
- `java.lang.Long getEscalationStartDaysBeforeEnd ()`
- `java.lang.Long getEscalationStartMillisBeforeEnd ()`
- `java.lang.Integer getMaxReminders ()`
- `java.lang.String getReminderEmailTemplate ()`
- `java.lang.String getReminderFrequency ()`
- `java.lang.Long getReminderFrequencyDays ()`
- `java.lang.Long getReminderFrequencyMillis ()`
- `java.lang.Long getReminderStartDaysBeforeEnd ()`
- `java.lang.Long getReminderStartMillisBeforeEnd ()`
- `java.util.Date getStartDate ()`
- `boolean isAnyEnabled ()`
- `boolean isEnabled ()`
- `boolean isEscalate ()`
- `boolean isOnce ()`
- `boolean isSendReminders ()`
- `void setConfigs (java.util.List< CertificationDefinition.NotificationConfig.IConfig > val)`
- `void setDefaultEscalationConfigForNew ( CertificationDefinition.NotificationConfig.EscalationConfig val)`
- `void setDefaultReminderConfigForNew ( CertificationDefinition.NotificationConfig.ReminderConfig val)`
- `void setEnabled (boolean val)`
- `void setEndDate (java.util.Date val)`
- `void setEscalate (boolean escalateBeforeExpiring)`
- `void setEscalationEmailTemplate (java.lang.String escalationEmailTemplate)`
- `void setEscalationFrequency (java.lang.String freq)`
- `void setEscalationFrequencyMillis (java.lang.Long millis)`
- `void setEscalationRule (java.lang.String selectedEscalationRule)`
- `void setEscalationStartDaysBeforeEnd (java.lang.Long days)`
- `void setEscalationStartMillisBeforeEnd (java.lang.Long escalationFrequency)`
- `void setMaxReminders (java.lang.Integer maxReminders)`
- `void setReminderEmailTemplate (java.lang.String selectedEmailTemplate)`
- `void setReminderFrequency (java.lang.String freq)`
- `void setReminderFrequencyDays (java.lang.Long val)`
- `void setReminderFrequencyMillis (java.lang.Long millis)`
- `void setReminderStartDaysBeforeEnd (java.lang.Long days)`
- `void setReminderStartMillisBeforeEnd (java.lang.Long reminderStart)`
- `void setSendReminders (boolean sendEmailOnExpiration)`
- `void setStartDate (java.util.Date val)`

---

## CertificationDefinition

**Package:** `sailpoint.object`

**Description:** Certification definitions hold information that specify how certifications should be created and what behavior they should exhibit. For example, phase durations, notifications/reminder configuration, type of certification, etc. are configured here.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.CertificationDefinition`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ARG_ACCOUNT_FILTER`
- `static java.lang.String ARG_ACCOUNT_FILTER_VALUES`
- `static java.lang.String ARG_ACTIVE_PERIOD_DURATION_AMOUNT`
- `static java.lang.String ARG_ACTIVE_PERIOD_DURATION_SCALE`
- `static java.lang.String ARG_ACTIVE_PHASE_ENTER_RULE_NAME`
- `static java.lang.String ARG_AUTO_SIGN_OFF_WHEN_NOTHING_TO_CERTIFY`
- `static java.lang.String ARG_AUTOMATE_SIGNOFF_POPUP`
- `static java.lang.String ARG_AUTOMATIC_CLOSING_DURATION_AMOUNT`
- `static java.lang.String ARG_AUTOMATIC_CLOSING_DURATION_SCALE`
- `static java.lang.String ARG_AUTOMATIC_CLOSING_ENABLED`
- `static java.lang.String ARG_AUTOMATIC_CLOSING_RULE_NAME`
- `static java.lang.String ARG_AUTOMATIC_CLOSING_SIGNER`
- `static java.lang.String ARG_BACKUP_CERTIFIER`
- `static java.lang.String ARG_CERT_NAME_TEMPLATE`
- `static java.lang.String ARG_CERT_OWNER`
- `static java.lang.String ARG_CERTIFICATION_TYPE`
- `static java.lang.String ARG_CERTIFIER`
- `static java.lang.String ARG_CERTIFIER_OWNER_ACCOUNT`
- `static java.lang.String ARG_CERTIFIER_OWNER_ENTITLEMENT`
- `static java.lang.String ARG_CERTIFIER_OWNER_ROLE`
- `static java.lang.String ARG_CERTIFIER_RULE`
- `static java.lang.String ARG_CERTIFIER_TYPE`
- `static java.lang.String ARG_CERTIFY_ACCOUNTS`
- `static java.lang.String ARG_CERTIFY_EMPTY_ACCOUNTS`
- `static java.lang.String ARG_CHALLENGE_PERIOD_DURATION_AMOUNT`
- `static java.lang.String ARG_CHALLENGE_PERIOD_DURATION_SCALE`
- `static java.lang.String ARG_CHALLENGE_PERIOD_ENABLED`
- `static java.lang.String ARG_CHALLENGE_PHASE_ENTER_RULE_NAME`
- `static java.lang.String ARG_COMPLETE_CERTIFICATION_HIERARCHY_ENABLED`
- `static java.lang.String ARG_DEFAULT_ASSIGNEE_NAME`
- `static java.lang.String ARG_ELECTRONIC_SIGNATURE_REQUIRED`
- `static java.lang.String ARG_ENABLE_ENTITLEMENT_ASSIGNMENTS`
- `static java.lang.String ARG_ENABLE_PARTITIONING`
- `static java.lang.String ARG_ENTITLEMENT_FILTER`
- `static java.lang.String ARG_ENTITLEMENT_FILTER_VALUES`
- `static java.lang.String ARG_ENTITLEMENT_GRANULARITY`
- `static java.lang.String ARG_ENTITY_FILTER`
- `static java.lang.String ARG_ENTITY_FILTER_VALUES`
- `static java.lang.String ARG_ENTITY_POPULATION`
- `static java.lang.String ARG_ENTITY_RULE`
- `static java.lang.String ARG_ENTITY_SELECTION_TYPE`
- `static java.lang.String ARG_EXCLUDE_INACTIVE`
- `static java.lang.String ARG_FINISH_PHASE_ENTER_RULE_NAME`
- `static java.lang.String ARG_FLATTEN_MANAGER_CERTIFICATION_HIERARCHY_ENABLED`
- `static java.lang.String ARG_INCLUDE_ADDITIONAL_ENTITLEMENTS`
- `static java.lang.String ARG_INCLUDE_ARCHIVED_ENTITIES`
- `static java.lang.String ARG_INCLUDE_REQUIRED_ROLES`
- `static java.lang.String ARG_INCLUDE_TARGET_PERMISSIONS`
- `static java.lang.String ARG_NO_SIMPLE_ENTITLEMENT_FILTER`
- `static java.lang.String ARG_OVERRIDE_CERTIFIERS`
- `static java.lang.String ARG_PARTITION_COUNT`
- `static java.lang.String ARG_PARTITION_SIZE`
- `static java.lang.String ARG_PRE_DELEGATION_RULE_NAME`
- `static java.lang.String ARG_PROFILE`
- `static java.lang.String ARG_REMEDIATION_PERIOD_DURATION_AMOUNT`
- `static java.lang.String ARG_REMEDIATION_PERIOD_DURATION_SCALE`
- `static java.lang.String ARG_REMEDIATION_PERIOD_ENABLED`
- `static java.lang.String ARG_REMEDIATION_PHASE_ENTER_RULE_NAME`
- `static java.lang.String ARG_ROLE_FILTER`
- `static java.lang.String ARG_ROLE_FILTER_VALUES`
- `static java.lang.String ARG_SEND_PRE_DELEGATION_COMPLETION_EMAILS`
- `static java.lang.String ARG_SIGN_OFF_APPROVER_RULE_NAME`
- `static java.lang.String ARG_SUBORDINATE_CERTIFICATION_ENABLED`
- `static java.lang.String ARG_SUPPRESS_EMAIL_WHEN_NOTHING_TO_CERTIFY`
- `static java.lang.String ARG_TARGET_PERMISSION_APP_FILTER`
- `static java.lang.String ARG_TARGET_PERMISSION_FILTER`
- `static java.lang.String ARG_TARGET_PERMISSION_FILTER_VALUES`
- `static java.lang.String ARG_UPDATE_IDENTITY_ENTITLEMENTS`
- `static java.lang.String ARG_USE_ENTITLEMENTS_TABLE`
- `static java.lang.String CERTIFICATION_NOTIF_PREFIX`
- `static java.lang.String CERTIFIER_OWNER_TYPE_APPLICATION_OWNER`
- `static java.lang.String CERTIFIER_OWNER_TYPE_ENTITLEMENT_OWNER`
- `static java.lang.String CERTIFIER_OWNER_TYPE_ROLE_OWNER`
- `static java.lang.String ENTITY_SELECTION_TYPE_FILTER`
- `static java.lang.String ENTITY_SELECTION_TYPE_POPULATION`
- `static java.lang.String ENTITY_SELECTION_TYPE_RULE`
- `static java.lang.String REMEDIATION_NOTIF_PREFIX`
- `static java.lang.String REMINDERS_AND_ESCALATIONS_KEY`

**Methods:**
- `void addFactory ( GroupFactory factory)`
- `void addGroup ( GroupDefinition def)`
- `java.util.List<ContinuousStateConfig> createContinuousConfig ( SailPointContext context)`
- `CertificationDefinition createCopy ()`
- `java.util.List<CertificationPhaseConfig> createPhaseConfig ( SailPointContext context)`
- `java.util.List<CertificationPhaseConfig> createPhaseConfig ( SailPointContext context, boolean bypassStaging)`
- `Filter getAccountFilter ()`
- `java.util.List<java.util.Map<java.lang.String,​java.lang.Object>> getAccountFilterValues ()`
- `java.lang.Long getActivePeriodDurationAmount ()`
- `Duration.Scale getActivePeriodDurationScale ()`
- `java.lang.String getActivePhaseEnterRuleName ()`
- `Duration getAllowExceptionDuration ( SailPointContext context)`
- `java.lang.Long getAllowExceptionDurationAmount ( SailPointContext context)`
- `Duration.Scale getAllowExceptionDurationScale ( SailPointContext context)`
- `int getApplicationCount ()`
- `java.util.List<CertificationDefinition.ApplicationGroup> getApplicationGroups ()`
- `java.util.List<java.lang.String> getApplicationIds ()`
- `java.lang.String getApproverRuleName ()`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `CertificationAction.Status getAutomaticClosingAction ()`
- `java.lang.String getAutomaticClosingComments ()`
- `java.lang.Long getAutomaticClosingInterval ()`
- `Duration.Scale getAutomaticClosingIntervalScale ()`
- `Rule getAutomaticClosingRule ( Resolver resolver)`
- `java.lang.String getAutomaticClosingRuleName ()`
- `Identity getAutomaticClosingSigner ( Resolver resolver)`
- `java.lang.String getAutomaticClosingSignerName ()`
- `java.lang.String getBackupCertifierName ()`
- `boolean getBoolean (java.lang.String name, boolean defaultValue)`
- `java.lang.String getBulkReassignmentEmailTemplate ()`
- `java.lang.String getBulkReassignmentEmailTemplate ( SailPointContext context)`
- `java.util.List<java.lang.String> getBusinessRoleIds ()`
- `java.lang.String getCertificationDecisionChallengedEmailTemplate ()`
- `java.lang.String getCertificationDecisionChallengedEmailTemplate ( SailPointContext context)`
- `java.lang.String getCertificationDetailedView ()`
- `java.lang.String getCertificationDetailedView ( SailPointContext context)`
- `java.lang.String getCertificationEmailTemplate ()`
- `java.lang.String getCertificationEmailTemplate ( SailPointContext context)`
- `java.lang.String getCertificationItemFilterAttributes ()`
- `java.lang.String getCertificationItemFilterAttributes ( SailPointContext context)`
- `java.lang.String getCertificationNameTemplate ()`
- `NotificationConfig getCertificationNotificationConfig ( SailPointContext context)`
- `java.lang.String getCertificationOwner ()`
- `Identity getCertificationOwner ( Resolver resolver)`
- `Duration getCertificationRequiredDuration ()`
- `java.lang.Long getCertificationRequiredDurationAmount ()`
- `Duration.Scale getCertificationRequiredDurationScale ()`
- `CertificationDefinition.NotificationConfig getCertificationRequiredNotificationConfig ( SailPointContext context)`
- `Duration getCertifiedDuration ()`
- `java.lang.Long getCertifiedDurationAmount ()`
- `Duration.Scale getCertifiedDurationScale ()`
- `Identity getCertifier ( Resolver resolver)`
- `java.lang.String getCertifierName ()`
- `java.lang.String getCertifierOwnerAccount ()`
- `java.lang.String getCertifierOwnerEntitlement ()`
- `java.lang.String getCertifierOwnerRole ()`
- `java.lang.String getCertifierRule ()`
- `java.util.List<java.lang.String> getCertifiers ()`
- `CertificationDefinition.CertifierSelectionType getCertifierSelectionType ()`
- `java.lang.Boolean getCertPageListItems ()`
- `boolean getCertPageListItems ( SailPointContext context)`
- `java.lang.String getChallengeAcceptedEmailTemplate ()`
- `java.lang.String getChallengeAcceptedEmailTemplate ( SailPointContext context)`
- `java.lang.String getChallengeDecisionExpirationEmailTemplate ()`
- `java.lang.String getChallengeDecisionExpirationEmailTemplate ( SailPointContext context)`
- `java.lang.String getChallengeExpirationEmailTemplate ()`
- `java.lang.String getChallengeExpirationEmailTemplate ( SailPointContext context)`
- `java.lang.String getChallengeGenerationEmailTemplate ()`
- `java.lang.String getChallengeGenerationEmailTemplate ( SailPointContext context)`
- `java.lang.Long getChallengePeriodDurationAmount ()`
- `Duration.Scale getChallengePeriodDurationScale ()`
- `java.lang.String getChallengePeriodEndEmailTemplate ()`
- `java.lang.String getChallengePeriodEndEmailTemplate ( SailPointContext context)`
- `java.lang.String getChallengePeriodStartEmailTemplate ()`
- `java.lang.String getChallengePeriodStartEmailTemplate ( SailPointContext context)`
- `java.lang.String getChallengePhaseEnterRuleName ()`
- `java.lang.String getChallengeRejectedEmailTemplate ()`
- `java.lang.String getChallengeRejectedEmailTemplate ( SailPointContext context)`
- `Identity getDefaultAssignee ( SailPointContext context)`
- `static java.util.List<java.lang.String> getEditableAttributesForPhase ( Certification.Phase phase)`
- `java.lang.String getElectronicSignatureName ()`
- `java.lang.String getElectronicSignatureName ( SailPointContext context)`
- `EmailTemplate getEmailTemplateFor ( SailPointContext context, java.lang.String key)`
- `java.lang.String getEmailTemplateNameFor (java.lang.String key)`
- `java.lang.String getEndPhaseEnterRuleName ()`
- `Filter getEntitlementFilter ()`
- `java.util.List<java.util.Map<java.lang.String,​java.lang.Object>> getEntitlementFilterValues ()`
- `Certification.EntitlementGranularity getEntitlementGranularity ()`
- `java.lang.String getEntityCompletionRuleName ()`
- `java.lang.String getEntityCustomizationRuleName ()`
- `java.lang.String getEntityCustomizationRuleName ( SailPointContext ctx)`
- `Filter getEntityFilter ()`
- `java.util.List<java.util.Map<java.lang.String,​java.lang.Object>> getEntityFilterValues ()`
- `java.lang.String getEntityPopulation ()`
- `java.lang.String getEntityRefreshRuleName ()`
- `java.lang.String getEntityRule ()`
- `java.lang.String getEntitySelectionType ()`
- `java.lang.String getExclusionRuleName ()`
- `CertificationDefinition.FactoryBean getFactory ( Resolver resolver, java.lang.String factoryId)`
- `java.util.List<CertificationDefinition.FactoryBean> getFactoryBeans ( Resolver resolver)`
- `java.util.Map<java.lang.String,​java.lang.String> getFactoryCertifierMap ()`
- `CertificationDefinition.GroupBean getGroup ( Resolver resolver, java.lang.String id)`
- `java.util.List<CertificationDefinition.GroupBean> getGroupBeans ( Resolver resolver)`
- `java.util.List<java.lang.String> getIdentitiesToCertify ()`
- `java.util.List<java.lang.String> getIncludedApplicationIds ()`
- `boolean getIncludeRequiredRoles ()`
- `java.util.Map<java.lang.String,​java.util.List<java.lang.String>> getIpopCertifierMap ()`
- `java.lang.String getItemCustomizationRuleName ()`
- `java.lang.String getItemCustomizationRuleName ( SailPointContext ctx)`
- `java.lang.String getNameTemplate ()`
- `CertificationDefinition.NotificationConfig getOverdueNotificationConfig ( SailPointContext context)`
- `java.util.List<java.lang.String> getOwnerIds ()`
- `java.util.List<Identity> getOwners ( SailPointContext context)`
- `java.lang.Integer getPartitionCount ()`
- `int getPartitionSize ()`
- `java.lang.String getPreDelegationRuleName ()`
- `java.lang.Integer getReassignmentLimit ()`
- `int getReassignmentLimit ( SailPointContext context)`
- `java.lang.Boolean getRecommendationsGenerated ()`
- `CertificationDefinition.NotificationConfig getRemediationNotificationConfig ( SailPointContext context)`
- `NotificationConfig getRemediationNotificationConfigFromDb ( SailPointContext context)`
- `java.lang.Long getRemediationPeriodDurationAmount ()`
- `Duration.Scale getRemediationPeriodDurationScale ()`
- `java.lang.String getRemediationPhaseEnterRuleName ()`
- `Filter getRoleFilter ()`
- `java.util.List<java.util.Map<java.lang.String,​java.lang.Object>> getRoleFilterValues ()`
- `java.util.List<java.lang.String> getRoleTypes ()`
- `boolean getSaveExclusions ()`
- `Certification.SelfCertificationAllowedLevel getSelfCertificationAllowedLevel ()`
- `Certification.SelfCertificationAllowedLevel getSelfCertificationAllowedLevel ( SailPointContext context)`
- `java.lang.String getSelfCertificationViolationOwner ()`
- `Identity getSelfCertificationViolationOwner ( Resolver resolver)`
- `java.lang.String getShortNameTemplate ()`
- `java.lang.Boolean getShowRecommendations ()`
- `boolean getShowRecommendations ( SailPointContext context)`
- `java.util.List<CertificationAction.Status> getStatusesRequiringComments ( SailPointContext context)`
- `java.util.List<Tag> getTags ()`
- `Filter getTargetPermissionApplicationFilter ()`
- `Filter getTargetPermissionFilter ()`
- `java.util.List<java.util.Map<java.lang.String,​java.lang.Object>> getTargetPermissionFilterValues ()`
- `java.lang.String getTriggerId ()`
- `Certification.Type getType ()`
- `Message getTypeScheduleDescription ()`
- `java.lang.String getUnownedDataOwner ()`
- `Identity getUnownedDataOwner ( Resolver resolver)`
- `boolean hasFactory (java.lang.String id)`
- `boolean hasGroup (java.lang.String id)`
- `void initialize ( SailPointContext context)`
- `void initialize ( SailPointContext context, Attributes <java.lang.String,java.lang.Object> options)`
- `boolean isAllowAccountRevocation ( SailPointContext context)`
- `boolean isAllowApproveAccounts ( SailPointContext context)`
- `boolean isAllowEntityBulkAccountRevocation ( SailPointContext context)`
- `java.lang.Boolean isAllowEntityBulkApprove ()`
- `boolean isAllowEntityBulkApprove ( SailPointContext context)`
- `java.lang.Boolean isAllowEntityBulkClearDecisions ()`
- `boolean isAllowEntityBulkClearDecisions ( SailPointContext context)`
- `boolean isAllowEntityBulkRevocation ( SailPointContext context)`
- `boolean isAllowEntityDelegation ( SailPointContext context)`
- `java.lang.Boolean isAllowExceptionPopup ()`
- `java.lang.Boolean isAllowExceptionPopup ( SailPointContext context)`
- `java.lang.Boolean isAllowExceptions ( SailPointContext context)`
- `boolean isAllowItemDelegation ( SailPointContext context)`
- `java.lang.Boolean isAllowListBulkAccountRevocation ( SailPointContext context)`
- `java.lang.Boolean isAllowListBulkApprove ()`
- `boolean isAllowListBulkApprove ( SailPointContext context)`
- `java.lang.Boolean isAllowListBulkClearDecisions ()`
- `boolean isAllowListBulkClearDecisions ( SailPointContext context)`
- `java.lang.Boolean isAllowListBulkMitigate ()`
- `boolean isAllowListBulkMitigate ( SailPointContext context)`
- `java.lang.Boolean isAllowListBulkReassign ()`
- `boolean isAllowListBulkReassign ( SailPointContext context)`
- `java.lang.Boolean isAllowListBulkRevocation ( SailPointContext context)`
- `java.lang.Boolean isAllowListBulkRevoke ()`
- `boolean isAllowListBulkRevoke ( SailPointContext context)`
- `boolean isAllowProvisioningRequirements ()`
- `boolean isAppOwnerIsUnownedOwner ()`
- `boolean isAssimilateBulkReassignments ( SailPointContext context)`
- `java.lang.Boolean isAutoApprove ()`
- `boolean isAutoApprove ( SailPointContext context)`
- `boolean isAutomateSignOffOnReassignment ( SailPointContext context)`
- `java.lang.Boolean isAutomateSignoffPopup ()`
- `boolean isAutomateSignoffPopup ( SailPointContext context)`
- `boolean isAutomaticClosingEnabled ()`
- `boolean isAutoSignOffWhenNothingToCertify ()`
- `boolean isCertificationDelegationReviewRequired ( SailPointContext context)`
- `boolean isCertificationDetailedViewFilterSet ( SailPointContext context)`
- `boolean isCertifyAccounts ()`
- `boolean isCertifyEmptyAccounts ()`
- `boolean isChallengePeriodEnabled ()`
- `boolean isCompleteCertificationHierarchy ()`
- `boolean isContinuous ()`
- `java.lang.Boolean isDelegationForwardingDisabled ()`
- `java.lang.Boolean isDisplayEntitlementDescriptions ()`
- `java.lang.Boolean isDisplayEntitlementDescriptions ( SailPointContext context)`
- `java.lang.Boolean isElectronicSignatureRequired ()`
- `java.lang.Boolean isElectronicSignatureRequired ( SailPointContext context)`
- `boolean isEnableOverrideViolationDefaultRemediator ( SailPointContext context)`
- `boolean isEnablePartitioning ()`
- `boolean isEnableReassignAccount ( SailPointContext context)`
- `boolean isExcludeBaseAppAccounts ()`
- `boolean isExcludeInactive ()`
- `boolean isFilterLogicalEntitlements ()`
- `boolean isFlattenManagerCertificationHierarchy ()`
- `boolean isGlobal ()`
- `boolean isIncludeAdditionalEntitlements ()`
- `boolean isIncludeArchivedEntities ()`
- `boolean isIncludeCapabilities ()`
- `java.lang.Boolean isIncludeClassifications ()`
- `boolean isIncludeClassifications ( SailPointContext context)`
- `java.lang.Boolean isIncludeElevatedAccess ()`
- `boolean isIncludeElevatedAccess ( SailPointContext context)`
- `boolean isIncludeEntitlementsGrantedByRoles ()`
- `boolean isIncludePolicyViolations ()`
- `boolean isIncludeRoleHierarchy ()`
- `boolean isIncludeRoles ()`
- `boolean isIncludeScopes ()`
- `boolean isIncludeTargetPermissions ()`
- `boolean isIncludeUnownedData ()`
- `java.lang.Boolean isLimitReassignments ()`
- `boolean isLimitReassignments ( SailPointContext context)`
- `java.lang.Boolean isMitigationDeprovisionEnabled ()`
- `java.lang.Boolean isMitigationDeprovisionEnabled ( SailPointContext context)`
- `java.lang.Boolean isNotifyRemediation ()`
- `boolean isNotifyRemediation ( SailPointContext context)`
- `boolean isProcessRevokesImmediately ()`
- `boolean isProfile ()`
- `boolean isRemediationPeriodEnabled ()`
- `boolean isRequireAccountRevokeComments ( SailPointContext context)`
- `boolean isRequireApprovalComments ()`
- `boolean isRequireApprovalComments ( SailPointContext context)`
- `boolean isRequireBulkCertifyConfirmation ( SailPointContext context)`
- `boolean isRequireMitigationComments ( SailPointContext context)`
- `boolean isRequireReassignmentCompletion ( SailPointContext context)`
- `boolean isRequireRemediationComments ( SailPointContext context)`
- `boolean isSendPreDelegationCompletionEmails ()`
- `boolean isStagingEnabled ()`
- `boolean isSubordinateCertificationEnabled ()`
- `boolean isSuppressEmailWhenNothingToCertify ()`
- `java.lang.Boolean isSuppressInitialNotification ()`
- `boolean isSuppressInitialNotification ( SailPointContext context)`
- `boolean isUpdateAttributeAssignments ()`
- `boolean isUpdateIdentityEntitlements ()`
- `void load ()`
- `void mergeAttributes ( Attributes <java.lang.String,java.lang.Object> mergeAttributes)`
- `void removeFactories ()`
- `void removeGroups ()`
- `void setAccountFilter ( Filter f)`
- `void setAccountFilterValues (java.util.List<java.util.Map<java.lang.String,java.lang.Object>> filterValues)`
- `void setActivePeriodDurationAmount (java.lang.Long amount)`
- `void setActivePeriodDurationScale ( Duration.Scale scale)`
- `void setActivePhaseEnterRuleName (java.lang.String activePhaseEnterRuleName)`
- `void setAllowAccountRevocation (java.lang.Boolean allow)`
- `void setAllowApproveAccounts (java.lang.Boolean allow)`
- `void setAllowEntityBulkAccountRevocation (java.lang.Boolean allow)`
- `void setAllowEntityBulkApprove (java.lang.Boolean approve)`
- `void setAllowEntityBulkClearDecisions (java.lang.Boolean allow)`
- `void setAllowEntityBulkRevocation (java.lang.Boolean allow)`
- `void setAllowEntityDelegation (java.lang.Boolean allow)`
- `void setAllowExceptionDurationAmount (java.lang.Long allowDuration)`
- `void setAllowExceptionDurationScale ( Duration.Scale scale)`
- `void setAllowExceptionPopup (java.lang.Boolean allowDuration)`
- `void setAllowExceptions (java.lang.Boolean allowExceptions)`
- `void setAllowItemDelegation (java.lang.Boolean allow)`
- `void setAllowListBulkAccountRevocation (java.lang.Boolean allow)`
- `void setAllowListBulkApprove (java.lang.Boolean approve)`
- `void setAllowListBulkClearDecisions (java.lang.Boolean revoke)`
- `void setAllowListBulkMitigate (java.lang.Boolean mitigate)`
- `void setAllowListBulkReassign (boolean allow)`
- `void setAllowListBulkRevocation (java.lang.Boolean allow)`
- `void setAllowListBulkRevoke (java.lang.Boolean revoke)`
- `void setAllowProvisioningRequirements (java.lang.Boolean allow)`
- `void setApplicationGroups (java.util.List< CertificationDefinition.ApplicationGroup > val)`
- `void setApplicationIds (java.util.List<java.lang.String> applicationIds)`
- `void setAppOwnerIsUnownedOwner (java.lang.Boolean appOwnerIsUnownedOwner)`
- `void setApproverRuleName (java.lang.String ruleName)`
- `void setAssimilateBulkReassignments (java.lang.Boolean assimilate)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attributes)`
- `void setAutoApprove (boolean autoDecisions)`
- `void setAutomateSignOffOnReassignment (java.lang.Boolean automate)`
- `void setAutomateSignoffPopup (boolean automateSignoffPopup)`
- `void setAutomaticClosingAction (java.lang.String action)`
- `void setAutomaticClosingAction ( CertificationAction.Status action)`
- `void setAutomaticClosingComments (java.lang.String comments)`
- `void setAutomaticClosingEnabled (java.lang.Boolean enabled)`
- `void setAutomaticClosingInterval (java.lang.Long amount)`
- `void setAutomaticClosingIntervalScale ( Duration.Scale scale)`
- `void setAutomaticClosingRuleName (java.lang.String automaticClosingRuleName)`
- `void setAutomaticClosingSigner ( Identity signer)`
- `void setAutomaticClosingSignerName (java.lang.String signer)`
- `void setAutoSignOffWhenNothingToCertify (boolean autoSignOffWhenNothingToCertify)`
- `void setBackupCertifierName (java.lang.String backupCertifier)`
- `void setBulkReassignmentEmailTemplate (java.lang.String template)`
- `void setBusinessRoleIds (java.util.List<java.lang.String> businessRoleIds)`
- `void setCertificationDecisionChallengedEmailTemplate (java.lang.String template)`
- `void setCertificationDelegationReviewRequired (java.lang.Boolean required)`
- `void setCertificationDetailedView (java.lang.String certificationDetailedView)`
- `void setCertificationDetailedViewFilterSet (java.lang.Boolean doit)`
- `void setCertificationEmailTemplate (java.lang.String template)`
- `void setCertificationNameTemplate (java.lang.String template)`
- `void setCertificationNotificationConfig ( NotificationConfig val)`
- `void setCertificationOwner (java.lang.String ownerIdOrName)`
- `void setCertificationOwner ( Identity owner)`
- `void setCertificationRequiredDurationAmount (java.lang.Long amount)`
- `void setCertificationRequiredDurationScale ( Duration.Scale scale)`
- `void setCertificationRequiredNotificationConfig ( NotificationConfig val)`
- `void setCertifiedDurationAmount (java.lang.Long amount)`
- `void setCertifiedDurationScale ( Duration.Scale scale)`
- `void setCertifierIdentities (java.util.List< Identity > identities)`
- `void setCertifierName (java.lang.String certifier)`
- `void setCertifierOwnerAccount (java.lang.String certifierOwnerAccount)`
- `void setCertifierOwnerEntitlement (java.lang.String certifierOwnerEntitlement)`
- `void setCertifierOwnerRole (java.lang.String certifierOwnerRole)`
- `void setCertifierRule (java.lang.String name)`
- `void setCertifiers (java.util.List<java.lang.String> names)`
- `void setCertifierSelectionType (java.lang.String certifierSelectionType)`
- `void setCertifierSelectionType ( CertificationDefinition.CertifierSelectionType certifierSelectionType)`
- `void setCertifyAccounts (java.lang.Boolean certifyAcounts)`
- `void setCertifyEmptyAccounts (java.lang.Boolean certifyAcounts)`
- `void setCertPageListItems (java.lang.Boolean certPageListItems)`
- `void setChallengeAcceptedEmailTemplate (java.lang.String template)`
- `void setChallengeDecisionExpirationEmailTemplate (java.lang.String template)`
- `void setChallengeExpirationEmailTemplate (java.lang.String template)`
- `void setChallengeGenerationEmailTemplate (java.lang.String template)`
- `void setChallengePeriodDurationAmount (java.lang.Long amount)`
- `void setChallengePeriodDurationScale ( Duration.Scale scale)`
- `void setChallengePeriodEnabled (java.lang.Boolean enabled)`
- `void setChallengePeriodEndEmailTemplate (java.lang.String template)`
- `void setChallengePeriodStartEmailTemplate (java.lang.String template)`
- `void setChallengePhaseEnterRuleName (java.lang.String challengePhaseEnterRuleName)`
- `void setChallengeRejectedEmailTemplate (java.lang.String template)`
- `void setCompleteCertificationHierarchy (java.lang.Boolean completeCertificationHierarchy)`
- `void setContinuous (boolean continuous)`
- `void setDefaultAssignee (java.lang.String assigneeIdOrName)`
- `void setDefaultAssignee ( Identity assignee)`
- `void setDelegationForwardingDisabled (java.lang.Boolean allow)`
- `void setDisplayEntitlementDescriptions (java.lang.Boolean displayEntitlementDescriptions)`
- `void setElectronicSignatureName (java.lang.String electronicSignatureName)`
- `void setElectronicSignatureRequired (boolean electronicSignatureRequired)`
- `void setEmailTemplateNameFor (java.lang.String key, java.lang.String template)`
- `void setEnableOverrideViaolationDefaultRemediator (java.lang.Boolean allowOverrideRemediator)`
- `void setEnablePartitioning (boolean val)`
- `void setEnableReassignAccount (java.lang.Boolean enable)`
- `void setEndPhaseEnterRuleName (java.lang.String val)`
- `void setEntitlementFilter ( Filter f)`
- `void setEntitlementFilterValues (java.util.List<java.util.Map<java.lang.String,java.lang.Object>> filterValues)`
- `void setEntitlementGranularity (java.lang.String entitlementGranularity)`
- `void setEntitlementGranularity ( Certification.EntitlementGranularity entitlementGranularity)`
- `void setEntityCompletionRuleName (java.lang.String ruleName)`
- `void setEntityCustomizationRuleName (java.lang.String ruleName)`
- `void setEntityFilter ( Filter f)`
- `void setEntityFilterValues (java.util.List<java.util.Map<java.lang.String,java.lang.Object>> filterValues)`
- `void setEntityPopulation (java.lang.String name)`
- `void setEntityRefreshRuleName (java.lang.String ruleName)`
- `void setEntityRule (java.lang.String name)`
- `void setEntitySelectionType (java.lang.String entitySelectionType)`
- `void setExcludeBaseAppAccounts (java.lang.Boolean excludeBaseAppAccounts)`
- `void setExcludeInactive (java.lang.Boolean exclude)`
- `void setExclusionRuleName (java.lang.String ruleName)`
- `void setFactoryBeans (java.util.List< CertificationDefinition.FactoryBean > factories)`
- `void setFactoryCertifierMap (java.util.Map<java.lang.String,java.lang.String> map)`
- `void setFilterLogicalEntitlements (boolean filter)`
- `void setFlattenManagerCertificationHierarchy (java.lang.Boolean flattenManagerCertificationHierarchy)`
- `void setGlobal (boolean global)`
- `void setGroupBeans (java.util.List< CertificationDefinition.GroupBean > factories)`
- `void setIdentitiesToCertify (java.util.List<java.lang.String> identitiesToCertify)`
- `void setIncludeAdditionalEntitlements (java.lang.Boolean includeEntitlements)`
- `void setIncludeArchivedEntities (boolean b)`
- `void setIncludeCapabilities (java.lang.Boolean includeCaps)`
- `void setIncludeClassifications (boolean includeClassifications)`
- `void setIncludedApplicationIds (java.util.List<java.lang.String> includedApplicationIds)`
- `void setIncludeElevatedAccess (boolean includeElevatedAccess)`
- `void setIncludeEntitlementsGrantedByRoles (java.lang.Boolean val)`
- `void setIncludePolicyViolations (java.lang.Boolean includeViolations)`
- `void setIncludeRequiredRoles (boolean value)`
- `void setIncludeRoleHierarchy (java.lang.Boolean includeRoleHierarchy)`
- `void setIncludeRoles (java.lang.Boolean includeRoles)`
- `void setIncludeScopes (java.lang.Boolean include)`
- `void setIncludeTargetPermissions (java.lang.Boolean include)`
- `void setIncludeUnownedData (java.lang.Boolean includeUnownedData)`
- `void setIpopCertifierMap (java.util.Map<java.lang.String,java.util.List<java.lang.String>> map)`
- `void setIsSubordinateCertificationEnabled (java.lang.Boolean subordinateCertificationEnabled)`
- `void setItemCustomizationRuleName (java.lang.String ruleName)`
- `void setLimitReassignments (java.lang.Boolean allow)`
- `void setMitigationDeprovisionEnabled (java.lang.Boolean mitigationDeprovisionEnabled)`
- `void setNameTemplate (java.lang.String nameTemplate)`
- `void setNotifyRemediation (boolean suppress)`
- `void setOverdueNotificationConfig ( NotificationConfig val)`
- `void setOwnerIds (java.util.List<java.lang.String> ownerIds)`
- `void setPartitionCount (java.lang.Integer count)`
- `void setPartitionSize (int i)`
- `void setPreDelegationRuleName (java.lang.String ruleName)`
- `void setProcessRevokesImmediately (java.lang.Boolean processRevokes)`
- `void setProfile (boolean b)`
- `void setReassignmentLimit (java.lang.Integer value)`
- `void setRecommendationsGenerated (boolean recsGenerated)`
- `void setRemediationNotificationConfig ( NotificationConfig notifConfig)`
- `void setRemediationPeriodDurationAmount (java.lang.Long amount)`
- `void setRemediationPeriodDurationScale ( Duration.Scale scale)`
- `void setRemediationPeriodEnabled (java.lang.Boolean enabled)`
- `void setRemediationPhaseEnterRuleName (java.lang.String remediationPhaseEnterRuleName)`
- `void setRequireApprovalComments (java.lang.Boolean requireApprovalComments)`
- `void setRequireBulkCertifyConfirmation (java.lang.Boolean require)`
- `void setRequireMitigationComments (java.lang.Boolean requireMitigationComments)`
- `void setRequireReassignmentCompletion (java.lang.Boolean require)`
- `void setRequireRemediationComments (java.lang.Boolean requireRemediationComments)`
- `void setRoleFilter ( Filter f)`
- `void setRoleFilterValues (java.util.List<java.util.Map<java.lang.String,java.lang.Object>> filterValues)`
- `void setRoleTypes (java.util.List<java.lang.String> roleTypes)`
- `void setSaveExclusions (java.lang.Boolean saveExclusions)`
- `void setSelfCertificationAllowedLevel (java.lang.String allowedLevel)`
- `void setSelfCertificationAllowedLevel ( Certification.SelfCertificationAllowedLevel allowedLevel)`
- `void setSelfCertificationViolationsOwner (java.lang.String selfCertificationViolationsOwner)`
- `void setSelfCertificationViolationsOwner ( Identity selfCertificationViolationsOwner)`
- `void setSendPreDelegationCompletionEmails (boolean val)`
- `void setShortNameTemplate (java.lang.String shortNameTemplate)`
- `void setShowRecommendations (boolean showRecs)`
- `void setStagingEnabled (boolean stagingEnabled)`
- `void setSuppressEmailWhenNothingToCertify (boolean suppressEmailWhenNothingToCertify)`
- `void setSuppressInitialNotification (boolean suppress)`
- `void setTags (java.util.List< Tag > tags)`
- `void setTargetPermissionApplicationFilter ( Filter f)`
- `void setTargetPermissionFilter ( Filter f)`
- `void setTargetPermissionFilterValues (java.util.List<java.util.Map<java.lang.String,java.lang.Object>> filterValues)`
- `void setTriggerId (java.lang.String triggerId)`
- `void setType (java.lang.String type)`
- `void setType ( Certification.Type type)`
- `void setUnownedDataOwner (java.lang.String val)`
- `void setUpdateAttributeAssignments (boolean update)`
- `void setUpdateIdentityEntitlements (boolean update)`
- `boolean shouldIncludeClassifications ()`
- `boolean shouldIncludeElevatedAccess ()`
- `void storeContext ( SailPointContext context, Certification cert)`
- `void visit ( Visitor v)`

---

## CertificationDelegation

**Package:** `sailpoint.object`

**Description:** An object holding the delegation state of a certification item. When one of these is created and stored on an CertificationIdentity or CertificationItem, it triggers the generation of a WorkItem for the delegated user. While the work item is active, it maintains a reference to the item for easier tracking. When the work item is completed, it holds a copy of the completion state.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.WorkItemMonitor`
- `sailpoint.object.CertificationDelegation`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `protected void clearData ()`
- `void delegate ( Identity requester, java.lang.String workItem, java.lang.String ownerName, java.lang.String description, java.lang.String comments)`
- `Identity getOwner ( Resolver resolver)`
- `boolean isReviewRequired ()`
- `boolean isRevoked ()`
- `void revoke ()`
- `void setReviewRequired (boolean b)`

---

## CertificationEntity.Type

**Package:** `sailpoint.object`

**Description:** Entity types.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `CertificationEntity.Type`
- `sailpoint.object.CertificationEntity.Type`
- `java.io.Serializable`
- `java.lang.Comparable<CertificationEntity.Type>`

**Attributes:** N/A

**Methods:**
- `java.util.List<AbstractCertificationItem.Status> getAllowedStatus ()`
- `java.lang.String getMessageKey ()`
- `boolean isHistorical ()`
- `staticCertificationEntity.Type valueOf (java.lang.String name)`
- `staticCertificationEntity.Type[] values ()`

---

## CertificationEntity

**Package:** `sailpoint.object`

**Description:** The state of one entity(Identity, AccountGroup/ManagedAttribute, etc) within an Certification.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.AbstractCertificationItem`
- `sailpoint.object.CertificationEntity`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `WorkItemOwnerChangeListener`
- `sailpoint.tools.WatchableMap.Watcher<java.lang.String,​java.lang.Object>`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATTR_SNAPSHOT`

**Methods:**
- `void add ( CertificationItem item)`
- `void applySummaryStatus (java.lang.Boolean completeOverride, AbstractCertificationItem.Status itemsStatus, boolean isComplete)`
- `java.util.List<CertificationItem> bulkCertify ( Identity who, java.lang.String workItem, CertificationAction bulkAction, CertificationItemSelector selector, boolean force)`
- `java.lang.String calculateDisplayName ( SailPointContext ctx, java.util.Locale locale)`
- `void clearIds ()`
- `boolean equals (java.lang.Object o)`
- `java.lang.String getAccountGroup ()`
- `ManagedAttribute getAccountGroup ( SailPointContext context)`
- `java.lang.String getApplication ()`
- `Application getApplication ( Resolver resolver)`
- `java.util.List<Application> getApplications ( CertificationAction action, boolean isBulkCertified, Resolver resolver)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `Certification getCertification ()`
- `CertificationEntity getCertificationEntity ()`
- `int getCompositeScore ()`
- `Identity getDefaultRemediator ( Resolver resolver)`
- `IdentityDifference getDifferences ()`
- `AbstractCertificationItem.Status getEntityDelegationStatus ()`
- `Filter getEqualsFilter ( Certification cert)`
- `java.lang.String getFirstname ()`
- `java.lang.String getFullname ()`
- `java.lang.String getIdentity ()`
- `Identity getIdentity ( Resolver r)`
- `IdentitySnapshot getIdentitySnapshot ( Resolver r)`
- `CertificationItem getItem (java.lang.String itemId)`
- `java.util.List<CertificationItem> getItems ()`
- `java.util.List<CertificationItem> getItemsOnSameAccount ( CertificationItem item)`
- `staticFilter getItemsOnSameAccountFilter ( CertificationItem item)`
- `java.lang.String getLastname ()`
- `java.lang.String getNativeIdentity ()`
- `boolean getNewUser ()`
- `java.lang.String getPendingCertification ()`
- `java.lang.String getReferenceAttribute ()`
- `RoleSnapshot getRoleSnapshot ()`
- `java.lang.String getSchemaObjectType ()`
- `java.lang.String getSnapshotId ()`
- `static java.util.Comparator<CertificationEntity> getSortComparator ()`
- `CertificationEntity.Type getType ()`
- `boolean hasAutoApprovals ()`
- `int hashCode ()`
- `boolean hasRoleItem (java.lang.String roleName)`
- `boolean isAccountRevokeChallengeActive ( CertificationItem item)`
- `static boolean isAccountRevokeChallengeActive ( CertificationItem item, Resolver resolver)`
- `boolean isAccountRevokeChallengeGenerated ( CertificationItem item)`
- `boolean isBulkCertified ()`
- `boolean isEntityDelegated ()`
- `boolean isNewUser ()`
- `void markForContinuousFlush ()`
- `void markForRefresh ()`
- `void markForRefresh ( SailPointContext context)`
- `java.util.List<CertificationItem> mergeEntity ( CertificationEntity entity, boolean authoritative, boolean markDiffs)`
- `java.util.List<CertificationItem> mergeEntity ( CertificationEntity entity, boolean authoritative, boolean markDiffs, boolean updateOnly, boolean purgeMergedItems)`
- `void refreshActionRequired ()`
- `void refreshContinuousState ( Certification cert)`
- `boolean refreshHasDifferences ( IdentityDifference diff, Resolver resolver)`
- `void refreshSummaryStatus (java.lang.Boolean completeOverride)`
- `void removeAutoApprovals ( SailPointContext context, Identity decider, java.lang.String workItemId)`
- `void removeItem ( CertificationItem item)`
- `boolean rollbackChanges (java.lang.String workItemId)`
- `void setAccountGroup (java.lang.String accountGroup)`
- `void setAccountGroup ( ManagedAttribute accountGroup)`
- `void setApplication (java.lang.String application)`
- `void setApplication ( Application application)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attributes)`
- `void setBulkCertified (boolean bulkCertified)`
- `void setCertification ( Certification cert)`
- `void setCompositeScore (int compositeScore)`
- `void setDifferences ( IdentityDifference diffs)`
- `void setFirstname (java.lang.String firstname)`
- `void setIdentity (java.lang.String s)`
- `void setIdentity ( AbstractCertifiableEntity entity)`
- `void setLastname (java.lang.String lastname)`
- `void setNativeIdentity (java.lang.String nativeIdentity)`
- `void setNewUser (boolean newUser)`
- `void setPendingCertification (java.lang.String id)`
- `void setReferenceAttribute (java.lang.String referenceAttribute)`
- `void setRoleSnapshot ( RoleSnapshot snapshot)`
- `void setSchemaObjectType (java.lang.String val)`
- `void setSnapshotId (java.lang.String s)`
- `void setType ( CertificationEntity.Type _type)`
- `void visit ( Visitor v)`

---

## CertificationGroup.Status

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `CertificationGroup.Status`
- `sailpoint.object.CertificationGroup.Status`
- `java.io.Serializable`
- `java.lang.Comparable<CertificationGroup.Status>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticCertificationGroup.Status valueOf (java.lang.String name)`
- `staticCertificationGroup.Status[] values ()`

---

## CertificationGroup.Type

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `CertificationGroup.Type`
- `sailpoint.object.CertificationGroup.Type`
- `java.io.Serializable`
- `java.lang.Comparable<CertificationGroup.Type>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticCertificationGroup.Type valueOf (java.lang.String name)`
- `staticCertificationGroup.Type[] values ()`

---

## CertificationGroup

**Package:** `sailpoint.object`

**Description:** Represents a grouping of Certification objects. Most commonly, this is used to group together all the access reviews generated for a given certification schedule execution.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.CertificationGroup`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String SCHEDULE_FREQUENCY`

**Methods:**
- `void addMessage ( Message msg)`
- `void addMessages (java.util.List< Message > msgs)`
- `Certification.CertificationStatistics calculateStatistics ( SailPointContext context)`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `int getCompletedCertifications ()`
- `CertificationDefinition getDefinition ()`
- `java.util.List<Message> getMessages ()`
- `int getPercentComplete ()`
- `CertificationGroup.Status getStatus ()`
- `int getTotalCertifications ()`
- `CertificationGroup.Type getType ()`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> a)`
- `void setCompletedCertifications (int completedCertifications)`
- `void setDefinition ( CertificationDefinition certificationDefinition)`
- `void setMessages (java.util.List< Message > messages)`
- `void setPercentComplete (int percentComplete)`
- `void setStatus ( CertificationGroup.Status status)`
- `void setTotalCertifications (int totalCertifications)`
- `void setType ( CertificationGroup.Type type)`
- `void visit ( Visitor v)`

---

## CertificationItem.SubType

**Package:** `sailpoint.object`

**Description:** Differentiates different certifiables which share the same basic type. This is being used in cases where a given item type is handled the same in all but a few places. - AssignedRole: The role being certified was assigned rather than detected.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `CertificationItem.SubType`
- `sailpoint.object.CertificationItem.SubType`
- `java.io.Serializable`
- `java.lang.Comparable<CertificationItem.SubType>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticCertificationItem.SubType valueOf (java.lang.String name)`
- `staticCertificationItem.SubType[] values ()`

---

## CertificationItem.Type

**Package:** `sailpoint.object`

**Description:** Item types. - Bundle: Cert: Item covers an individual user's entitlements. - BusinessRole: Item certifies the parent-child relationship between two business roles. So the certifier will be certifying that the relationship between this business role and its parent(the CertificationEntity) is valid - Profile: Certifies that the profile is a valid member of a given BusinessRole(the CertificationEntity).

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `CertificationItem.Type`
- `sailpoint.object.CertificationItem.Type`
- `java.io.Serializable`
- `java.lang.Comparable<CertificationItem.Type>`
- `sailpoint.tools.MessageKeyHolder`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `java.lang.String getShortMessageKey ()`
- `staticCertificationItem.Type valueOf (java.lang.String name)`
- `staticCertificationItem.Type[] values ()`

---

## CertificationItem

**Package:** `sailpoint.object`

**Description:** The state of one item within an Certification. There are several types of certification item that use different properties.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.AbstractCertificationItem`
- `sailpoint.object.CertificationItem`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `java.lang.Comparable<CertificationItem>`
- `Notifiable`
- `Phaseable`
- `WorkItemOwnerChangeListener`
- `sailpoint.tools.WatchableMap.Watcher<java.lang.String,​java.lang.Object>`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATTR_AUTO_DECISION_GENERATED`
- `static java.lang.String ATTR_RECOMMENDATION`
- `static java.lang.String ATTR_ROLE_ASSIGNMENT`
- `static java.lang.String ATTR_ROLE_DETECTION`

**Methods:**
- `void acceptChallenge ( Identity who, java.lang.String comments)`
- `void acknowledge ( SailPointContext context, Identity who, java.lang.String workItem, java.lang.String comments)`
- `boolean allowAccountLevelActions ()`
- `static boolean allowAccountLevelActions ( CertificationItem.Type type, java.lang.String appName, Certification.Type certType)`
- `void approve ( SailPointContext context, Identity who, java.lang.String workItem)`
- `void approve ( SailPointContext context, Identity who, java.lang.String workItem, java.lang.String comments)`
- `void approve ( SailPointContext context, Identity who, java.lang.String workItem, java.lang.String comments, boolean autoDecision)`
- `void approve ( SailPointContext context, Identity who, java.lang.String workItem, ProvisioningPlan additionalActions, java.lang.String additionalActionOwner, java.lang.String additionalActionDesc, java.lang.String additionalActionComments)`
- `void approveAccount ( SailPointContext context, Identity who, java.lang.String workItem, java.lang.String comments)`
- `void assignContinuousState ( AbstractCertificationItem.ContinuousState state, Certification cert)`
- `java.util.List<CertificationItem> bulkCertify ( Identity who, java.lang.String workItem, CertificationAction bulkAction, CertificationItemSelector selector, boolean autoClose)`
- `boolean calculateExceptionDifferences ( IdentityDifference diff, java.util.Map<java.lang.String,java.util.Map<java.lang.String,java.lang.Boolean>> newAttrs, java.util.Map<java.lang.String,java.util.Map<java.lang.String,java.lang.Boolean>> newPerms)`
- `void challengeDecisionExpired ()`
- `boolean challengeExpired ()`
- `void challengeGenerated ( WorkItem item, Identity owner)`
- `java.lang.String checkForDecisionErrors ( Identity who, java.lang.String workItem, CertificationAction.Status newAction, boolean isActionOnThisItem)`
- `void clearChallenge ()`
- `void clearDecision ( SailPointContext context, Identity who, java.lang.String workItem)`
- `void clearDecisionForContinuous ()`
- `void clearDecisionForManagerChange ()`
- `void clearIds ()`
- `int compareTo ( CertificationItem item)`
- `void delegate ( SailPointContext context, Identity requester, java.lang.String workItem, java.lang.String recipient, java.lang.String description, java.lang.String comments)`
- `java.lang.String getAccountGroup ()`
- `java.util.List<java.lang.String> getApplicationNames ()`
- `java.util.List<Application> getApplications ( CertificationAction action, boolean isBulkCertified, Resolver resolver)`
- `java.util.Set<Application> getApplications ( Resolver r)`
- `java.lang.Object getAttribute (java.lang.String attr)`
- `java.util.Map<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getBundle ()`
- `Bundle getBundle ( Resolver r)`
- `java.lang.String getBundleAssignmentId ()`
- `java.util.List<EntitlementSnapshot> getBundleEntitlements ()`
- `Certification getCertification ()`
- `CertificationEntity getCertificationEntity ()`
- `CertificationChallenge getChallenge ()`
- `java.util.List<java.lang.String> getClassificationNames ()`
- `Identity getDefaultRemediator ( Resolver resolver)`
- `java.util.List<EntitlementSnapshot> getEntitlements ()`
- `java.lang.String getErrorDescription ()`
- `int getEscalationCount ()`
- `java.lang.String getExceptionApplication ()`
- `java.lang.String getExceptionAttributeName ()`
- `java.lang.String getExceptionAttributeValue ()`
- `EntitlementSnapshot getExceptionEntitlements ()`
- `Message getExceptionEntitlementsDescription ()`
- `java.lang.String getExceptionPermissionRight ()`
- `java.lang.String getExceptionPermissionTarget ()`
- `java.util.Date getExpirationDate ()`
- `java.util.Map<java.lang.String,​java.lang.Object> getExtendedAttributes ()`
- `java.util.Date getFinishedDate ()`
- `java.lang.String getIdentity ()`
- `Identity getIdentity ( Resolver r)`
- `java.lang.Boolean getIiqElevatedAccess ()`
- `LinkSnapshot getLinkSnapshot ( SailPointContext ctx, java.lang.String application, java.lang.String instance, java.lang.String nativeId)`
- `boolean getNeedsRefresh ()`
- `Certification.Phase getNextPhase ()`
- `java.util.Date getNextPhaseTransition ()`
- `NotificationConfig getNotificationConfig ()`
- `java.lang.String getNotificationName ()`
- `Identity getNotificationOwner ( Resolver resolver)`
- `staticObjectConfig getObjectConfig ()`
- `CertificationEntity getParent ()`
- `Certification.Phase getPhase ()`
- `PolicyViolation getPolicyViolation ()`
- `Certification.Phase getPreviousPhase ()`
- `Recommendation getRecommendation ()`
- `java.lang.String getRecommendValue ()`
- `int getRemindersSent ()`
- `RoleAssignment getRoleAssignment ()`
- `RoleDetection getRoleDetection ()`
- `java.util.List<java.lang.String> getRolesToRemediate ()`
- `java.lang.String getSecondarySortKey ()`
- `java.lang.String getShortDescription ()`
- `Snapshot getSnapshot ()`
- `static java.util.Comparator<CertificationItem> getSortComparator (boolean secondarySort)`
- `java.lang.String getSortKey ()`
- `CertificationItem.SubType getSubType ()`
- `SailPointObject getTargetObject ( Resolver r)`
- `CertificationItem.Type getType ()`
- `java.lang.String getViolationSummary ()`
- `java.util.Date getWakeUpDate ()`
- `boolean hasAssignedScope ()`
- `void incrementEscalationCount ()`
- `void incrementRemindersSent ()`
- `boolean isActedUpon ()`
- `boolean isAutoDecisionGenerated ()`
- `boolean isChallengeActive ()`
- `boolean isChallengeActive ( Resolver resolver)`
- `boolean isChallengeGenerated ()`
- `boolean isCleared ()`
- `static boolean isDecisionLockedByPhase ( Certification cert, CertificationAction action, Certification.Phase itemPhase)`
- `static boolean isDecisionLockedByRevokes ( Certification cert, CertificationDelegation itemDelegation, CertificationDelegation parentDelegation, CertificationAction action)`
- `boolean isDelegated ()`
- `boolean isDelegatedOrWaitingReview ()`
- `boolean isEscalateOnMaxReminders ()`
- `boolean isExpirable ()`
- `boolean isExpired ()`
- `boolean isFinished ()`
- `boolean isHistorical ()`
- `java.lang.Boolean isIiqElevatedAccess ()`
- `boolean isNeedsContinuousFlush ()`
- `boolean isReturned ()`
- `boolean isReviewed ()`
- `boolean isReviewRequired ()`
- `void markForContinuousFlush ()`
- `void markForRefresh ()`
- `void markForRefresh ( SailPointContext context)`
- `boolean matches ( IdentityHistoryItem historyItem)`
- `void merge ( CertificationItem item)`
- `void mitigate ( SailPointContext context, Identity who, java.lang.String workItem, java.util.Date expiration, java.lang.String comments)`
- `boolean referencesApplications (java.util.List<java.lang.String> applicationNames, Resolver resolver)`
- `void refreshActionRequired ()`
- `boolean refreshHasDifferences ( IdentityDifference diff, Resolver resolver)`
- `void refreshSummaryStatus (java.lang.Boolean completeOverride)`
- `void rejectChallenge ( Identity who, java.lang.String comments)`
- `void remediate ( SailPointContext context, Identity who, java.lang.String workItem, CertificationAction.RemediationAction action, java.lang.String recipient, java.lang.String description, java.lang.String comments, ProvisioningPlan details, ProvisioningPlan additionalActions)`
- `boolean requiresReview ()`
- `static boolean requiresReview ( CertificationAction action, CertificationDelegation itemDel, CertificationDelegation entityDel)`
- `void resetRemindersSent ()`
- `void review ( Identity who, CertificationAction toReview)`
- `void revokeAccount ( SailPointContext context, Identity who, java.lang.String workItem, CertificationAction.RemediationAction action, java.lang.String recipient, java.lang.String description, java.lang.String comments)`
- `void saveEscalationError ( InvalidEscalationTargetException error)`
- `void setApplicationCollection (java.util.Collection< Application > applications)`
- `void setApplicationNames (java.util.List<java.lang.String> applicationNames)`
- `void setAttribute (java.lang.String attr, java.lang.Object value)`
- `void setAttributes (java.util.Map<java.lang.String,java.lang.Object> attributes)`
- `void setAutoDecisionGenerated (boolean autoDecision)`
- `void setBundle (java.lang.String s)`
- `void setBundle ( Bundle b)`
- `void setBundleAssignmentId (java.lang.String id)`
- `void setBundleEntitlements (java.util.List< EntitlementSnapshot > ents)`
- `void setChallenge ( CertificationChallenge challenge)`
- `void setClassificationNames (java.util.List<java.lang.String> classificationNames)`
- `void setExceptionApplication (java.lang.String exceptionApplication)`
- `void setExceptionAttributeName (java.lang.String exceptionEntitlement)`
- `void setExceptionAttributeValue (java.lang.String exceptionValue)`
- `void setExceptionEntitlements ( EntitlementSnapshot ents)`
- `void setExceptionPermissionRight (java.lang.String right)`
- `void setExceptionPermissionTarget (java.lang.String target)`
- `void setExtended (int index, java.lang.String value)`
- `void setFinishedDate (java.util.Date finishedDate)`
- `void setIiqElevatedAccess (java.lang.Boolean elevatedAccess)`
- `void setNeedsContinuousFlush (boolean flushed)`
- `void setNeedsRefresh (boolean needsRefresh)`
- `void setNextPhaseTransition (java.util.Date next)`
- `void setParent ( CertificationEntity entity)`
- `void setPhase ( Certification.Phase phase)`
- `void setPolicyViolation ( PolicyViolation v)`
- `protected void setPseudo (java.lang.String name, java.lang.Object value)`
- `void setReadyForRemediation (boolean ready)`
- `void setRecommendation ( Recommendation recommendation)`
- `void setRecommendValue (java.lang.String recommendValue)`
- `void setRemindersSent (int sent)`
- `void setRoleAssignment ( RoleAssignment roleAssignment)`
- `void setRoleDetection ( RoleDetection roleDetection)`
- `void setSubType ( CertificationItem.SubType subType)`
- `void setType ( CertificationItem.Type type)`
- `void setWakeUpDate (java.util.Date nextWakeUp)`
- `void sort ()`
- `java.lang.String toString ()`
- `boolean useRevokeAccountInsteadOfRevoke ()`
- `static boolean useRevokeAccountInsteadOfRevoke ( Certification cert, CertificationItem.Type itemType, boolean allowBulkAccountActions)`
- `void visit ( Visitor v)`
- `boolean wasDecidedInIdentityDelegationChain ( CertificationDelegation identityDel)`

---

## CertificationItemSelector

**Package:** `sailpoint.object`

**Description:** Interface that tells whether a certification item matches certain criteria.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `boolean matches ( CertificationItem item)`

---

## CertificationLink

**Package:** `sailpoint.object`

**Description:** Part of the Identity model. Used to represent references to past certifications made for this identity.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.CertificationLink`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `boolean equals (java.lang.Object o)`
- `java.lang.String getApplicationId ()`
- `java.util.List<java.lang.String> getCertifiers ()`
- `java.util.Date getCompleted ()`
- `java.lang.String getId ()`
- `IdentitySnapshot getIdentitySnapshot ( Resolver resolver)`
- `java.lang.String getIdentitySnapshotId ()`
- `java.util.Date getModified ()`
- `Certification.Type getType ()`
- `int hashCode ()`
- `void setApplicationId (java.lang.String applicationId)`
- `void setCertifiers (java.util.List<java.lang.String> s)`
- `void setCompleted (java.util.Date d)`
- `void setId (java.lang.String s)`
- `void setIdentitySnapshotId (java.lang.String id)`
- `void setModified (java.util.Date d)`
- `void setType ( Certification.Type t)`

---

## CertificationPhaseConfig

**Package:** `sailpoint.object`

**Description:** Configuration for a Certification phase.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.CertificationStateConfig`
- `sailpoint.object.CertificationPhaseConfig`

**Attributes:** N/A

**Methods:**
- `Certification.Phase getPhase ()`
- `void setPhase ( Certification.Phase phase)`

---

## CertificationSchedule

**Package:** `sailpoint.object`

**Description:** This class is a composite object that holds a CertificationDefinition and the properties need to generate a TaskSchedule. It is used to simplify the process of passing a set of certification schedule parameters around.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.CertificationSchedule`

**Attributes:**
- `static java.lang.String ARG_CERTIFICATION_DEFINITION_ID`
- `static java.lang.String ARG_FIRST_EXECUTION`

**Methods:**
- `TaskSchedule buildTask ( SailPointContext context)`
- `java.util.Date getActivated ()`
- `java.util.Date getActiveEndDate ()`
- `java.util.Date getActiveStartDate ()`
- `int getApplicationCount ()`
- `Scope getAssignedScope ()`
- `java.util.Date getAutomaticClosingDate ()`
- `java.util.Date getChallengeEndDate ()`
- `CertificationDefinition getDefinition ()`
- `java.lang.String getDescription ()`
- `TaskSchedule getExistingTask ( SailPointContext context)`
- `java.util.Date getFirstExecution ()`
- `java.lang.String getFrequency ()`
- `java.lang.String getName ()`
- `java.util.Date getRemediationEndDate ()`
- `java.util.Date getRemediationStartDate ()`
- `java.lang.String getTaskId ()`
- `boolean isGlobalCertification ()`
- `boolean isRunNow ()`
- `void setActivated (java.util.Date activated)`
- `void setAssignedScope ( Scope assignedScope)`
- `void setDefinition ( CertificationDefinition definition)`
- `void setDescription (java.lang.String description)`
- `void setFirstExecution (java.util.Date firstExecution)`
- `void setFrequency (java.lang.String frequency)`
- `void setName (java.lang.String name)`
- `void setRunNow (boolean runNow)`
- `void setTaskId (java.lang.String taskId)`

---

## CertificationScheduleChangeEvent

**Package:** `sailpoint.object`

**Description:** An event that gets fired when a certification schedule is created/update/ deleted.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.AbstractChangeEvent`
- `sailpoint.object.CertificationScheduleChangeEvent`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `TaskSchedule getNewTaskSchedule ()`
- `TaskSchedule getOldTaskSchedule ()`

---

## CertificationSnapshot

**Package:** `sailpoint.object`

**Description:** Only persisted as XML.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.CertificationSnapshot`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.util.List<java.lang.String> getCertifiers ()`
- `java.util.List<java.lang.String> getCompletedEntities ()`
- `java.util.List<java.lang.String> getDelegatedEntities ()`
- `java.util.List<java.lang.String> getTotalEntities ()`
- `Certification.Type getType ()`
- `boolean isXml ()`
- `void setCertifiers (java.util.List<java.lang.String> certifiers)`
- `void setCompletedEntities (java.util.List<java.lang.String> completedEntities)`
- `void setDelegatedEntities (java.util.List<java.lang.String> delegatedEntities)`
- `void setTotalEntities (java.util.List<java.lang.String> totalEntities)`
- `void setType ( Certification.Type type)`

---

## CertificationStateConfig<S extends java.lang.Comparable>

**Package:** `sailpoint.object`

**Description:** Configuration for a Certification state.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.CertificationStateConfig<S>`

**Attributes:** N/A

**Methods:**
- `static <S extends java.lang.Comparable>java.util.Date calculateStateEndDate (S state, java.util.List<? extends CertificationStateConfig <S>> configs, java.util.Date startDate)`
- `static <S extends java.lang.Comparable>java.util.Date calculateStateEndDate (S startState, S endState, java.util.List<? extends CertificationStateConfig <S>> configs, java.util.Date startDate)`
- `Duration getDuration ()`
- `static <S extends java.lang.Comparable>S getNextState (java.util.List<? extends CertificationStateConfig <S>> configs, S current, S initialState, S endState)`
- `NotificationConfig getNotificationConfig ()`
- `static <S extends java.lang.Comparable>S getPreviousState (java.util.List<? extends CertificationStateConfig <S>> configs, S current)`
- `S getState ()`
- `static <T extendsCertificationStateConfig>T getStateConfig (java.lang.Object state, java.util.List<T> configs)`
- `boolean isEnabled ()`
- `static boolean isEnabled (java.lang.Object state, java.util.List<? extends CertificationStateConfig > configs)`
- `void setDuration ( Duration duration)`
- `void setEnabled (boolean enabled)`
- `void setNotificationConfig ( NotificationConfig notificationConfig)`
- `void setState ( S state)`

---

## CertificationStatistic

**Package:** `sailpoint.object`

**Description:** Used to capture statistics about all of the open certifications that are currently owned/related to a SailPointObject such as an identity/application/group definition. See sailpoint.api.CertificationService for ways in which these are built and sent to the UI.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.CertificationStatistic`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `int getCompleted ()`
- `int getDelegated ()`
- `int getOverdue ()`
- `int getPercentComplete ()`
- `int getRemaining ()`
- `int getRemediationsCompleted ()`
- `int getRemediationsStarted ()`
- `int getTotal ()`
- `void setCompleted (int completed)`
- `void setDelegated (int delegated)`
- `void setOverdue (int overdue)`
- `void setRemediationsCompleted (int remediationsCompleted)`
- `void setRemediationsStarted (int remediationsStarted)`
- `void setTotal (int total)`

---

## ChangeSummary

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ChangeSummary`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.util.List<Difference> getDifferences ()`
- `boolean isCreate ()`
- `boolean isDelete ()`
- `void setCreate (boolean b)`
- `void setDelete (boolean b)`
- `void setDifferences (java.util.List< Difference > diffs)`

---

## Chart

**Package:** `sailpoint.object`

**Description:** Holds information about optional charts included as part of live reports.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Chart`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String ATTR_ROWS`
- `static java.lang.String CHART_TYPE_COLUMN`
- `static java.lang.String CHART_TYPE_LINE`
- `static java.lang.String CHART_TYPE_PIE`
- `static java.lang.String FIELD_CATEGORY`
- `static java.lang.String FIELD_SERIES`
- `static java.lang.String FIELD_VALUE`

**Methods:**
- `void addAttribute (java.lang.String name, java.lang.Object value)`
- `java.lang.Object getAttribute (java.lang.String key)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getBottomLabel ()`
- `java.lang.String getCategory ()`
- `java.lang.String getCustomizerClass ()`
- `java.util.List<java.util.Map<java.lang.String,​java.lang.Object>> getData ()`
- `Rule getDataSourceRule ()`
- `java.lang.String getGroupBy ()`
- `java.util.List<java.lang.String> getGroupByList ()`
- `java.lang.String getLeftLabel ()`
- `int getLimit ()`
- `java.lang.String getNullCategory ()`
- `java.lang.String getNullSeries ()`
- `Script getScript ()`
- `java.lang.String getSeries ()`
- `java.util.List<Sort> getSortBy ()`
- `java.lang.String getTitle ()`
- `java.lang.String getType ()`
- `java.lang.String getValue ()`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attributes)`
- `void setBottomLabel (java.lang.String bottomLabel)`
- `void setCategory (java.lang.String category)`
- `void setCustomizerClass (java.lang.String customizerClass)`
- `void setData (java.util.List<java.util.Map<java.lang.String,java.lang.Object>> data)`
- `void setDataSourceRule ( Rule rule)`
- `void setGroupBy (java.lang.String groupBy)`
- `void setLeftLabel (java.lang.String leftLabel)`
- `void setLimit (int limit)`
- `void setNullCategory (java.lang.String nullCategory)`
- `void setNullSeries (java.lang.String nullSeries)`
- `void setScript ( Script script)`
- `void setSeries (java.lang.String series)`
- `void setSortBy (java.util.List< Sort > sortBy)`
- `void setTitle (java.lang.String title)`
- `void setType (java.lang.String type)`
- `void setValue (java.lang.String value)`

---

## ClassLists

**Package:** `sailpoint.object`

**Description:** Class that serves as a registry of class lists organized for various purposes.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.ClassLists`

**Attributes:**
- `static java.lang.Class[] ExportClasses`
- `static java.lang.Class[] ForbiddenExtractableClasses`
- `static java.lang.Class[] MajorClasses`
- `static java.lang.Class[] NonExtractableClasses`
- `static java.lang.Class[] VolumeClasses`

**Methods:** N/A

---

## Classifiable

**Package:** `sailpoint.object`

**Description:** Interface for objects that support Classifications

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `default boolean addClassification ( Classification classification, java.lang.String source, boolean effective)`
- `boolean addClassification ( ObjectClassification classification)`
- `default java.util.List<java.lang.String> getClassificationDisplayNames ()`
- `default java.util.List<java.lang.String> getClassificationNames ()`
- `java.util.List<ObjectClassification> getClassifications ()`
- `default boolean removeClassification ( Classification c)`
- `boolean removeClassification ( ObjectClassification classification)`
- `default void removeClassificationsBySource (java.lang.String source)`
- `void setClassifications (java.util.List< ObjectClassification > classifications)`
- `default void updateClassificationsBySource (java.util.Set< Classification > updates, java.lang.String source, boolean effective)`

---

## Classification

**Package:** `sailpoint.object`

**Description:** Simple SailPoint object that can be used to classify some other object. Currently can be associated with Bundle and ManagedAttribute objects.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Classification`
- `java.io.Serializable`
- `Describable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `void addDescription (java.lang.String locale, java.lang.String desc)`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getDescription (java.lang.String locale)`
- `java.lang.String getDescription (java.util.Locale locale)`
- `java.util.Map<java.lang.String,​java.lang.String> getDescriptions ()`
- `java.lang.String getDisplayableName ()`
- `java.lang.String getDisplayName ()`
- `java.lang.String getOrigin ()`
- `java.lang.String getType ()`
- `boolean hasAssignedScope ()`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attributes)`
- `void setDescriptions (java.util.Map<java.lang.String,java.lang.String> map)`
- `void setDisplayName (java.lang.String displayName)`
- `void setOrigin (java.lang.String s)`
- `void setType (java.lang.String t)`
- `void visit ( Visitor v)`

---

## CloudAccess3Way

**Package:** `sailpoint.object`

**Description:** Because a CloudAccessRole can have different CloudAccessScopes depending on the context of the CloudAcesssGroup also, we model the relationships using this association table. Previously, the CloudAccessRole had a field to hold a list of scopes. But now, since we have learned that a CloudAccessRole has different depending on the CloudAccessGroup it is in, we moved to this association model which provides the flexibility of using both the CloudAccessGroup and CloudAccessRole to find the list of CloudAccessScope.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.CloudAccess3Way`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `CloudAccessGroup getCloudAccessGroup ()`
- `CloudAccessRole getCloudAccessRole ()`
- `CloudAccessScope getCloudAccessScope ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `void setCloudAccessGroup ( CloudAccessGroup cloudAccessGroup)`
- `void setCloudAccessRole ( CloudAccessRole cloudAccessRole)`
- `void setCloudAccessScope ( CloudAccessScope cloudAccessScope)`

---

## CloudAccessGroup

**Package:** `sailpoint.object`

**Description:** Objects normally have unique user-defined names, though some like AuditRecord do not have names at all, and others like SODConstraint have names that might not be unique.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.CloudAccessGroup`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.String getApplicationId ()`
- `java.lang.String getCloudType ()`
- `java.lang.String getDisplayName ()`
- `java.util.Date getEventTimeStamp ()`
- `java.lang.String getName ()`
- `java.lang.String getObjectType ()`
- `java.lang.String getUri ()`
- `boolean hasAssignedScope ()`
- `void setApplicationId (java.lang.String applicationId)`
- `void setCloudType (java.lang.String cloudType)`
- `void setDisplayName (java.lang.String displayName)`
- `void setEventTimeStamp (java.util.Date eventTimeStamp)`
- `void setName (java.lang.String name)`
- `void setObjectType (java.lang.String objectType)`
- `void setUri (java.lang.String uri)`
- `void visit ( Visitor v)`

---

## CloudAccessObjectUtil

**Package:** `sailpoint.object`

**Description:** Use this class to read/delete the associations between CloudAccessGroup, CloudAccessRole, and CloudAccessScope.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.CloudAccessObjectUtil`

**Attributes:** N/A

**Methods:**
- `static void deleteGroupAll ( SailPointContext ctx, CloudAccessGroup group)`
- `static void deleteGroupRoles ( SailPointContext ctx, CloudAccessGroup group, java.util.List< CloudAccessRole > rolesToDelete)`
- `static void deleteGroupRoleScopes ( SailPointContext ctx, CloudAccessGroup group, CloudAccessRole role, java.util.List< CloudAccessScope > scopesToDelete)`
- `static void deleteGroupRoleScopesAll ( SailPointContext ctx, CloudAccessGroup group, CloudAccessRole role)`
- `static void deleteRoleAll ( SailPointContext ctx, CloudAccessRole role)`
- `static void deleteScopeAll ( SailPointContext ctx, CloudAccessScope scope)`
- `static boolean deleteUngroupedRole ( SailPointContext ctx, CloudAccessRole role)`
- `static java.util.Set<java.lang.String> getCloudAccessGroupTypes ( SailPointContext ctx, java.lang.String managedAttrVal)`
- `static java.lang.String getCloudAccessRoleType ( SailPointContext ctx, java.lang.String managedAttrVal)`
- `static java.util.List<CloudAccessRole> getGroupRoles ( SailPointContext ctx, java.lang.String cloudAccessGroupId)`
- `static java.util.List<CloudAccessScope> getGroupRoleScopes ( SailPointContext ctx, java.lang.String cloudAccessGroupId, java.lang.String cloudAccessRoleId)`

---

## CloudAccessRole

**Package:** `sailpoint.object`

**Description:** Objects normally have unique user-defined names, though some like AuditRecord do not have names at all, and others like SODConstraint have names that might not be unique.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.CloudAccessRole`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.String getCloudType ()`
- `java.lang.String getDisplayName ()`
- `java.util.Date getEventTimeStamp ()`
- `java.lang.String getName ()`
- `java.lang.String getUri ()`
- `boolean hasAssignedScope ()`
- `void setCloudType (java.lang.String cloudType)`
- `void setDisplayName (java.lang.String displayName)`
- `void setEventTimeStamp (java.util.Date eventTimeStamp)`
- `void setName (java.lang.String name)`
- `void setUri (java.lang.String uri)`
- `void visit ( Visitor v)`

---

## CloudAccessScope

**Package:** `sailpoint.object`

**Description:** Objects normally have unique user-defined names, though some like AuditRecord do not have names at all, and others like SODConstraint have names that might not be unique.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.CloudAccessScope`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.String getCloudType ()`
- `java.lang.String getDisplayName ()`
- `java.lang.String getName ()`
- `java.lang.String getUri ()`
- `boolean hasAssignedScope ()`
- `void setCloudType (java.lang.String cloudType)`
- `void setDisplayName (java.lang.String displayName)`
- `void setName (java.lang.String name)`
- `void setUri (java.lang.String uri)`
- `void visit ( Visitor v)`

---

## ColumnConfig.FixedPosition

**Package:** `sailpoint.object`

**Description:** Enumeration for values of 'fixed' attribute. Only 'Right' is currently implemented.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ColumnConfig.FixedPosition`
- `sailpoint.object.ColumnConfig.FixedPosition`
- `java.io.Serializable`
- `java.lang.Comparable<ColumnConfig.FixedPosition>`

**Attributes:** N/A

**Methods:**
- `staticColumnConfig.FixedPosition valueOf (java.lang.String name)`
- `staticColumnConfig.FixedPosition[] values ()`

---

## ColumnConfig

**Package:** `sailpoint.object`

**Description:** A ColumnConfig holds information about columns of a grid, including the header for the column, the name of the property with the contents of the column, and a percent width for the column.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ColumnConfig`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `boolean equals (java.lang.Object obj)`
- `java.lang.String getDataIndex ()`
- `java.lang.String getDateStyle ()`
- `java.lang.Integer getDateStyleValue ()`
- `java.lang.String getEditorClass ()`
- `java.lang.String getEvaluator ()`
- `ColumnConfig.FixedPosition getFixed ()`
- `float getFlex ()`
- `java.lang.String getGroupProperty ()`
- `java.lang.String getHeaderKey ()`
- `java.lang.String getJsonDataIndex ()`
- `java.lang.String getJsonProperty ()`
- `int getMinWidth ()`
- `java.lang.String getName ()`
- `int getPercentWidth ()`
- `java.lang.String getPluginClass ()`
- `java.lang.String getProperty ()`
- `java.lang.String getRenderer ()`
- `java.lang.String getSecondarySort ()`
- `java.lang.String getSortProperty ()`
- `java.lang.String getStateId ()`
- `java.lang.String getTimeStyle ()`
- `java.lang.Integer getTimeStyleValue ()`
- `int getWidth ()`
- `int hashCode ()`
- `boolean isFieldOnly ()`
- `boolean isHidden ()`
- `boolean isHideable ()`
- `boolean isLocalize ()`
- `boolean isNoEscape ()`
- `boolean isPositionFixed ()`
- `boolean isResizable ()`
- `boolean isSortable ()`
- `void setDataIndex (java.lang.String dataIndex)`
- `void setDateStyle (java.lang.String dateStyle)`
- `void setEditorClass (java.lang.String editorClass)`
- `void setEvaluator (java.lang.String evaluator)`
- `void setFieldOnly (boolean fieldOnly)`
- `void setFixed ( ColumnConfig.FixedPosition fixed)`
- `void setFlex (float d)`
- `void setGroupProperty (java.lang.String groupProperty)`
- `void setHeaderKey (java.lang.String header)`
- `void setHidden (boolean hidden)`
- `void setHideable (boolean hideable)`
- `void setLocalize (boolean b)`
- `void setMinWidth (int width)`
- `void setName (java.lang.String val)`
- `void setNoEscape (boolean noEscape)`
- `void setPercentWidth (int width)`
- `void setPluginClass (java.lang.String pluginClass)`
- `void setPositionFixed (boolean positionFixed)`
- `void setProperty (java.lang.String property)`
- `void setRenderer (java.lang.String renderer)`
- `void setResizable (boolean resizable)`
- `void setSecondarySort (java.lang.String secondarySort)`
- `void setSortable (boolean sortable)`
- `void setSortProperty (java.lang.String sortProperty)`
- `void setStateId (java.lang.String stateId)`
- `void setTimeStyle (java.lang.String timeStyle)`
- `void setWidth (int width)`

---

## Comment

**Package:** `sailpoint.object`

**Description:** A Comment represents a comment added to a work item.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Comment`
- `java.io.Serializable`
- `sailpoint.tools.Localizable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.util.Comparator<Comment> SP_COMMENT_BY_DATE`

**Methods:**
- `boolean equals (java.lang.Object o)`
- `java.lang.String getAuthor ()`
- `java.lang.String getComment ()`
- `java.util.Date getDate ()`
- `java.lang.String getLocalizedMessage ()`
- `java.lang.String getLocalizedMessage (java.util.Locale locale, java.util.TimeZone timezone)`
- `int hashCode ()`
- `void setAuthor (java.lang.String author)`
- `void setComment (java.lang.String comment)`
- `void setDate (java.util.Date date)`
- `java.lang.String toString ()`

---

## CompositeDefinition.Tier

**Package:** `sailpoint.object`

**Description:** Tier application within a composite. Other than just indicating which apps are part of a composite, it also defines how to correlate a given link on a tier to a link on the primary tier app.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.CompositeDefinition.Tier`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getApplication ()`
- `java.util.Map<java.lang.String,​java.lang.String> getCorrelationMap ()`
- `java.lang.String getCorrelationRule ()`
- `IdentitySelector getIdentitySelector ()`
- `boolean hasCorrelationRule ()`
- `void setApplication (java.lang.String application)`
- `void setCorrelationMap (java.util.Map<java.lang.String,java.lang.String> correlationMap)`
- `void setCorrelationRule (java.lang.String correlationRule)`
- `void setIdentitySelector ( IdentitySelector selector)`

---

## CompositeDefinition

**Package:** `sailpoint.object`

**Description:** Defines the composition of a composite application and the relationship between the composite and it's tier applications. ThisSailPoint.connector.DefaultCompositeConnector, which is our base, out of the box connector for composites. NOTE: CompositeConnector implementations can completely custom to a customer, so it should not be assumed that a composite application will have this definition.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.CompositeDefinition`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void addTier ( CompositeDefinition.Tier tier)`
- `java.lang.String getAccountRule ()`
- `java.lang.String getPrimaryTier ()`
- `java.lang.String getRemediationRule ()`
- `java.util.List<java.lang.String> getTierAppList ()`
- `CompositeDefinition.Tier getTierByAppName (java.lang.String appName)`
- `java.util.List<CompositeDefinition.Tier> getTiers ()`
- `boolean hasAccountRule ()`
- `void setAccountRule (java.lang.String accountRule)`
- `void setPrimaryTier (java.lang.String primaryTier)`
- `void setRemediationRule (java.lang.String remediationRule)`
- `void setTiers (java.util.List< CompositeDefinition.Tier > tiers)`

---

## CompoundFilter

**Package:** `sailpoint.object`

**Description:** Used within IdentitySelector to define filters whose property names might reference attributes from several application accounts as well as attributes in the IdentityIQ identity cube. The scope of the property is defined by a prefix convention to avoid complicating the Filter model. Filter.eq("1:costCenter", "42"); Property names without a prefix are assumed to be identity attributes. This is used in combination with Matchmaker to do complex matching of Identity objects and their associated Links. Prefixes are usually numbers that are then used as indexes into the applications list. Prefixes can also be application names, but this is uncommon since names might contain spaces and this is not allowed in the string representation of filters.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.CompoundFilter`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String XML_PREAMBLE_COMPOUND`
- `static java.lang.String XML_PREAMBLE_FILTER`

**Methods:**
- `Application getApplication (int index)`
- `java.util.List<Application> getApplications ()`
- `Filter getFilter ()`
- `void load ()`
- `void parse (sailpoint.tools.xml.XMLReferenceResolver res, java.lang.String src)`
- `java.lang.String render ()`
- `void setApplications (java.util.List< Application > apps)`
- `void setFilter ( Filter f)`
- `void update (sailpoint.tools.xml.XMLReferenceResolver res, java.lang.String src)`

---

## CompressibleProperties

**Package:** `sailpoint.object`

**Description:** Interface for SailPointObjects to support compression of properties for storage For a SailPointObject to implement this interface it is required to supply the following: 1. A list of one or more PROPERTY NAMES that can be compressed for storage. 2. A boolean indicating that the list from #1 should be compressed. Since the compression can be turned off an on (by #2), it is necessary to know if an instance of the object was stored in a compressed state or not. Object must supply the following as well: 3. A PROPERTY NAME that indicates if an instance of the object was stored in a compressed state or not 4. A VALUE indicating an instance was stored as compressed. (The expected value of #3) WARNING: Only String property types are compressible see sailpoint.tools.Compressor compress method.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `java.lang.String getCompressedPropertyFlag ()`
- `java.lang.String getCompressedPropertyFlagValue ()`
- `java.util.List<java.lang.String> getCompressiblePropertyNames ()`
- `java.lang.Boolean shouldCompress ()`

---

## Configuration.EmailNotify

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Configuration.EmailNotify`
- `sailpoint.object.Configuration.EmailNotify`
- `java.io.Serializable`
- `java.lang.Comparable<Configuration.EmailNotify>`

**Attributes:** N/A

**Methods:**
- `staticConfiguration.EmailNotify valueOf (java.lang.String name)`
- `staticConfiguration.EmailNotify[] values ()`

---

## Configuration.EmailOAuthConfiguration

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Configuration.EmailOAuthConfiguration`

**Attributes:**
- `static java.lang.String ClientID`
- `static java.lang.String ClientSecret`
- `static java.lang.String RefreshTokenEndpoint`
- `static java.lang.String Scope`
- `static java.lang.String ServiceEndpoint`
- `static java.lang.String TokenEndpoint`

**Methods:** N/A

---

## Configuration.SmtpConfiguration

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Configuration.SmtpConfiguration`

**Attributes:**
- `static java.lang.String AuthenticationType`
- `static java.lang.String EncryptionType`
- `static java.lang.String Password`
- `static java.lang.String SessionProperties`
- `static java.lang.String SslSocketFactoryClass`
- `static java.lang.String Username`

**Methods:** N/A

---

## Configuration

**Package:** `sailpoint.object`

**Description:** Class to hold extensible configuration parameters. An instance of this class named "SystemConfiguration" holds many configuration parameters presented in the UI under the "System Setup" tab. Most of the name constants defined in this class are key names in the system configuration object.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Configuration`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `Cacheable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ACCELERATOR_PACK_VERSION`
- `static java.lang.String ACCESS_REQUEST_REMINDER_EMAIL_TEMPLATE`
- `static java.lang.String ACCESS_REQUEST_TYPES`
- `static java.lang.String ACCESSHISTORY_CONFIG`
- `static java.lang.String ACCESSHISTORY_CONFIG_CAPTURE_MAX_AGE_IN_DAYS`
- `static java.lang.String ACCESSHISTORY_CONFIG_CONSUMER_REFRESH_TIME`
- `static java.lang.String ACCESSHISTORY_CONFIG_JSON_FORMAT`
- `static java.lang.String ACCESSHISTORY_CONFIG_MAX_ALLOWED_PATCH_DOCUMENTS`
- `static java.lang.String ACCESSHISTORY_CONFIG_MAX_REQUEUES_ALLOWED`
- `static java.lang.String ACCESSHISTORY_CONFIG_SAMPLE_STRING`
- `static java.lang.String ACCESSHISTORY_CONFIG_SAVE_NON_INTERESTING_CHANGES`
- `static java.lang.String ACCESSHISTORY_CREATE_DISCARDED_MESSAGE_EVENT`
- `static java.lang.String ACCESSHISTORY_ENABLED`
- `static java.lang.String ACTIVE_PERIOD_DURATION`
- `static java.lang.String ACTIVEMQ_CONFIG`
- `static java.lang.String ADDITIONAL_ENTITLEMENT_GRANULARITY`
- `static java.lang.String ALLOW_ADMIN_PASS_THROUGH`
- `static java.lang.String ALLOW_CERT_ENTITY_BULK_ACCOUNT_REVOCATION`
- `static java.lang.String ALLOW_CERT_ENTITY_BULK_APPROVE`
- `static java.lang.String ALLOW_CERT_ENTITY_BULK_CLEAR_DECISIONS`
- `static java.lang.String ALLOW_CERT_ENTITY_BULK_REVOCATION`
- `static java.lang.String ALLOW_CREATE_ROLES_FROM_CERTIFICATION`
- `static java.lang.String ALLOW_DISABLE_NOTIFICATIONS`
- `static java.lang.String ALLOW_DUPLICATE_ACCOUNTS`
- `static java.lang.String ALLOW_LIST_VIEW_BULK_ACCOUNT_REVOKE`
- `static java.lang.String ALLOW_LIST_VIEW_BULK_APPROVE`
- `static java.lang.String ALLOW_LIST_VIEW_BULK_CLEAR_DECISIONS`
- `static java.lang.String ALLOW_LIST_VIEW_BULK_MITIGATE`
- `static java.lang.String ALLOW_LIST_VIEW_BULK_REASSIGN`
- `static java.lang.String ALLOW_LIST_VIEW_BULK_REVOKE`
- `static java.lang.String ALLOW_LIST_VIEW_BULK_SAVE_CUSTOM_ENTITY_FIELDS`
- `static java.lang.String ALLOW_MULTIPLE_ROLE_ASSIGNMENTS`
- `static java.lang.String ALLOW_PROV_MISSING_REQUIREMENTS`
- `static java.lang.String ALLOW_ROLE_PROPAGATION`
- `static java.lang.String ALLOW_SELF_CERTIFICATION`
- `static java.lang.String ALLOW_UNAUTHENTICATED_END_USER_PAGES`
- `static java.lang.String ALLOWED_ENTRA_JAVAX_FACES_RESOURCES`
- `static java.lang.String ALWAYS_USE_BASIC_AUTH_ELECTRONIC_SIGNATURE`
- `static java.lang.String API_AUTH_AUDIENCE`
- `static java.lang.String API_AUTH_ISSUERS`
- `static java.lang.String API_AUTH_SCOPE`
- `static java.lang.String API_CORRELATION_VARIABLE`
- `static java.lang.String APP_TARGET_COLLECTOR_REGISTRY`
- `static java.lang.String APPEND_POLICY_REQS`
- `static java.lang.String APPLICATION_POLICY_FORM`
- `static java.lang.String APPLICATION_TEMPLATE_ACCOUNT_USAGES`
- `static java.lang.String APPLICATION_TEMPLATES`
- `static java.lang.String APPLY_CUSTOM_RULE_AFTER_ATTRIBUTE_SYNC`
- `static java.lang.String ASSIMILATE_BULK_REASSIGNMENTS`
- `static java.lang.String ASYNC_CACHE_REFRESH`
- `static java.lang.String ATT_CATALOG_CACHE_TTL_MILLIS`
- `static java.lang.String ATT_CEF_LINK_ATTRIBUTE_NAME`
- `static java.lang.String ATT_CEF_LOGFILE_ACTIVITYFEED_DATASOURCE`
- `static java.lang.String ATT_CEF_LOGFILE_CORRELATION_RULE`
- `static java.lang.String ATT_CEF_LOGFILE_TRANSFORMATION_RULE`
- `static java.lang.String ATT_CEF_USER_NAME`
- `static java.lang.String ATT_EMAIL_NOTIFY`
- `static java.lang.String ATT_EMAIL_TEMPLATE`
- `static java.lang.String ATT_IDENTITIES`
- `static java.lang.String ATT_SIGNATURE_TYPE`
- `static java.lang.String ATT_TASK_COMPLETION_RULE`
- `static java.lang.String ATTACHMENT_CONFIG_RULES`
- `static java.lang.String ATTACHMENTS_ALLOWED_FILE_TYPES`
- `static java.lang.String ATTACHMENTS_ENABLED`
- `static java.lang.String ATTACHMENTS_FILENAME_ALLOWED_SPECIAL_CHARACTERS`
- `static java.lang.String ATTACHMENTS_MAX_FILE_SIZE`
- `static java.lang.String ATTACHMENTS_MAX_FILE_SIZE_LIMIT`
- `static java.lang.String ATTACHMENTS_MAX_PER_ITEM`
- `static java.lang.String ATTRIBUTE_SYNC_WORKGROUP`
- `static java.lang.String AUDIENCE_CLAIM_VALIDATION_REQUIRED`
- `static java.lang.String AUTH_QUESTION_LOCKOUT_DURATION_MILLIS`
- `static java.lang.String AUTH_QUESTIONS_ENABLED`
- `static java.lang.String AUTO_SIGN_OFF_WHEN_NOTHING_TO_CERTIFY`
- `static java.lang.String AUTOMATE_SIGNOFF_ON_REASSIGNMENT`
- `static java.lang.String AUTOMATE_SIGNOFF_POPUP`
- `static java.lang.String AUTOMATIC_CLOSING_ACTION`
- `static java.lang.String AUTOMATIC_CLOSING_COMMENTS`
- `static java.lang.String AUTOMATIC_CLOSING_DURATION`
- `static java.lang.String AUTOMATIC_CLOSING_ENABLED`
- `static java.lang.String AUTOMATIC_CLOSING_RULE_NAME`
- `static java.lang.String AUTOMATIC_CLOSING_SIGNER`
- `static java.lang.String BATCH_REQUEST_APPROVER`
- `static java.lang.String BLOCK_FORWARD_WORK_ITEM_SELF_CERTIFICATION`
- `static java.lang.String BPR_REFRESHED_DISABLED`
- `static java.lang.String BULK_REASSIGNMENT_EMAIL_TEMPLATE`
- `static java.lang.String BULK_SELECTION_COUNT_FOR_CONFIRMATION`
- `static java.lang.String BUNDLE_PROFILE_KEEP_ALIVE`
- `static java.lang.String BUNDLE_PROFILE_MAX_THREADS`
- `static java.lang.String BUNDLE_PROFILE_MIN_THREADS`
- `static java.lang.String BUNDLES_UI_DISPLAY_LIMIT`
- `static java.lang.String CACHED_OBJECT_DURATION`
- `static java.lang.String CACHED_OBJECT_NO_EXPIRATION`
- `static java.lang.String CAM_CONFIG`
- `static java.lang.String CAM_CONFIG_CLIENT_ID`
- `static java.lang.String CAM_CONFIG_CLIENT_SECRET`
- `static java.lang.String CAM_CONFIG_CONNECT_TIMEOUT_SECS`
- `static java.lang.String CAM_CONFIG_EVENT_ACK_ENDPOINT`
- `static java.lang.String CAM_CONFIG_EVENT_DO_INITIALIZATION`
- `static java.lang.String CAM_CONFIG_EVENT_GROUP_ID`
- `static java.lang.String CAM_CONFIG_EVENT_INITIALIZATION_ENDPOINT`
- `static java.lang.String CAM_CONFIG_EVENT_INITIALIZATION_ERROR`
- `static java.lang.String CAM_CONFIG_EVENT_INITIALIZATION_HOST`
- `static java.lang.String CAM_CONFIG_EVENT_INITIALIZED_DATE`
- `static java.lang.String CAM_CONFIG_EVENT_MESSAGES_ENDPOINT`
- `static java.lang.String CAM_CONFIG_GROUP_ENDPOINT`
- `static java.lang.String CAM_CONFIG_HEALTH_CHECK_ENDPOINT`
- `static java.lang.String CAM_CONFIG_HOSTNAME`
- `static java.lang.String CAM_CONFIG_IGNORE_RATE_LIMIT`
- `static java.lang.String CAM_CONFIG_OAUTH_HOSTNAME`
- `static java.lang.String CAM_CONFIG_READ_TIMEOUT_SECS`
- `static java.lang.String CAM_CONFIG_ROLE_ENDPOINT`
- `static java.lang.String CAM_CONFIG_SCOPE_ENDPOINT`
- `static java.lang.String CAM_CONFIG_SERVICE_ENDPOINT`
- `static java.lang.String CAM_CONFIG_SUBSCRIBERS_ENDPOINT`
- `static java.lang.String CAM_CONFIG_SUBSCRIPTIONS_ENDPOINT`
- `static java.lang.String CAM_CONFIG_SUPPORTED_APPS`
- `static java.lang.String CAM_ENABLED`
- `static java.lang.String CEF_LOG_FILE_AUDIT_EXTENSION`
- `static java.lang.String CEF_LOG_FILE_COLLECTOR_TYPE`
- `static java.lang.String CEF_LOG_FILE_DEVICE_PRODUCT`
- `static java.lang.String CEF_LOG_FILE_DEVICE_VENDOR`
- `static java.lang.String CEF_LOG_FILE_DEVICE_VERSION`
- `static java.lang.String CEF_LOG_FILE_EXTENSION`
- `static java.lang.String CEF_LOG_FILE_FORMAT`
- `static java.lang.String CEF_LOG_FILE_HEADER`
- `static java.lang.String CEF_LOG_FILE_IDENTITY_EXTENSION`
- `static java.lang.String CEF_LOG_FILE_LINK_EXTENSION`
- `static java.lang.String CEF_LOG_FILE_NAME`
- `static java.lang.String CEF_LOG_FILE_SEVERITY`
- `static java.lang.String CEF_LOG_FILE_SEVERITY_SYSLOG_COLUMN`
- `static java.lang.String CEF_LOG_FILE_SEVERITY_SYSLOG_SEVERITY`
- `static java.lang.String CEF_LOG_FILE_SIGNATURE_ID`
- `static java.lang.String CEF_LOG_FILE_SYSLOG_EXTENSION`
- `static java.lang.String CEF_LOG_FILE_VERSION`
- `static java.lang.String CERT_DECISION_CHALLENGED_EMAIL_TEMPLATE`
- `static java.lang.String CERT_PAGE_LIST_ITEMS`
- `static java.lang.String CERT_SCHEDULE_SHOW_ENTITLEMENT_UPDATE_CHECKBOX`
- `static java.lang.String CERT_SIGN_OFF_APPROVAL_EMAIL_TEMPLATE`
- `static java.lang.String CERTIFICATION_ACTIVE_PHASE_ENTER_RULE`
- `static java.lang.String CERTIFICATION_ACTIVE_PHASE_EXIT_RULE`
- `static java.lang.String CERTIFICATION_ARCHIVE_MAX_AGE`
- `static java.lang.String[] CERTIFICATION_ATTRIBUTES`
- `static java.lang.String CERTIFICATION_AUTO_APPROVE`
- `static java.lang.String CERTIFICATION_CHALLENGE_PHASE_ENTER_RULE`
- `static java.lang.String CERTIFICATION_CHALLENGE_PHASE_ENTER_RULE_LEGACY`
- `static java.lang.String CERTIFICATION_CHALLENGE_PHASE_EXIT_RULE`
- `static java.lang.String[] CERTIFICATION_DEFINITION_ATTRIBUTES`
- `static java.lang.String CERTIFICATION_DELEGATION_REVIEW`
- `static java.lang.String CERTIFICATION_DETAILED_VIEW_FILTER_SET`
- `static java.lang.String CERTIFICATION_DIFFERENCING_NO_ARCHIVE_SEARCHING`
- `static java.lang.String CERTIFICATION_DISABLE_DELEGATION_FORWARDING`
- `static java.lang.String CERTIFICATION_EMAIL_TEMPLATE`
- `static java.lang.String CERTIFICATION_ENTITY_COMPLETION_RULE`
- `static java.lang.String CERTIFICATION_ENTITY_CUSTOMIZATION_RULE`
- `static java.lang.String CERTIFICATION_ENTITY_DECACHE_INTERVAL`
- `static java.lang.String CERTIFICATION_ENTITY_DELEGATION_ENABLED`
- `static java.lang.String CERTIFICATION_ENTITY_REFRESH_RULE`
- `static java.lang.String CERTIFICATION_FINISH_PHASE_ENTER_RULE`
- `static java.lang.String CERTIFICATION_INCLUDE_CLASSIFICATIONS`
- `static java.lang.String CERTIFICATION_INCLUDE_ELEVATED_ACCESS`
- `static java.lang.String CERTIFICATION_ITEM_COMPLETION_RULE`
- `static java.lang.String CERTIFICATION_ITEM_CUSTOMIZATION_RULE`
- `static java.lang.String CERTIFICATION_ITEM_DELEGATION_ENABLED`
- `static java.lang.String CERTIFICATION_ITEM_FILTER_ATTRIBUTES`
- `static java.lang.String CERTIFICATION_ITEM_PAGE_SIZE`
- `static java.lang.String CERTIFICATION_LIMIT_REASSIGNMENTS`
- `static java.lang.String CERTIFICATION_MAX_AGE`
- `static java.lang.String CERTIFICATION_MITIGATION_DEPROVISION_ENABLED`
- `static java.lang.String CERTIFICATION_MITIGATION_DURATION`
- `static java.lang.String CERTIFICATION_MITIGATION_DURATION_AMOUNT`
- `static java.lang.String CERTIFICATION_MITIGATION_DURATION_SCALE`
- `static java.lang.String CERTIFICATION_MITIGATION_ENABLED`
- `static java.lang.String CERTIFICATION_MITIGATION_POPUP_ENABLED`
- `static java.lang.String CERTIFICATION_REASSIGNMENT_LIMIT`
- `static java.lang.String CERTIFICATION_REMEDIATION_PHASE_ENTER_RULE`
- `static java.lang.String CERTIFICATION_REMEDIATION_PHASE_EXIT_RULE`
- `static java.lang.String CERTIFICATION_REMINDER_EMAIL_TEMPLATE`
- `static java.lang.String CERTIFICATION_REQUIRED_DURATION`
- `static java.lang.String CERTIFICATION_SHOW_RECOMMENDATIONS`
- `static java.lang.String CERTIFICATION_SUBCERT_PAGE_SIZE`
- `static java.lang.String CERTIFIED_DURATION`
- `static java.lang.String CHALLENGE_ACCEPTED_EMAIL_TEMPLATE`
- `static java.lang.String CHALLENGE_DECISION_EXPIRED_EMAIL_TEMPLATE`
- `static java.lang.String CHALLENGE_EXPIRED_EMAIL_TEMPLATE`
- `static java.lang.String CHALLENGE_GENERATION_EMAIL_TEMPLATE`
- `static java.lang.String CHALLENGE_PERIOD_DURATION`
- `static java.lang.String CHALLENGE_PERIOD_ENABLED`
- `static java.lang.String CHALLENGE_PERIOD_END_EMAIL_TEMPLATE`
- `static java.lang.String CHALLENGE_PERIOD_START_EMAIL_TEMPLATE`
- `static java.lang.String CHALLENGE_REJECTED_EMAIL_TEMPLATE`
- `static java.lang.String CHART_BODY_FONT_NAME`
- `static java.lang.String CHART_BODY_FONT_SIZE`
- `static java.lang.String CHART_BODY_FONT_STYLE`
- `static java.lang.String CHART_LABEL_FONT_NAME`
- `static java.lang.String CHART_LABEL_FONT_SIZE`
- `static java.lang.String CHART_LABEL_FONT_STYLE`
- `static java.lang.String CHART_TITLE_FONT_NAME`
- `static java.lang.String CHART_TITLE_FONT_SIZE`
- `static java.lang.String CHART_TITLE_FONT_STYLE`
- `static java.lang.String CHECK_PASSWORD_POLICY_RULE`
- `static java.lang.String CHECK_PASSWORDS_AGAINST_ACCOUNT_ATTRIBUTES`
- `static java.lang.String CHECK_PASSWORDS_AGAINST_DICTIONARY`
- `static java.lang.String CHECK_PASSWORDS_AGAINST_IDENTITY_ATTRIBUTES`
- `static java.lang.String COLUMN_SUGGEST_BLACKLIST`
- `static java.lang.String COMMENT_CONFIG_RULES`
- `static java.lang.String COMMIT_MANUAL_OBJECT_REQUESTS`
- `static java.lang.String COMPLETE_CERTIFICATION_HIERARCHY`
- `static java.lang.String CONFIRM_RISKY_CERTIFICATION_SCHEDULES`
- `static java.lang.String CONNECTOR_REGISTRY`
- `static java.lang.String CONTINUOUS_CERT_REQUIRED_SCAN_INTERVAL`
- `static java.lang.String CONTINUOUS_OVERDUE_SCAN_INTERVAL`
- `static java.lang.String CREATE_IDENTITY_FORM`
- `static java.lang.String CUSTOM_THEME_CODE_MIRROR`
- `static java.lang.String DAHSBOARD_DEFAULT`
- `static java.lang.String DASHBOARD_COMPLIANCE_DEFAULT`
- `static java.lang.String DASHBOARD_LCM_SUFFIX`
- `static java.lang.String DASHBOARD_LIFECYCLE_DEFAULT`
- `static java.lang.String DASHBOARD_MAX_CERT_PERCENT_APPLICATIONS`
- `static java.lang.String DASHBOARD_MAX_CERT_PERCENT_GROUPS`
- `static java.lang.String DASHBOARD_MAX_CERT_PERCENTS`
- `static java.lang.String DATA_EXTRACT_TASKS_ENABLED`
- `static java.lang.String DATAEXTRACT_CONFIG`
- `static java.lang.String DEFAULT_ASSIGNEE`
- `static java.lang.String DEFAULT_EMAIL_FROM`
- `static java.lang.String DEFAULT_EMAIL_GAP`
- `static java.lang.String DEFAULT_EMAIL_HOST`
- `static java.lang.String DEFAULT_EMAIL_PORT`
- `static java.lang.String DEFAULT_ESCALATION_EMAIL_TEMPLATE`
- `static java.lang.String DEFAULT_ESCALATION_RULE`
- `static java.lang.String DEFAULT_HOME_WIDGETS`
- `static java.lang.String DEFAULT_LANGUAGE`
- `static java.lang.String DEFAULT_LIST_RESULT_SIZE`
- `static java.lang.String DEFAULT_MAX_REMINDERS`
- `static java.lang.String DEFAULT_QUICKLINK_CARDS`
- `static java.lang.String DEFAULT_REMEDIATION_MODIFIABLE_OP`
- `static java.lang.String DEFAULT_REMEDIATOR`
- `static java.lang.String DEFAULT_REMINDER_EMAIL_TEMPLATE`
- `static java.lang.String DEFAULT_REMINDER_START`
- `static java.lang.String DEFAULT_ROLE_CHANGE_APPROVER`
- `static java.lang.String DEFAULT_SERVER_ROOT_PATH`
- `static java.lang.String DEFAULT_TASK_COMPLETION_EMAIL_TEMPLATE`
- `static java.lang.String DEFAULT_WAKEUP_INTERVAL`
- `static java.lang.String DEFAULT_WORK_ITEM_DURATION`
- `static java.lang.String DELEGATION_EMAIL_TEMPLATE`
- `static java.lang.String DELEGATION_FINISHED_EMAIL_TEMPLATE`
- `static java.lang.String DELEGATION_REVOCATION_EMAIL_TEMPLATE`
- `static java.lang.String DETAILED_LOGIN_STYLE`
- `static java.lang.String DETECT_NATIVE_IDENTITY_CHANGE_CASE_SENSITIVE`
- `static java.lang.String DISABLE_DEFAULT_TO_APP_OWNER_REMEDIATION`
- `static java.lang.String DISABLE_PASSTHROUGH_AUTO_CREATE`
- `static java.lang.String DISABLE_POLICY_CACHE`
- `static java.lang.String DISABLE_ROLE_MODELER_TREE_VIEW`
- `static java.lang.String DISPLAY_CLASSIFICATIONS_IN_ACCESS_REQUEST`
- `static java.lang.String DISPLAY_ELEVATED_ACCESS_IN_ACCESS_REQUEST`
- `static java.lang.String DISPLAY_ENTITLEMENT_DESC`
- `static java.lang.String ELECTRONIC_SIGNATURE`
- `static java.lang.String EMAIL_NOTIFIER_CLASS`
- `static java.lang.String EMAIL_NOTIFIER_SEND_IMMEDIATELY`
- `static java.lang.String EMAIL_NOTIFIER_TYPE`
- `static java.lang.String EMAIL_NOTIFIER_TYPE_HTTP`
- `static java.lang.String EMAIL_NOTIFIER_TYPE_REDIRECT_TO_EMAIL`
- `static java.lang.String EMAIL_NOTIFIER_TYPE_REDIRECT_TO_FILE`
- `static java.lang.String EMAIL_NOTIFIER_TYPE_SMTP`
- `static java.lang.String EMAIL_REQUEST_DEFINITION`
- `static java.lang.String EMAIL_THREAD_LOCK_TIMEOUT_MIN`
- `static java.lang.String ENABLE_ACCOUNT_APPROVE_ACTION`
- `static java.lang.String ENABLE_ACCOUNT_REASSIGN_ACTION`
- `static java.lang.String ENABLE_ACCOUNT_REVOKE_ACTION`
- `static java.lang.String ENABLE_ACCOUNT_UNLOCK`
- `static java.lang.String ENABLE_AUTH_LOCKOUT`
- `static java.lang.String ENABLE_CONTRAST`
- `static java.lang.String ENABLE_FORGOT_PASSWORD`
- `static java.lang.String ENABLE_INTERCEPTED_DELETE_CAPTURE`
- `static java.lang.String ENABLE_LOCALIZED_APP_DESCRIPTIONS`
- `static java.lang.String ENABLE_LOCALIZED_MANAGED_ATTRIBUTE_DESCRIPTIONS`
- `static java.lang.String ENABLE_LOCALIZED_POLICY_DESCRIPTIONS`
- `static java.lang.String ENABLE_LOCALIZED_ROLE_DESCRIPTIONS`
- `static java.lang.String ENABLE_MODELER_MULTIPLE_ASSIGNMENTS`
- `static java.lang.String ENABLE_MODELER_PROFILE_VIEW`
- `static java.lang.String ENABLE_NATIVE_IDENTITY_CHANGE_EVENT_PROPAGATION`
- `static java.lang.String ENABLE_OVERRIDE_VIOLATION_DEFAULT_REMEDIATOR`
- `static java.lang.String ENABLE_PINCH_ZOOM`
- `static java.lang.String ENABLE_PROVISIONING_PAGES`
- `static java.lang.String ENABLE_PROVISIONING_TRANSACTION_LOG`
- `static java.lang.String ENABLE_ROLE_SUN_ACTIVATION`
- `static java.lang.String ENABLE_ROLE_SUN_ASSIGNMENT`
- `static java.lang.String ENABLE_SYSLOG`
- `static java.lang.String ENABLE_TEAMS_NOTIFICATIONS`
- `static java.lang.String ENCRYPTED_CLASS_FIELD_CONFIG`
- `static java.lang.String ENTITLEMENT_CATALOG_FULLTEXT`
- `static java.lang.String ENTITLEMENT_FULLTEXT`
- `static java.lang.String ENTITLEMENT_FULLTEXT_MAX_RESULT`
- `static java.lang.String ENTITLEMENT_MINING_MAX_APP_BUCKETS`
- `static java.lang.String ENTITLEMENT_MINING_MAX_BUCKETS`
- `static java.lang.String EXCLUDE_BASE_APP_ACCOUNTS`
- `static java.lang.String FAILED_LOGIN_ATTEMPTS`
- `static java.lang.String FALLBACK_WORK_ITEM_FORWARD_RULE`
- `static java.lang.String FAM_CONFIG`
- `static java.lang.String FAM_CONFIG_AUTH_TYPE`
- `static java.lang.String FAM_CONFIG_CLIENT_ID`
- `static java.lang.String FAM_CONFIG_CLIENT_SECRET`
- `static java.lang.String FAM_CONFIG_MENU_PATH`
- `static java.lang.String FAM_CONFIG_PASSWORD`
- `static java.lang.String FAM_CONFIG_SCIM_CORRELATION_APPS`
- `static java.lang.String FAM_CONFIG_SCIM_CORRELATION_RULE`
- `static java.lang.String FAM_CONFIG_URL`
- `static java.lang.String FAM_CONFIG_USER_NAME`
- `static java.lang.String FAM_ENABLED`
- `static java.lang.String FILTER_LOGICAL_ENTITLEMENTS`
- `static java.lang.String FLATTEN_CERTIFICATION_MANAGER_HIERARCHY`
- `static java.lang.String FORCE_CLASSIC_APPROVAL_UI`
- `static java.lang.String FORCE_ROLE_MERGE_TEMPLATE`
- `static java.lang.String FORMS_TYPE_FILTER`
- `static java.lang.String GENERAL_QUICKLINKS`
- `static java.lang.String GLOBAL_ATTRIBUTE_SYNC_USING_WORKFLOW`
- `static java.lang.String GRANULE_DAY`
- `static java.lang.String GRANULE_HOUR`
- `static java.lang.String GRANULE_INFINITE`
- `static java.lang.String GRANULE_MINUTE`
- `static java.lang.String GRANULE_MONTH`
- `static java.lang.String GRANULE_NONE`
- `static java.lang.String GRANULE_SECOND`
- `static java.lang.String GRANULE_WEEK`
- `static java.lang.String GROUP_INDEX_GRANULE`
- `static java.lang.String HASH_IDENTITY_SECRETS`
- `static java.lang.String HASHING_ITERATIONS`
- `static java.lang.String HELP_EMAIL_ADDRESS`
- `static java.lang.String HIBERNATE_LISTENER_CONFIG`
- `static java.lang.String HIBERNATE_LISTENER_CONFIG_EXCLUDED_ATTRIBUTES`
- `static java.lang.String HIBERNATE_LISTENER_CONFIG_INCLUDED_ATTRIBUTES`
- `static java.lang.String HIBERNATE_LISTENER_CONFIG_OPERATIONS`
- `static java.lang.String HIBERNATE_LISTENER_CONFIG_SKIP_UPDATES_WITHOUT_OLD_ATTRIBUTES`
- `static java.lang.String HIBERNATE_LISTENER_KEEP_ALIVE`
- `static java.lang.String HIBERNATE_LISTENER_MAX_THREADS`
- `static java.lang.String HIBERNATE_LISTENER_MIN_THREADS`
- `static java.lang.String HTML_SANITIZER_POLICIES`
- `static java.lang.String HTTP_UNAUTHORIZED_RESPONSE_CODE`
- `static java.lang.String HTTP_UNAUTHORIZED_RESPONSE_HEADER`
- `static java.lang.String HTTP_UNAUTHORIZED_RESPONSE_MESSAGE`
- `static java.lang.String IAI_CONFIG`
- `static java.lang.String IAI_CONFIG_ACC_REQ_RECO_CATALOG_ENDPOINT`
- `static java.lang.String IAI_CONFIG_ACCESS_RECO_ENDPOINT`
- `static java.lang.String IAI_CONFIG_CLIENT_ID`
- `static java.lang.String IAI_CONFIG_CLIENT_SECRET`
- `static java.lang.String IAI_CONFIG_CONNECT_TIMEOUT_SECS`
- `static java.lang.String IAI_CONFIG_FAILED_TOKEN_CHECK_INTERVAL`
- `static java.lang.String IAI_CONFIG_GENAI_ENTITLEMENT_APPROVAL`
- `static java.lang.String IAI_CONFIG_GENAI_ENTITLEMENT_DESC`
- `static java.lang.String IAI_CONFIG_GENAI_PRUNE_DAYS`
- `static java.lang.String IAI_CONFIG_HOSTNAME`
- `static java.lang.String IAI_CONFIG_IDENTITYNOW_URL`
- `static java.lang.String IAI_CONFIG_IDLE_CONNECTION_REFRESH_INTERVAL`
- `static java.lang.String IAI_CONFIG_IGNORE_RATE_LIMIT`
- `static java.lang.String IAI_CONFIG_LLM_PROXY_CLIENT_ID`
- `static java.lang.String IAI_CONFIG_LLM_PROXY_CLIENT_SECRET`
- `static java.lang.String IAI_CONFIG_LLM_PROXY_CONNECT_TIMEOUT_SECS`
- `static java.lang.String IAI_CONFIG_LLM_PROXY_HOSTNAME`
- `static java.lang.String IAI_CONFIG_LLM_PROXY_READ_TIMEOUT_SECS`
- `static java.lang.String IAI_CONFIG_MIN_NUM_IDENTITIES_ROLE`
- `static java.lang.String IAI_CONFIG_READ_TIMEOUT_SECS`
- `static java.lang.String IAI_CONFIG_RECO_CATALOG_ENDPOINT`
- `static java.lang.String IAI_CONFIG_RECO_ENDPOINT`
- `static java.lang.String IAI_CONFIG_ROLE_MINING_SESSION_PATH`
- `static java.lang.String IAI_CONFIG_TOKEN_REFRESH_PERCENT`
- `static java.lang.String IAI_GENAI_CONFIG`
- `static java.lang.String IDENTITY_CONTROLS_ASSIGNED_SCOPE`
- `static java.lang.String IDENTITY_FILTERS`
- `static java.lang.String IDENTITY_INDEX_GRANULE`
- `static java.lang.String IDENTITY_MAX_SEARCHABLE_ATTRIBUTES`
- `static java.lang.String IDENTITY_SELECTOR_CONFIG`
- `static java.lang.String IDENTITY_SNAPSHOT_INTERVAL`
- `static java.lang.String IDENTITY_SNAPSHOT_MAX_AGE`
- `static java.lang.String IDENTITYAI_ENABLED`
- `static java.lang.String IIQ_ALLOW_AUTOCOMPLETE`
- `static java.lang.String IIQ_ALLOW_IFRAME`
- `static java.lang.String INACTIVE_OWNER_WORK_ITEM_FORWARD_RULE`
- `static java.lang.String INSIGNIFICANT_PROPS_MAP`
- `static java.lang.String INSTALLED_CONNECTORS`
- `static java.lang.String INTEGRATION_CONFIG_CACHE_AGGRESIVE_REFRESH`
- `static java.lang.String INTEGRATION_CONFIG_CACHE_REFRESH_INTERVAL`
- `static java.lang.String IQ_SERVICE_CONFIG`
- `static java.lang.String ISSUERS_CLAIM_VALIDATION_REQUIRED`
- `static java.lang.String JASPER_CSV_DELIMITER`
- `static java.lang.String JASPER_ENCODING`
- `static java.lang.String LAST_FULL_CERT_REFRESH`
- `static java.lang.String LCM_ALLOW_ACCOUNT_ONLY_REQUESTS`
- `static java.lang.String LCM_ALLOW_ENTITLEMENT_ATTRIBUTES_SEARCH`
- `static java.lang.String LCM_ALLOW_ENTITLEMENT_IDENTITIES_SEARCH`
- `static java.lang.String LCM_ALLOW_ENTITLEMENT_PERCENT_LIMIT`
- `static java.lang.String LCM_ALLOW_ENTITLEMENT_PERCENT_LIMIT_PERCENT`
- `static java.lang.String LCM_ALLOW_ENTITLEMENT_PERCENTAGE_SLIDER`
- `static java.lang.String LCM_ALLOW_ENTITLEMENT_POPULATION_SEARCH`
- `static java.lang.String LCM_ALLOW_ENTITLEMENT_SORT_PERCENTAGE`
- `static java.lang.String LCM_ALLOW_ENTITLEMENT_SORT_PERCENTAGE_COUNT`
- `static java.lang.String LCM_ALLOW_GENERATE_PASSWORD_DELEGATION`
- `static java.lang.String LCM_ALLOW_IDENTITY_SEARCH`
- `static java.lang.String LCM_ALLOW_MANAGE_ACCOUNTS_ADDITIONAL_ACCOUNT_REQUESTS`
- `static java.lang.String LCM_ALLOW_MANAGE_EXISTING_ACCOUNTS`
- `static java.lang.String LCM_ALLOW_POPULATION_SEARCH`
- `static java.lang.String LCM_ALLOW_PRIORITY_EDITING`
- `static java.lang.String LCM_ALLOW_RECOMMENDED_ACCESS`
- `static java.lang.String LCM_ALLOW_REQUEST_ENTITLEMENTS`
- `static java.lang.String LCM_ALLOW_REQUEST_ENTITLEMENTS_ADDITIONAL_ACCOUNT_REQUESTS`
- `static java.lang.String LCM_ALLOW_REQUEST_ENTITLEMENTS_REMOVE`
- `static java.lang.String LCM_ALLOW_REQUEST_ENTITLEMENTS_SHOW_POPUPLATION`
- `static java.lang.String LCM_ALLOW_REQUEST_PERMITS`
- `static java.lang.String LCM_ALLOW_REQUEST_ROLES`
- `static java.lang.String LCM_ALLOW_REQUEST_ROLES_ADDITIONAL_ACCOUNT_REQUESTS`
- `static java.lang.String LCM_ALLOW_REQUEST_ROLES_REMOVE`
- `static java.lang.String LCM_ALLOW_REQUEST_ROLES_SHOW_POPUPLATION`
- `static java.lang.String LCM_ALLOW_ROLE_ATTRIBUTES_SEARCH`
- `static java.lang.String LCM_ALLOW_ROLE_IDENTITIES_SEARCH`
- `static java.lang.String LCM_ALLOW_ROLE_PERCENT_LIMIT`
- `static java.lang.String LCM_ALLOW_ROLE_PERCENT_LIMIT_PERCENT`
- `static java.lang.String LCM_ALLOW_ROLE_PERCENTAGE_SLIDER`
- `static java.lang.String LCM_ALLOW_ROLE_POPULATION_SEARCH`
- `static java.lang.String LCM_ALLOW_ROLE_SELECTOR_RULE_OVERRIDE`
- `static java.lang.String LCM_ALLOW_ROLE_SORT_PERCENTAGE`
- `static java.lang.String LCM_ALLOW_ROLE_SORT_PERCENTAGE_COUNT`
- `static java.lang.String LCM_ALLOW_WORKGROUP_SELF_APPROVAL`
- `static java.lang.String LCM_CREATE_IDENTITY_USE_BY_DAYS`
- `static java.lang.String LCM_DISABLE_ROLE_POPULATION_STATS`
- `static java.lang.String LCM_ENABLE_APPROVAL_RECOMMENDATIONS`
- `static java.lang.String LCM_ENABLE_FULLTEXT`
- `static java.lang.String LCM_ENABLED`
- `static java.lang.String LCM_FULL_TEXT_INDEX_PATH`
- `static java.lang.String LCM_GENERAL_POPULATION`
- `static java.lang.String LCM_HELP_DESK`
- `static java.lang.String LCM_IDENTITY_UPDATE_APPROVAL_ADAPTIVE_CARD_NOTIFICATION`
- `static java.lang.String LCM_MANAGE_ACCOUNTS_ACTIONS`
- `static java.lang.String LCM_MANAGE_ACCOUNTS_ALLOW_GROUP_MANAGEMENT`
- `static java.lang.String LCM_MANAGE_ACCOUNTS_DISABLE_AUTO_REFRESH_STATUS`
- `static java.lang.String LCM_MANAGE_ACCOUNTS_PREFIX`
- `static java.lang.String LCM_MANAGE_ACCOUNTS_SHOW_ALL_BUTTONS`
- `static java.lang.String LCM_MANAGED_ATTRIBUTE_STATS_MAX_ATTRIBUTES`
- `static java.lang.String LCM_MANAGED_ATTRIBUTE_STATS_MAX_IDENTITIES`
- `static java.lang.String LCM_MANAGER`
- `static java.lang.String LCM_MAX_ROLES_RETURNED_FROM_USER_SEARCH`
- `static java.lang.String LCM_MOBILE_MAX_SELECTABLE_USERS`
- `static java.lang.String LCM_OP_DELETE`
- `static java.lang.String LCM_OP_DISABLE`
- `static java.lang.String LCM_OP_ENABLE`
- `static java.lang.String LCM_OP_ENABLED_SUFFIX`
- `static java.lang.String LCM_OP_LOCK`
- `static java.lang.String LCM_OP_UNLOCK`
- `static java.lang.String LCM_OTHERS`
- `static java.lang.String LCM_REQUEST_CONTROLS_ALLOW_ALL`
- `static java.lang.String LCM_REQUEST_CONTROLS_APPLICATION_SELECTOR_RULE`
- `static java.lang.String LCM_REQUEST_CONTROLS_ATTRIBUTE_FILTER_CONTROL`
- `static java.lang.String LCM_REQUEST_CONTROLS_CUSTOM_CONTROL`
- `static java.lang.String LCM_REQUEST_CONTROLS_DIRECT`
- `static java.lang.String LCM_REQUEST_CONTROLS_DIRECT_OR_INDIRECT`
- `static java.lang.String LCM_REQUEST_CONTROLS_DISABLE_SCOPING`
- `static java.lang.String LCM_REQUEST_CONTROLS_ENABLE_ATTRIBUTE_CONTROL`
- `static java.lang.String LCM_REQUEST_CONTROLS_ENABLE_CUSTOM_CONTROL`
- `static java.lang.String LCM_REQUEST_CONTROLS_ENABLE_FILTER_RULE`
- `static java.lang.String LCM_REQUEST_CONTROLS_ENABLE_SUBORDINATE_CONTROL`
- `static java.lang.String LCM_REQUEST_CONTROLS_FILTER_RULE_ID`
- `static java.lang.String LCM_REQUEST_CONTROLS_FILTER_RULE_NAME`
- `static java.lang.String LCM_REQUEST_CONTROLS_MANAGED_ATTRIBUTE_SELECTOR_RULE`
- `static java.lang.String LCM_REQUEST_CONTROLS_MATCH_ALL`
- `static java.lang.String LCM_REQUEST_CONTROLS_MATCH_ANY`
- `static java.lang.String LCM_REQUEST_CONTROLS_MATCH_ANY_OR_ALL`
- `static java.lang.String LCM_REQUEST_CONTROLS_MATCH_NONE`
- `static java.lang.String LCM_REQUEST_CONTROLS_MAX_HIERARCHY_DEPTH`
- `static java.lang.String LCM_REQUEST_CONTROLS_ROLE_SELECTOR_RULE`
- `static java.lang.String LCM_REQUEST_CONTROLS_SUBORDINATE_CHOICE`
- `static java.lang.String LCM_REQUEST_ROLES_ASSIGNABLE`
- `static java.lang.String LCM_REQUEST_ROLES_PERMITTED`
- `static java.lang.String LCM_REQUEST_ROLES_PREFIX`
- `static java.lang.String LCM_REQUIRE_PASSWORD_IDENTITY_CREATE`
- `static java.lang.String LCM_SEARCH_MAX_RESULTS`
- `static java.lang.String LCM_SEARCH_TYPE`
- `static java.lang.String LCM_SEARCH_TYPE_CONTAINS`
- `static java.lang.String LCM_SEARCH_TYPE_STARTSWITH`
- `static java.lang.String LCM_SELF`
- `static java.lang.String LCM_SELF_SERVICE`
- `static java.lang.String LCM_SHOW_EXTERNAL_TICKET_ID`
- `static java.lang.String LCM_SHOW_ROLE_DETAILS`
- `static java.lang.String LCM_SKIP_FULLTEXT_FIELDS`
- `static java.lang.String LCM_SUBORDINATE`
- `static java.lang.String LCM_USER_ACCESS_FULLTEXT_INDEX`
- `static java.lang.String[] LCM_USER_TYPES`
- `static java.lang.String LINK_MAX_SEARCHABLE_ATTRIBUTES`
- `static java.lang.String LOCK_TIMEOUT`
- `static java.lang.String LOCK_WAIT_TIMEOUT`
- `static java.lang.String LOGIN_ERROR_STYLE`
- `static java.lang.String LOGIN_LOCKOUT_DURATION`
- `static java.lang.String LOGIN_PASS_THROUGH`
- `static java.lang.String LOGIN_RETURNS_TO_DASHBOARD`
- `static java.lang.String LOGIN_SSO_RULE`
- `static java.lang.String LOGIN_SSO_VALIDATION_RULE`
- `static java.lang.String LONG_RUNNING_LOCK_TIMEOUT`
- `static java.lang.String MANAGED_ATTRIBUTE_CUSTOMIZATION_RULE`
- `static java.lang.String MAX_AUTH_QUESTION_FAILURES`
- `static java.lang.String MAX_LIST_RESULT_SIZE`
- `static java.lang.String MAX_UPLOAD_SIZE`
- `static java.lang.String MAX_WORKGROUPS_FOR_OWNER_SCOPE_FILTER`
- `static java.lang.String MFA`
- `static java.lang.String MFA_CONFIG_LIST`
- `static java.lang.String MITIGATION_EXPIRATION_ACTION`
- `static java.lang.String MITIGATION_EXPIRATION_ACTION_PARAMETERS`
- `static java.lang.String MITIGATION_EXPIRATION_EMAIL_TEMPLATE`
- `static java.lang.String MOBILE_QUICKLINK_CARDS`
- `static java.lang.String NATIVE_IDENTITY_CHANGE_EVENT_MAX_AGE`
- `static java.lang.String NATIVE_IDENTITY_REPLACER_CLASS`
- `static java.lang.String NO_IDP_SAMESITE_NONE`
- `static java.lang.String NOTIFY_REMEDIATION`
- `static java.lang.String NUM_AUTH_QUESTION_ANSWERS_REQUIRED`
- `static java.lang.String NUM_AUTH_QUESTIONS_FOR_AUTHN`
- `static java.lang.String OAUTH_CONFIGURATION`
- `static java.lang.String OBJ_NAME`
- `static java.lang.String OPEN_CERTIFICATIONS_EMAIL_TEMPLATE`
- `static java.lang.String PAM_CREATE_CONTAINER_ENABLED`
- `static java.lang.String PAM_ENABLED`
- `static java.lang.String PAM_MAX_SELECTABLE_IDENTITIES`
- `static java.lang.String PAM_MODIFY_PRIVILEGED_DATA_ENABLED`
- `static java.lang.String PAM_OWNER_CAN_EDIT_CONTAINER`
- `static java.lang.String PAM_PRIVILEGED_ITEM_SELECTOR_RULE`
- `static java.lang.String PAM_PROVISIONING_ENABLED`
- `static java.lang.String PAM_WORKFLOW_IDENTITY_PROVISIONING`
- `static java.lang.String PASSWORD_CHANGE_MIN_DURATION`
- `static java.lang.String PASSWORD_LOWER_CHARACTERS`
- `static java.lang.String PASSWORD_NUMBER_CHARACTERS`
- `static java.lang.String PASSWORD_SPECIAL_CHARACTERS`
- `static java.lang.String PASSWORD_UPPER_CHARACTERS`
- `static java.lang.String PASSWORD_VALIDATION_RULE`
- `static java.lang.String PENDING_ATTACHMENT_PRUNE_AGE`
- `static java.lang.String PENDING_ROLE_REQUEST_DELETE_EMAIL_TEMPLATE`
- `static java.lang.String PLUGIN_PROHIBIT_SCRIPTING`
- `static java.lang.String PLUGIN_RELAX_EXPORT_ENFORCEMENT`
- `static java.lang.String POLICY_VIOLATION_DELEGATION_EMAIL_TEMPLATE`
- `static java.lang.String POLICY_VIOLATION_EMAIL_TEMPLATE`
- `static java.lang.String PROMPT_FOR_AUTH_QUESTION_ANSWERS_AFTER_LOGIN`
- `static java.lang.String PROTECTED_USER_LOCKOUT`
- `static java.lang.String PROVISIONING_REQUEST_EXPIRATION_DAYS`
- `static java.lang.String PROVISIONING_TRANSACTION_LOG_LEVEL`
- `static java.lang.String PROVISIONING_TRANSACTION_LOG_PRUNE_AGE`
- `static java.lang.String PUBLISHERS_CONFIG`
- `static java.lang.String QUICK_LINK_UPGRADE`
- `static java.lang.String QUICKLINK_CATEGORIES`
- `static java.lang.String RAPIDSETUP_CONFIG`
- `static java.lang.String RAPIDSETUP_CONFIG_BIRTHRIGHT`
- `static java.lang.String RAPIDSETUP_CONFIG_BIRTHRIGHT_ROLETYPES`
- `static java.lang.String RAPIDSETUP_CONFIG_EMAIL`
- `static java.lang.String RAPIDSETUP_CONFIG_ENABLED`
- `static java.lang.String RAPIDSETUP_CONFIG_JOINER`
- `static java.lang.String RAPIDSETUP_CONFIG_JOINER_ALT_NOTIFY_WORKGROUP`
- `static java.lang.String RAPIDSETUP_CONFIG_JOINER_ALT_NOTIFY_WORKGROUP_SUGGEST`
- `static java.lang.String RAPIDSETUP_CONFIG_JOINER_AUTO_JOIN_NEW_EMPTY`
- `static java.lang.String RAPIDSETUP_CONFIG_JOINER_BARE_PROV`
- `static java.lang.String RAPIDSETUP_CONFIG_JOINER_COMPLETED_EMAIL_TEMPLATE`
- `static java.lang.String RAPIDSETUP_CONFIG_JOINER_COMPLETED_EMAIL_TEMPLATE_SUGGEST`
- `static java.lang.String RAPIDSETUP_CONFIG_JOINER_EMAIL`
- `static java.lang.String RAPIDSETUP_CONFIG_JOINER_POST_JOINER_RULE`
- `static java.lang.String RAPIDSETUP_CONFIG_JOINER_POST_JOINER_RULE_SUGGEST`
- `static java.lang.String RAPIDSETUP_CONFIG_JOINER_PRODUCING`
- `static java.lang.String RAPIDSETUP_CONFIG_JOINER_PROV_SELECTOR`
- `static java.lang.String RAPIDSETUP_CONFIG_JOINER_PROV_SELECTOR_DTO`
- `static java.lang.String RAPIDSETUP_CONFIG_JOINER_REPROCESS_SKIPPED`
- `static java.lang.String RAPIDSETUP_CONFIG_JOINER_REQUIRE_CORRELATED`
- `static java.lang.String RAPIDSETUP_CONFIG_JOINER_SEND_TEMPORARY_PASSWORD_EMAIL`
- `static java.lang.String RAPIDSETUP_CONFIG_JOINER_WORKFLOW_SUGGEST`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_ALT_NOTIFY_WORKGROUP`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_ALT_NOTIFY_WORKGROUP_SUGGEST`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_COMPLETED`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_COMPLETED_SUGGEST`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_ENABLE_REASSIGN_ARTIFACTS`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_ENABLE_REASSIGN_IDENTITIES`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_ENTITLEMENT_EXCEPTION`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_OWNERSHIP_REASSIGNMENT`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_OWNERSHIP_REASSIGNMENT_SUGGEST`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_POST_RULE`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_POST_RULE_SUGGEST`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_REASSIGN_ALT_ARTIFACTS_SUGGEST`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_REASSIGN_ALT_IDENTITIES_SUGGEST`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_REASSIGN_ALTERNATIVE`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_REASSIGN_ARTIFACT_TYPES`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_REASSIGN_ARTIFACTS`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_REASSIGN_ARTIFACTS_RULE_SUGGEST`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_REASSIGN_ARTIFACTS_TO_MANAGER`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_REASSIGN_IDENTITIES`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_REASSIGN_IDENTITIES_RULE_SUGGEST`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_REASSIGN_IDENTITIES_TO_MANAGER`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_REASSIGN_RULE`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_REASSIGN_TO_IF_NO_MANAGER`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_REQUIRE_CORRELATED`
- `static java.lang.String RAPIDSETUP_CONFIG_LEAVER_WORKFLOW_SUGGEST`
- `static java.lang.String RAPIDSETUP_CONFIG_MOVER`
- `static java.lang.String RAPIDSETUP_CONFIG_MOVER_BACKUP_CERTIFIER`
- `static java.lang.String RAPIDSETUP_CONFIG_MOVER_CERTIFICATION_ADDITIONAL_ENTITLEMENTS`
- `static java.lang.String RAPIDSETUP_CONFIG_MOVER_CERTIFICATION_ENABLED`
- `static java.lang.String RAPIDSETUP_CONFIG_MOVER_CERTIFICATION_OWNER`
- `static java.lang.String RAPIDSETUP_CONFIG_MOVER_CERTIFICATION_PARAMS`
- `static java.lang.String RAPIDSETUP_CONFIG_MOVER_CERTIFICATION_TARGET_PERMISSION`
- `static java.lang.String RAPIDSETUP_CONFIG_MOVER_JOINER_ENABLED`
- `static java.lang.String RAPIDSETUP_CONFIG_MOVER_PERFORM_JOINER`
- `static java.lang.String RAPIDSETUP_CONFIG_MOVER_POST_MOVER_RULE`
- `static java.lang.String RAPIDSETUP_CONFIG_MOVER_POST_MOVER_RULE_SUGGEST`
- `static java.lang.String RAPIDSETUP_CONFIG_MOVER_REQUIRE_CORRELATED`
- `static java.lang.String RAPIDSETUP_CONFIG_MOVER_WORKFLOW_SUGGEST`
- `static java.lang.String RAPIDSETUP_CONFIG_PARAM_GROUP`
- `static java.lang.String RAPIDSETUP_CONFIG_PARAM_ITEMS`
- `static java.lang.String RAPIDSETUP_CONFIG_PARAM_TRIGGER_FILTER`
- `static java.lang.String RAPIDSETUP_CONFIG_PARAM_TRIGGER_WORKFLOW`
- `static java.lang.String RAPIDSETUP_CONFIG_SECTION_APPS`
- `static java.lang.String RAPIDSETUP_CONFIG_SECTION_BUSINESS_PROCESSES`
- `static java.lang.String RAPIDSETUP_CONFIG_SECTION_EMAIL`
- `static java.lang.String RAPIDSETUP_CONFIG_SECTION_EMAIL_ALT_MANAGER`
- `static java.lang.String RAPIDSETUP_CONFIG_SECTION_EMAIL_ERROR_WORKGROUP`
- `static java.lang.String RAPIDSETUP_CONFIG_SECTION_EMAIL_FOOTER`
- `static java.lang.String RAPIDSETUP_CONFIG_SECTION_EMAIL_FOOTER_SUGGEST`
- `static java.lang.String RAPIDSETUP_CONFIG_SECTION_EMAIL_HEADER`
- `static java.lang.String RAPIDSETUP_CONFIG_SECTION_EMAIL_HEADER_SUGGEST`
- `static java.lang.String RAPIDSETUP_CONFIG_SECTION_EMAIL_STYLE_SHEET`
- `static java.lang.String RAPIDSETUP_CONFIG_SECTION_EMAIL_STYLE_SHEET_SUGGEST`
- `static java.lang.String RAPIDSETUP_CONFIG_SECTION_WORKFLOW`
- `static java.lang.String RAPIDSETUP_CONFIG_SUPT_PROC`
- `static java.lang.String RAPIDSETUP_CONFIG_TERMINATE`
- `static java.lang.String RAPIDSETUP_CONFIG_WORKFLOW_REQUESTER`
- `static java.lang.String RAPIDSETUP_ENABLED`
- `static java.lang.String RECOMMENDER_SELECTED`
- `static java.lang.String REDIRECTING_EMAIL_NOTIFIER_ADDRESS`
- `static java.lang.String REDIRECTING_EMAIL_NOTIFIER_FILENAME`
- `static java.lang.String REFRESH_PASSTHROUGH_LINK_DURING_AUTHENTICATION`
- `static java.lang.String REGISTER_FORM`
- `static java.lang.String REMED_ITEM_ASSIGNMENT_EMAIL_TEMPLATE`
- `static java.lang.String REMED_ITEM_ASSIGNMENT_REMOVAL_EMAIL_TEMPLATE`
- `static java.lang.String REMEDIATE_LOGICAL_APP_TO_TIER`
- `static java.lang.String REMEDIATION_GOES_TO_ROLE_OWNER_INSTEAD_OF_DEFAULT`
- `static java.lang.String REMEDIATION_NOTIFICATION_EMAIL_TEMPLATE`
- `static java.lang.String REMEDIATION_PERIOD_DURATION`
- `static java.lang.String REMEDIATION_PERIOD_ENABLED`
- `static java.lang.String REMEDIATION_SCAN_INTERVAL`
- `static java.lang.String REMEDIATION_WORK_ITEM_EMAIL_TEMPLATE`
- `static java.lang.String REMOTE_LOGIN_TOKEN_MAX_AGE`
- `static java.lang.String REPORT_COMPLETION_EMAIL_TEMPLATE`
- `static java.lang.String REPORT_RESULT_ROW_THRESHOLD`
- `static java.lang.String REPORT_SEARCH_TYPE`
- `static java.lang.String REQUEST_MAX_AGE`
- `static java.lang.String REQUEST_PRESERVE_IF_ERRORS`
- `static java.lang.String REQUEST_PROCESSOR_CYCLE_SECONDS`
- `static java.lang.String REQUIRE_ACCESS_REQUEST_COMMENTS_ALL`
- `static java.lang.String REQUIRE_ACCOUNT_REVOKE_COMMENTS`
- `static java.lang.String REQUIRE_APPROVAL_COMMENTS`
- `static java.lang.String REQUIRE_BATCH_REQUEST_APPROVAL`
- `static java.lang.String REQUIRE_BULK_CERTIFY_CONFIRMATION`
- `static java.lang.String REQUIRE_DELEGATION_COMPLETION`
- `static java.lang.String REQUIRE_ELECTRONIC_SIGNATURE`
- `static java.lang.String REQUIRE_MITIGATION_COMMENTS`
- `static java.lang.String REQUIRE_OLD_PASSWORD_AT_CHANGE`
- `static java.lang.String REQUIRE_REASSIGNMENT_COMPLETION`
- `static java.lang.String REQUIRE_REMEDIATION_COMMENTS`
- `static java.lang.String RETAIN_ASSIGNED_ENTITLEMENTS_ASSIGNED_ROLE`
- `static java.lang.String RETAIN_ASSIGNED_ENTITLEMENTS_DETECTED_ROLE`
- `static java.lang.String RO_SERVICE_REFRESH`
- `static java.lang.String RO_SERVICE_REFRESH_OPTIONS`
- `static java.lang.String ROLE_POLICY_FORM`
- `static java.lang.String ROLE_SUNSET_NOTIFICATION_DAYS_REMINDER`
- `static java.lang.String RULE_BASED_SSO_ENABLED`
- `static java.lang.String SAML`
- `static java.lang.String SAML_ENABLED`
- `static java.lang.String SAML_NAMEQUALIFIER`
- `static java.lang.String SAML_PROVIDER`
- `static java.lang.String SCIM_SEARCH_MAX_RESULTS`
- `static java.lang.String SCIM_TRIGGER_SNAPSHOTS`
- `static java.lang.String SCOPE_CLAIM_VALIDATION_REQUIRED`
- `static java.lang.String SCOPE_PATHS_DENORMALIZED`
- `static java.lang.String SCOPE_TREE_UI_DISPLAY_LIMIT`
- `static java.lang.String SCOPING_ENABLED`
- `static java.lang.String SEARCH_INPUT_DEFINITIONS`
- `static java.lang.String SECRET_PROVISION_ATTRIBUTE_NAMES`
- `static java.lang.String SELF_CERTIFICATION_VIOLATION_OWNER`
- `static java.lang.String SELF_REGISTRATION_WORKGROUP`
- `static java.lang.String SERVER_ROOT_PATH`
- `static java.lang.String SHOW_AUTO_REMEDIATION_DIALOG`
- `static java.lang.String SHOW_CERTIFICATION_ICON_TOOLTIPS`
- `static java.lang.String SHOW_CERTIFICATION_ROLE_REVOCATION_DETAILS`
- `static java.lang.String SHOW_CHANGE_PASSWORD_TAB`
- `static java.lang.String SHOW_EDIT_FORWARDING`
- `static java.lang.String SIGNOFF_EMAIL_TEMPLATE`
- `static java.lang.String SIMPLE_LOGIN_STYLE`
- `static java.lang.String SM_LISTENER_APPLICATIONS`
- `static java.lang.String SM_LISTENER_HOST`
- `static java.lang.String SM_LISTENER_REFRESH`
- `static java.lang.String SM_LISTENER_REFRESH_OPTIONS`
- `static java.lang.String SM_MAX_ACTIVE_TRANSACTIONS`
- `static java.lang.String SM_READ_TIMEOUT`
- `static java.lang.String SM_SOCKET_CONNECT_RETRY`
- `static java.lang.String SM_SYNC_SCHEMA`
- `static java.lang.String SMS_RESET_CONFIG`
- `static java.lang.String SSO_AUTHENTICATORS`
- `static java.lang.String SUBORDINATE_CERTIFICATION_ENABLED`
- `static java.lang.String SUGGEST_COLUMN_WHITELIST`
- `static java.lang.String SUGGEST_OBJECT_WHITELIST`
- `static java.lang.String SUNSET_EXPIRATION_REMINDER_EMAIL_TEMPLATE`
- `static java.lang.String SUPPORTED_LANGUAGES`
- `static java.lang.String SUPPRESS_DUPLICATE_EMAILS`
- `static java.lang.String SUPPRESS_EMAIL_WHEN_NOTHING_TO_CERTIFY`
- `static java.lang.String SUPPRESS_INITIAL_NOTIFICATION`
- `static java.lang.String SYSLOG_LEVEL`
- `static java.lang.String SYSLOG_PRUNE_AGE`
- `static java.lang.String TASK_COMPLETION_EMAIL_NOTIFY`
- `static java.lang.String TASK_COMPLETION_EMAIL_TEMPLATE`
- `static java.lang.String TASK_COMPLETION_RECIPIENTS`
- `static java.lang.String TASK_COMPLETION_RULE`
- `static java.lang.String TASK_RESULT_MAX_AGE`
- `static java.lang.String TASKS_EXECUTE_IN_FOREGROUND_OPTION`
- `static java.lang.String TEAMS_AUTH_WRAPPER_ADDRESS`
- `static java.lang.String TEAMS_SAML`
- `static java.lang.String TEAMS_SAML_ENABLED`
- `static java.lang.String TEMP_DIR`
- `static java.lang.String UNSCOPED_OBJECTS_GLOBALLY_ACCESSIBLE`
- `static java.lang.String UNSUPPORTED_BROWSER_NOTIFICATION`
- `static java.lang.String UPDATE_IDENTITY_FORM`
- `static java.lang.String USE_CERT_CONTEXTS_CACHE`
- `static java.lang.String USE_MANAGED_ATTRIBUTES_FOR_REMEDIATION`
- `static java.lang.String WEB_RESOURCE_CONFIG`
- `static java.lang.String WEB_RESOURCES`
- `static java.lang.String WEB_SERVICE_CONFIG_CLIENT_ID`
- `static java.lang.String WEB_SERVICE_CONFIG_CLIENT_SECRET`
- `static java.lang.String WEB_SERVICE_CONFIG_CONNECT_TIMEOUT_SECS`
- `static java.lang.String WEB_SERVICE_CONFIG_FAILED_TOKEN_CHECK_INTERVAL`
- `static java.lang.String WEB_SERVICE_CONFIG_HOSTNAME`
- `static java.lang.String WEB_SERVICE_CONFIG_IDLE_CONNECTION_REFRESH_INTERVAL`
- `static java.lang.String WEB_SERVICE_CONFIG_IGNORE_PROXY_PROPERTIES`
- `static java.lang.String WEB_SERVICE_CONFIG_OAUTH_CLIENT_USE_QUERY_PARAMS`
- `static java.lang.String WEB_SERVICE_CONFIG_OAUTH_HOSTNAME`
- `static java.lang.String WEB_SERVICE_CONFIG_OAUTH_PATH`
- `static java.lang.String WEB_SERVICE_CONFIG_PASSWORD`
- `static java.lang.String WEB_SERVICE_CONFIG_READ_TIMEOUT_SECS`
- `static java.lang.String WEB_SERVICE_CONFIG_TOKEN_REFRESH_PERCENT`
- `static java.lang.String WEB_SERVICE_CONFIG_USER_NAME`
- `static java.lang.String WORK_ITEM_ARCHIVE_TYPES`
- `static java.lang.String WORK_ITEM_ASSIGNMENT_ADAPTIVE_CARD_NOTIFICATION`
- `static java.lang.String WORK_ITEM_ASSIGNMENT_EMAIL_TEMPLATE`
- `static java.lang.String WORK_ITEM_ASSIGNMENT_NOTIFICATION`
- `static java.lang.String WORK_ITEM_ASSIGNMENT_REMOVAL_ADAPTIVE_CARD_NOTIFICATION`
- `static java.lang.String WORK_ITEM_ASSIGNMENT_REMOVAL_EMAIL_TEMPLATE`
- `static java.lang.String WORK_ITEM_ASSIGNMENT_REMOVAL_NOTIFICATION`
- `static java.lang.String WORK_ITEM_COMMENT_EMAIL_TEMPLATE`
- `static java.lang.String WORK_ITEM_FILTER_ATTRIBUTES`
- `static java.lang.String WORK_ITEM_FORWARD_ADAPTIVE_CARD_NOTIFICATION`
- `static java.lang.String WORK_ITEM_FORWARD_EMAIL_TEMPLATE`
- `static java.lang.String WORK_ITEM_FORWARD_RULE`
- `static java.lang.String WORK_ITEM_NOTIFICATIONS_INTERVAL`
- `static java.lang.String WORK_ITEM_PRIORITY_EDITING_ENABLED`
- `static java.lang.String WORKFLOW_ATTRIBUTE_SYNC`
- `static java.lang.String WORKFLOW_FORM`
- `static java.lang.String WORKFLOW_IDENTITY_CORRELATION`
- `static java.lang.String WORKFLOW_IDENTITY_REFRESH`
- `static java.lang.String WORKFLOW_IDENTITY_UPDATE`
- `static java.lang.String WORKFLOW_LCM_ACCESS_REQUEST`
- `static java.lang.String WORKFLOW_LCM_ACCOUNTS_REQUEST`
- `static java.lang.String WORKFLOW_LCM_CREATE_IDENTITY`
- `static java.lang.String WORKFLOW_LCM_CREATE_IDENTITY_REQUEST`
- `static java.lang.String WORKFLOW_LCM_ENTITLEMENTS_REQUEST`
- `static java.lang.String WORKFLOW_LCM_IDENTITY_EDIT_REQUEST`
- `static java.lang.String WORKFLOW_LCM_MANAGE_ACCOUNTS`
- `static java.lang.String WORKFLOW_LCM_MANAGE_ATTRIBUTES`
- `static java.lang.String WORKFLOW_LCM_PASSWORD_REQUEST`
- `static java.lang.String WORKFLOW_LCM_REQUEST_ENTITLEMENTS`
- `static java.lang.String WORKFLOW_LCM_ROLE_PROPAGATION`
- `static java.lang.String WORKFLOW_LCM_ROLE_REQUEST`
- `static java.lang.String WORKFLOW_LCM_ROLES_REQUEST`
- `static java.lang.String WORKFLOW_LCM_SSR_REQUEST`
- `static java.lang.String WORKFLOW_LCM_UNLOCK_ACCOUNT`
- `static java.lang.String WORKFLOW_MANAGED_ATTRIBUTE`
- `static java.lang.String WORKFLOW_PASSWORD_INTERCEPT`
- `static java.lang.String WORKFLOW_ROLE_APPROVAL`
- `static java.lang.String WORKFLOW_SCHEDULED_ASSIGNMENT`
- `static java.lang.String WORKFLOW_SCHEDULED_ROLE_ACTIVATION`

**Methods:**
- `java.lang.Object clone ()`
- `boolean containsAttribute (java.lang.String name)`
- `boolean containsKey (java.lang.String key)`
- `boolean decache (java.lang.String className)`
- `java.lang.Object get (java.lang.String name)`
- `staticConfiguration getAccessHistoryConfig ()`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `boolean getBoolean (java.lang.String name)`
- `boolean getBoolean (java.lang.String name, boolean dflt)`
- `staticConfiguration getCAMConfig ()`
- `staticConfiguration getDataExtractConfig ()`
- `java.util.Date getDate (java.lang.String name)`
- `staticConfiguration getFAMConfig ()`
- `staticConfiguration getGenAIConfig ()`
- `staticConfiguration getHibernateListenerConfig ()`
- `staticConfiguration getIdentityAIConfig ()`
- `staticConfiguration getIdentitySelectorConfig ()`
- `int getInt (java.lang.String name)`
- `java.lang.Integer getInteger (java.lang.String name)`
- `java.util.List getList (java.lang.String name)`
- `long getLong (java.lang.String name)`
- `staticConfiguration getRapidSetupConfig ()`
- `java.lang.String getString (java.lang.String name)`
- `java.util.List<java.lang.String> getStringList (java.lang.String name)`
- `staticConfiguration getSystemConfig ()`
- `static boolean isXmlStrictMode ()`
- `void put (java.lang.String name, int value)`
- `void put (java.lang.String name, java.lang.Object value)`
- `void remove (java.lang.String name)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> a)`
- `void visit ( Visitor v)`

---

## ConnectorConfig

**Package:** `sailpoint.object`

**Description:** Deprecated.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.ConnectorConfig`
- `java.lang.Cloneable`

**Attributes:** N/A

**Methods:**
- `java.lang.Object clone ()`
- `boolean equals (java.lang.Object obj)`
- `java.lang.String getAttributesForm ()`
- `java.lang.String getClassName ()`
- `java.lang.String getDisplayName ()`
- `void setAttributesForm (java.lang.String attrForm)`
- `void setClassName (java.lang.String clazz)`
- `void setDisplayName (java.lang.String displayName)`

---

## ConnectorOperationData

**Package:** `sailpoint.object`

**Description:** Deprecated.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.ConnectorOperationData`

**Attributes:**
- `static java.lang.String ATT_AFTER_RULE`
- `static java.lang.String ATT_BEFORE_RULE`
- `static java.lang.String ATT_BODY`
- `static java.lang.String ATT_BODY_FORM_DATA`
- `static java.lang.String ATT_BODY_FORMAT`
- `static java.lang.String ATT_BODY_FORMAT_RAW`
- `static java.lang.String ATT_CONTEXT_URL`
- `static java.lang.String ATT_CURL_COMMAND`
- `static java.lang.String ATT_CURL_ENABLED`
- `static java.lang.String ATT_CUSTOM_AUTH_URL`
- `static java.lang.String ATT_HEADER`
- `static java.lang.String ATT_HTTP_METHOD_TYPE`
- `static java.lang.String ATT_JSON_BODY`
- `static java.lang.String ATT_OPERATION_TYPE`
- `static java.lang.String ATT_PAGINATION_INITIAL_OFFSET`
- `static java.lang.String ATT_PAGINATION_SIZE`
- `static java.lang.String ATT_PAGINATION_STEPS`
- `static java.lang.String ATT_PARENT_ENDPOINT_NAME`
- `static java.lang.String ATT_RES_CODE`
- `static java.lang.String ATT_RES_MAP_OBJ`
- `static java.lang.String ATT_ROOT_PATH`
- `static java.lang.String ATT_SEQUENCE_NUMBER_FOR_ENDPOINT`
- `static java.lang.String ATT_STATUS`
- `static java.lang.String ATT_UNIQUE_NAME`
- `static java.lang.String ATT_XPATH_NAMESPACES`
- `static java.lang.String CONNECTOR_OP_ACCOUNT_AGGREGATION`
- `static java.lang.String CONNECTOR_OP_ADD_ENTITLEMENT`
- `static java.lang.String CONNECTOR_OP_CHANGE_PASSWORD`
- `static java.lang.String CONNECTOR_OP_CREATE`
- `static java.lang.String CONNECTOR_OP_CREATE_ACCOUT`
- `static java.lang.String CONNECTOR_OP_CREATE_GROUP`
- `static java.lang.String CONNECTOR_OP_CUSTOM_AUTHENTICATION`
- `static java.lang.String CONNECTOR_OP_DELETE`
- `static java.lang.String CONNECTOR_OP_DELETE_ACCOUNT`
- `static java.lang.String CONNECTOR_OP_DELETE_GROUP`
- `static java.lang.String CONNECTOR_OP_DELTA_ACCOUNT_AGGREGATION`
- `static java.lang.String CONNECTOR_OP_DISABLE_ACCOUNT`
- `static java.lang.String CONNECTOR_OP_ENABLE_ACCOUNT`
- `static java.lang.String CONNECTOR_OP_GET_OBJECT`
- `static java.lang.String CONNECTOR_OP_GET_OBJECT_GROUP`
- `static java.lang.String CONNECTOR_OP_GET_PARTITIONS`
- `static java.lang.String CONNECTOR_OP_GROUP_AGGREGATION`
- `static java.lang.String CONNECTOR_OP_PARTITIONED_ACCOUNT_AGGREGATION`
- `static java.lang.String CONNECTOR_OP_PTA_AUTHENTICATION`
- `static java.lang.String CONNECTOR_OP_REMOVE_ENTITLEMENT`
- `static java.lang.String CONNECTOR_OP_TEST_CONNECTION`
- `static java.lang.String CONNECTOR_OP_UNLOCK_ACCOUNT`
- `static java.lang.String CONNECTOR_OP_UPDATE`
- `static java.lang.String CONNECTOR_OP_UPDATE_ACCOUNT`
- `static java.lang.String CONNECTOR_OP_UPDATE_GROUP`

**Methods:**
- `void addBody ()`
- `void addHeader ()`
- `void addResAttributeMapObj ()`
- `void addXpathNamespace ()`
- `void deleteBody (java.lang.String id)`
- `void deleteHeader (java.lang.String id)`
- `void deleteResAttributeMapObj (java.lang.String id)`
- `void deleteXpathNamespace (java.lang.String id)`
- `java.lang.String getAfterRule ()`
- `java.lang.String getBeforeRule ()`
- `java.util.List<MapDTO> getBody ()`
- `java.lang.String getBodyFormat ()`
- `java.util.Map<java.lang.String,​java.lang.Object> getConfigObject (java.lang.String configStr)`
- `java.lang.String getContextUrl ()`
- `java.lang.String getCurlCommand ()`
- `boolean getCurlEnabled ()`
- `java.lang.String getCustomAuthUrl ()`
- `java.util.List<MapDTO> getHeader ()`
- `java.lang.String getHttpMethodType ()`
- `java.lang.String getJsonBody ()`
- `java.util.List<javax.faces.model.SelectItem> getMethodTypeList ()`
- `java.util.List<java.lang.String> getMethodTypes ()`
- `java.lang.String getName ()`
- `java.lang.String getOperation ()`
- `java.util.List<javax.faces.model.SelectItem> getOperationList (boolean filterCustomAuth)`
- `java.util.List<javax.faces.model.SelectItem> getOperationListV1 ()`
- `java.util.List<java.lang.String> getOptions ()`
- `java.lang.String getOrder ()`
- `java.lang.String getPaginationSteps ()`
- `int getPagingInitialOffset ()`
- `int getPagingSize ()`
- `java.lang.String getParentEndpointName ()`
- `java.util.List<MapDTO> getResAttMapObj ()`
- `java.lang.String getResponseCode ()`
- `java.lang.String getRootPath ()`
- `java.lang.String getStatus ()`
- `java.util.List<MapDTO> getXpathNamespaces ()`
- `void setAfterRule (java.lang.String arule)`
- `void setBeforeRule (java.lang.String brule)`
- `void setBody (java.util.List< MapDTO > body)`
- `void setBodyFormat (java.lang.String formatType)`
- `void setContextUrl (java.lang.String endPoint)`
- `void setCurlCommand (java.lang.String curlCommand)`
- `void setCurlEnabled (boolean curlEnabled)`
- `void setCustomAuthUrl (java.lang.String endPoint)`
- `void setHeader (java.util.List< MapDTO > header)`
- `void setHttpMethodType (java.lang.String method)`
- `void setJsonBody (java.lang.String jbody)`
- `void setName (java.lang.String name)`
- `void setOperation (java.lang.String op)`
- `void setOrder (java.lang.String order)`
- `void setPaginationSteps (java.lang.String paginationSteps)`
- `void setPagingInitialOffset (int pagingInitialOffset)`
- `void setPagingSize (int pagingLimit)`
- `void setParentEndpointName (java.lang.String parentEndpointName)`
- `void setResAttMapObj (java.util.List< MapDTO > resObj)`
- `void setResponseCode (java.lang.String resCode)`
- `void setRootPath (java.lang.String rPath)`
- `void setStatus (java.lang.String status)`
- `void setXpathNamespaces (java.util.List< MapDTO > xpathNamespaces)`

---

## ConnectorTestConfig.ConnectorTest

**Package:** `sailpoint.object`

**Description:** Inner class ConnectorTests that describes the behavior of each individual test.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ConnectorTestConfig.ConnectorTest`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `java.lang.String partitionStatementType`

**Methods:**
- `ConnectorTestConfig.ConnectorTest clone ()`
- `java.lang.String getAccountAttrValue ()`
- `java.lang.String getAccountSchemaAttrName ()`
- `Script getAggregationScope ()`
- `int getAttempts ()`
- `Script getAttributeToAdd ()`
- `java.lang.String getAttributeToFilter ()`
- `java.lang.String getAttributeToRemove ()`
- `java.lang.String getAuthAttribute ()`
- `Script getCheckAppAttributeScript ()`
- `Script getCompareDeltaRO ()`
- `Script getCompareROScript ()`
- `java.lang.String getCurrentPassword ()`
- `int getDelay ()`
- `Script getDeleteValidationScript ()`
- `int getDeltaThreshold ()`
- `java.lang.String getDoNotDeleteAccountAttrValue ()`
- `int getExactIterate ()`
- `java.lang.String getExpectedStatus ()`
- `java.lang.String getGroup ()`
- `java.lang.String getIdentityAttribute ()`
- `int getInvalidAuthCount ()`
- `boolean getIsPartition ()`
- `Script getLockScript ()`
- `int getMaxIterate ()`
- `int getMinIterate ()`
- `java.lang.String getName ()`
- `java.lang.String getNativeIdentity ()`
- `Script getNegativeTestValidationScript ()`
- `Script getObjectIdGenerationScript ()`
- `java.lang.String getObjectType ()`
- `java.lang.String getPartitionStatementType ()`
- `java.lang.String getPassword ()`
- `ProvisioningPlan getPlan ()`
- `Script getPostTestScript ()`
- `Script getPreTestScript ()`
- `java.lang.String getReferenceFile ()`
- `ProvisioningResult getResult ()`
- `java.lang.String getRunAgainstTestApps ()`
- `java.lang.String getRunType ()`
- `java.lang.String getSchemaAttributeToExclude ()`
- `Script getSchemaAttributeToRemove ()`
- `Script getSchemaAttributeToUpdate ()`
- `ConnectorTestConfig.TestType getType ()`
- `java.util.List<java.lang.String> getUnverifiableAttributeList ()`
- `java.lang.String getUnverifiableAttributes ()`
- `Script getValidateROScript ()`
- `java.lang.String getValidationAttrbutes ()`
- `boolean isCheckAppAttribute ()`
- `boolean isCompareRO ()`
- `boolean isDebug ()`
- `boolean isDeleteAll ()`
- `boolean isDisable ()`
- `boolean isDisableConnectorStateMapUpdate ()`
- `boolean isDisabled ()`
- `boolean isNegative ()`
- `boolean isNoDefaultSchema ()`
- `boolean isRetry ()`
- `boolean isSkipForINOW ()`
- `boolean isValidateRO ()`
- `boolean isValidateUsingTestConfiguration ()`
- `void setAccountAttrValue (java.lang.String accountAttrValue)`
- `void setAccountSchemaAttrName (java.lang.String accountSchemaAttrName)`
- `void setAggregationScope ( Script aggregationScope)`
- `void setAttempts (int attempts)`
- `void setAttributeToAdd ( Script attributeToAdd)`
- `void setAttributeToFilter (java.lang.String attributeName)`
- `void setAttributeToRemove (java.lang.String attributeToRemove)`
- `void setAuthAttribute (java.lang.String authAttribute)`
- `void setCheckAppAttribute (boolean checkAppAttribute)`
- `void setCheckAppAttributeScript ( Script CheckAppAttributecript)`
- `void setCompareDeltaRO ( Script compareDeltaRO)`
- `void setCompareRO (boolean compareRO)`
- `void setCompareROScript ( Script compareROScript)`
- `void setCurrentPassword (java.lang.String currentPassword)`
- `void setDebug (boolean debug)`
- `void setDelay (int delay)`
- `void setDeleteAll (boolean deleteAll)`
- `void setDeleteValidationScript ( Script deleteValidationScript)`
- `void setDeltaThreshold (int deltaThreshold)`
- `void setDisable (boolean disable)`
- `void setDisableConnectorStateMapUpdate (boolean disableConnectorStateMapUpdate)`
- `void setDoNotDeleteAccountAttrValue (java.lang.String doNotDeleteAccountAttrValue)`
- `void setExactIterate (int exactIterate)`
- `void setExpectedStatus (java.lang.String expectedStatus)`
- `void setGroup (java.lang.String group)`
- `void setIdentityAttribute (java.lang.String identityAttribute)`
- `void setInvalidAuthCount (int invalidAuthCount)`
- `void setIsPartition (boolean isPartition)`
- `void setLockScript ( Script lockScript)`
- `void setMaxIterate (int maxIterate)`
- `void setMinIterate (int minIterate)`
- `void setName (java.lang.String name)`
- `void setNativeIdentity (java.lang.String nativeIdentitifer)`
- `void setNegative (boolean negative)`
- `void setNegativeTestValidationScript ( Script negativeTestValidationScript)`
- `void setNoDefaultSchema (boolean noDefaultSchema)`
- `void setObjectIdGenerationScript ( Script objectIdGenerationScript)`
- `void setObjectType (java.lang.String objectType)`
- `void setPartitionStatementType (java.lang.String partitionStatementType)`
- `void setPassword (java.lang.String password)`
- `void setPlan ( ProvisioningPlan plan)`
- `void setPostTestScript ( Script postTestScript)`
- `void setPreTestScript ( Script preTestScript)`
- `void setReferenceFile (java.lang.String referenceFile)`
- `void setResult ( ProvisioningResult result)`
- `void setRetry (boolean retry)`
- `void setRunAgainstTestApps (java.lang.String runAgainstTestApps)`
- `void setRunType (java.lang.String runType)`
- `void setSchemaAttributeToExclude (java.lang.String schemaAttributeToExclude)`
- `void setSchemaAttributeToRemove ( Script schemaAttributeToRemove)`
- `void setSchemaAttributeToUpdate ( Script schemaAttributeToUpdate)`
- `void setSkipForINOW (boolean skipForINOW)`
- `void setType ( ConnectorTestConfig.TestType type)`
- `void setUnverifiableAttributes (java.lang.String unverifiableAttributeCSV)`
- `void setValidateRO (boolean validationRO)`
- `void setValidateROScript ( Script validationROScript)`
- `void setValidateUsingTestConfiguration (boolean validateUsingTestConfiguration)`
- `void setValidationAttrbutes (java.lang.String validationAttrbutes)`

---

## ConnectorTestConfig.TestType

**Package:** `sailpoint.object`

**Description:** Specifies which type of test is being defined.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ConnectorTestConfig.TestType`
- `sailpoint.object.ConnectorTestConfig.TestType`
- `java.io.Serializable`
- `java.lang.Comparable<ConnectorTestConfig.TestType>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getDefaultGroup ()`
- `Application.Feature getFeature ()`
- `boolean isSupported ( Application application)`
- `staticConnectorTestConfig.TestType valueOf (java.lang.String name)`
- `staticConnectorTestConfig.TestType[] values ()`

---

## ConnectorTestConfig

**Package:** `sailpoint.object`

**Description:** Configuration that indicates the settings and configuration for each connector while being executed by the ConnectorTestFramework. The idea is to extract out the things necessary to execute the tests without requiring code. The idea is to run each connector to plug into the framework so it can be verified and in working order. 1) Create In this case the test accountId should be generated. The rest of the attribute list should be as complete as possible and include at least all of "typical" attributes. Type objectTypes supported account AND group, if left null indicates account.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ConnectorTestConfig`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `Application getApplication ()`
- `java.lang.String getAppNameStartWith ()`
- `java.util.List<ConnectorTestConfig.ConnectorTest> getBeforeTests ()`
- `java.lang.String getCsvListDelimiter ()`
- `boolean getExecutedFromInow ()`
- `java.util.HashMap<java.lang.String,​java.lang.Object> getExtraParams ()`
- `java.lang.String getImportFile ()`
- `java.lang.String getName ()`
- `java.lang.String getRunAgainstTestApps ()`
- `java.lang.String getTestConfigName ()`
- `java.util.List<ConnectorTestConfig.ConnectorTest> getTests ()`
- `java.util.List<ConnectorTestConfig.ConnectorTest> getTests ( ConnectorTestConfig.TestType type)`
- `java.lang.String getType ()`
- `boolean isDebug ()`
- `boolean isDisable ()`
- `boolean isNativeIdentityGenerated ()`
- `boolean isNativeIdentityGeneratedInResult ()`
- `boolean isUseCreateAccountForTests ()`
- `boolean isUseExistingApplication ()`
- `boolean isUseTestAppFeatures ()`
- `boolean isUseTestAppSchema ()`
- `void setApplication ( Application application)`
- `void setAppNameStartWith (java.lang.String appNameStartWith)`
- `void setBeforeTests (java.util.List< ConnectorTestConfig.ConnectorTest > tests)`
- `void setCsvListDelimiter (java.lang.String csvListDelimiter)`
- `void setDebug (boolean debug)`
- `void setDisable (boolean disable)`
- `void setExecutedFromInow (boolean _executedFromInow)`
- `void setExtraParams (java.util.HashMap<java.lang.String,java.lang.Object> extraParams)`
- `void setImportFile (java.lang.String importFile)`
- `void setName (java.lang.String name)`
- `void setNativeIdentityGenerated (boolean nativeIdentityGenerated)`
- `void setNativeIdentityGeneratedInResult (boolean nativeIdentityGeneratedInResult)`
- `void setRunAgainstTestApps (java.lang.String runAgainstTestApps)`
- `void setTestConfigName (java.lang.String testConfigName)`
- `void setTests (java.util.List< ConnectorTestConfig.ConnectorTest > tests)`
- `void setType (java.lang.String type)`
- `void setUseCreateAccountForTests (boolean useCreateAccountForTests)`
- `void setUseExistingApplication (boolean useExistingApplication)`
- `void setUseTestAppFeatures (boolean useTestAppFeatures)`
- `void setUseTestAppSchema (boolean useTestAppSchema)`

---

## ContinuousStateConfig

**Package:** `sailpoint.object`

**Description:** Configuration for a Certification continuous state.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.CertificationStateConfig`
- `sailpoint.object.ContinuousStateConfig`

**Attributes:** N/A

**Methods:**
- `AbstractCertificationItem.ContinuousState getContinuousState ()`
- `void setContinuousState ( AbstractCertificationItem.ContinuousState state)`

---

## CorrelationConfig

**Package:** `sailpoint.object`

**Description:** A representation of the configuration for account correlation. This is an alternate to Rule based correlation.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.CorrelationConfig`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `void addAttributeAssignment ( Filter filter)`
- `void addDirect ( DirectAssignment direct)`
- `java.util.List<Filter> getAttributeAssignments ()`
- `java.util.List<DirectAssignment> getDirectAssignments ()`
- `void load ()`
- `void setAttributeAssignments (java.util.List< Filter > attributeAssignments)`
- `void setDirectAssignments (java.util.List< DirectAssignment > direct)`
- `void visit ( Visitor v)`

---

## Custom

**Package:** `sailpoint.object`

**Description:** A class used to store customer-specific data. This just stores a Map as an XML blob. In that way it is similar to Configuration but having a different class ensures that the namespaces will not conflict. Also unlike Configuration, Custom does not require a unique name. The intent is that there not be very many of these so they can be considered "exportable" classes. Do not use it for things like a custom audit log where you can have thousands of instances.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Custom`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.Object clone ()`
- `boolean containsAttribute (java.lang.String name)`
- `java.lang.Object get (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `boolean getBoolean (java.lang.String name)`
- `boolean getBoolean (java.lang.String name, boolean dflt)`
- `int getInt (java.lang.String name)`
- `java.util.List getList (java.lang.String name)`
- `long getLong (java.lang.String name)`
- `java.lang.String getString (java.lang.String name)`
- `void put (java.lang.String name, int value)`
- `void put (java.lang.String name, java.lang.Object value)`
- `void remove (java.lang.String name)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> a)`

---

## CustomGlobal

**Package:** `sailpoint.object`

**Description:** A class used to maintain a static Map of custom attributes. This can be used as a way to maintain global variables across calls to custom rules.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.CustomGlobal`

**Attributes:** N/A

**Methods:**
- `static void clear ()`
- `static java.lang.Object get (java.lang.String name)`
- `static java.util.Set<java.lang.String> keySet ()`
- `static void put (java.lang.String name, java.lang.Object value)`
- `static java.lang.Object remove (java.lang.String name)`
- `static int size ()`

---

## DatabaseVersion

**Package:** `sailpoint.object`

**Description:** A class used to maintain a persistent version number for the object model and associated Hibernate schema. This is used during system startup to verify that a database that is about to be connected to has a schema that is compatible with Java classes the system was built with.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.DatabaseVersion`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String OBJ_NAME`
- `static java.lang.String REQUIRED_UPGRADE_MAJOR_VERSION`
- `static java.lang.String SCHEMA_VERSION`
- `static java.lang.String SYSTEM_VERSION`

**Methods:**
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `java.lang.String getSchemaVersion ()`
- `static java.lang.String getSchemaVersionConstant ()`
- `java.lang.String getSystemVersion ()`
- `static java.lang.String getSystemVersionConstant ()`
- `boolean hasAssignedScope ()`
- `void setSchemaVersion (java.lang.String schemaVersion)`
- `void setSystemVersion (java.lang.String s)`

---

## DeletedObject

**Package:** `sailpoint.object`

**Description:** Class used represent deleted accounts and groups on applications supporting recycle bin.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.DeletedObject`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.Object clone ()`
- `Application getApplication ()`
- `java.lang.String getApplicationName ()`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getDisplayableName ()`
- `java.util.Map<java.lang.String,​java.lang.Object> getExtendedAttributes ()`
- `java.util.Date getLastRefresh ()`
- `java.lang.String getName ()`
- `java.lang.String getNativeIdentity ()`
- `staticObjectConfig getObjectConfig ()`
- `java.lang.String getObjectType ()`
- `java.lang.String getUuid ()`
- `boolean hasName ()`
- `void setApplication ( Application res)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> a)`
- `void setDisplayableName (java.lang.String displayableName)`
- `void setLastRefresh (java.util.Date D)`
- `void setName (java.lang.String Name)`
- `void setNativeIdentity (java.lang.String id)`
- `void setObjectType (java.lang.String objectType)`
- `void setUuid (java.lang.String id)`
- `java.lang.String toString ()`

---

## Describable

**Package:** `sailpoint.object`

**Description:** Interface for objects that have descriptions. As of the time this interface originated these are: Application, Policy, Bundle, ManagedAttribute

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `void addDescription (java.lang.String locale, java.lang.String desc)`
- `default java.lang.String getAiGeneratedDescriptionLocales ()`
- `java.lang.String getDescription (java.lang.String locale)`
- `java.lang.String getDescription (java.util.Locale locale)`
- `java.util.Map<java.lang.String,​java.lang.String> getDescriptions ()`
- `default void setAiGeneratedDescriptionLocales (java.lang.String locales)`
- `void setDescriptions (java.util.Map<java.lang.String,java.lang.String> map)`

---

## Dictionary

**Package:** `sailpoint.object`

**Description:** Used to maintain a collection of words that should not be allowed as passwords.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Dictionary`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String OBJ_NAME`

**Methods:**
- `java.lang.String getName ()`
- `DictionaryTerm getTerm (java.lang.String value)`
- `java.util.List<DictionaryTerm> getTerms ()`
- `void setName (java.lang.String name)`
- `void setTerms (java.util.List< DictionaryTerm > terms)`

---

## DictionaryTerm

**Package:** `sailpoint.object`

**Description:** Part of the Dictionary model, used to maintain a collection of words that should not be used as passwords.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.DictionaryTerm`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `Dictionary getDictionary ()`
- `java.lang.String getValue ()`
- `boolean hasName ()`
- `void setDictionary ( Dictionary dictionary)`
- `void setValue (java.lang.String value)`

---

## Difference

**Package:** `sailpoint.object`

**Description:** This class provides a model for a difference between two abstract attributes. It also provides a set of static methods to compare various classes and calculate differences.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Difference`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static int MAX_MULTI_VALUES`
- `static int MAX_STRING_LENGTH`

**Methods:**
- `void addAddedValue (java.lang.String value)`
- `void addRemovedValue (java.lang.String value)`
- `staticDifference diff (java.lang.Object oldValue, java.lang.Object newValue)`
- `staticDifference diff (java.lang.Object oldValue, java.lang.Object newValue, int maxStringLength)`
- `staticDifference diff (java.lang.Object oldValue, java.lang.Object newValue, int maxStringLength, boolean caseInsensitive)`
- `static java.util.List<Difference> diffMaps (java.util.Map map1, java.util.Map map2)`
- `static java.util.List<Difference> diffMaps (java.util.Map map1, java.util.Map map2, java.util.List exclusions)`
- `static java.util.List<Difference> diffMaps (java.util.Map map1, java.util.Map map2, java.util.List exclusions, int maxStringLength)`
- `static java.util.List<Difference> diffMaps (java.util.Map map1, java.util.Map map2, java.util.List exclusions, int maxStringLength, int maxDiff)`
- `static boolean equal (java.util.Map map1, java.util.Map map2)`
- `java.util.List<java.lang.String> getAddedValues ()`
- `java.lang.String getAddedValuesCsv ()`
- `java.util.List<java.lang.String> getAllNewValues ()`
- `java.lang.String getAttribute ()`
- `java.lang.String getContext ()`
- `java.lang.String getDisplayableName ()`
- `java.lang.String getDisplayName ()`
- `java.lang.String getNewValue ()`
- `java.lang.String getOldValue ()`
- `java.util.List<java.lang.String> getRemovedValues ()`
- `java.lang.String getRemovedValuesCsv ()`
- `static boolean hasIncrementalChanges (java.util.Collection<?> oldValues, java.util.Collection<?> newValues)`
- `boolean isMulti ()`
- `static java.util.List<java.lang.String> listify (java.util.Collection src)`
- `static java.util.List<java.lang.String> listify (java.util.Collection src, int maxStringLength)`
- `void setAddedValues (java.util.List<java.lang.String> values)`
- `void setAttribute (java.lang.String name)`
- `void setAttribute ( AttributeDefinition def)`
- `void setAttribute ( ObjectAttribute ida)`
- `void setContext (java.lang.String name)`
- `void setDisplayName (java.lang.String name)`
- `static int setMaxMultiValues (int max)`
- `static int setMaxStringLength (int max)`
- `void setMulti (boolean b)`
- `void setNewValue (java.lang.String v)`
- `void setOldValue (java.lang.String v)`
- `void setRemovedValues (java.util.List<java.lang.String> values)`
- `static java.lang.String stringify (java.lang.Object value)`
- `static java.lang.String stringify (java.lang.Object value, int maxStringLength)`
- `Difference truncateStrings ()`
- `Difference truncateStrings (int maxStringLength)`

---

## DirectAssignment

**Package:** `sailpoint.object`

**Description:** A representation of the configuration for correlation. This includes both Account Correlation and Manager correlation. An alternate easier way to configure correlation when a Rule is too complex.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.DirectAssignment`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void add ( Filter filter)`
- `java.util.List<Filter> getFilters ()`
- `Identity getIdentity ()`
- `void setFilters (java.util.List< Filter > filters)`
- `void setIdentity ( Identity identity)`

---

## DomainData

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.DomainData`

**Attributes:**
- `static java.lang.String AUTH_TYPE_SIMPLE`
- `static java.lang.String DEFAULT_PORT`
- `static java.lang.String SSL_PORT`

**Methods:**
- `boolean getAuthEnabled ()`
- `java.lang.String getAuthenticationType ()`
- `java.lang.String getAuthType ()`
- `java.lang.String getDomainDN ()`
- `java.lang.String getDomainForestName ()`
- `java.lang.String getDomainIterateSearchFilter ()`
- `java.lang.String getNetBIOS ()`
- `java.lang.String getPassword ()`
- `java.lang.String getPort ()`
- `java.util.List getServerList ()`
- `java.lang.String getShadowAccountMembershipFilter ()`
- `boolean getTlsEnabled ()`
- `java.lang.String getUser ()`
- `boolean isDisableShadowAccountMembership ()`
- `boolean isEnablePasswordLessAuthentication ()`
- `boolean isUseSSL ()`
- `void setAuthEnabled (boolean authEnabled)`
- `void setAuthenticationType (java.lang.String authType)`
- `void setAuthType (java.lang.String authType)`
- `void setDisableShadowAccountMembership (boolean _disableShadowAccountMembership)`
- `void setDomainDN (java.lang.String domain)`
- `void setDomainForestName (java.lang.String forestName)`
- `void setDomainIterateSearchFilter (java.lang.String domainIterateSearchFilter)`
- `void setEnablePasswordLessAuthentication (boolean enablePasswordLessAuthentication)`
- `void setNetBIOS (java.lang.String netBIOS)`
- `void setPassword (java.lang.String password)`
- `void setPort (java.lang.String port)`
- `void setServerList (java.util.List serverList)`
- `void setShadowAccountMembershipFilter (java.lang.String shadowAccountMembershipFilter)`
- `void setTlsEnabled (boolean tlsEnabled)`
- `void setUser (java.lang.String userName)`
- `void setUseSSL (boolean useSSL)`

---

## Duration.Scale

**Package:** `sailpoint.object`

**Description:** Enumeration of the scales of a duration. Note that there is a subset of this enum in CertificationScheduleCommonModule.DURATION_SCALE. If you update this enum, you may need to update that constant as well.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Duration.Scale`
- `sailpoint.object.Duration.Scale`
- `java.io.Serializable`
- `java.lang.Comparable<Duration.Scale>`
- `sailpoint.tools.MessageKeyHolder`

**Attributes:** N/A

**Methods:**
- `java.lang.String format (long amount, java.util.Locale locale)`
- `int getCalendarField ()`
- `java.lang.String getMessageKey ()`
- `staticDuration.Scale valueOf (java.lang.String name)`
- `staticDuration.Scale[] values ()`

---

## Duration

**Package:** `sailpoint.object`

**Description:** A duration of time specified as a number of units (the amount) and a scale.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Duration`

**Attributes:** N/A

**Methods:**
- `java.util.Date addTo (java.util.Date date)`
- `boolean equals (java.lang.Object o)`
- `java.lang.String format (java.util.Locale locale)`
- `static java.lang.String formatTimeDifference (java.util.Date end, java.util.Date start, java.util.Locale locale)`
- `static java.lang.String formatTimeDifference (java.util.Date end, java.util.Date start, java.util.Locale locale, Duration.Scale minimum)`
- `long getAmount ()`
- `Duration.Scale getScale ()`
- `int hashCode ()`
- `void setAmount (long amount)`
- `void setScale ( Duration.Scale scale)`
- `java.util.Date subtractFrom (java.util.Date date)`
- `java.lang.String toString ()`

---

## DynamicScope.PopulationRequestAuthority.MatchConfig

**Package:** `sailpoint.object`

**Description:** Match Configuration Object used to create the filter.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.DynamicScope.PopulationRequestAuthority.MatchConfig`

**Attributes:** N/A

**Methods:**
- `java.lang.String getCustomControl ()`
- `java.lang.String getFilterGenerationRuleName ()`
- `IdentityAttributeFilterControl getIdentityAttributeFilterControl ()`
- `int getMaxHierarchyCount ()`
- `int getMaxHierarchyDepth ()`
- `java.lang.String getSubordinateOption ()`
- `boolean isEnableAttributeControl ()`
- `boolean isEnableCustomControl ()`
- `boolean isEnableFilterGenerationRule ()`
- `boolean isEnableSubordinateControl ()`
- `boolean isMatchAll ()`
- `void setCustomControl (java.lang.String customControl)`
- `void setEnableAttributeControl (boolean enableAttributeControl)`
- `void setEnableCustomControl (boolean enableCustomControl)`
- `void setEnableFilterGenerationRule (boolean enableFilterGenerationRule)`
- `void setEnableSubordinateControl (boolean enableSubordinateControl)`
- `void setFilterGenerationRuleName (java.lang.String filterGenerationRuleName)`
- `void setIdentityAttributeFilterControl ( IdentityAttributeFilterControl identityAttributeFilterControl)`
- `void setMatchAll (boolean matchAll)`
- `void setMaxHierarchyCount (int maxHierarchyCount)`
- `void setMaxHierarchyDepth (int maxHierarchyDepth)`
- `void setSubordinateOption (java.lang.String subordinateOption)`

---

## DynamicScope.PopulationRequestAuthority

**Package:** `sailpoint.object`

**Description:** PopulationRequestAuthority is used to define the list of identities a user can 'request for'. In the previous releases to version 6.4 this was defined in various configuration options but is now consolidated to this object. Setting Configuration.LCM_REQUEST_CONTROLS_ALLOW_ALL to true in the map will ignore any other properties (Configuration.LCM_REQUEST_CONTROLS_DISABLE_SCOPING excluded)

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.DynamicScope.PopulationRequestAuthority`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `DynamicScope.PopulationRequestAuthority.MatchConfig getMatchConfig ()`
- `boolean isAllowAll ()`
- `boolean isIgnoreScoping ()`
- `void setAllowAll (boolean allowAll)`
- `void setIgnoreScoping (boolean ignoreScoping)`
- `void setMatchConfig ( DynamicScope.PopulationRequestAuthority.MatchConfig match)`

---

## DynamicScope

**Package:** `sailpoint.object`

**Description:** Dynamic Scopes incorporate various existing ways of defining identity populations into a unified model.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.DynamicScope`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.Object clone ()`
- `Rule getApplicationRemoveControl ()`
- `Rule getApplicationRequestControl ()`
- `java.util.List<Identity> getExclusions ()`
- `java.util.List<Identity> getInclusions ()`
- `Rule getManagedAttributeRemoveControl ()`
- `Rule getManagedAttributeRequestControl ()`
- `DynamicScope.PopulationRequestAuthority getPopulationRequestAuthority ()`
- `Rule getRoleRemoveControl ()`
- `Rule getRoleRequestControl ()`
- `IdentitySelector getSelector ()`
- `boolean isAllowAll ()`
- `void setAllowAll (boolean allowAll)`
- `void setApplicationRemoveControl ( Rule _applicationRemoveControl)`
- `void setApplicationRequestControl ( Rule applicationRequestControl)`
- `void setExclusions (java.util.List< Identity > exclusions)`
- `void setInclusions (java.util.List< Identity > inclusions)`
- `void setManagedAttributeRemoveControl ( Rule _managedAttributeRemoveControl)`
- `void setManagedAttributeRequestControl ( Rule managedAttributeRequestControl)`
- `void setPopulationRequestAuthority ( DynamicScope.PopulationRequestAuthority populationRequestAuthority)`
- `void setRoleRemoveControl ( Rule _roleRemoveControl)`
- `void setRoleRequestControl ( Rule rule)`
- `void setSelector ( IdentitySelector identitySelector)`
- `java.lang.String toString ()`
- `void visit ( Visitor v)`

---

## DynamicValue

**Package:** `sailpoint.object`

**Description:** Return a DynamicValue for the requested attribute in the attributes map, or null if the requested attribute is null or not a DynamicValue (for example - rule or script).

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.DynamicValue`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `staticDynamicValue get ( Attributes <java.lang.String,java.lang.Object> attrs, java.lang.String attribute, Resolver resolver)`
- `staticDynamicValue get ( Attributes <java.lang.String,java.lang.Object> attrs, java.lang.String attribute, Resolver resolver, boolean excludeLiterals)`
- `Rule getRule ()`
- `Script getScript ()`
- `staticScriptlet getScriptlet ( Attributes <java.lang.String,java.lang.Object> attrs, java.lang.String attribute)`
- `java.lang.Object getValue ()`
- `static boolean isDynamicValue ( Attributes <java.lang.String,java.lang.Object> attrs, java.lang.String attribute)`
- `boolean isEmpty ()`
- `boolean isLiteral ()`
- `void load ()`
- `staticAttributes<java.lang.String,​java.lang.Object> set ( Attributes <java.lang.String,java.lang.Object> attrs, java.lang.String attribute, DynamicValue dv)`
- `void setFinalValue (java.lang.Object value)`
- `void setRule ( Rule rule)`
- `void setScript ( Script s)`
- `void setValue (java.lang.Object value)`

---

## ESignatureType

**Package:** `sailpoint.object`

**Description:** A class holding the definition of one electronic signature "meaning".

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ESignatureType`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String CONFIG_ATT_TYPES`
- `static java.lang.String CONFIG_NAME`

**Methods:**
- `void addMeaning (java.lang.String locale, java.lang.String text)`
- `java.lang.String getDisplayableName ()`
- `java.lang.String getDisplayName ()`
- `java.lang.String getMeaning (java.lang.String locale)`
- `java.util.Map<java.lang.String,​java.lang.String> getMeanings ()`
- `java.lang.String getName ()`
- `void setDisplayName (java.lang.String name)`
- `void setMeanings (java.util.Map<java.lang.String,java.lang.String> meanings)`
- `void setName (java.lang.String name)`

---

## ElectronicSignature

**Package:** `sailpoint.object`

**Description:** Author: peter.holcomb

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.ElectronicSignature`

**Attributes:**
- `static java.lang.String INPUT_SIGNATURE_ACCOUNT`
- `static java.lang.String INPUT_SIGNATURE_PASSWORD`
- `static java.lang.String INPUT_SIGNATURE_SAML_ASSERTIONID`
- `static java.lang.String INPUT_SIGNATURE_SAML_NAMEID`

**Methods:**
- `java.lang.String getAccountId ()`
- `java.lang.String getPassword ()`
- `java.lang.String getSamlAssertionId ()`
- `java.lang.String getSamlNameId ()`

---

## EmailFileAttachment.MimeType

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `EmailFileAttachment.MimeType`
- `sailpoint.object.EmailFileAttachment.MimeType`
- `java.io.Serializable`
- `java.lang.Comparable<EmailFileAttachment.MimeType>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getType ()`
- `staticEmailFileAttachment.MimeType valueOf (java.lang.String name)`
- `staticEmailFileAttachment.MimeType[] values ()`

---

## EmailFileAttachment

**Package:** `sailpoint.object`

**Description:** Class that can be used to describe file attachments when sending email. Basic idea here is to name the MimeType, data(filecontents, and the name of the filename or attachment. Attachments are passed into the notifier via the EmailOptions.addAttachment(EmailFileAttachment attachment) method. Defaults to a application/octet-stream Mime type.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.EmailFileAttachment`
- `java.io.Serializable`

**Attributes:** N/A

**Methods:**
- `byte[] getData ()`
- `java.lang.String getFileName ()`
- `EmailFileAttachment.MimeType getMimeType ()`
- `java.lang.String getMimeTypeString ()`
- `void setData (byte[] data)`
- `void setFileName (java.lang.String name)`
- `void setMimeType ( EmailFileAttachment.MimeType type)`

---

## EmailOptions

**Package:** `sailpoint.object`

**Description:** Set of inputs to an email template.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.EmailOptions`
- `java.io.Serializable`
- `java.lang.Cloneable`

**Attributes:** N/A

**Methods:**
- `void addAttachment ( EmailFileAttachment attachment)`
- `void addVariables (java.util.Map<java.lang.String,java.lang.Object> newVariables)`
- `java.lang.Object clone ()`
- `java.util.List<EmailFileAttachment> getAttachments ()`
- `java.lang.String getCc ()`
- `java.lang.String getFileName ()`
- `java.lang.String getString (java.lang.String name)`
- `java.lang.String getTo ()`
- `java.lang.Object getVariable (java.lang.String name)`
- `java.util.Map<java.lang.String,​java.lang.Object> getVariables ()`
- `void setAttachments (java.util.List< EmailFileAttachment > attachments)`
- `void setCc (java.lang.String cc)`
- `void setFileName (java.lang.String fileName)`
- `void setTo (java.lang.String to)`
- `void setTo (java.util.List<java.lang.String> toAddresses)`
- `void setVariable (java.lang.String name, java.lang.Object value)`
- `void setVariables (java.util.Map<java.lang.String,java.lang.Object> vars)`

---

## EmailTemplate

**Package:** `sailpoint.object`

**Description:** Class containing information required to send an email. Templates are shared objects, they are typically combined with a EmailOptions object at runtime.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.EmailTemplate`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `NotificationTemplate`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String HOST_PROPERTY`
- `static java.lang.String PORT_PROPERTY`

**Methods:**
- `java.lang.Object clone ()`
- `EmailTemplate compile ( Resolver resolver, Configuration sysconfig, EmailOptions options)`
- `java.lang.String getBcc ()`
- `java.lang.String getBody ()`
- `java.lang.String getCc ()`
- `java.lang.String getFrom ()`
- `java.util.Map<java.lang.String,​java.lang.String> getSessionProperties ()`
- `Signature getSignature ()`
- `java.lang.String getSubject ()`
- `java.lang.String getTo ()`
- `void load ()`
- `void setBcc (java.lang.String bcc)`
- `void setBody (java.lang.String body)`
- `void setCc (java.lang.String cc)`
- `void setFrom (java.lang.String from)`
- `void setSessionProperties (java.util.Map<java.lang.String,java.lang.String> props)`
- `void setSignature ( Signature s)`
- `void setSubject (java.lang.String subject)`
- `void setTo (java.lang.String _to)`

---

## Entitlement

**Package:** `sailpoint.object`

**Description:** Instances of this class are non-persistent objects that contain the information required to process and display entitlements

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Entitlement`

**Attributes:**
- `static java.lang.String TEMPLATE_APPLICATION_NAME`
- `static java.lang.String TEMPLATE_ATTRIBUTE_NAME`
- `static java.lang.String TEMPLATE_ATTRIBUTE_VALUE`
- `static java.lang.String TEMPLATE_DESCRIPTION`
- `static java.lang.String TEMPLATE_PERMISSION_RIGHTS`
- `static java.lang.String TEMPLATE_PERMISSION_TARGET`

**Methods:**
- `boolean equals (java.lang.Object obj)`
- `static java.util.List<Entitlement> getAccountEntitlements (java.util.Locale locale, Link link, java.lang.String attributeFilter)`
- `static java.util.List<Entitlement> getAccountEntitlements ( Application app, java.util.Map<java.lang.String,java.lang.Object> attributes, java.util.Locale locale, java.lang.String attributeFilter)`
- `java.lang.String getApplicationName ()`
- `java.lang.String getAttributeName ()`
- `java.lang.String getAttributeValue ()`
- `java.lang.String getDescription ()`
- `Permission getPermission ()`
- `static java.util.List<Entitlement> getPermissionEntitlements ( Application app, java.util.List< Permission > permissions, java.util.Locale locale, java.lang.String permissionFilter)`
- `java.lang.String getRoleName (java.lang.String template)`
- `int hashCode ()`

---

## EntitlementCollection

**Package:** `sailpoint.object`

**Description:** An EntitlementCollection is a non-persistent class that holds entitlements grouped by application, instance, and nativeIdentity. This provides functionality such as merging entitlements when adding new entitlements, and removing pieces of entitlements.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.EntitlementCollection`
- `java.io.Serializable`

**Attributes:**
- `static java.lang.String KEY_DELIMITER`

**Methods:**
- `void add ( EntitlementCollection other)`
- `void addAttribute (java.lang.String app, java.lang.String instance, java.lang.String nativeIdentity, java.lang.String displayName, java.lang.String attrName, java.lang.Object value)`
- `void addAttributes (java.lang.String app, java.lang.String instance, java.lang.String nativeIdentity, java.lang.String displayName, java.util.Map<java.lang.String,java.lang.Object> newAttrs)`
- `void addEntitlements ( EntitlementSnapshot entitlement)`
- `void addPermission (java.lang.String app, java.lang.String instance, java.lang.String nativeIdentity, java.lang.String displayName, Permission p)`
- `void addPermissions (java.lang.String app, java.lang.String instance, java.lang.String nativeIdentity, java.lang.String displayName, java.util.List< Permission > perms)`
- `void clear ()`
- `boolean containsAny ( EntitlementCollection ec)`
- `java.util.List<EntitlementGroup> getEntitlementGroups ( Resolver res)`
- `java.util.Collection<EntitlementSnapshot> getEntitlements ()`
- `static java.lang.String getKey (java.lang.String application, java.lang.String instance)`
- `static java.lang.String getKeyApplication (java.lang.String key)`
- `static java.lang.String getKeyInstance (java.lang.String key)`
- `boolean isEmpty ()`
- `static java.util.Map<java.lang.String,​java.lang.Object> mergeValues (java.lang.String attrName, java.lang.Object newVal, java.util.Map<java.lang.String,java.lang.Object> mergeMap)`
- `void remove ( EntitlementCollection ec)`
- `java.lang.String toString ()`

---

## EntitlementComment

**Package:** `sailpoint.object`

**Description:** Stores comments made on a given certifiable.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Comment`
- `sailpoint.object.EntitlementComment`
- `java.io.Serializable`
- `EntitlementHistoryItem`
- `sailpoint.tools.Localizable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getBusinessRole ()`
- `CertifiableDescriptor getCertifiableDescriptor ()`
- `EntitlementSnapshot getExceptionEntitlements ()`
- `boolean isSimiliarViolation ( PolicyViolation otherViolation)`
- `void setBusinessRole (java.lang.String businessRole)`
- `void setCertifiableDescriptor ( CertifiableDescriptor desc)`
- `void setConstraintId (java.lang.String constraintId)`
- `void setConstraintRuleName (java.lang.String constraintRuleName)`
- `void setExceptionEntitlements ( EntitlementSnapshot exceptionEntitlements)`
- `void setPolicyId (java.lang.String policyId)`
- `void setPolicyName (java.lang.String policyName)`
- `void setPolicyViolation ( PolicyViolation policyViolation)`

---

## EntitlementDataSource

**Package:** `sailpoint.object`

**Description:** This interface is implemented by SailPointObjects that contain information that represents entitlements.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `java.util.List<Entitlement> getEntitlements (java.util.Locale locale, java.lang.String attributeOrPermissionFilter)`

---

## EntitlementGroup

**Package:** `sailpoint.object`

**Description:** An EntitlementGroup holds a logical group of low-level entitlements on a specific account on an application. This can be used in different contexts, for example, holding exceptional entitlements, holding mappings from a job function to which entitlements granted the business role, etc.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.EntitlementGroup`
- `java.io.Serializable`
- `Certifiable`
- `EntitlementDataSource`
- `Entitlements`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `void add ( Permission p)`
- `EntitlementSnapshot convertToSnapshot ()`
- `Entitlements create (java.util.List< Permission > perms, Attributes <java.lang.String,java.lang.Object> attrs)`
- `boolean equals (java.lang.Object obj)`
- `Application getApplication ()`
- `java.lang.String getApplicationName ()`
- `Application getApplicationObject ( Resolver resolver)`
- `java.util.List<java.lang.String> getAttributeNames ()`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getDisplayName ()`
- `java.util.List<Entitlement> getEntitlements (java.util.Locale locale, java.lang.String permissionFilter)`
- `java.lang.String getInstance ()`
- `java.lang.String getNativeIdentity ()`
- `java.util.List<Permission> getPermissions ()`
- `int getValueCount ()`
- `int hashCode ()`
- `boolean isAccountOnly ()`
- `boolean isEmpty ()`
- `boolean isNameUnique ()`
- `void setAccountOnly (boolean accountOnly)`
- `void setApplication ( Application application)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attributes)`
- `void setDisplayName (java.lang.String displayName)`
- `void setInstance (java.lang.String ins)`
- `void setNativeIdentity (java.lang.String nativeIdentity)`
- `void setPermissions (java.util.List< Permission > permissions)`
- `static java.util.List<Entitlements> splitToAttributes (java.util.List<? extends Entitlements > ents)`
- `static java.util.List<Entitlements> splitToValues (java.util.List<? extends Entitlements > ents)`
- `static java.util.List<Entitlements> splitToValues (java.util.List<? extends Entitlements > ents, boolean excludePermissions)`

---

## EntitlementHistoryItem

**Package:** `sailpoint.object`

**Description:** Returns true if the decision represents a decision on the given violation.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `java.lang.String getBusinessRole ()`
- `CertifiableDescriptor getCertifiableDescriptor ()`
- `EntitlementSnapshot getExceptionEntitlements ()`
- `boolean isSimiliarViolation ( PolicyViolation otherViolation)`

---

## EntitlementSnapshot

**Package:** `sailpoint.object`

**Description:** Holds a collection of entitlements for an application. This is almost identical to EntitlementGroup but this is used in "archival" objects and as such it has no direct references to other objects, in this case an Application . Primarily used inside IdentitySnapshot and RoleDetection .

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.EntitlementSnapshot`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `Certifiable`
- `Entitlements`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.Object clone ()`
- `EntitlementSnapshot convertToSnapshot ()`
- `Entitlements create (java.util.List< Permission > perms, Attributes <java.lang.String,java.lang.Object> attrs)`
- `Certification.EntitlementGranularity estimateGranularity ()`
- `java.lang.String generateAccountKey ()`
- `java.lang.String getApplication ()`
- `java.lang.String getApplicationName ()`
- `Application getApplicationObject ( Resolver resolver)`
- `static java.util.Collection<java.lang.String> getApplications (java.util.Collection< EntitlementSnapshot > snaps)`
- `java.lang.String getAttributeName ()`
- `java.util.List<java.lang.String> getAttributeNames ()`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.Object getAttributeValue ()`
- `java.util.List<java.lang.Object> getAttributeValues ()`
- `java.lang.String getDisplayableName ()`
- `java.lang.String getDisplayName ()`
- `java.lang.String getId ()`
- `java.lang.String getInstance ()`
- `java.lang.String getNativeIdentity ()`
- `java.lang.String getPermissionRight ()`
- `java.lang.String getPermissionRights ()`
- `java.util.List<Permission> getPermissions ()`
- `java.util.List<Permission> getPermissionsByTarget (java.lang.String target)`
- `java.lang.String getPermissionTarget ()`
- `boolean hasAttribute (java.lang.String name, java.lang.String value)`
- `boolean hasAttributes ()`
- `boolean hasPermission (java.lang.String target, java.lang.String right)`
- `boolean hasPermissions ()`
- `boolean isAccountOnly ()`
- `boolean isAttributeGranularity ()`
- `boolean isEmpty ()`
- `boolean isValueGranularity ()`
- `void load ()`
- `boolean referencesLink ( LinkInterface link)`
- `Application resolveApplication ( Resolver r)`
- `void setAccountOnly (boolean accountOnly)`
- `void setApplication (java.lang.String name)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attrs)`
- `void setDisplayName (java.lang.String displayName)`
- `void setId (java.lang.String s)`
- `void setInstance (java.lang.String instance)`
- `void setNativeIdentity (java.lang.String nativeIdentity)`
- `void setPermissions (java.util.List< Permission > permissions)`
- `java.lang.String toString ()`

---

## EntitlementWeight.EntitlementType

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `EntitlementWeight.EntitlementType`
- `sailpoint.object.EntitlementWeight.EntitlementType`
- `java.io.Serializable`
- `java.lang.Comparable<EntitlementWeight.EntitlementType>`

**Attributes:** N/A

**Methods:**
- `staticEntitlementWeight.EntitlementType valueOf (java.lang.String name)`
- `staticEntitlementWeight.EntitlementType[] values ()`

---

## EntitlementWeight

**Package:** `sailpoint.object`

**Description:** An EntitlementWeight holds the weight value of the specified entitlement category.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.EntitlementWeight`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `java.lang.Comparable`

**Attributes:** N/A

**Methods:**
- `java.lang.Object clone ()`
- `int compareTo (java.lang.Object o)`
- `java.lang.String getAttribute ()`
- `java.lang.String getRight ()`
- `java.lang.String getTarget ()`
- `EntitlementWeight.EntitlementType getType ()`
- `java.lang.String getValue ()`
- `java.lang.String getWeight ()`
- `boolean isAttribute ()`
- `boolean isPermission ()`
- `void setTarget (java.lang.String target)`
- `void setType ( EntitlementWeight.EntitlementType type)`
- `void setValue (java.lang.String value)`
- `void setWeight (java.lang.String weight)`

---

## Entitlements

**Package:** `sailpoint.object`

**Description:** This is an interface for an object that maintains a group of entitlements on an application.

**Inherited Classes/Interfaces:**
- `Certifiable`

**Attributes:** N/A

**Methods:**
- `EntitlementSnapshot convertToSnapshot ()`
- `Entitlements create (java.util.List< Permission > perms, Attributes <java.lang.String,java.lang.Object> attrs)`
- `java.lang.String getApplicationName ()`
- `Application getApplicationObject ( Resolver resolver)`
- `java.util.List<java.lang.String> getAttributeNames ()`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getDisplayName ()`
- `java.lang.String getInstance ()`
- `java.lang.String getNativeIdentity ()`
- `java.util.List<Permission> getPermissions ()`
- `boolean isAccountOnly ()`

---

## ExchangeData

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.ExchangeData`

**Attributes:** N/A

**Methods:**
- `java.util.List<java.lang.String> getAccountForestList ()`
- `java.util.List<java.lang.String> getAccountForests ()`
- `java.lang.String getExchangeForest ()`
- `java.util.List<java.lang.String> getExchHost ()`
- `java.lang.String getPassword ()`
- `java.lang.String getUser ()`
- `boolean isUseTLS ()`
- `void setAccountForestList (java.util.List userForestList)`
- `void setExchangeForest (java.lang.String exchangeForest)`
- `void setExchHost (java.util.List exchHostList)`
- `void setPassword (java.lang.String password)`
- `void setUser (java.lang.String user)`
- `void setUseTLS (boolean useSSL)`

---

## ExpansionItem.Cause

**Package:** `sailpoint.object`

**Description:** An enumeration of reasons for expansion.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ExpansionItem.Cause`
- `sailpoint.object.ExpansionItem.Cause`
- `java.io.Serializable`
- `java.lang.Comparable<ExpansionItem.Cause>`

**Attributes:** N/A

**Methods:**
- `staticExpansionItem.Cause valueOf (java.lang.String name)`
- `staticExpansionItem.Cause[] values ()`

---

## ExpansionItem

**Package:** `sailpoint.object`

**Description:** An ExpansionItem contains information about why a value was expanded in a provisioning plan as a result of plan compilation. This contains information that identifies the expanded value (application, native identity, name, value, etc...) and information about the expansion (why did it happen).

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.AccountItem`
- `sailpoint.object.IdentityItem`
- `sailpoint.object.ExpansionItem`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `boolean equals (java.lang.Object o)`
- `ExpansionItem.Cause getCause ()`
- `ProvisioningPlan.Operation getOperation ()`
- `java.lang.String getSourceInfo ()`
- `int hashCode ()`
- `boolean isSyncUsingWorkflow ()`
- `void setCause ( ExpansionItem.Cause cause)`
- `void setOperation ( ProvisioningPlan.Operation operation)`
- `void setSourceInfo (java.lang.String sourceInfo)`
- `void setSyncUsingWorkflow (boolean syncUsingWorkflow)`

---

## ExtState

**Package:** `sailpoint.object`

**Description:** An ExtState holds information about how an ext-based component should be displayed. This is used when transitioning in the UI to remember how an ext-based component was previously displayed so it can be displayed in the same manner again when the user comes back to the page in which the component was shown. This is used in conjunction with the SailPoint.State javascript object by converting this object to JSON and passing the JSON-created object to the SailPoint.State.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ExtState`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getName ()`
- `java.lang.String getState ()`
- `void setName (java.lang.String name)`
- `void setState (java.lang.String state)`

---

## ExtendedAttributeConfig

**Package:** `sailpoint.object`

**Description:** Deprecated.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.ExtendedAttributeConfig`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.util.List<IdentityAttribute> getAttributes ()`
- `void setAttributes (java.util.List< IdentityAttribute > atts)`

---

## ExternalAttribute

**Package:** `sailpoint.object`

**Description:** Class used to represent a multi-valued extended attribute. Single valued extended attributes are stored as columns in the associated class table, multi-valued attributes have to be stored in a different table.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.ExternalAttribute`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.Object clone ()`
- `java.lang.String getAttributeName ()`
- `java.lang.String getObjectId ()`
- `java.lang.String getValue ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `void setAttributeName (java.lang.String name)`
- `void setObjectId (java.lang.String objId)`
- `void setValue (java.lang.String value)`

---

## Field.ApplicationDependency

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Field.ApplicationDependency`

**Attributes:** N/A

**Methods:**
- `java.lang.String getApplicationName ()`
- `java.lang.String getSchemaAttributeName ()`
- `void setApplicationName (java.lang.String _applicationName)`
- `void setSchemaAttributeName (java.lang.String _schemaAttributeName)`

---

## Field

**Package:** `sailpoint.object`

**Description:** The name of a field that when used in account creation templates will specify the native identity of the new account.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.BaseAttributeDefinition`
- `sailpoint.object.Field`
- `java.io.Serializable`
- `FormItem`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String ACCOUNT_ID`
- `static java.lang.String ATT_IGNORED`
- `static java.lang.String ATT_OPERATION`
- `static java.lang.String ATT_SCRIPT_ARGS`
- `static java.lang.String ATTR_EXTRA_RECS`
- `static java.lang.String ATTR_HIDDEN`
- `static java.lang.String ATTR_READ_ONLY`
- `static java.lang.String ATTR_VALUE_OBJ_COLUMN`
- `static java.lang.String ATTR_VALUE_PROPERTY`
- `static java.lang.String ATTR_VALUE_PROPERTY_NAME`
- `static java.lang.String DISPLAY_TYPE_CHECKBOX`
- `static java.lang.String DISPLAY_TYPE_COMBOBOX`
- `static java.lang.String DISPLAY_TYPE_LABEL`
- `static java.lang.String DISPLAY_TYPE_RADIO`
- `static java.lang.String DISPLAY_TYPE_TEXTAREA`
- `static java.lang.String FORMAT_CSV`
- `static java.lang.String NULL_CONST`
- `static java.lang.String OWNER_REQUESTER`
- `static java.lang.String RENDER_END_DATE`
- `static java.lang.String RENDER_SHOW_TIME`
- `static java.lang.String RENDER_USE_SELECT_BOX`
- `static java.lang.String TYPE_APPLICATION_ATTR`
- `static java.lang.String TYPE_MANAGED_ATTR`
- `static java.lang.String TYPE_ROLE_ATTR`

**Methods:**
- `void addAttribute (java.lang.String name, java.lang.Object value)`
- `static java.lang.Object convertSimpleTypeValue (java.lang.String type, java.lang.Object value)`
- `static java.lang.Object convertSimpleTypeValue (java.lang.String type, java.lang.Object value, java.util.TimeZone userTimeZone)`
- `boolean equals (java.lang.Object o)`
- `DynamicValue getAllowedValuesDefinition ()`
- `Field.ApplicationDependency getAppDependency ()`
- `java.lang.String getApplication ()`
- `java.lang.Object getAttribute (java.lang.String attribute)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `boolean getBooleanAttribute (java.lang.String name)`
- `int getColumnSpan ()`
- `java.lang.String getDependencies ()`
- `java.util.List<java.lang.String> getDependencyList ()`
- `java.lang.String getDisplayLabel ()`
- `java.lang.String getDisplayType ()`
- `Rule getFieldRule ()`
- `java.lang.String getFilterString ()`
- `java.lang.String getFormat ()`
- `java.lang.String getHelpKey ()`
- `DynamicValue getHiddenDefinition ( Resolver r)`
- `java.lang.String getInputTemplate ()`
- `java.lang.String getNormalizedType ()`
- `java.lang.String getOriginalName ()`
- `DynamicValue getOwnerDefinition ()`
- `Script getOwnerScriptXml ()`
- `java.lang.String getPrefix ()`
- `java.lang.Object getPreviousValue ()`
- `int getPriority ()`
- `java.lang.String getPrompt ()`
- `DynamicValue getReadOnlyDefinition ( Resolver r)`
- `java.lang.String getRole ()`
- `Rule getRule ()`
- `Script getScript ()`
- `java.util.Map<java.lang.String,​java.lang.Object> getScriptArguments ()`
- `java.lang.String getSection ()`
- `java.lang.String getStringAttribute (java.lang.String name)`
- `java.lang.String getTemplate ()`
- `java.lang.Class getTypeClass ()`
- `java.lang.String getUnqualifiedName ()`
- `Rule getValidationRule ()`
- `Script getValidationScript ()`
- `java.lang.Object getValue ()`
- `DynamicValue getValueDefinition ()`
- `boolean isAllowed (java.lang.Object value)`
- `boolean isAllowedValuesDynamic ()`
- `boolean isAuthoritative ()`
- `boolean isDisplayOnly ()`
- `boolean isDynamic ()`
- `boolean isHidden ()`
- `boolean isIncomplete ()`
- `boolean isPermission ()`
- `boolean isPostBack ()`
- `boolean isReadOnly ()`
- `boolean isReviewRequired ()`
- `boolean isSortable ()`
- `boolean isXmlAllowedValuesDynamic ()`
- `void load ()`
- `java.lang.String qualifyName (java.lang.String prefix, java.lang.String name)`
- `void setAllowedValuesDefinition ( DynamicValue def)`
- `void setAllowedValuesDynamic (boolean b)`
- `void setAppDependency (java.lang.String appName, java.lang.String schemaAtt)`
- `void setAppDependency ( Field.ApplicationDependency _appDependency)`
- `void setApplication (java.lang.String s)`
- `void setAttribute (java.lang.String attribute, java.lang.Object value)`
- `void setAttributeDynamicValue (java.lang.String attribute, DynamicValue dv)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attributes)`
- `void setAuthoritative (boolean b)`
- `void setColumnSpan (int columnSpan)`
- `void setDependencies (java.lang.String s)`
- `void setDisplayOnly (boolean val)`
- `void setDisplayType (java.lang.String displayType)`
- `void setDynamic (boolean b)`
- `void setFieldRule ( Rule rule)`
- `void setFilterString (java.lang.String s)`
- `void setFormat (java.lang.String format)`
- `void setHelpKey (java.lang.String s)`
- `void setHidden (boolean hidden)`
- `void setHiddenDefinition ( DynamicValue hidden)`
- `void setIncomplete (boolean b)`
- `void setInputTemplate (java.lang.String inputTemplate)`
- `void setNormalizedType (java.lang.String type)`
- `void setOriginalName (java.lang.String val)`
- `void setOwnerDefinition ( DynamicValue def)`
- `void setOwnerScript ( Script s)`
- `void setOwnerScriptXml ( Script s)`
- `void setPermission (boolean b)`
- `void setPostBack (boolean postBack)`
- `void setPreviousValue (java.lang.Object value)`
- `void setPriority (int p)`
- `void setPrompt (java.lang.String s)`
- `void setReadOnly (boolean readOnly)`
- `void setReadOnlyDefinition ( DynamicValue readOnly)`
- `void setReviewRequired (boolean required)`
- `void setRole (java.lang.String s)`
- `void setRule ( Rule rule)`
- `void setScript ( Script s)`
- `void setScriptArguments (java.util.Map<java.lang.String,java.lang.Object> args)`
- `void setSection (java.lang.String s)`
- `void setSortable (boolean sortable)`
- `void setTemplate (java.lang.String s)`
- `void setValidationRule ( Rule rule)`
- `void setValidationScript ( Script validationScript)`
- `void setValue (java.lang.Object value)`
- `void setValueDefinition ( DynamicValue dv)`
- `void setXmlAllowedValuesDynamic (boolean b)`

---

## FileBucket

**Package:** `sailpoint.object`

**Description:** Chunk of a file written to the database. For larger files, break them up into FileBuckets so that they can be read into and out of the database efficiently.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.FileBucket`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `byte[] getData ()`
- `int getFileIndex ()`
- `PersistedFile getParent ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `void setData (byte[] data)`
- `void setFileIndex (int fileIndex)`
- `void setParent ( PersistedFile parent)`

---

## Filter.BaseFilterVisitor

**Package:** `sailpoint.object`

**Description:** Base implementation of a FilterVisitor that throws unsupported exceptions for all operations.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Filter.BaseFilterVisitor`
- `Filter.FilterVisitor`

**Attributes:** N/A

**Methods:**
- `void visitAnd ( Filter.CompositeFilter filter)`
- `void visitCollectionCondition ( Filter.LeafFilter filter)`
- `void visitContainsAll ( Filter.LeafFilter filter)`
- `void visitEQ ( Filter.LeafFilter filter)`
- `void visitGE ( Filter.LeafFilter filter)`
- `void visitGT ( Filter.LeafFilter filter)`
- `void visitIn ( Filter.LeafFilter filter)`
- `void visitIsEmpty ( Filter.LeafFilter filter)`
- `void visitIsNull ( Filter.LeafFilter filter)`
- `void visitJoin ( Filter.LeafFilter filter)`
- `void visitLE ( Filter.LeafFilter filter)`
- `void visitLeftJoin ( Filter.LeafFilter filter)`
- `void visitLike ( Filter.LeafFilter filter)`
- `void visitLT ( Filter.LeafFilter filter)`
- `void visitNE ( Filter.LeafFilter filter)`
- `void visitNot ( Filter.CompositeFilter filter)`
- `void visitNotNull ( Filter.LeafFilter filter)`
- `void visitOr ( Filter.CompositeFilter filter)`
- `void visitSubquery ( Filter.LeafFilter filter)`

---

## Filter.BooleanOperation

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Filter.BooleanOperation`
- `sailpoint.object.Filter.BooleanOperation`
- `java.io.Serializable`
- `java.lang.Comparable<Filter.BooleanOperation>`

**Attributes:** N/A

**Methods:**
- `staticFilter.BooleanOperation valueOf (java.lang.String name)`
- `staticFilter.BooleanOperation[] values ()`

---

## Filter.CompositeFilter

**Package:** `sailpoint.object`

**Description:** Shallow copy for the optimizer.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Filter`
- `sailpoint.object.Filter.CompositeFilter`
- `java.io.Serializable`
- `sailpoint.tools.xml.IXmlEqualable<Filter>`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void accept ( Filter.FilterVisitor visitor)`
- `void add ( Filter child)`
- `java.util.List<Filter> getChildren ()`
- `java.lang.String getExpression ()`
- `Filter.BooleanOperation getOperation ()`
- `void setChildren (java.util.List< Filter > children)`
- `void setOperation ( Filter.BooleanOperation op)`
- `java.lang.String toString ()`

---

## Filter.FilterCompiler.IdentitiferLookAhead

**Package:** `sailpoint.object`

**Description:** Identifiers can have ambiguity because they can contain spaces. To figure out if a space should be a part of the identifier or not, look ahead to see if the next part of the string is something we expect in the grammar after an identifier - either a dot (for a dotted property), a parenthesis (when using an identifier as a function name), or an operator.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.Parser.BaseLookAhead`
- `sailpoint.object.Filter.FilterCompiler.IdentitiferLookAhead`
- `sailpoint.tools.Parser.LookAhead`

**Attributes:** N/A

**Methods:**
- `boolean continueParsingInternal (sailpoint.tools.Parser p)`
- `boolean isAmbiguous (char c)`

---

## Filter.FilterCompiler

**Package:** `sailpoint.object`

**Description:** A compiler that can create a Filter from a string representation using the following grammar (note the Java-like syntax): String literals should have double-quotes. true/false are treated as boolean literals digits are treated as numbers the string value 'null' (no quotes) is treated as null fully-qualified constants are resolved to enums everything else is assumed to be the property name Leafs: Any comparison operator can be prepended with an 'i' to signify a case-insensitive comparison (for example - i==, i!=, etc...). EQ - propertyName == value NE - propertyName != value LT - propertyName < value GT - propertyName > value LE - propertyName <= value GE - propertyName >= value IN - propertyName.in({ "foo", "bar", "baz" }) (or inIgnoreCase()) CONTAINS_ALL - propertyName.containsAll({ "foo", "bar", "baz" }) (or containsAllIgnoreCase()) ISNULL - propertyName.isNull() NOTNULL - propertyName.notNull() ISEMPTY - propertyName.isEmpty() LIKE - EXACT - propertyName == value - START - propertyName.startsWith(value) (or startsWithIgnoreCase()) - END - propertyName.endsWith(value) (or endsWithIgnoreCase()) - ANYWHERE - propertyName.contains(value) (or containsIgnoreCase()) JOIN - propertyName.join(ClassName.propertyName) LEFT_JOIN - propertyName.leftJoin(ClassName.propertyName) COLLECTION_CONDITION - propertyName.collectionCondition("fooProp == \"bar\"") Note that the parameter to collectionCondition() is the string representation (with quotes escaped) of the collection element filter. SUBQUERY propertyName.subquery("firstname", sailpoint.object.Bundle, "name", "riskScoreWeight > 500"); A subquery takes the following parameters: - property - subquery class - subquery property - subquery filter: Either a string representation of a filter (with quotes escaped) or null. Composites: AND - (expr && expr) OR - (expr || expr) NOT - !(expr) .

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Filter.FilterCompiler`

**Attributes:** N/A

**Methods:**
- `Filter compileFilter (java.lang.String filter)`

---

## Filter.FilterVisitor

**Package:** `sailpoint.object`

**Description:** Visitor interface that is accepted by filters to perform various operations. It is the responsibility of the visitor implementation to iterate through children on composite operations.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `void visitAnd ( Filter.CompositeFilter filter)`
- `void visitCollectionCondition ( Filter.LeafFilter filter)`
- `void visitContainsAll ( Filter.LeafFilter filter)`
- `void visitEQ ( Filter.LeafFilter filter)`
- `void visitGE ( Filter.LeafFilter filter)`
- `void visitGT ( Filter.LeafFilter filter)`
- `void visitIn ( Filter.LeafFilter filter)`
- `void visitIsEmpty ( Filter.LeafFilter filter)`
- `void visitIsNull ( Filter.LeafFilter filter)`
- `void visitJoin ( Filter.LeafFilter filter)`
- `void visitLE ( Filter.LeafFilter filter)`
- `void visitLeftJoin ( Filter.LeafFilter filter)`
- `void visitLike ( Filter.LeafFilter filter)`
- `void visitLT ( Filter.LeafFilter filter)`
- `void visitNE ( Filter.LeafFilter filter)`
- `void visitNot ( Filter.CompositeFilter filter)`
- `void visitNotNull ( Filter.LeafFilter filter)`
- `void visitOr ( Filter.CompositeFilter filter)`
- `void visitSubquery ( Filter.LeafFilter filter)`

---

## Filter.LeafFilter

**Package:** `sailpoint.object`

**Description:** Shallow copy for the optimizer.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Filter`
- `sailpoint.object.Filter.LeafFilter`
- `java.io.Serializable`
- `sailpoint.tools.xml.IXmlEqualable<Filter>`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void accept ( Filter.FilterVisitor visitor)`
- `java.lang.String getCast ()`
- `Filter.CompositeFilter getCollectionCondition ()`
- `java.lang.String getExpression ()`
- `java.lang.String getJoinProperty ()`
- `Filter.MatchMode getMatchMode ()`
- `java.lang.String getMatchModeString (java.lang.String value, java.lang.String wild)`
- `Filter.LogicalOperation getOperation ()`
- `java.lang.String getProperty ()`
- `java.lang.Class<?> getSubqueryClass ()`
- `Filter getSubqueryFilter ()`
- `java.lang.String getSubqueryProperty ()`
- `java.lang.Object getValue ()`
- `java.lang.String getValueXMLAttribute ()`
- `java.lang.Object getValueXMLElement ()`
- `boolean isIgnoreCase ()`
- `void setCast (java.lang.String _cast)`
- `void setCollectionCondition ( Filter.CompositeFilter filter)`
- `void setIgnoreCase (boolean ignoreCase)`
- `void setJoinProperty (java.lang.String joinProperty)`
- `void setMatchMode ( Filter.MatchMode mm)`
- `void setOperation ( Filter.LogicalOperation op)`
- `void setProperty (java.lang.String property)`
- `void setSubqueryClass (java.lang.Class<?> clazz)`
- `void setSubqueryFilter ( Filter filter)`
- `void setSubqueryProperty (java.lang.String property)`
- `void setValue (java.lang.Object val)`
- `void setValueXMLAttribute (java.lang.String value)`
- `void setValueXMLElement (java.lang.Object value)`
- `java.lang.String toString ()`

---

## Filter.LogicalOperation

**Package:** `sailpoint.object`

**Description:** Apply a filter to elements of a collection.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Filter.LogicalOperation`
- `sailpoint.object.Filter.LogicalOperation`
- `java.io.Serializable`
- `java.lang.Comparable<Filter.LogicalOperation>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getDisplayName ()`
- `Filter.LogicalOperation getInverseOperation ()`
- `java.lang.String getStringRepresentation ()`
- `staticFilter.LogicalOperation valueOf (java.lang.String name)`
- `staticFilter.LogicalOperation[] values ()`

---

## Filter.MatchMode

**Package:** `sailpoint.object`

**Description:** An enumeration that describes how to match strings in a 'like' filter.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Filter.MatchMode`
- `sailpoint.object.Filter.MatchMode`
- `java.io.Serializable`
- `java.lang.Comparable<Filter.MatchMode>`

**Attributes:** N/A

**Methods:**
- `abstract java.lang.String toMatchString (java.lang.String value, java.lang.String wildcard)`
- `staticFilter.MatchMode valueOf (java.lang.String name)`
- `staticFilter.MatchMode[] values ()`

---

## Filter

**Package:** `sailpoint.object`

**Description:** A Filter is an abstract class that is used to express boolean logical expressions. The static methods on this class should be considered the public API as they are the most straight-forward to use when constructing query filters. Note that Filter.toExpression() can be fed back into Filter.compile(String) to reconstruct a filter. The inner classes are public, but are typically only used in an SPI to convert Filters into consumer-specific queries (for example - an LDAP filter string).

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Filter`
- `java.io.Serializable`
- `sailpoint.tools.xml.IXmlEqualable<Filter>`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `abstract void accept ( Filter.FilterVisitor visitor)`
- `staticFilter and (java.util.List< Filter > children)`
- `staticFilter and ( Filter ... children)`
- `staticFilter and ( Filter filter1, Filter filter2)`
- `staticFilter clone ( Filter src)`
- `staticFilter collectionCondition (java.lang.String collectionProperty, Filter compoundFilter)`
- `staticFilter compile (java.lang.String filter)`
- `staticFilter contains (java.lang.String propertyName, java.lang.Object value)`
- `staticFilter containsAll (java.lang.String propertyName, java.util.Collection value)`
- `boolean contentEquals ( Filter other)`
- `staticFilter eq (java.lang.String propertyName, java.lang.Object value)`
- `boolean equals (java.lang.Object o)`
- `staticFilter fromExample (java.lang.Object o)`
- `staticFilter ge (java.lang.String propertyName, java.lang.Object value)`
- `abstract java.lang.String getExpression ()`
- `java.lang.String getExpression (boolean readable)`
- `staticFilter gt (java.lang.String propertyName, java.lang.Object value)`
- `int hashCode ()`
- `staticFilter ignoreCase ( Filter filter)`
- `staticFilter in (java.lang.String propertyName, java.util.Collection<?> value)`
- `staticFilter isempty (java.lang.String propertyName)`
- `staticFilter isnull (java.lang.String propertyName)`
- `staticFilter join (java.lang.String property, java.lang.String joinProperty)`
- `staticFilter le (java.lang.String propertyName, java.lang.Object value)`
- `staticFilter leftJoin (java.lang.String property, java.lang.String joinProperty)`
- `staticFilter like (java.lang.String propertyName, java.lang.Object value)`
- `staticFilter like (java.lang.String propertyName, java.lang.Object value, Filter.MatchMode matchMode)`
- `staticFilter lt (java.lang.String propertyName, java.lang.Object value)`
- `staticFilter ne (java.lang.String propertyName, java.lang.Object value)`
- `staticFilter not ( Filter filter)`
- `staticFilter notnull (java.lang.String propertyName)`
- `staticFilter or (java.util.List< Filter > children)`
- `staticFilter or ( Filter ... children)`
- `staticFilter or ( Filter filter1, Filter filter2)`
- `staticFilter subquery (java.lang.String property, java.lang.Class<?> subqueryClass, java.lang.String subqueryProperty, Filter subqueryFilter)`

---

## FilterRenderer

**Package:** `sailpoint.object`

**Description:** A FilterVisitor that renders the filter as a SQL-like string. This is an alternative to the Filter.toString representation which is more Java-like. The intention is that this be used whenever you have to display a read-only summary of the filter, such as in approval work items. The syntax should more closely resemble what is shown in the modeler.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.FilterRenderer`
- `Filter.FilterVisitor`

**Attributes:** N/A

**Methods:**
- `java.lang.String render ()`
- `java.lang.String render ( Filter f)`
- `void visitAnd ( Filter.CompositeFilter filter)`
- `void visitCollectionCondition ( Filter.LeafFilter filter)`
- `void visitContainsAll ( Filter.LeafFilter filter)`
- `void visitEQ ( Filter.LeafFilter filter)`
- `void visitGE ( Filter.LeafFilter filter)`
- `void visitGT ( Filter.LeafFilter filter)`
- `void visitIn ( Filter.LeafFilter filter)`
- `void visitIsEmpty ( Filter.LeafFilter filter)`
- `void visitIsNull ( Filter.LeafFilter filter)`
- `void visitJoin ( Filter.LeafFilter filter)`
- `void visitLE ( Filter.LeafFilter filter)`
- `void visitLeftJoin ( Filter.LeafFilter filter)`
- `void visitLike ( Filter.LeafFilter filter)`
- `void visitLT ( Filter.LeafFilter filter)`
- `void visitNE ( Filter.LeafFilter filter)`
- `void visitNot ( Filter.CompositeFilter filter)`
- `void visitNotNull ( Filter.LeafFilter filter)`
- `void visitOr ( Filter.CompositeFilter filter)`
- `void visitSubquery ( Filter.LeafFilter filter)`

---

## ForestData

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.ForestData`

**Attributes:**
- `static java.lang.String AUTH_TYPE_SIMPLE`
- `static java.lang.String GC_DEFAULT_PORT`
- `static java.lang.String GC_SSL_PORT`

**Methods:**
- `boolean getAuthEnabled ()`
- `java.lang.String getAuthenticationType ()`
- `java.lang.String getAuthType ()`
- `java.lang.String getForestName ()`
- `java.lang.String getGcServer ()`
- `boolean getIsResourceForest ()`
- `java.lang.String getPassword ()`
- `boolean getTlsEnabled ()`
- `java.lang.String getUseGroupMembershipPreloading ()`
- `java.lang.String getUser ()`
- `boolean isEnablePasswordLessAuthentication ()`
- `boolean isManageAllDomain ()`
- `boolean isPreviewDomains ()`
- `boolean isUseSSL ()`
- `void setAuthEnabled (boolean authEnabled)`
- `void setAuthenticationType (java.lang.String authType)`
- `void setAuthType (java.lang.String authType)`
- `void setEnablePasswordLessAuthentication (boolean enablePasswordLessAuthentication)`
- `void setForestName (java.lang.String forestName)`
- `void setGcServer (java.lang.String gcServer)`
- `void setIsResourceForest (boolean _isResourceForest)`
- `void setManageAllDomain (boolean manageAllDomain)`
- `void setPassword (java.lang.String password)`
- `void setPreviewDomains (boolean previewDomains)`
- `void setTlsEnabled (boolean tlsEnabled)`
- `void setUseGroupMembershipPreloading (java.lang.String useGroupMembershipPreloading)`
- `void setUser (java.lang.String userName)`
- `void setUseSSL (boolean useSSL)`

---

## Form.Button

**Package:** `sailpoint.object`

**Description:** Need to have a priority to be a FormItem but button order is not determined by this.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Form.Button`
- `FormItem`

**Attributes:** N/A

**Methods:**
- `java.lang.String getAction ()`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getLabel ()`
- `java.lang.String getParameter ()`
- `int getPriority ()`
- `boolean getSkipValidation ()`
- `java.lang.String getValue ()`
- `boolean hasSameAction ( Form.Button otherButton)`
- `boolean isClicked ()`
- `boolean isReadOnly ()`
- `void load ()`
- `void setAction (java.lang.String s)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> atts)`
- `void setClicked (boolean clicked)`
- `void setLabel (java.lang.String s)`
- `void setParameter (java.lang.String s)`
- `void setReadOnly (boolean b)`
- `void setSkipValidation (boolean b)`
- `void setValue (java.lang.String s)`

---

## Form.FieldIterator

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Form.FieldIterator`
- `java.util.Iterator<Field>`

**Attributes:** N/A

**Methods:**
- `boolean hasNext ()`
- `Field next ()`
- `void remove ()`

---

## Form.Section

**Package:** `sailpoint.object`

**Description:** Forms use sections to organize sets of fields. In theory sections can contain subsections to define layout, not using that yet. The model and Formicator support nested fields but the editor and renderer do not.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Form.Section`
- `java.io.Serializable`
- `FormItem`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String ATT_HIDDEN`
- `static java.lang.String ATT_HIDE_NULLS`
- `static java.lang.String ATT_READ_ONLY`
- `static java.lang.String ATT_SUBTITLE`
- `static java.lang.String TYPE_DATA_TABLE`
- `static java.lang.String TYPE_TEXT`

**Methods:**
- `void add ( FormItem item)`
- `void addAttribute (java.lang.String attr, java.lang.Object value)`
- `void append ( FormItem item)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `int getColumns ()`
- `Field getField (java.lang.String name)`
- `java.util.List<Field> getFields ()`
- `DynamicValue getHiddenDefinition ( Resolver r)`
- `DynamicValue getHideNullsDefinition ( Resolver r)`
- `java.util.List<FormItem> getItems ()`
- `java.lang.String getLabel ()`
- `java.lang.String getLayout ()`
- `java.lang.String getName ()`
- `int getPriority ()`
- `DynamicValue getReadOnlyDefinition ( Resolver r)`
- `java.lang.String getSubtitle ()`
- `java.lang.String getType ()`
- `boolean hasFields ()`
- `boolean hideNulls ()`
- `boolean isHidden ()`
- `boolean isInteractive ()`
- `boolean isWrapper ()`
- `void load ()`
- `void put (java.lang.String name, java.lang.Object value)`
- `void setAttributeDynamicValue (java.lang.String attribute, DynamicValue dv)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attributes)`
- `void setColumns (int columns)`
- `void setHiddenDefinition ( DynamicValue hidden)`
- `void setHideNullsDefinition ( DynamicValue hidden)`
- `void setItems (java.util.List< FormItem > l)`
- `void setLabel (java.lang.String s)`
- `void setLayout (java.lang.String s)`
- `void setName (java.lang.String s)`
- `void setPriority (int p)`
- `void setReadOnlyDefinition ( DynamicValue readOnly)`
- `void setSubtitle (java.lang.String val)`
- `void setType (java.lang.String s)`

---

## Form.Type

**Package:** `sailpoint.object`

**Description:** Form types

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Form.Type`
- `sailpoint.object.Form.Type`
- `java.io.Serializable`
- `java.lang.Comparable<Form.Type>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticForm.Type valueOf (java.lang.String name)`
- `staticForm.Type[] values ()`

---

## Form.Usage

**Package:** `sailpoint.object`

**Description:** An enumeration of usage constants for for application forms.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Form.Usage`
- `sailpoint.object.Form.Usage`
- `java.io.Serializable`
- `java.lang.Comparable<Form.Usage>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticForm.Usage valueOf (java.lang.String name)`
- `staticForm.Usage[] values ()`

---

## Form

**Package:** `sailpoint.object`

**Description:** Forms use sections to organize sets of fields.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Form`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ACTION_BACK`
- `static java.lang.String ACTION_CANCEL`
- `static java.lang.String ACTION_NEXT`
- `static java.lang.String ACTION_REFRESH`
- `static java.lang.String ATT_HIDE_INCOMPLETE_FIELDS`
- `static java.lang.String ATT_IIQ_TEMPLATE_APPLICATION`
- `static java.lang.String ATT_IIQ_TEMPLATE_OWNER_DEFINITION`
- `static java.lang.String ATT_INCLUDE_HIDEN_FIELDS`
- `static java.lang.String ATT_MERGE_PROFILES`
- `static java.lang.String ATT_PAGE_TITLE`
- `static java.lang.String ATT_PAGE_TITLE_PARAM`
- `static java.lang.String ATT_READ_ONLY`
- `static java.lang.String ATT_SUBTITLE`
- `static java.lang.String ATT_TITLE`
- `static java.lang.String ATT_WIZARD`
- `static java.lang.String OWNER_APPLICATION`
- `static java.lang.String OWNER_PARENT`
- `static java.lang.String OWNER_ROLE`

**Methods:**
- `void add (java.util.List< FormItem > items)`
- `void add ( FormItem item)`
- `void addButtons (java.util.List< Form.Button > buttons)`
- `void clearButtons ()`
- `void clearFieldMap ()`
- `Form.Usage convertFormType ( Form.Type type)`
- `static java.util.List<Form> convertTemplates (java.util.List< Template > templates)`
- `Form.Type convertUsage ( Form.Usage usage)`
- `staticForm.Type convertUsage ( Template.Usage usage)`
- `java.lang.Object get (java.lang.String name)`
- `Application getApplication ()`
- `Application getApplication ( Resolver res)`
- `java.lang.String getApplicationId ()`
- `Reference getApplicationRef ()`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getBasePath ()`
- `boolean getBoolean (java.lang.String name)`
- `java.util.List<Form.Button> getButtons ()`
- `Form.Button getClickedButton ()`
- `java.util.List<Field> getEntireFields ()`
- `Field getField (java.lang.String name)`
- `Field getField ( Field peer, java.lang.String name)`
- `java.util.List<Field> getFields ()`
- `java.util.Map<java.lang.String,​java.lang.Object> getFieldValues ()`
- `FormRef getFormRef ()`
- `java.util.List<Form.Button> getHibernateButtons ()`
- `java.lang.String getIdentityFieldName (java.lang.String name)`
- `int getInt (java.lang.String name)`
- `java.util.List<FormItem> getItems ()`
- `java.lang.String getLabelAlign ()`
- `Form.Button getMatchingButton ( Form.Button other)`
- `java.lang.String getObjectType ()`
- `DynamicValue getOwnerDefinition ()`
- `java.lang.String getPageTitle ()`
- `Form.Section getSection ()`
- `Form.Section getSection (int index)`
- `Form.Section getSection (java.lang.String name)`
- `java.util.List<Form.Section> getSections ()`
- `java.lang.String getString (java.lang.String name)`
- `java.lang.String getSubtitle ()`
- `java.lang.String getTargetUser ()`
- `java.lang.String getTitle ()`
- `Form.Type getType ()`
- `boolean hasBasePath ()`
- `boolean hasFields ()`
- `boolean hasWrapperLessFields ()`
- `boolean isHidden ()`
- `boolean isHideIncompleteFields ()`
- `boolean isIncludeHiddenFields ()`
- `boolean isMatch ( Form.Type type, java.lang.String objectType)`
- `boolean isMergeProfiles ()`
- `boolean isReadOnly ()`
- `boolean isType ( Form.Type t)`
- `boolean isWizard ()`
- `boolean isXml ()`
- `java.util.Iterator<Field> iterateFields ()`
- `void load ()`
- `void put (java.lang.String name, boolean b)`
- `void put (java.lang.String name, java.lang.Object value)`
- `void remove ( Form.Button b)`
- `void remove ( Form.Section s)`
- `void removeField (java.lang.String name)`
- `void setApplication ( Application r)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> atts)`
- `void setBasePath (java.lang.String path)`
- `void setButtons (java.util.List< Form.Button > l)`
- `void setFieldValue (java.lang.String fieldName, java.lang.Object value)`
- `void setFormRef ( FormRef ref)`
- `void setHibernateButtons (java.util.List< Form.Button > buttons)`
- `void setHidden (boolean _hidden)`
- `void setHideIncompleteFields (boolean b)`
- `void setIncludeHiddenFields (boolean b)`
- `void setItems (java.util.List< FormItem > items)`
- `void setLabelAlign (java.lang.String align)`
- `void setMergeProfiles (boolean b)`
- `void setObjectType (java.lang.String type)`
- `void setOwnerDefinition ( DynamicValue owner)`
- `void setPageTitle (java.lang.String s)`
- `void setReadOnly (boolean b)`
- `void setRealApplication ( Application r)`
- `void setSections (java.util.List< Form.Section > l)`
- `void setSubtitle (java.lang.String s)`
- `void setTargetUser (java.lang.String s)`
- `void setTitle (java.lang.String s)`
- `void setType ( Form.Type type)`
- `void setWizard (boolean wizard)`

---

## FormItem

**Package:** `sailpoint.object`

**Description:** A number that influences the ordering of fields and sections when assembled into a form for presentation.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `int getPriority ()`
- `void load ()`

---

## FormRef

**Package:** `sailpoint.object`

**Description:** FormRef object to represent referenced form within a template

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.FormRef`
- `java.io.Serializable`
- `FormItem`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getId ()`
- `java.lang.String getIdOrName ()`
- `java.lang.String getName ()`
- `int getPriority ()`
- `void load ()`
- `void setId (java.lang.String refId)`
- `void setName (java.lang.String refName)`

---

## FullTextIndex.FullTextField

**Package:** `sailpoint.object`

**Description:** The definition of a field within the index and how it will be used. Analyzed means that the field will be broken up and indexed for full text search with substring matching. Indexed means that the field will be stored and can be used in filters, but cannot be used with substring matching. Stored means that the field will be returned in the search result, but it cannot be used in full text search or filters. Ignored means that the field may be sent down in an IdentityIQ Filter but it should be ignored.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.FullTextIndex.FullTextField`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getName ()`
- `boolean isAnalyzed ()`
- `boolean isIgnored ()`
- `boolean isIndexed ()`
- `boolean isStored ()`
- `void setAnalyzed (boolean b)`
- `void setIgnored (boolean b)`
- `void setIndexed (boolean b)`
- `void setName (java.lang.String name)`
- `void setStored (boolean b)`

---

## FullTextIndex

**Package:** `sailpoint.object`

**Description:** The definition of a field within the index and how it will be used.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.FullTextIndex`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATT_ANALYZER`
- `static java.lang.String ATT_ANALYZER_CONFIG`
- `static java.lang.String ATT_CLASSES`
- `static java.lang.String ATT_DISABLED`
- `static java.lang.String ATT_FIELDS`
- `static java.lang.String ATT_INCLUDE_DISABLED`
- `static java.lang.String ATT_INCLUDE_TARGETS`
- `static java.lang.String ATT_INDEX_PATH`
- `static java.lang.String ATT_INDEXER`

**Methods:**
- `void addError (java.lang.String s)`
- `void addError (java.lang.Throwable t)`
- `void addError ( Message msg)`
- `void addTransientField ( FullTextIndex.FullTextField field)`
- `boolean doClassUpgrade ()`
- `boolean doFieldUpgrade ()`
- `java.lang.Object get (java.lang.String name)`
- `org.apache.lucene.analysis.Analyzer getAnalyzer ()`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `boolean getBoolean (java.lang.String name)`
- `java.util.List<java.lang.Class<? extendsSailPointObject>> getClasses ()`
- `java.util.List<java.lang.String> getClassNames ()`
- `java.util.Date getDate (java.lang.String name)`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `java.util.List<Message> getErrors ()`
- `FullTextIndex.FullTextField getField (java.lang.String name)`
- `java.util.Map<java.lang.String,​FullTextIndex.FullTextField> getFieldMap ()`
- `java.util.List<FullTextIndex.FullTextField> getFields ()`
- `java.lang.String getIndexerName ()`
- `int getInt (java.lang.String name)`
- `java.util.Date getLastRefresh ()`
- `java.util.List getList (java.lang.String name)`
- `java.lang.String getPath ()`
- `java.lang.String getString (java.lang.String name)`
- `boolean hasAssignedScope ()`
- `boolean isDisabled ()`
- `void put (java.lang.String name, java.lang.Object value)`
- `java.lang.Object remove (java.lang.String name)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> a)`
- `void setClassNames (java.util.List<java.lang.String> classNames)`
- `void setDisabled (boolean b)`
- `void setErrors (java.util.List< Message > errors)`
- `void setFields (java.util.List< FullTextIndex.FullTextField > fields)`
- `void setIndexerName (java.lang.String indexerName)`
- `void setLastRefresh (java.util.Date d)`
- `void setPath (java.lang.String s)`

---

## GenericConstraint

**Package:** `sailpoint.object`

**Description:** A class holding information about a policy constraint used in Entitlement SOD and "advanced" policies.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.BaseConstraint`
- `sailpoint.object.GenericConstraint`
- `java.io.Serializable`
- `PolicyViolation.IPolicyViolationOwnerSource`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `IdentitySelector getLeftSelector ()`
- `IdentitySelector getRightSelector ()`
- `IdentitySelector getSelector (int psn)`
- `java.util.List<IdentitySelector> getSelectors ()`
- `boolean isNameUnique ()`
- `void load ()`
- `void setLeftSelector ( IdentitySelector sel)`
- `void setRightSelector ( IdentitySelector sel)`
- `void setSelector (int psn, IdentitySelector sel)`
- `void setSelectors (java.util.List< IdentitySelector > list)`

---

## GenericIndex

**Package:** `sailpoint.object`

**Description:** The base model for holding scores and statistics. This is the basis for the GroupIndex, Scorecard, and ApplicationScorecard.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.GenericIndex`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `void addItem ( ScoreItem item)`
- `void addItems (java.util.List< ScoreItem > items)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `int getCompositeScore ()`
- `int getScore (java.lang.String name)`
- `java.util.List<ScoreItem> getScoreItems ()`
- `boolean hasName ()`
- `boolean isDifferent ( GenericIndex other)`
- `boolean isIncomplete ()`
- `void reset ()`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> atts)`
- `void setCompositeScore (int i)`
- `void setIncomplete (boolean b)`
- `void setScore (java.lang.String name, int value)`
- `void setScoreItems (java.util.List< ScoreItem > items)`

---

## GridState

**Package:** `sailpoint.object`

**Description:** A GridState holds information about how a grid should be displayed. This is used when transitioning in the UI to remember how a grid was previously displayed so you can go back to the same row in the grid, use the same sorting, etc... This is used in conjunction with the SailPoint.GridState javascript object by converting this object to JSON and passing the JSON-created object to the SailPoint.GridState.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.GridState`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `int getFirstRow ()`
- `java.lang.String getJSON ()`
- `java.lang.String getName ()`
- `int getPageSize ()`
- `int getScrollPosition ()`
- `java.lang.String getSortColumn ()`
- `java.lang.String getSortOrder ()`
- `java.lang.String getState ()`
- `void resetFirstRow ()`
- `void setAttribute (java.lang.String attribute)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attributes)`
- `void setFirstRow (int firstRow)`
- `void setFirstRowXml (int firstRowXml)`
- `void setName (java.lang.String name)`
- `void setPageSize (int pageSize)`
- `void setScrollPosition (int scrollPosition)`
- `void setScrollPositionXml (int scrollPositionXml)`
- `void setSortColumn (java.lang.String sortColumn)`
- `void setSortColumnXml (java.lang.String sortColumnXml)`
- `void setSortOrder (java.lang.String sortOrder)`
- `void setSortOrderXml (java.lang.String sortOrderXml)`
- `void setState (java.lang.String state)`
- `java.lang.String toJSONString ()`

---

## GroupDefinition

**Package:** `sailpoint.object`

**Description:** A class defining a group of identities. These are used for what the UI calls "populations" as well as the groups automatically generated by group factories.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.GroupDefinition`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `GroupFactory getFactory ()`
- `Filter getFilter ()`
- `GroupIndex getIndex ()`
- `java.util.Date getLastRefresh ()`
- `boolean hasName ()`
- `boolean isIndexed ()`
- `boolean isNameUnique ()`
- `boolean isNullGroup ()`
- `boolean isPrivate ()`
- `void setFactory ( GroupFactory f)`
- `void setFilter ( Filter f)`
- `void setIndex ( GroupIndex i)`
- `void setIndexed (boolean b)`
- `void setLastRefresh (java.util.Date d)`
- `void setNullGroup (boolean b)`
- `void setPrivate (boolean p)`
- `void visit ( Visitor v)`

---

## GroupFactory

**Package:** `sailpoint.object`

**Description:** A class defining a method for generating In the ui these are displayed as "identity group types". Group types are defined by selecting an identity attribute whose values will be the names of the materialized groups. The groups are materialized as instances of the GroupDefinition class. Note that you might also have GroupDefinition objects that are not affiliated with a GroupFactory. These are "singleton" groups also known as "Interesting Populations of People" commonly abbreviated to IPOPs.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.GroupFactory`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.String getFactoryAttribute ()`
- `Rule getGroupOwnerRule ()`
- `java.util.Date getLastRefresh ()`
- `boolean isEnabled ()`
- `void setEnabled (boolean b)`
- `void setFactoryAttribute (java.lang.String s)`
- `void setGroupOwnerRule ( Rule rule)`
- `void setLastRefresh (java.util.Date d)`
- `void visit ( Visitor v)`

---

## GroupIndex

**Package:** `sailpoint.object`

**Description:** A class containing statistics about a group of identities.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.GenericIndex`
- `sailpoint.object.BaseIdentityIndex`
- `sailpoint.object.GroupIndex`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static int MAX_BANDS`

**Methods:**
- `void accumulate ( BaseIdentityIndex other, java.util.List< ScoreBandConfig > bands)`
- `void assimilate ( GroupIndex src)`
- `void average ()`
- `int getBand (int index)`
- `int getBand1 ()`
- `int getBand10 ()`
- `int getBand2 ()`
- `int getBand3 ()`
- `int getBand4 ()`
- `int getBand5 ()`
- `int getBand6 ()`
- `int getBand7 ()`
- `int getBand8 ()`
- `int getBand9 ()`
- `int getBandCount ()`
- `int getCertificationsDue ()`
- `int getCertificationsOnTime ()`
- `GroupDefinition getDefinition ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `int getMemberCount ()`
- `boolean hasName ()`
- `void incCertificationsDue ()`
- `void incCertificationsOnTime ()`
- `boolean isDifferent ( GroupIndex other)`
- `boolean isNameUnique ()`
- `void reset ()`
- `void setBand (int index, int value)`
- `void setBand1 (int i)`
- `void setBand10 (int i)`
- `void setBand2 (int i)`
- `void setBand3 (int i)`
- `void setBand4 (int i)`
- `void setBand5 (int i)`
- `void setBand6 (int i)`
- `void setBand7 (int i)`
- `void setBand8 (int i)`
- `void setBand9 (int i)`
- `void setBandCount (int i)`
- `void setCertificationsDue (int certificationsDue)`
- `void setCertificationsOnTime (int certificationsOnTime)`
- `void setDefinition ( GroupDefinition def)`
- `void setMemberCount (int i)`
- `void visit ( Visitor v)`

---

## GroupScopeData

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.GroupScopeData`

**Attributes:** N/A

**Methods:**
- `java.lang.String getIterateSearchFilter ()`
- `java.lang.String getObjectType ()`
- `java.lang.String getSearchDN ()`
- `java.lang.String getSearchScope ()`
- `void setIterateSearchFilter (java.lang.String iterateSearchFilter)`
- `void setObjectType (java.lang.String objectType)`
- `void setSearchDN (java.lang.String searchDN)`
- `void setSearchScope (java.lang.String searchScope)`

---

## ITRoleMiningTaskResult.EntitlementStatistics

**Package:** `sailpoint.object`

**Description:** Get the number of identities that matches this entitlement group exactly

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.ITRoleMiningTaskResult.EntitlementStatistics`

**Attributes:** N/A

**Methods:**
- `void addExactMatch ()`
- `void addSuperMatches (int numSuperMatches)`
- `int getExactMatches ()`
- `int getSuperMatches ()`

---

## ITRoleMiningTaskResult.SimplifiedEntitlement

**Package:** `sailpoint.object`

**Description:** Constructor used to represent an entitlement attribute value

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.ITRoleMiningTaskResult.SimplifiedEntitlement`

**Attributes:** N/A

**Methods:**
- `boolean equals (java.lang.Object obj)`
- `java.lang.String getAnnotation ()`
- `java.lang.String getApplicationId ()`
- `java.lang.String getApplicationName ()`
- `java.lang.String getDisplayId ()`
- `java.lang.String getDisplayName ()`
- `java.lang.String getInstance ()`
- `java.lang.String getNameOrTarget ()`
- `java.lang.String getRightOrValue ()`
- `java.lang.String getTooltip ()`
- `int hashCode ()`
- `boolean isPermission ()`
- `java.lang.String toString ()`

---

## ITRoleMiningTaskResult.SimplifiedEntitlementsKey

**Package:** `sailpoint.object`

**Description:** Add a link

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.ITRoleMiningTaskResult.SimplifiedEntitlementsKey`

**Attributes:** N/A

**Methods:**
- `void addLink ( Link link, java.util.Set< ITRoleMiningTaskResult.SimplifiedEntitlement > entitlements, boolean isExcluded)`
- `boolean equals (java.lang.Object obj)`
- `java.util.Set<ITRoleMiningTaskResult.SimplifiedEntitlement> getSimplifiedEntitlements ()`
- `java.util.Set<ITRoleMiningTaskResult.SimplifiedEntitlement> getSimplifiedEntitlementsByApplication (java.lang.String applicationId)`
- `int hashCode ()`
- `boolean isSuperSetOf ( ITRoleMiningTaskResult.SimplifiedEntitlementsKey otherKey)`
- `boolean meetsEntitlementsRequirement (int minEntitlementsPerRole)`
- `java.lang.String toString ()`

---

## ITRoleMiningTaskResult

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ITRoleMiningTaskResult`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `boolean contains ( ITRoleMiningTaskResult.SimplifiedEntitlement entitlement)`
- `ITRoleMiningTaskResult.SimplifiedEntitlementsKey getEntitlementSet ()`
- `java.lang.String getIdentifier ()`
- `ITRoleMiningTaskResult.EntitlementStatistics getStatistics ()`
- `int getTotalPopulation ()`
- `void setEntitlementSet ( ITRoleMiningTaskResult.SimplifiedEntitlementsKey entitlementSet)`
- `void setIdentifier (java.lang.String identifier)`
- `void setStatistics ( ITRoleMiningTaskResult.EntitlementStatistics statistics)`
- `void setTotalPopulation (int totalPopulation)`

---

## Identity.CapabilityManager

**Package:** `sailpoint.object`

**Description:** Return a non-null Attributes map that contains the localized names of this Identity's capabilities as if they were "attributes" on the identity.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Identity.CapabilityManager`

**Attributes:** N/A

**Methods:**
- `Attributes<java.lang.String,​java.lang.Object> createCapabilitiesAttributes ()`
- `java.util.List<Capability> getEffectiveCapabilities ()`
- `java.util.List<Capability> getEffectiveFlattenedCapabilities ()`
- `java.util.Collection<java.lang.String> getEffectiveFlattenedRights ()`
- `boolean hasCapability (java.lang.String capabilityName)`
- `boolean hasNativeCapability (java.lang.String capabilityName)`
- `boolean hasRight (java.lang.String rightName)`

---

## Identity.CreateProcessingStep

**Package:** `sailpoint.object`

**Description:** Enumeration of values that specify which creation processing step is of interest. This is used for storing and retrieving the need for creation processing independently for different functions.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Identity.CreateProcessingStep`
- `sailpoint.object.Identity.CreateProcessingStep`
- `java.io.Serializable`
- `java.lang.Comparable<Identity.CreateProcessingStep>`

**Attributes:** N/A

**Methods:**
- `staticIdentity.CreateProcessingStep valueOf (java.lang.String name)`
- `staticIdentity.CreateProcessingStep[] values ()`

---

## Identity.WorkgroupNotificationOption

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Identity.WorkgroupNotificationOption`
- `sailpoint.object.Identity.WorkgroupNotificationOption`
- `java.io.Serializable`
- `java.lang.Comparable<Identity.WorkgroupNotificationOption>`

**Attributes:** N/A

**Methods:**
- `staticIdentity.WorkgroupNotificationOption valueOf (java.lang.String name)`
- `staticIdentity.WorkgroupNotificationOption[] values ()`

---

## Identity

**Package:** `sailpoint.object`

**Description:** The core class representing the "identity cube".

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.AbstractCertifiableEntity`
- `sailpoint.object.Identity`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ADMIN_NAME`
- `static java.lang.String ATT_ADMINISTRATOR`
- `static java.lang.String ATT_BUNDLE_SUMMARY`
- `static java.lang.String ATT_CAPABILITIES`
- `static java.lang.String ATT_COMPOSITE_SCORE`
- `static java.lang.String ATT_CORRELATED`
- `static java.lang.String ATT_DISPLAYNAME`
- `static java.lang.String ATT_EMAIL`
- `static java.lang.String ATT_EXCEPTIONS`
- `static java.lang.String ATT_FIRSTNAME`
- `static java.lang.String ATT_INACTIVE`
- `static java.lang.String ATT_LAST_LOGIN`
- `static java.lang.String ATT_LAST_REFRESH`
- `static java.lang.String ATT_LASTNAME`
- `static java.lang.String ATT_MANAGER`
- `static java.lang.String ATT_MANAGER_STATUS`
- `static java.lang.String ATT_PASSWORD_LAST_CHANGED`
- `static java.lang.String ATT_PROTECTED`
- `static java.lang.String ATT_RAPIDSETUP_PROC_STATE`
- `static java.lang.String ATT_RIGHTS`
- `static java.lang.String ATT_SOFTWARE_VERSION`
- `static java.lang.String ATT_TYPE`
- `static java.lang.String ATT_USERNAME`
- `static java.lang.String ATT_VERIFICATION_TOKEN`
- `static java.lang.String ATT_WORKGROUP_FLAG`
- `static java.lang.String ATT_WORKGROUPS`
- `static int MAX_BUNDLE_SUMMARY`
- `static java.lang.String PRF_ATTRIBUTE_ASSIGNMENTS`
- `static java.lang.String PRF_BAD_PASSWORD_COUNT`
- `static java.lang.String PRF_FORWARD`
- `static java.lang.String PRF_FORWARD_END_DATE`
- `static java.lang.String PRF_FORWARD_START_DATE`
- `static java.lang.String PRF_ROLE_ASSIGNMENTS`
- `static java.lang.String PRF_ROLE_DETECTIONS`
- `static java.lang.String PRF_ROLE_REQUESTS`
- `static java.lang.String PRF_USE_BY_DATE`
- `static java.lang.String PRF_WORKGROUP_NOTIFICATION_OPTION`
- `static java.lang.String RAPIDSETUP_PROC_STATE_FORCED`
- `static java.lang.String RAPIDSETUP_PROC_STATE_NEEDED`
- `static java.lang.String RAPIDSETUP_PROC_STATE_PROCESSED`
- `static java.lang.String RAPIDSETUP_PROC_STATE_SKIPPED`
- `static java.lang.String[] SYSTEM_ATTRIBUTES`

**Methods:**
- `void add ( AttributeAssignment assignment)`
- `void add ( Bundle role)`
- `void add ( Capability cap)`
- `void add ( CertificationLink link)`
- `void add ( Certification cert, CertificationEntity entity)`
- `void add ( EntitlementGroup e)`
- `void add ( Identity workgroup)`
- `void add ( Link link)`
- `MitigationExpiration add ( MitigationExpiration exp)`
- `void addAssignedRole ( Bundle role)`
- `void addCertificationDecision ( SailPointContext context, CertificationItem certItem)`
- `void addCertificationDecision ( SailPointContext context, CertificationItem certItem, CertifiableDescriptor certDesc)`
- `void addCertificationDecision ( SailPointContext context, PolicyViolation violation, CertificationAction action)`
- `void addControlledScope ( Scope scope)`
- `void addDetectedRole ( Bundle role)`
- `void addEntitlementComment ( SailPointContext context, CertificationItem certItem, java.lang.String actor, java.lang.String comment)`
- `void addLatestCertification ( Certification cert, CertificationEntity entity)`
- `void addRoleAssignment ( RoleAssignment ra)`
- `void addRoleDetection ( RoleDetection rd)`
- `void addRoleMetadata ( RoleMetadata roleMetadata)`
- `void addRoleRequest ( RoleRequest req)`
- `void addScorecard ( Scorecard c)`
- `void assignAuthenticationAnswers (java.util.List< AuthenticationAnswer > answers)`
- `void assignLinks (java.util.List< Link > links)`
- `void assimilateAttributes ( Attributes <java.lang.String,java.lang.Object> a)`
- `java.lang.Object clone ()`
- `EntitlementCollection convertLinks (boolean onlyEntitlementAttrs)`
- `Attributes<java.lang.String,​java.lang.Object> createCapabilitiesAttributes ()`
- `Attributes<java.lang.String,​java.lang.Object> createEffectiveControlledScopesAttributes ( Configuration sysConfig)`
- `java.util.List<RoleAssignment> getActiveRoleAssignments ()`
- `java.util.List<RoleAssignment> getActiveRoleAssignments (java.lang.String roleName)`
- `java.util.List<RoleAssignment> getActiveRoleAssignments ( Bundle bundle)`
- `ActivityConfig getActivityConfig ()`
- `Identity getAdministrator ()`
- `Bundle getAssignedRole (java.lang.String id)`
- `java.util.List<Bundle> getAssignedRoles ()`
- `java.lang.String getAssignedRoleSummary ()`
- `java.lang.Object getAttribute (java.lang.String name)`
- `AttributeAssignment getAttributeAssignment (java.lang.String appName, java.lang.String nativeId, java.lang.String attribute, java.lang.String value, java.lang.String instance, java.lang.String assignmentId)`
- `java.util.List<AttributeAssignment> getAttributeAssignments ()`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getAuthAccount ()`
- `java.lang.String getAuthApplication ()`
- `java.util.List<AuthenticationAnswer> getAuthenticationAnswers ()`
- `java.util.Date getAuthLockStart ()`
- `Bundle getBundle (java.lang.String id)`
- `Bundle getBundleByName (java.lang.String name)`
- `java.util.List<Bundle> getBundles ()`
- `java.util.List<Bundle> getBundles (java.util.List< Application > apps)`
- `java.util.List<Bundle> getBundles ( Application app)`
- `java.lang.String getBundleSummary ()`
- `java.util.List<Capability> getCapabilities ()`
- `Identity.CapabilityManager getCapabilityManager ()`
- `java.util.List<IdentityHistoryItem> getCertificationDecisions ( SailPointContext context)`
- `java.util.List<CertificationLink> getCertifications ()`
- `java.util.List<Scope> getControlledScopes ()`
- `java.lang.Boolean getControlsAssignedScope ()`
- `boolean getControlsAssignedScope ( Configuration sysConfig)`
- `Attributes getCustomAttributes ()`
- `Bundle getDetectedRole (java.lang.String id)`
- `Bundle getDetectedRoleByName (java.lang.String name)`
- `java.util.List<Bundle> getDetectedRoles ()`
- `java.lang.String getDisplayableName ()`
- `java.lang.String getDisplayName ()`
- `java.util.List<Capability> getEffectiveCapabilities ()`
- `java.util.List<Scope> getEffectiveControlledScopes ( Configuration sysConfig)`
- `java.util.List<Scope> getEffectiveControlledScopes ( Configuration sysConfig, boolean expandIndirect)`
- `java.util.Collection<java.lang.String> getEffectiveFlattenedRights ()`
- `java.lang.String getEmail ()`
- `java.util.List<EntitlementGroup> getExceptions ()`
- `java.util.List<EntitlementGroup> getExceptions (java.util.List< Application > apps)`
- `java.lang.Object getExtendedAttribute (java.lang.String key)`
- `java.util.Map<java.lang.String,​java.lang.Object> getExtendedAttributes ()`
- `Identity getExtendedIdentity1 ()`
- `Identity getExtendedIdentity2 ()`
- `Identity getExtendedIdentity3 ()`
- `Identity getExtendedIdentity4 ()`
- `Identity getExtendedIdentity5 ()`
- `ObjectAttribute getExtendedIdentityAttribute (java.lang.String name)`
- `java.util.List<ExtState> getExtStates ()`
- `int getFailedAuthQuestionAttempts ()`
- `int getFailedLoginAttempts ()`
- `java.lang.String getFirstname ()`
- `RoleAssignment getFirstRoleAssignment (java.lang.String name)`
- `RoleAssignment getFirstRoleAssignment ( Bundle role)`
- `java.util.Collection<java.lang.String> getFlattenedRights ()`
- `java.lang.String getFullName ()`
- `java.util.List<GridState> getGridStates ()`
- `Identity getIdentityAttribute (java.lang.String name)`
- `IdentityTypeDefinition getIdentityTypeDefinition ()`
- `java.util.Date getLastLogin ()`
- `java.lang.String getLastname ()`
- `java.util.Date getLastRefresh ()`
- `IdentityHistoryItem getLastViolationDecision ( SailPointContext context, PolicyViolation violation)`
- `CertificationLink getLatestCertification ()`
- `CertificationLink getLatestCertification ( Certification.Type type)`
- `Link getLink (java.lang.String id)`
- `Link getLink ( Application res)`
- `Link getLink ( Application res, java.lang.String identity)`
- `Link getLink ( Application res, java.lang.String instance, java.lang.String identity)`
- `Link getLink ( Application res, java.lang.String instance, java.lang.String identity, java.lang.String uuid)`
- `Link getLink ( Application app, ResourceObject ro)`
- `Link getLink ( ProvisioningPlan.AccountRequest req)`
- `java.util.List<Link> getLinks ()`
- `java.util.List<Link> getLinks ( Application res)`
- `java.util.List<Link> getLinks ( Application res, java.lang.String instance)`
- `java.util.List<Link> getLinksByAppIdOrName (java.lang.String id, java.lang.String name)`
- `Identity getManager ()`
- `boolean getManagerStatus ()`
- `java.util.List<MitigationExpiration> getMitigationExpirations ()`
- `java.util.List<NativeChangeDetection> getNativeChangeDetections ()`
- `java.util.List<RoleAssignment> getNegativeRoleAssignments (java.lang.String roleName)`
- `Identity.WorkgroupNotificationOption getNotificationOption ()`
- `staticObjectConfig getObjectConfig ()`
- `Link getOwningCompositeLink ( Application app, java.lang.String nativeIdentity)`
- `Link getOwningCompositeLink ( Application app, java.lang.String instance, java.lang.String nativeIdentity)`
- `Link getOwningCompositeLink ( Link componentLink)`
- `java.util.List<Link> getOwningCompositeLinks ( Application app, java.lang.String instance, java.lang.String nativeIdentity)`
- `java.util.List<Link> getOwningCompositeLinks ( Link componentLink)`
- `java.lang.String getPassword ()`
- `java.util.Date getPasswordExpiration ()`
- `java.lang.String getPasswordHistory ()`
- `java.lang.String getPendingRefreshWorkflow ()`
- `java.lang.Object getPreference (java.lang.String name)`
- `java.util.Map<java.lang.String,​java.lang.Object> getPreferences ()`
- `java.util.List<CertificationLink> getRecentAppOwnerCertifications (java.util.Date recentDate)`
- `RoleAssignment getRoleAssignment (java.lang.String id)`
- `RoleAssignment getRoleAssignment (java.lang.String id, java.lang.String name)`
- `RoleAssignment getRoleAssignment ( Bundle role)`
- `RoleAssignment getRoleAssignmentByAssignmentAndRoleId (java.lang.String assignmentId, java.lang.String roleId)`
- `RoleAssignment getRoleAssignmentByAssignmentIdAndRoleName (java.lang.String assignmentId, java.lang.String roleName)`
- `RoleAssignment getRoleAssignmentById (java.lang.String assignmentId)`
- `java.util.List<RoleAssignment> getRoleAssignments ()`
- `java.util.List<RoleAssignment> getRoleAssignments (java.lang.String name)`
- `java.util.List<RoleAssignment> getRoleAssignments ( Bundle role)`
- `RoleDetection getRoleDetection (java.lang.String assignmentId, java.lang.String bundleId)`
- `RoleDetection getRoleDetection ( Bundle role)`
- `java.util.List<RoleDetection> getRoleDetections ()`
- `java.util.Set<RoleDetection> getRoleDetections (java.util.List< Application > apps)`
- `java.util.List<RoleDetection> getRoleDetections ( Application app)`
- `java.util.Map<Bundle,​java.util.List<EntitlementGroup>> getRoleEntitlementMappings ( Resolver r)`
- `java.util.List<RoleMetadata> getRoleMetadatas ()`
- `RoleRequest getRoleRequest ( Bundle role)`
- `java.util.List<RoleRequest> getRoleRequests ()`
- `java.lang.String getRoleSummary (java.util.List< Bundle > roles)`
- `java.util.List<SearchItem> getSavedSearches ()`
- `int getScore ()`
- `Scorecard getScorecard ()`
- `java.lang.String getSoftwareVersion ()`
- `java.lang.String getStringAttribute (java.lang.String name)`
- `java.lang.String getType ()`
- `java.lang.String getTypeName (boolean plural)`
- `java.lang.Object getUIPreference (java.lang.String name)`
- `java.lang.Object getUIPreference (java.lang.String name, Attributes <java.lang.String,java.lang.Object> defaults)`
- `java.lang.Object getUIPreference (java.lang.String name, Attributes <java.lang.String,java.lang.Object> defaults, java.lang.String defaultsKey)`
- `UIPreferences getUIPreferences ()`
- `RoleDetection getUnassignedRoleDetection ( Bundle bundle)`
- `java.util.Date getUseBy ()`
- `VerificationToken getVerificationToken ()`
- `java.util.List<Identity> getWorkgroups ()`
- `Scorecard getXmlScorecard ()`
- `boolean hasCapability (java.lang.String capabilityName)`
- `boolean hasRole ( Bundle role, boolean checkInheritedRoles)`
- `boolean isCorrelated ()`
- `boolean isCorrelatedOverridden ()`
- `boolean isDifferencable ()`
- `boolean isInactive ()`
- `boolean isInWorkGroup ( Identity workgroup)`
- `boolean isNeedsRefresh ()`
- `boolean isProtected ()`
- `static boolean isStandardAttributeName (java.lang.String attributeName)`
- `boolean isSystemAttribute (java.lang.String name)`
- `static boolean isValidTypeValue (java.lang.Object newValue)`
- `boolean isWorkgroup ()`
- `void loadCapabilities ()`
- `void loadForProvisioning ()`
- `boolean needsCreateProcessing ( Identity.CreateProcessingStep step)`
- `void remove ( AttributeAssignment assignment)`
- `void remove ( Bundle role)`
- `void remove ( Capability cap)`
- `void remove ( CertificationLink link)`
- `void remove ( Identity workgroup)`
- `void remove ( Link link)`
- `MitigationExpiration remove ( MitigationExpiration exp)`
- `void removeAssignedRole ( Bundle role)`
- `void removeAttribute (java.lang.String name)`
- `void removeAuthenticationAnswer ( AuthenticationAnswer answer)`
- `void removeControlledScope ( Scope scope)`
- `void removeDetectedRole ( Bundle role)`
- `void removeRoleAssignment ( RoleAssignment ra)`
- `void removeRoleDetection (java.lang.String roleName, java.lang.String assignmentIds)`
- `void removeRoleRequest ( RoleRequest req)`
- `void setActivityConfig ( ActivityConfig config)`
- `void setAdministrator ( Identity administrator)`
- `void setAssignedRoles (java.util.List< Bundle > roles)`
- `void setAssignedRoleSummary (java.lang.String s)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributeAssignments (java.util.List< AttributeAssignment > assignments)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> a)`
- `void setAuthAccount (java.lang.String authAccount)`
- `void setAuthApplication (java.lang.String authApplication)`
- `void setAuthenticationAnswers (java.util.List< AuthenticationAnswer > answers)`
- `void setAuthLockStart (java.util.Date lockStart)`
- `void setBundles (java.util.List< Bundle > bundles)`
- `void setBundleSummary (java.lang.String s)`
- `void setCapabilities (java.util.List< Capability > caps)`
- `void setCertifications (java.util.List< CertificationLink > certs)`
- `void setControlledScopes (java.util.List< Scope > scopes)`
- `void setControlsAssignedScope (java.lang.Boolean b)`
- `void setCorrelated (boolean b)`
- `void setCorrelatedOverridden (boolean correlatedOverridden)`
- `void setDetectedRoles (java.util.List< Bundle > roles)`
- `void setDisplayName (java.lang.String displayName)`
- `void setEmail (java.lang.String value)`
- `void setExceptions (java.util.List< EntitlementGroup > ents)`
- `void setExtendedIdentity1 ( Identity val)`
- `void setExtendedIdentity2 ( Identity val)`
- `void setExtendedIdentity3 ( Identity val)`
- `void setExtendedIdentity4 ( Identity val)`
- `void setExtendedIdentity5 ( Identity val)`
- `void setExtStates (java.util.List< ExtState > states)`
- `void setFailedAuthQuestionAttempts (int attempts)`
- `void setFailedLoginAttempts (int _failedLoginAttempts)`
- `void setFirstname (java.lang.String value)`
- `void setGridStates (java.util.List< GridState > states)`
- `void setInactive (boolean b)`
- `void setLastLogin (java.util.Date lastLogin)`
- `void setLastname (java.lang.String value)`
- `void setLastRefresh (java.util.Date lastRefresh)`
- `void setLinks (java.util.List< Link > links)`
- `void setManager ( Identity u)`
- `void setManagerStatus (boolean b)`
- `void setMitigationExpirations (java.util.List< MitigationExpiration > exps)`
- `void setNativeChangeDetections (java.util.List< NativeChangeDetection > detections)`
- `void setNeedsCreateProcessing (boolean needs, Identity.CreateProcessingStep step)`
- `void setNeedsRefresh (boolean b)`
- `void setNotificationOption ( Identity.WorkgroupNotificationOption value)`
- `void setPassword (java.lang.String password)`
- `void setPasswordExpiration (java.util.Date d)`
- `void setPasswordHistory (java.lang.String hist)`
- `void setPendingRefreshWorkflow (java.lang.String id)`
- `void setPreference (java.lang.String name, java.lang.Object value)`
- `void setPreferences (java.util.Map<java.lang.String,java.lang.Object> preferences)`
- `void setProtected (boolean b)`
- `void setRoleAssignments (java.util.List< RoleAssignment > roleAssignments)`
- `void setRoleDetections (java.util.List< RoleDetection > detections)`
- `void setRoleMetadatas (java.util.List< RoleMetadata > roleMetadatas)`
- `void setRoleRequests (java.util.List< RoleRequest > roles)`
- `void setSavedSearches (java.util.List< SearchItem > items)`
- `void setScorecard ( Scorecard c)`
- `void setSoftwareVersion (java.lang.String softwareVersion)`
- `void setType (java.lang.String type)`
- `void setUIPreference (java.lang.String name, java.lang.Object value)`
- `void setUIPreferences ( UIPreferences prefs)`
- `void setUseBy (java.util.Date d)`
- `void setVerificationToken ( VerificationToken t)`
- `void setWorkgroup (boolean isWorkgroup)`
- `void setWorkgroups (java.util.List< Identity > workgroups)`
- `void setXmlScorecard ( Scorecard c)`
- `boolean supportsExtendedIdentity ()`
- `java.lang.String toString ()`
- `void updateAssignedRoleSummary ()`
- `void updateBundleSummary ()`
- `void updateDetectedRoleSummary ()`
- `void validateAttributeAssignments ( Resolver resolver)`
- `void visit ( Visitor v)`

---

## IdentityArchive

**Package:** `sailpoint.object`

**Description:** An archive of an Identity object. This is similar to IdentitySnapshot, but does not have to go through a translation process to create a different model. Whereas snapshots are meant to be kept forever with loose references, this object is meant to have a shorter lifespan and can have hard references to object. This adds nothing to the Archive base class, but is its own class so that it is stored in its own table.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Archive`
- `sailpoint.object.IdentityArchive`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:** N/A

---

## IdentityAttributeFilterControl

**Package:** `sailpoint.object`

**Description:** This is a nonpersistent value that is used by the UI to determine how this control item is rendered.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.IdentityAttributeFilterControl`

**Attributes:** N/A

**Methods:**
- `java.util.List<IdentityAttributeFilterControl> getChildren ()`
- `java.lang.String getDisplayName ()`
- `Filter getFilter ( Identity requester)`
- `java.lang.String getName ()`
- `java.lang.String getOperation ()`
- `boolean isGrouping ()`
- `boolean isLeafAttribute ()`
- `boolean isSelectable ()`
- `void setChildren (java.util.List< IdentityAttributeFilterControl > children)`
- `void setDisplayName (java.lang.String displayName)`
- `void setGrouping (boolean isGrouping)`
- `void setLeafAttribute ()`
- `void setName (java.lang.String name)`
- `void setOperation (java.lang.String operation)`
- `void setSelectable (boolean isSelectable)`

---

## IdentityChangeEvent

**Package:** `sailpoint.object`

**Description:** An event that gets fired when an identity is created/update/deleted during aggregation, refresh, or through the UI.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.AbstractChangeEvent`
- `sailpoint.object.IdentityChangeEvent`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getCause ()`
- `java.lang.String getIdentityFullName ()`
- `java.lang.String getIdentityName ()`
- `java.util.List<NativeChangeDetection> getNativeChanges ()`
- `IdentityTrigger getTrigger ()`
- `void setNativeChanges (java.util.List< NativeChangeDetection > nativeChanges)`
- `void setTrigger ( IdentityTrigger trigger)`

---

## IdentityDifference

**Package:** `sailpoint.object`

**Description:** Class used to contain the results of a comparison between two IdentitySnapshot objects.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.IdentityDifference`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String ATT_POLICY_VIOLATIONS`

**Methods:**
- `void add ( PermissionDifference diff)`
- `void addAssignedRoleDifference ( Difference d)`
- `void addAttributeDifference ( Difference d)`
- `void addAttributeDifferences (java.util.List< Difference > diffs)`
- `void addBundleDifference ( Difference d)`
- `void addLinkDifferences (java.util.List< Difference > diffs)`
- `void addPermissionDifferences (java.util.List< PermissionDifference > diffs)`
- `void addPolicyViolationDifference ( Difference d)`
- `static java.lang.String generateContext (java.lang.String application, java.lang.String nativeIdentity)`
- `Difference getAssignedRoleDifferences ()`
- `Difference getAttributeDifference (java.lang.String attrName)`
- `java.util.List<Difference> getAttributeDifferences ()`
- `Difference getBundleDifferences ()`
- `java.util.List<Difference> getLinkDifferences ()`
- `java.util.List<Difference> getLinkDifferences (java.lang.String appName)`
- `java.util.List<Difference> getLinkDifferences (java.lang.String appName, java.lang.String nativeIdentity)`
- `java.util.List<PermissionDifference> getPermissionDifferences ()`
- `java.util.List<PermissionDifference> getPermissionDifferences (java.lang.String appName)`
- `Difference getPolicyViolationDifferences ()`
- `boolean hasDifferences ()`
- `void setAttributeDifferences (java.util.List< Difference > diffs)`
- `void setLinkDifferences (java.util.List< Difference > diffs)`
- `void setPermissionDifferences (java.util.List< PermissionDifference > diffs)`
- `IdentityDifference truncateStrings ()`
- `IdentityDifference truncateStrings (int max)`

---

## IdentityEntitlement.AggregationState

**Package:** `sailpoint.object`

**Description:** The state of the Entitlement, which is how origination and current state of the entitlement are tracked.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `IdentityEntitlement.AggregationState`
- `sailpoint.object.IdentityEntitlement.AggregationState`
- `java.io.Serializable`
- `java.lang.Comparable<IdentityEntitlement.AggregationState>`

**Attributes:** N/A

**Methods:**
- `staticIdentityEntitlement.AggregationState valueOf (java.lang.String name)`
- `staticIdentityEntitlement.AggregationState[] values ()`

---

## IdentityEntitlement

**Package:** `sailpoint.object`

**Description:** Class used to maintain entitlement connections and encapsulate some certification and request meta data for an identity. In hibernate these object are modeled as a structure which provides the ability to query through the identity object, (for example, identity.identityEntitlements.name), but prevents them from being like an ordered collection or maintained on the Identity. All operations on these values (outside searching) must be performed directly on the IdentityEntitlement object This object models application entitlements, IdentityIQ assigned and IdentityIQ detected roles using this same structure and table. These objects are typically created during aggregation.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.PersistentIdentityItem`
- `sailpoint.object.IdentityEntitlement`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String IDENTITY_COLUMN`
- `static java.lang.String SOURCE_ASSIGNABLE`
- `static java.lang.String SOURCE_DETECTED`

**Methods:**
- `boolean equals (java.lang.Object e)`
- `boolean foundInFeed ()`
- `IdentityEntitlement.AggregationState getAggregationState ()`
- `java.lang.String getAppId ()`
- `Application getApplication ()`
- `java.lang.String getAppName ()`
- `java.lang.String getAssigner ()`
- `java.lang.String getAssignmentId ()`
- `java.lang.String getAssignmentNote ()`
- `CertificationItem getCertificationItem ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `Identity getIdentity ()`
- `CertificationItem getPendingCertificationItem ()`
- `IdentityRequestItem getPendingRequestItem ()`
- `IdentityRequestItem getRequestItem ()`
- `java.lang.String getSource ()`
- `java.lang.String getSourceAssignableRoles ()`
- `java.lang.String getSourceDetectedRoles ()`
- `Source getSourceObject ()`
- `ManagedAttribute.Type getType ()`
- `int hashCode ()`
- `boolean isAllowed ()`
- `boolean isAssigned ()`
- `boolean isConnected ()`
- `boolean isDisconnected ()`
- `boolean isGrantedByRole ()`
- `boolean matches ( AttributeAssignment assignment)`
- `void setAggregationState ( IdentityEntitlement.AggregationState aggregationState)`
- `void setAllowed (boolean allowed)`
- `void setApplication ( Application a)`
- `void setAssigned (boolean isAssigned)`
- `void setAssigner (java.lang.String assigner)`
- `void setAssignmentId (java.lang.String assignmentId)`
- `void setAssignmentNote (java.lang.String assignmentNote)`
- `void setCertificationItem ( CertificationItem certificationItem)`
- `void setFoundInFeed (boolean found)`
- `void setGrantedByRole (boolean grantedByRole)`
- `void setIdentity ( Identity id)`
- `void setPendingCertificationItem ( CertificationItem pendingCertificationItem)`
- `void setPendingRequestItem ( IdentityRequestItem pendingRequestItem)`
- `void setRequestItem ( IdentityRequestItem requestItem)`
- `void setSource (java.lang.String source)`
- `void setSourceAssignableRoles (java.lang.String sourceRoles)`
- `void setSourceDetectedRoles (java.lang.String sourceRoles)`
- `void setType ( ManagedAttribute.Type type)`
- `java.lang.String toString ()`
- `void visit ( Visitor v)`

---

## IdentityExternalAttribute

**Package:** `sailpoint.object`

**Description:** An extension of ExternalAttribute that results in a table for identity attributes that is distinct from extended attribute tables for other classes.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.ExternalAttribute`
- `sailpoint.object.IdentityExternalAttribute`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:** N/A

---

## IdentityFilter.FilterBuilder

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.IdentityFilter.FilterBuilder`

**Attributes:**
- `protectedIdentityFilter.FilterSource _filterSource`

**Methods:**
- `abstractFilter getFilter (java.util.Map<java.lang.String,java.lang.Object> requestParams)`
- `void setFilterSource ( IdentityFilter.FilterSource filterSource)`

---

## IdentityFilter.FilterSource

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.IdentityFilter.FilterSource`

**Attributes:** N/A

**Methods:**
- `Filter getFilter ()`
- `IdentityFilter.FilterTemplate getFilterTemplate ()`
- `void setFilter ( Filter filter)`
- `void setFilterTemplate ( IdentityFilter.FilterTemplate filterTemplate)`

---

## IdentityFilter.FilterTemplate

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.IdentityFilter.FilterTemplate`

**Attributes:** N/A

**Methods:**
- `java.util.List<java.lang.String> getFilterParameters ()`
- `java.lang.String getFilterString ()`
- `void setFilterParameters (java.util.List<java.lang.String> parameters)`
- `void setFilterString (java.lang.String filterString)`
- `java.lang.String toString ()`

---

## IdentityFilter.Order

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `IdentityFilter.Order`
- `sailpoint.object.IdentityFilter.Order`
- `java.io.Serializable`
- `java.lang.Comparable<IdentityFilter.Order>`

**Attributes:** N/A

**Methods:**
- `staticIdentityFilter.Order valueOf (java.lang.String name)`
- `staticIdentityFilter.Order[] values ()`

---

## IdentityFilter

**Package:** `sailpoint.object`

**Description:** Context for entitlement owners.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.IdentityFilter`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String CONTEXT_ENTITLEMENT_OWNER`
- `static java.lang.String CONTEXT_LCM_POPULATION`
- `static java.lang.String CONTEXT_LCM_POPULATION_MANAGER`
- `static java.lang.String CONTEXT_ROLE_OWNER`
- `static java.lang.String GLOBAL_FILTER`
- `static java.lang.String IDENTITY_MANAGER_ATTRIBUTE`
- `static java.lang.String INCLUDE_WORKGROUPS_FILTER`

**Methods:**
- `QueryOptions buildQuery (java.util.Map<java.lang.String,java.lang.Object> requestParameters, SailPointContext context)`
- `protected static java.util.Map<java.lang.String,​java.lang.Object> escapeParametersForFilterParsing (java.util.Map<java.lang.String,java.lang.Object> params)`
- `Script getFilterScript ()`
- `IdentityFilter.FilterSource getFilterSrc ()`
- `java.util.List<java.lang.String> getIncludedFilterReferences ()`
- `java.util.List<IdentityFilter> getIncludedFilters ()`
- `java.lang.String getName ()`
- `IdentityFilter.Order getOrder ()`
- `java.util.List<java.lang.String> getOrderBy ()`
- `boolean isIgnoreGlobal ()`
- `void setFilterScript ( Script script)`
- `void setFilterSrc ( IdentityFilter.FilterSource filter)`
- `void setIgnoreGlobal (boolean ignoreGlobal)`
- `void setIncludedFilterReferences (java.util.List<java.lang.String> filterReferences)`
- `void setName (java.lang.String name)`
- `void setOrder ( IdentityFilter.Order order)`
- `void setOrderBy (java.util.List<java.lang.String> orderBy)`
- `java.lang.String toString ()`
- `static java.lang.String unescapeBackslashes (java.lang.String s)`

---

## IdentityHistoryItem.Type

**Package:** `sailpoint.object`

**Description:** History item types: Decision - a certification decision for an entitlement Comment - a comment made on an entitlement

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `IdentityHistoryItem.Type`
- `sailpoint.object.IdentityHistoryItem.Type`
- `java.io.Serializable`
- `java.lang.Comparable<IdentityHistoryItem.Type>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticIdentityHistoryItem.Type valueOf (java.lang.String name)`
- `staticIdentityHistoryItem.Type[] values ()`

---

## IdentityHistoryItem

**Package:** `sailpoint.object`

**Description:** The IdentityHistoryItem class is used to track the history, particularly history involving certifications, for an Identity. At the time of this writing, either certification decisions made against an Identity (for example - role, entitlement, policy violation) or comments made against a particular entitlement for that Identity can be recorded.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.IdentityHistoryItem`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.String getAccount ()`
- `CertificationAction getAction ()`
- `java.lang.String getActor ()`
- `java.lang.String getApplication ()`
- `java.lang.String getAttribute ()`
- `java.lang.String getBusinessRole ()`
- `CertifiableDescriptor getCertifiableDescriptor ()`
- `CertificationLink getCertificationLink ()`
- `CertificationItem.Type getCertificationType ()`
- `java.lang.String getComments ()`
- `java.lang.String getConstraintName ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `EntitlementSnapshot getEntitlements ()`
- `java.util.Date getEntryDate ()`
- `EntitlementSnapshot getExceptionEntitlements ()`
- `java.lang.String getHistoryComments ()`
- `Identity getIdentity ()`
- `java.lang.String getInstance ()`
- `java.lang.String getNativeIdentity ()`
- `java.lang.String getPolicy ()`
- `PolicyViolation getPolicyViolation ()`
- `java.lang.String getRole ()`
- `CertificationAction.Status getStatus ()`
- `IdentityHistoryItem.Type getType ()`
- `java.lang.String getValue ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `boolean isSimiliarViolation ( PolicyViolation otherViolation)`
- `void setAccount (java.lang.String account)`
- `void setAction ( CertificationAction action)`
- `void setActor (java.lang.String name)`
- `void setApplication (java.lang.String application)`
- `void setAttributeAndTruncate (java.lang.String attribute)`
- `void setAttributeAndValue ( Certification.EntitlementGranularity granularity, EntitlementSnapshot snapshot)`
- `void setCertifiableDescriptor ( CertifiableDescriptor desc)`
- `void setCertificationLink ( CertificationLink certificationLink)`
- `void setCertificationType ( CertificationItem.Type cType)`
- `void setComments (java.lang.String comment)`
- `void setConstraintNameAndTruncate (java.lang.String constraintName)`
- `void setEntryDate (java.util.Date entryDate)`
- `void setIdentity ( Identity identity)`
- `void setInstance (java.lang.String instance)`
- `void setNativeIdentity (java.lang.String nativeIdentity)`
- `void setPolicy (java.lang.String policy)`
- `void setRole (java.lang.String role)`
- `void setStatus ( CertificationAction.Status status)`
- `void setType ( IdentityHistoryItem.Type type)`
- `void setValueAndTruncate (java.lang.String value)`
- `java.util.Map<java.lang.String,​java.lang.Object> toMap ()`
- `java.lang.String toString ()`

---

## IdentityItem.Path

**Package:** `sailpoint.object`

**Description:** Normally transient objects maintained in a list to represent the path from a role or entitlement involved in an SOD conflict to the role on an identity that indirectly granted the conflicting thing. The relationship applies to the previous item on the list. For example this path: A inherits B requires C permits D Would be expressed in path XML as: <ItemPaths> <ItemPath role='A'/> <ItemPath role='B' relationship='I'/> <ItemPath role='C' relationship='R'/> <ItemPath role='D' relationship='P'/> </ItemPaths>

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.IdentityItem.Path`

**Attributes:** N/A

**Methods:**
- `java.lang.String getRelationship ()`
- `java.lang.String getRole ()`
- `void setRelationship (java.lang.String s)`
- `void setRole (java.lang.String s)`

---

## IdentityItem

**Package:** `sailpoint.object`

**Description:** A class used to represent a single item (attribute or entitlement) from an identity. This is a general purpose model used in several contexts. They are used by Matchmaker to keep track of the specific identity attributes that satisfied an IdentitySelector or other form of matching rule. They are used in RoleDetection to keep track of the specific entitlements that were used in the detection of a role.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.AccountItem`
- `sailpoint.object.IdentityItem`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String RELATIONSHIP_INHERITS`
- `static java.lang.String RELATIONSHIP_PERMITS`
- `static java.lang.String RELATIONSHIP_REQUIRES`

**Methods:**
- `java.lang.String getAccountDisplayName ()`
- `java.lang.String getApplication ()`
- `java.lang.String getApplicationId ()`
- `java.lang.String getInstance ()`
- `java.lang.String getNativeIdentity ()`
- `java.util.List<IdentityItem.Path> getPath ()`
- `java.lang.String getRole ()`
- `java.lang.String getRoleId ()`
- `boolean isEqual ( IdentityItem other)`
- `void setAccount ( Link link)`
- `void setAccountDisplayName (java.lang.String s)`
- `void setApplication (java.lang.String s)`
- `void setApplication ( Application app)`
- `void setApplicationId (java.lang.String s)`
- `void setInstance (java.lang.String s)`
- `void setNativeIdentity (java.lang.String s)`
- `void setPath (java.util.List< IdentityItem.Path > path)`
- `void setRole (java.lang.String s)`
- `void setRole ( Bundle role)`
- `void setRoleId (java.lang.String roleId)`

---

## IdentityMatcher

**Package:** `sailpoint.object`

**Description:** An identity matcher can evaluate an IdentitySelector against an identity to determine whether it matches or not. This interface is here to allow classes in the object package to match without explicitly referencing the Matchmaker in the api package.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `boolean isMatch ( IdentitySelector selector, Identity identity)`

---

## IdentityRequest.CompletionStatus

**Package:** `sailpoint.object`

**Description:** The CompletionStatus of the request. This indicates what the status of the request was after completion.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `IdentityRequest.CompletionStatus`
- `sailpoint.object.IdentityRequest.CompletionStatus`
- `java.io.Serializable`
- `java.lang.Comparable<IdentityRequest.CompletionStatus>`
- `sailpoint.tools.MessageKeyHolder`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticIdentityRequest.CompletionStatus valueOf (java.lang.String name)`
- `staticIdentityRequest.CompletionStatus[] values ()`

---

## IdentityRequest.ExecutionStatus

**Package:** `sailpoint.object`

**Description:** An enumeration to describe the current execution state of the request.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `IdentityRequest.ExecutionStatus`
- `sailpoint.object.IdentityRequest.ExecutionStatus`
- `java.io.Serializable`
- `java.lang.Comparable<IdentityRequest.ExecutionStatus>`
- `sailpoint.tools.MessageKeyHolder`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticIdentityRequest.ExecutionStatus valueOf (java.lang.String name)`
- `staticIdentityRequest.ExecutionStatus[] values ()`

---

## IdentityRequest

**Package:** `sailpoint.object`

**Description:** The CompletionStatus of the request.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.IdentityRequest`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ACCOUNTS_REQUEST_FLOW_CONFIG_NAME`
- `static java.lang.String ATT_ALLOW_BULK`
- `static java.lang.String ATT_APPROVAL_SUMMARIES`
- `static java.lang.String ATT_BULK_REQUEST`
- `static java.lang.String ATT_FLOW_NAME`
- `static java.lang.String ATT_MESSAGES`
- `static java.lang.String ATT_POLICY_VIOLATION_MAPS`
- `static java.lang.String ATT_PROVISIONED_PROJECT`
- `static java.lang.String ATT_SUPPRESSED_EXPANSION_ITEMS`
- `static java.lang.String ATT_TASK_RESULT_ID`
- `static java.lang.String ATT_TERMINATED_DATE`
- `static java.lang.String ATTRIBUTE_SYNC_FLOW`
- `static java.lang.String ENTITLEMENTS_REQUEST_FLOW_CONFIG_NAME`
- `static java.lang.String EXPIRED_PASSWORD_FLOW`
- `static java.lang.String FORGOT_PASSWORD_FLOW`
- `static java.lang.String IDENTITY_CREATE_FLOW_CONFIG_NAME`
- `static java.lang.String IDENTITY_UPDATE_FLOW_CONFIG_NAME`
- `static java.lang.String PASSWORD_REQUEST_FLOW`
- `static java.lang.String ROLES_REQUEST_FLOW_CONFIG_NAME`
- `static java.util.Map<java.lang.String,​java.lang.String> typeConversionMap`

**Methods:**
- `void add ( IdentityRequestItem item)`
- `void addExpansion ( IdentityRequestItem item, ProvisioningProject project)`
- `void addMessage ( Message message)`
- `void addMessages (java.util.List< Message > messages)`
- `int applyAccountRequestResults ( ProvisioningPlan plan)`
- `int applyResultMessages ( ProvisioningResult result)`
- `void assimilateResultState ( ProvisioningResult result, IdentityRequestItem item)`
- `void computeCompletionStatus ()`
- `void computeHasMessages ()`
- `boolean executing ()`
- `boolean failure ()`
- `IdentityRequestItem findItem ( ProvisioningPlan.AccountRequest req, ProvisioningPlan.GenericRequest attrReq, java.lang.String valueStr)`
- `IdentityRequestItem findItem ( ProvisioningPlan.AccountRequest req, ProvisioningPlan.GenericRequest attrReq, java.lang.String valueStr, boolean ignoreAccountId)`
- `java.util.List<IdentityRequestItem> findItems (java.lang.String appName, java.lang.String nativeIdentity, java.lang.String instance, java.lang.String attrName, java.lang.String operation, java.lang.String assignmentId)`
- `java.util.List<IdentityRequestItem> findItems ( ApprovalItem aitem)`
- `java.util.List<IdentityRequestItem> findItems ( ProvisioningPlan.AccountRequest req)`
- `java.util.List<IdentityRequestItem> getApprovalCompleteItems ()`
- `java.util.List<WorkflowSummary.ApprovalSummary> getApprovalSummaries ()`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `IdentityRequest.CompletionStatus getCompletionStatus ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `java.util.Date getEndDate ()`
- `java.util.List<Message> getErrors ()`
- `IdentityRequest.ExecutionStatus getExecutionStatus ()`
- `java.lang.String getExternalTicketId ()`
- `boolean getHasMessages ()`
- `java.util.List<IdentityRequestItem> getItems ()`
- `java.util.List<Message> getMessages ()`
- `java.util.List<Message> getMessagesByType ( Message.Type type)`
- `java.util.List<IdentityRequestItem> getPendingProvisioning ()`
- `java.util.List<java.util.Map<java.lang.String,​java.lang.Object>> getPolicyViolationMaps ()`
- `WorkItem.Level getPriority ()`
- `java.lang.String getProcessId ()`
- `ProvisioningProject getProvisionedProject ()`
- `java.util.List<IdentityRequestItem> getProvisioningCompleteItems ()`
- `java.util.List<IdentityRequestItem> getProvisioningFailedItems ()`
- `java.util.List<IdentityRequestItem> getProvisioningPendingItems ()`
- `java.util.List<IdentityRequestItem> getProvisioningRetryItems ()`
- `java.lang.String getRequesterDisplayName ()`
- `java.lang.String getRequesterId ()`
- `java.lang.String getSource ()`
- `Source getSourceObject ()`
- `java.lang.String getState ()`
- `java.lang.String getStringAttribute (java.lang.String name)`
- `java.lang.String getTargetClass ()`
- `java.lang.String getTargetDisplayName ()`
- `java.lang.String getTargetId ()`
- `java.lang.String getTaskResultId ()`
- `java.lang.String getType ()`
- `java.lang.String getUserFriendlyType ()`
- `java.lang.String getUserFriendlyType (java.util.Locale locale, java.util.TimeZone timeZone)`
- `java.util.Date getVerified ()`
- `java.util.List<Message> getWarnings ()`
- `boolean hasErrors ()`
- `boolean hasMessages ()`
- `boolean hasWarnings ()`
- `boolean incomplete ()`
- `boolean isBulkRequest ()`
- `boolean isExecuting ()`
- `boolean isFailure ()`
- `boolean isIIQOnlyRequest ()`
- `boolean isIncomplete ()`
- `boolean isNameUnique ()`
- `boolean isRejected ()`
- `boolean isSuccessful ()`
- `boolean isSuppressedExpansionItems ()`
- `boolean isTerminated ()`
- `void mergeProvisionedProject ( SailPointContext ctx, ProvisioningProject project)`
- `static java.lang.String opToString (java.lang.Object operation)`
- `boolean provisioningComplete ()`
- `void setApprovalSummaries (java.util.List< WorkflowSummary.ApprovalSummary > summaries)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attributes)`
- `void setBulkRequest (boolean isBulk)`
- `void setCompletionStatus ( IdentityRequest.CompletionStatus status)`
- `void setEndDate (java.util.Date end)`
- `void setExecutionStatus ( IdentityRequest.ExecutionStatus status)`
- `void setExternalTicketId (java.lang.String externalTicketId)`
- `void setHasMessages (boolean hasSome)`
- `void setItems (java.util.List< IdentityRequestItem > items)`
- `void setMessages (java.util.List< Message > messages)`
- `void setPolicyViolationMaps (java.util.List<java.util.Map<java.lang.String,java.lang.Object>> violations)`
- `void setPriority ( WorkItem.Level priority)`
- `void setProcessId (java.lang.String processId)`
- `void setProvisionedProject ( SailPointContext ctx, ProvisioningProject project)`
- `void setRequesterDisplayName (java.lang.String requesterDisplayName)`
- `void setRequesterId (java.lang.String requesterId)`
- `void setSource (java.lang.String source)`
- `void setState (java.lang.String state)`
- `void setSuppressedExpansionItems (boolean b)`
- `void setTargetClass (java.lang.String targetClass)`
- `void setTargetDisplayName (java.lang.String targetDisplayName)`
- `void setTargetId (java.lang.String targetId)`
- `void setTaskResultId (java.lang.String taskResultId)`
- `void setType (java.lang.String type)`
- `void setUserFriendlyType (java.lang.String type)`
- `void setVerified (java.util.Date verificationDate)`
- `boolean terminated ()`
- `void visit ( Visitor v)`

---

## IdentityRequestItem.CompilationStatus

**Package:** `sailpoint.object`

**Description:** The item was added to the request during compilation because it was necessary for a requested item to be fulfilled.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `IdentityRequestItem.CompilationStatus`
- `sailpoint.object.IdentityRequestItem.CompilationStatus`
- `java.io.Serializable`
- `java.lang.Comparable<IdentityRequestItem.CompilationStatus>`
- `sailpoint.tools.MessageKeyHolder`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticIdentityRequestItem.CompilationStatus valueOf (java.lang.String name)`
- `staticIdentityRequestItem.CompilationStatus[] values ()`

---

## IdentityRequestItem

**Package:** `sailpoint.object`

**Description:** An object to describe the items that were requested for provisioning. This object is a just like ApprovalItem but is encapsulated in its own class because of they inheritance model of the ApprovalItem objects.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.PersistentIdentityItem`
- `sailpoint.object.IdentityRequestItem`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATT_ASSIGNMENT_ID`
- `static java.lang.String ATT_ERRORS`
- `static java.lang.String ATT_EXPANSION_INFO`
- `static java.lang.String ATT_MANAGED_ATTRIBUTE_TYPE`
- `static java.lang.String ATT_PROVISIONING_PLAN`
- `static java.lang.String ATT_PROVISIONING_REQUEST_ID`
- `static java.lang.String ATT_REQUESTER_COMMENTS`
- `static java.lang.String ATT_TRACKING_ID`
- `static java.lang.String ATT_WARNINGS`

**Methods:**
- `void addError ( Message message)`
- `void addErrors (java.util.List< Message > messages)`
- `void addWarning ( Message message)`
- `void addWarnings (java.util.List< Message > messages)`
- `java.lang.String getApplication ()`
- `WorkItem.State getApprovalState ()`
- `java.lang.String getApproverName ()`
- `java.lang.String getAssignmentId ()`
- `java.util.List<Attachment> getAttachments ()`
- `IdentityRequestItem.CompilationStatus getCompilationStatus ()`
- `java.util.List<Message> getErrors ()`
- `ExpansionItem.Cause getExpansionCause ()`
- `java.lang.String getExpansionInfo ()`
- `IdentityRequest getIdentityRequest ()`
- `java.lang.String getManagedAttributeType ()`
- `java.lang.String getOperation ()`
- `java.lang.String getOwnerName ()`
- `java.lang.String getProvisioningEngine ()`
- `ProvisioningPlan getProvisioningPlan ()`
- `java.lang.String getProvisioningRequestId ()`
- `ApprovalItem.ProvisioningState getProvisioningState ()`
- `java.lang.String getRequesterComments ()`
- `int getRetries ()`
- `java.util.List<Message> getWarnings ()`
- `boolean hasAssignedScope ()`
- `void incrementRetries ()`
- `boolean isApprovalComplete ()`
- `boolean isApproved ()`
- `boolean isCommitted ()`
- `boolean isExpansion ()`
- `boolean isFiltered ()`
- `boolean isIIQ ()`
- `boolean isNameUnique ()`
- `boolean isNonverifiable ()`
- `boolean isProvisioningCommited ()`
- `boolean isProvisioningComplete ()`
- `boolean isProvisioningFailed ()`
- `boolean isRejected ()`
- `void setApplication (java.lang.String s)`
- `void setApprovalState ( WorkItem.State state)`
- `void setApproverName (java.lang.String approverName)`
- `void setAssignmentId (java.lang.String s)`
- `void setAttachments (java.util.List< Attachment > attachments)`
- `void setCompilationStatus ( IdentityRequestItem.CompilationStatus compilationStatus)`
- `void setErrors (java.util.List< Message > errors)`
- `void setExpansionCause ( ExpansionItem.Cause cause)`
- `void setExpansionInfo (java.lang.String info)`
- `void setIdentityRequest ( IdentityRequest ir)`
- `void setManagedAttributeType ( ManagedAttribute.Type type)`
- `void setOperation (java.lang.String op)`
- `void setOwnerName (java.lang.String owner)`
- `void setProvisioningEngine (java.lang.String pe)`
- `void setProvisioningPlan ( ProvisioningPlan plan)`
- `void setProvisioningRequestId (java.lang.String provisioningRequestId)`
- `void setProvisioningState ( ApprovalItem.ProvisioningState provisioningState)`
- `void setRequesterComments (java.lang.String comments)`
- `void setRetries (int i)`
- `void setWarnings (java.util.List< Message > warnings)`
- `void visit ( Visitor v)`

---

## IdentitySelector.EntitlementAttributes

**Package:** `sailpoint.object`

**Description:** Returns query property used when value is null.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `IdentitySelector.EntitlementAttributes`
- `sailpoint.object.IdentitySelector.EntitlementAttributes`
- `java.io.Serializable`
- `java.lang.Comparable<IdentitySelector.EntitlementAttributes>`
- `IdentitySelector.IAttribute`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:**
- `java.lang.String getLocalizedMessage ()`
- `java.lang.String getLocalizedMessage (java.util.Locale locale, java.util.TimeZone timezone)`
- `java.lang.String getMessageKey ()`
- `java.lang.String getName ()`
- `java.lang.String getNullQueryProperty ()`
- `java.lang.String getType ()`
- `boolean isMultiValued ()`
- `staticIdentitySelector.EntitlementAttributes valueOf (java.lang.String name)`
- `staticIdentitySelector.EntitlementAttributes[] values ()`

---

## IdentitySelector.IAttribute

**Package:** `sailpoint.object`

**Description:** Returns query property used when value is null.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `java.lang.String getName ()`
- `java.lang.String getNullQueryProperty ()`
- `java.lang.String getType ()`
- `boolean isMultiValued ()`

---

## IdentitySelector.MatchExpression

**Package:** `sailpoint.object`

**Description:** Representation for a set of MatchTerms.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.IdentitySelector.MatchExpression`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void addTerm ( IdentitySelector.MatchTerm t)`
- `Application getApplication ()`
- `java.util.List<IdentitySelector.MatchTerm> getTerms ()`
- `boolean isAnd ()`
- `java.lang.String render ()`
- `void setAnd (boolean b)`
- `void setApplication ( Application a)`
- `void setTerms (java.util.List< IdentitySelector.MatchTerm > terms)`

---

## IdentitySelector.MatchMonitor

**Package:** `sailpoint.object`

**Description:** Interface of an object that can be passed into match evaluation methods to be informed about things encountered during evaluation. This was added as a way to accumulate the Applications involved in a match to set the "relevant apps" list in a PolicyViolation, but it was made an interface so it can be extended if necessary. Currently used only by MatchExpression/MatchTerm, eventually should be used by Matchmaker for other selection styles (filter, script, rule, etc.)

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `void matchMonitorApplication ( Application app)`
- `void matchMonitorAttribute ( Link link, java.lang.String name, java.lang.Object value)`
- `void matchMonitorPermission ( Link link, Permission p, java.lang.Object value)`

---

## IdentitySelector.MatchTerm.ContributingEntitlement

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.IdentitySelector.MatchTerm.ContributingEntitlement`

**Attributes:** N/A

**Methods:**
- `java.util.List<java.lang.String> getClassificationNames ()`
- `java.lang.Boolean getIiqElevatedAccess ()`
- `java.lang.String getPath ()`
- `java.lang.String getSource ()`
- `java.lang.String getType ()`
- `void setClassificationNames (java.util.List<java.lang.String> classificationNames)`
- `void setIiqElevatedAccess (java.lang.Boolean iiqElevatedAccess)`
- `void setPath (java.lang.String path)`
- `void setSource (java.lang.String source)`
- `void setType (java.lang.String type)`

---

## IdentitySelector.MatchTerm.Type

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `IdentitySelector.MatchTerm.Type`
- `sailpoint.object.IdentitySelector.MatchTerm.Type`
- `java.io.Serializable`
- `java.lang.Comparable<IdentitySelector.MatchTerm.Type>`

**Attributes:** N/A

**Methods:**
- `staticIdentitySelector.MatchTerm.Type valueOf (java.lang.String name)`
- `staticIdentitySelector.MatchTerm.Type[] values ()`

---

## IdentitySelector.MatchTerm

**Package:** `sailpoint.object`

**Description:** Generic representation for a single attribute or permission value within a MatchExpression. This is similar to EntitlementWeight in that the same class is used to represent both attribute values and Permission values. Could consider factoring out something to share but there is not much in here and the usage contexts are different.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.IdentitySelector.MatchTerm`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void addChild ( IdentitySelector.MatchTerm val)`
- `void addContributingEntitlement ( IdentitySelector.MatchTerm.ContributingEntitlement ent)`
- `Application getApplication ()`
- `java.util.List<IdentitySelector.MatchTerm> getChildren ()`
- `java.util.List<IdentitySelector.MatchTerm.ContributingEntitlement> getContributingEntitlements ()`
- `java.lang.String getName ()`
- `TargetSource getTargetSource ()`
- `IdentitySelector.MatchTerm.Type getType ()`
- `java.lang.String getValue ()`
- `boolean isAnd ()`
- `boolean isCheckEffective ()`
- `boolean isContainer ()`
- `boolean isEntitlementType ()`
- `boolean isNegative ()`
- `boolean isPermission ()`
- `boolean isPermissionType ()`
- `void load ()`
- `java.lang.String render ()`
- `static java.lang.String renderLeaf (java.lang.String type, java.lang.String name, java.lang.String value, boolean negative)`
- `void setAnd (boolean val)`
- `void setApplication ( Application a)`
- `void setCheckEffective (boolean b)`
- `void setChildren (java.util.List< IdentitySelector.MatchTerm > val)`
- `void setContainer (boolean val)`
- `void setContributingEntitlements (java.util.List< IdentitySelector.MatchTerm.ContributingEntitlement > ents)`
- `void setName (java.lang.String name)`
- `void setNegative (boolean val)`
- `void setPermission (boolean b)`
- `void setTargetSource ( TargetSource ts)`
- `void setType ( IdentitySelector.MatchTerm.Type t)`
- `void setValue (java.lang.String value)`
- `boolean shouldCheckEffective ()`

---

## IdentitySelector.RoleAttributes

**Package:** `sailpoint.object`

**Description:** Returns query property used when value is null.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `IdentitySelector.RoleAttributes`
- `sailpoint.object.IdentitySelector.RoleAttributes`
- `java.io.Serializable`
- `java.lang.Comparable<IdentitySelector.RoleAttributes>`
- `IdentitySelector.IAttribute`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:**
- `java.lang.String getLocalizedMessage ()`
- `java.lang.String getLocalizedMessage (java.util.Locale locale, java.util.TimeZone timezone)`
- `java.lang.String getMessageKey ()`
- `java.lang.String getName ()`
- `java.lang.String getNullQueryProperty ()`
- `java.lang.String getType ()`
- `boolean isMultiValued ()`
- `staticIdentitySelector.RoleAttributes valueOf (java.lang.String name)`
- `staticIdentitySelector.RoleAttributes[] values ()`

---

## IdentitySelector

**Package:** `sailpoint.object`

**Description:** A class encapsulating various ways to select a population of identities. This is the basis for identity selection in entitlement SOD and advanced policies, as well as for role assignment rules and identity attribute visibility rules.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.IdentitySelector`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String SELECTOR_TYPE_FILTER`
- `static java.lang.String SELECTOR_TYPE_MATCH_LIST`
- `static java.lang.String SELECTOR_TYPE_POPULATION`
- `static java.lang.String SELECTOR_TYPE_RULE`
- `static java.lang.String SELECTOR_TYPE_SCRIPT`

**Methods:**
- `java.lang.String generateSummary ()`
- `CompoundFilter getFilter ()`
- `IdentitySelector.MatchExpression getMatchExpression ()`
- `GroupDefinition getPopulation ()`
- `Rule getRule ()`
- `Script getScript ()`
- `java.lang.String getSummary ()`
- `boolean isEmpty ()`
- `void setFilter ( CompoundFilter f)`
- `void setMatchExpression ( IdentitySelector.MatchExpression exp)`
- `void setPopulation ( GroupDefinition pop)`
- `void setRule ( Rule r)`
- `void setScript ( Script s)`
- `void setSummary (java.lang.String s)`

---

## IdentitySnapshot

**Package:** `sailpoint.object`

**Description:** A class used to hold historical information about identities. It contains a simplified representation of the full identity cube and can be used to track the roles and exceptional entitlements an identity has had over time. The createDate of the SailPoint object stores the date of each snapshot.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.IdentitySnapshot`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.Object clone ()`
- `java.lang.String getApplications ()`
- `java.util.List<RoleAssignmentSnapshot> getAssignedRoles ()`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.util.List<BundleSnapshot> getBundles ()`
- `java.util.List<BundleSnapshot> getBusinessRoles ()`
- `java.lang.String getDifferences ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `java.util.List<EntitlementSnapshot> getExceptions ()`
- `java.lang.String getIdentityId ()`
- `java.lang.String getIdentityName ()`
- `LinkSnapshot getLink (java.lang.String appName, java.lang.String instance, java.lang.String identity)`
- `java.util.List<LinkSnapshot> getLinks ()`
- `java.util.List<LinkSnapshot> getLinks (java.lang.String appName)`
- `java.util.List<LinkSnapshot> getLinks (java.lang.String appName, boolean includeCompositeLinks)`
- `LinkSnapshot getOwningCompositeLink ( LinkSnapshot componentLink)`
- `Scorecard getScorecard ()`
- `java.lang.String getSummary ()`
- `java.util.List<PolicyViolation> getViolations ()`
- `boolean isNameUnique ()`
- `void setApplications (java.lang.String names)`
- `void setApplicationsAndTruncate (java.lang.String applications)`
- `void setAssignedRoles (java.util.List< RoleAssignmentSnapshot > assignedRoles)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attrs)`
- `void setBundles (java.util.List< BundleSnapshot > bundles)`
- `void setDifferences (java.lang.String diffs)`
- `void setDifferencesAndTruncate (java.lang.String differences)`
- `void setExceptions (java.util.List< EntitlementSnapshot > exceptions)`
- `void setIdentityId (java.lang.String name)`
- `void setIdentityName (java.lang.String name)`
- `void setLinks (java.util.List< LinkSnapshot > links)`
- `void setScorecard ( Scorecard card)`
- `void setSummary (java.lang.String s)`
- `void setSummaryAndTruncate (java.lang.String summary)`
- `void setViolations (java.util.List< PolicyViolation > violations)`

---

## IdentityTrigger.InactiveCheck

**Package:** `sailpoint.object`

**Description:** used to declare the method parameters required for the inactiveChecker lambda

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `boolean isInactive ( IdentityTrigger trigger)`

---

## IdentityTrigger.Type

**Package:** `sailpoint.object`

**Description:** Enumeration of the possible event types.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `IdentityTrigger.Type`
- `sailpoint.object.IdentityTrigger.Type`
- `java.io.Serializable`
- `java.lang.Comparable<IdentityTrigger.Type>`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:**
- `java.lang.String getLocalizedMessage ()`
- `java.lang.String getLocalizedMessage (java.util.Locale locale, java.util.TimeZone timezone)`
- `boolean isComparesTwoIdentities ()`
- `boolean isNeedsNewIdentity ()`
- `boolean isNeedsPreviousIdentity ()`
- `staticIdentityTrigger.Type valueOf (java.lang.String name)`
- `staticIdentityTrigger.Type[] values ()`

---

## IdentityTrigger

**Package:** `sailpoint.object`

**Description:** An identity trigger is used used to determine when certain events happen to an identity. These are attached to some sort of action that will be executed when an identity meets the criteria of the trigger.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.IdentityTrigger`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String IDENTITY_PROCESSING_THRESHOLD`
- `static java.lang.String IDENTITY_PROCESSING_THRESHOLD_TYPE`
- `static java.lang.String MATCH_PARAM_PROCESS`
- `static java.lang.String PARAM_CERT_DEF_ID`
- `static java.lang.String PARAM_WORKFLOW`

**Methods:**
- `IdentityChangeEvent createEvent ( Identity prev, Identity neu)`
- `static boolean defaultInactiveCheck ( IdentityTrigger trigger)`
- `java.lang.String formatCause ( IdentityChangeEvent event)`
- `java.lang.String getAttributeName ()`
- `CertificationDefinition getCertificationDefinition ( Resolver r)`
- `java.lang.String getHandler ()`
- `java.lang.String getIdentityProcessingThreshold ()`
- `java.lang.String getIdentityProcessingThresholdType ()`
- `java.lang.String getMatchProcess ()`
- `java.lang.String getNewValueFilter ()`
- `java.lang.String getOldValueFilter ()`
- `Attributes<java.lang.String,​java.lang.Object> getParameters ()`
- `Rule getRule ()`
- `IdentitySelector getSelector ()`
- `IdentityTrigger.Type getType ()`
- `Workflow getWorkflow ( Resolver r)`
- `java.lang.String getWorkflowName ()`
- `boolean isInactive ()`
- `void load ()`
- `boolean matches ( Identity prevIdentity, Identity newIdentity, IdentityMatcher matcher, SailPointContext spContext)`
- `void setAttribute (java.lang.String attrName, java.lang.Object value)`
- `void setAttributeName (java.lang.String attributeName)`
- `void setCertificationDefinition ( CertificationDefinition def)`
- `void setHandler (java.lang.String handler)`
- `void setIdentityProcessingThreshold (java.lang.String value)`
- `void setIdentityProcessingThresholdType (java.lang.String type)`
- `void setMatchProcess (java.lang.String process)`
- `void setNewValueFilter (java.lang.String newValueFilter)`
- `void setOldValueFilter (java.lang.String oldValueFilter)`
- `void setParameters ( Attributes <java.lang.String,java.lang.Object> parameters)`
- `void setRule ( Rule rule)`
- `void setSelector ( IdentitySelector selector)`
- `void setType ( IdentityTrigger.Type type)`
- `void setWorkflow ( Workflow workflow)`
- `void setWorkflowName (java.lang.String s)`
- `void visit ( Visitor v)`

---

## IdentityTypeDefinition

**Package:** `sailpoint.object`

**Description:** An object defining a identity type. These are stored in the ObjectConfig named "Identity".

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.IdentityTypeDefinition`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String DEFAULT_TYPE_NAME`

**Methods:**
- `java.lang.String getDescription ()`
- `java.util.List<java.lang.String> getDisallowedAttributes ()`
- `java.lang.String getDisplayableName ()`
- `java.lang.String getDisplayName ()`
- `java.lang.String getManagerCertifierAttribute ()`
- `java.lang.String getName ()`
- `void setDescription (java.lang.String s)`
- `void setDisallowedAttributes (java.util.List<java.lang.String> val)`
- `void setDisplayName (java.lang.String displayName)`
- `void setManagerCertifierAttribute (java.lang.String managerCertifierAttribute)`
- `void setName (java.lang.String name)`

---

## ImpactAnalysis.PolicyConflict

**Package:** `sailpoint.object`

**Description:** Class tracking conflicts with SOD policies.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.ImpactAnalysis.PolicyConflict`

**Attributes:** N/A

**Methods:**
- `java.lang.String getConstraintName ()`
- `java.lang.String getDescription ()`
- `java.lang.String getPolicyName ()`
- `java.lang.String getRoleName ()`
- `void setConstraintName (java.lang.String s)`
- `void setDescription (java.lang.String s)`
- `void setPolicyName (java.lang.String s)`
- `void setRoleName (java.lang.String s)`

---

## ImpactAnalysis.RoleAssignments

**Package:** `sailpoint.object`

**Description:** Class tracking changes in role assignment.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.ImpactAnalysis.RoleAssignments`

**Attributes:**
- `static int DFLT_MAX_IDENTITIES`

**Methods:**
- `void addGain ( Identity id)`
- `void addLoss ( Identity id)`
- `java.util.List<java.lang.String> getGainedIdentities ()`
- `int getGains ()`
- `int getLosses ()`
- `java.util.List<java.lang.String> getLostIdentities ()`
- `java.lang.String getName ()`
- `java.lang.String getUid ()`
- `void incGains ()`
- `void incLosses ()`
- `void setGainedIdentities (java.util.List<java.lang.String> ids)`
- `void setGains (int i)`
- `void setLosses (int i)`
- `void setLostIdentities (java.util.List<java.lang.String> ids)`
- `void setMaxIdentities (int max)`
- `void setName (java.lang.String s)`

---

## ImpactAnalysis.Similarity

**Package:** `sailpoint.object`

**Description:** Class tracking objects with similar features.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.ImpactAnalysis.Similarity`

**Attributes:** N/A

**Methods:**
- `java.lang.String getName ()`
- `java.lang.String getOtherName ()`
- `int getPercent ()`
- `void setName (java.lang.String s)`
- `void setOtherName (java.lang.String s)`
- `void setPercent (int i)`

---

## ImpactAnalysis

**Package:** `sailpoint.object`

**Description:** Used to hold the results of an impact analysis on a role. These will be stored inside a TaskResult .

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ImpactAnalysis`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void add ( ImpactAnalysis.PolicyConflict pc)`
- `void add ( ImpactAnalysis.RoleAssignments ra)`
- `java.util.List<ImpactAnalysis.PolicyConflict> getPolicyConflicts ()`
- `int getRoleAssignmentCount ()`
- `java.util.List<ImpactAnalysis.RoleAssignments> getRoleAssignments ()`
- `java.util.List<ImpactAnalysis.Similarity> getSimilarities ()`
- `int getTotalPolicyConflicts ()`
- `int getTotalRoleGains ()`
- `int getTotalRoleLosses ()`
- `int getTotalRoleSimilarities ()`
- `void setPolicyConflicts (java.util.List< ImpactAnalysis.PolicyConflict > cons)`
- `void setRoleAssignments (java.util.List< ImpactAnalysis.RoleAssignments > roles)`
- `void setSimilarities (java.util.List< ImpactAnalysis.Similarity > sims)`

---

## ImportAction

**Package:** `sailpoint.object`

**Description:** An object intended for use only in XML import files. These are recognized by the Importer and trigger special operations during the import.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ImportAction`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String EXECUTE`
- `static java.lang.String INCLUDE`
- `static java.lang.String INSTALL_PLUGIN`
- `static java.lang.String LOG_CONFIG`
- `static java.lang.String MERGE`
- `static java.lang.String MERGE_CONNECTOR_REGISTRY`
- `static java.lang.String MERGE_IF_NULL`

**Methods:**
- `AbstractXmlObject getArgument ()`
- `Attributes getAttributes ()`
- `java.lang.String getDatabaseName ()`
- `java.lang.String getGroup ()`
- `java.lang.String getName ()`
- `java.lang.String getRevision ()`
- `java.lang.String getSystemVersion ()`
- `java.lang.String getValue ()`
- `void setArgument ( AbstractXmlObject arg)`
- `void setAttributes ( Attributes attrs)`
- `void setDatabaseName (java.lang.String databaseName)`
- `void setGroup (java.lang.String group)`
- `void setName (java.lang.String name)`
- `void setRevision (java.lang.String revision)`
- `void setSystemVersion (java.lang.String systemVersion)`
- `void setValue (java.lang.String value)`

---

## ImportMergable

**Package:** `sailpoint.object`

**Description:** As the name implies this interface is used during import to perform object specific merge behavior. Currently, QuickLink and WebResource are the only objects which utilize this interface

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `void merge (java.lang.Object obj)`

---

## IntegrationConfig.RoleSyncHistory

**Package:** `sailpoint.object`

**Description:** Used to maintain history about the roles sent to the IDM system.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.IntegrationConfig.RoleSyncHistory`

**Attributes:** N/A

**Methods:**
- `java.util.Date getModified ()`
- `java.lang.String getName ()`
- `boolean isTouched ()`
- `void setModified (java.util.Date d)`
- `void setName (java.lang.String s)`
- `void setTouched (boolean b)`

---

## IntegrationConfig

**Package:** `sailpoint.object`

**Description:** Class to hold configuration for an Identity Management (IDM) system integration.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.IntegrationConfig`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATT_GROUP_PROVISIONING`
- `static java.lang.String ATT_HOST`
- `static java.lang.String ATT_NAME`
- `static java.lang.String ATT_NO_GROUP_PERMISSIONS`
- `static java.lang.String ATT_NO_PERMISSIONS`
- `static java.lang.String ATT_NO_PROVISIONING_REQUESTS`
- `static java.lang.String ATT_OPERATIONS`
- `static java.lang.String ATT_PASSWORD`
- `static java.lang.String ATT_PASSWORD_CONFIRM`
- `static java.lang.String ATT_PROVISIONING_REQUEST_EXPIRATION`
- `static java.lang.String ATT_ROLE_SYNC_HISTORY`
- `static java.lang.String ATT_SCHEMA_PROVISIONING_MAP`
- `static java.lang.String ATT_STATUS_SUCCESS_IS_COMMITTED`
- `static java.lang.String ATT_UNIVERSAL_MANAGER`
- `static java.lang.String ATT_URL`
- `static java.lang.String ATT_USERNAME`
- `static java.lang.String EXEC_STYLE_REQUEST`
- `static java.lang.String EXEC_STYLE_SYNCHRONOUS`
- `static java.lang.String OP_SET_PASSWORD`
- `static java.lang.String ROLE_SYNC_STYLE_ASSIGNABLE`
- `static java.lang.String ROLE_SYNC_STYLE_DETECTABLE`
- `static java.lang.String ROLE_SYNC_STYLE_DUAL`
- `static java.lang.String ROLE_SYNC_STYLE_NONE`

**Methods:**
- `void add ( ManagedResource res)`
- `Application getApplication ()`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `boolean getBoolean (java.lang.String name)`
- `java.lang.String getExecStyle ()`
- `java.lang.String getExecutor ()`
- `int getInt (java.lang.String name)`
- `long getMaintenanceExpiration ()`
- `ManagedResource getManagedResource (java.lang.String name)`
- `ManagedResource getManagedResource ( Application app)`
- `Rule getPlanInitializer ()`
- `DynamicValue getPlanInitializerLogic ()`
- `Script getPlanInitializerScript ()`
- `ManagedResource getRemoteManagedResource (java.lang.String name)`
- `java.util.List<ManagedResource> getResources ()`
- `Bundle getRoleSyncContainer ()`
- `Filter getRoleSyncFilter ()`
- `java.util.List<IntegrationConfig.RoleSyncHistory> getRoleSyncHistory ()`
- `java.lang.String getRoleSyncStyle ()`
- `Signature getSignature ()`
- `java.lang.String getString (java.lang.String name)`
- `java.util.List<java.lang.String> getStringList (java.lang.String name)`
- `java.util.List<Bundle> getSynchronizedRoles ()`
- `boolean isExecStyleRequest ()`
- `boolean isExecStyleSynchronous ()`
- `boolean isGroupProvisioning ()`
- `boolean isGroupProvisioning (java.lang.String objectType)`
- `boolean isRoleSyncStyle (java.lang.String style)`
- `boolean isRoleSyncStyleAssignable ()`
- `boolean isRoleSyncStyleDetectable ()`
- `boolean isRoleSyncStyleDual ()`
- `boolean isTemplate ()`
- `boolean isUniversalManager ()`
- `void removeManagedResource ( Application app)`
- `void removeSynchronizedRole ( Bundle role)`
- `void setApplication ( Application app)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> a)`
- `void setExecStyle (java.lang.String s)`
- `void setExecutor (java.lang.String s)`
- `void setMaintenanceExpiration (long i)`
- `void setPlanInitializer ( Rule initializer)`
- `void setPlanInitializerScript ( Script script)`
- `void setResources (java.util.List< ManagedResource > resources)`
- `void setRoleSyncContainer ( Bundle b)`
- `void setRoleSyncFilter ( Filter f)`
- `void setRoleSyncHistory (java.util.List< IntegrationConfig.RoleSyncHistory > history)`
- `void setRoleSyncStyle (java.lang.String style)`
- `void setSignature ( Signature s)`
- `void setSynchronizedRoles (java.util.List< Bundle > roles)`
- `void setTemplate (boolean b)`
- `boolean supportedOperation (java.lang.String op)`
- `void visit ( Visitor v)`

---

## IntegrationExecutor

**Package:** `sailpoint.object`

**Description:** Deprecated.

**Inherited Classes/Interfaces:**
- `IntegrationInterface`

**Attributes:** N/A

**Methods:**
- `void finishRoleDefinition ( IntegrationConfig config, Bundle src, RoleDefinition dest)`

---

## InterceptedDelete

**Package:** `sailpoint.object`

**Description:** Let the ScopeService know this class does not have a scope.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.InterceptedDelete`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `java.lang.String getExtractConfigName ()`
- `java.lang.String getExtractedObjectJson ()`
- `java.lang.Long getExtractExecutionTimeMs ()`
- `java.util.Date getObjectCreatedDate ()`
- `java.util.Date getObjectDeletedDate ()`
- `java.lang.String getObjectId ()`
- `java.lang.String getObjectName ()`
- `java.lang.String getObjectType ()`
- `java.lang.String getTransformConfigName ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `void setExtractConfigName (java.lang.String extractConfigName)`
- `void setExtractedObjectJson (java.lang.String json)`
- `void setExtractExecutionTimeMs (java.lang.Long extractExecutionTimeMs)`
- `void setObjectCreatedDate (java.util.Date objectCreatedDate)`
- `void setObjectDeletedDate (java.util.Date objectDeletedDate)`
- `void setObjectId (java.lang.String objectId)`
- `void setObjectName (java.lang.String objectName)`
- `void setObjectType (java.lang.String objectType)`
- `void setTransformConfigName (java.lang.String transformConfigName)`
- `java.lang.String toString ()`

---

## InvalidEscalationTargetException

**Package:** `sailpoint.object`

**Description:** An exception thrown when a Notifiable item is escalated to someone not capable of receiving the item.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `java.lang.Throwable`
- `java.lang.Exception`
- `java.lang.RuntimeException`
- `java.lang.IllegalArgumentException`
- `sailpoint.object.InvalidEscalationTargetException`
- `java.io.Serializable`

**Attributes:** N/A

**Methods:**
- `java.lang.String getProposedTarget ()`

---

## JasperResult

**Package:** `sailpoint.object`

**Description:** The definition of a JasperResult. This object is a wrapper around the JasperPrint object.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.JasperResult`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `void addAttribute (java.lang.String key, java.lang.Object value)`
- `void addFile ( PersistedFile file)`
- `java.lang.Object clone ()`
- `java.lang.Object getAttribute (java.lang.String attribute)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `PersistedFile getFileByType (java.lang.String contentType)`
- `java.util.List<PersistedFile> getFiles ()`
- `java.lang.String getHandlerId ()`
- `int getHandlerPageCount ()`
- `net.sf.jasperreports.engine.JasperPrint getJasperPrint ()`
- `java.lang.String getName ()`
- `int getPageCount ()`
- `sailpoint.reporting.export.PageHandler getPageHandler ()`
- `int getPagesPerBucket ()`
- `java.lang.String getPrintXml ()`
- `boolean hasName ()`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> atts)`
- `void setFiles (java.util.List< PersistedFile > files)`
- `void setHandlerId (java.lang.String id)`
- `void setHandlerPageCount (int count)`
- `void setJasperPrint (net.sf.jasperreports.engine.JasperPrint print)`
- `void setPageCount (int count)`
- `void setPagesPerBucket (int bucketSize)`
- `void setPrintXml (java.lang.String xml)`
- `void visit ( Visitor v)`

---

## JasperTemplate

**Package:** `sailpoint.object`

**Description:** The definition of a JasperTemplate. This is the object where JasperReport objects can be stored off in the repository. The design is the xml format, but the JasperReport object is the actual representation of a compiled report. The main difference between a report and a report design is that reports are already compiled and validated, so many characteristics are read only.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.JasperTemplate`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.Object clone ()`
- `void compile ()`
- `net.sf.jasperreports.engine.design.JasperDesign getDesign ()`
- `net.sf.jasperreports.engine.design.JasperDesign getDesign (boolean forceLoad)`
- `java.lang.String getDesignXml ()`
- `java.lang.String getName ()`
- `net.sf.jasperreports.engine.JasperReport getReport ()`
- `void setDesignXml (java.lang.String xml)`
- `void setReport (net.sf.jasperreports.engine.JasperReport report)`

---

## JavaRuleContext

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.JavaRuleContext`

**Attributes:** N/A

**Methods:**
- `Attributes<java.lang.String,​java.lang.Object> getArguments ()`
- `boolean getBoolean (java.lang.String name)`
- `SailPointContext getContext ()`
- `java.util.Date getDate (java.lang.String name)`
- `int getInt (java.lang.String name)`
- `java.lang.String getString (java.lang.String name)`

---

## JavaRuleExecutor

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `java.lang.Object execute ( JavaRuleContext context)`

---

## LimitReassignmentException

**Package:** `sailpoint.object`

**Description:** Exception thrown when amount of reassignment exceeds the defined limit of reassignment.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `java.lang.Throwable`
- `java.lang.Exception`
- `sailpoint.tools.AbstractLocalizableException`
- `sailpoint.tools.GeneralException`
- `sailpoint.object.LimitReassignmentException`
- `java.io.Serializable`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:** N/A

---

## Link

**Package:** `sailpoint.object`

**Description:** Class used represent accounts on applications correlated to an identity.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Link`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `java.lang.Comparable<Link>`
- `EntitlementDataSource`
- `LinkInterface`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATT_RENAMED_ACCOUNT_NATIVE_IDENTITIES`
- `static java.lang.String ATT_RENAMED_GROUP_NATIVE_IDENTITIES`

**Methods:**
- `void addComponent ( Link comp)`
- `java.lang.Object clone ()`
- `int compareTo ( Link other)`
- `boolean equals (java.lang.Object o)`
- `Application getApplication ()`
- `java.lang.String getApplicationId ()`
- `java.lang.String getApplicationName ()`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `boolean getBooleanAttribute (java.lang.String name)`
- `java.lang.String getComponentIds ()`
- `java.lang.String getDisplayableName ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `java.lang.String getDisplayName ()`
- `Attributes getEntitlementAttributes ()`
- `java.util.List<Entitlement> getEntitlements (java.util.Locale locale, java.lang.String attributeFilter)`
- `java.util.Map<java.lang.String,​java.lang.Object> getExtendedAttributes ()`
- `java.util.List<Permission> getFlattenedPermissions ()`
- `Identity getIdentity ()`
- `java.lang.Boolean getIiqDisabled ()`
- `java.lang.Boolean getIiqLocked ()`
- `java.lang.String getInstance ()`
- `java.lang.String getKey1 ()`
- `java.lang.String getKey2 ()`
- `java.lang.String getKey3 ()`
- `java.lang.String getKey4 ()`
- `java.util.Date getLastRefresh ()`
- `java.util.Date getLastTargetAggregation ()`
- `java.lang.String getNativeIdentity ()`
- `staticObjectConfig getObjectConfig ()`
- `Attributes<java.lang.String,​java.lang.Object> getOldAttributes ()`
- `java.lang.String getPasswordHistory ()`
- `java.util.List<Permission> getPermissions ()`
- `Permission getSinglePermission (java.lang.String target)`
- `java.util.List<Permission> getTargetPermissions ()`
- `java.lang.String getUuid ()`
- `boolean hasEntitlements ()`
- `boolean hasName ()`
- `boolean isComposite ()`
- `boolean isDisabled ()`
- `boolean isEntitlements ()`
- `boolean isLocked ()`
- `boolean isManuallyCorrelated ()`
- `void setApplication ( Application res)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attrs)`
- `void setComponentIds (java.lang.String csv)`
- `void setDisplayName (java.lang.String displayName)`
- `void setEntitlements (boolean entitlements)`
- `void setIdentity ( Identity id)`
- `void setIiqDisabled (java.lang.Boolean iiqDisabled)`
- `void setIiqLocked (java.lang.Boolean iiqLocked)`
- `void setInstance (java.lang.String s)`
- `void setKey1 (java.lang.String s)`
- `void setKey2 (java.lang.String s)`
- `void setKey3 (java.lang.String s)`
- `void setKey4 (java.lang.String s)`
- `void setLastRefresh (java.util.Date d)`
- `void setLastTargetAggregation (java.util.Date d)`
- `void setManuallyCorrelated (boolean manual)`
- `void setNativeIdentity (java.lang.String id)`
- `void setOldAttributes ( Attributes <java.lang.String,java.lang.Object> atts)`
- `void setPasswordHistory (java.lang.String hist)`
- `void setSinglePermission ( Permission single)`
- `void setUuid (java.lang.String id)`
- `static void sort (java.util.List< Link > links)`
- `java.lang.String toString ()`
- `void visit ( Visitor v)`

---

## LinkExternalAttribute

**Package:** `sailpoint.object`

**Description:** Extension of ExternalAttribute to define a table for the storage of multi-valued extended attribute for Link objects.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.ExternalAttribute`
- `sailpoint.object.LinkExternalAttribute`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:** N/A

---

## LinkInterface

**Package:** `sailpoint.object`

**Description:** An read-only interface for Links (for example - application accounts). This provides a common interface to Links and LinkSnapshots.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `java.lang.String getApplicationName ()`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getDisplayableName ()`
- `java.lang.String getDisplayName ()`
- `java.lang.String getId ()`
- `java.lang.String getInstance ()`
- `java.util.Date getLastRefresh ()`
- `java.lang.String getNativeIdentity ()`

---

## LinkSnapshot

**Package:** `sailpoint.object`

**Description:** An object which represents a definition of a Link a given point in time. This object is serialized as xml and is a private object of IdentitySnapshot object.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.LinkSnapshot`
- `java.io.Serializable`
- `LinkInterface`

**Attributes:** N/A

**Methods:**
- `void assimilate ( Link link)`
- `java.lang.Object clone ()`
- `java.lang.String getApplication ()`
- `java.lang.String getApplicationName ()`
- `Attributes getAttributes ()`
- `java.lang.String getComponentIds ()`
- `java.lang.String getDisplayableName ()`
- `java.lang.String getDisplayName ()`
- `java.lang.String getId ()`
- `java.lang.String getInstance ()`
- `java.util.Date getLastRefresh ()`
- `java.lang.String getNativeIdentity ()`
- `java.lang.String getSimpleIdentity ()`
- `void setApplication (java.lang.String name)`
- `void setAttributes ( Attributes attrs)`
- `void setComponentIds (java.lang.String csv)`
- `void setId (java.lang.String id)`
- `void setInstance (java.lang.String ins)`
- `void setLastRefresh (java.util.Date refreshDate)`
- `void setNativeIdentity (java.lang.String identity)`
- `void setSimpleIdentity (java.lang.String identity)`

---

## LiveReport.LiveReportSummary

**Package:** `sailpoint.object`

**Description:** Configuration object for report summary tables. This includes the list of values to display, the data source and a title.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.LiveReport.LiveReportSummary`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getDataSourceClass ()`
- `LiveReport.LiveReportSummaryDataSource getDataSourceInstance ()`
- `Rule getDataSourceRule ()`
- `Script getDataSourceScript ()`
- `java.lang.String getTitle ()`
- `java.util.List<java.util.Map<java.lang.String,​java.lang.String>> getValueMap ()`
- `java.util.List<LiveReport.LiveReportSummaryValue> getValues ()`
- `void setData (java.util.Map<java.lang.String,java.lang.Object> dataSource)`
- `void setDataSourceClass (java.lang.String dataSourceClass)`
- `void setDataSourceRule ( Rule dataSourceRule)`
- `void setDataSourceScript ( Script dataSourceScript)`
- `void setTitle (java.lang.String title)`
- `void setValues (java.util.List< LiveReport.LiveReportSummaryValue > values)`

---

## LiveReport.LiveReportSummaryDataSource

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `Attributes<java.lang.String,​java.lang.Object> getData ( SailPointContext ctx, Attributes <java.lang.String,java.lang.Object> args)`

---

## LiveReport.LiveReportSummaryValue

**Package:** `sailpoint.object`

**Description:** An individual value in a report summary table. They are made up of a unique identifier - the name, a label and a value.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.LiveReport.LiveReportSummaryValue`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getLabel ()`
- `java.lang.String getName ()`
- `java.lang.Object getValue ()`
- `void setLabel (java.lang.String label)`
- `void setName (java.lang.String name)`
- `void setValue (java.lang.Object value)`

---

## LiveReport

**Package:** `sailpoint.object`

**Description:** Configuration object for a 'live' report. LiveReports are our latest report implementation. They allow for previewing of report data before the report is run. LiveReports always display data in a grid format. They can optionally include a table of summary data, or a chart.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.LiveReport`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void addExtendedArgument ( Argument arg)`
- `Chart getChart ()`
- `ReportDataSource getDataSource ()`
- `java.lang.String getDisablePreviewMessage ()`
- `java.util.List<Argument> getExtendedArguments ()`
- `Rule getExtendedColumnRule ()`
- `Script getExtendedColumnScript ()`
- `DynamicValue getExtendedColumnsDef ()`
- `Form getForm ()`
- `ReportColumnConfig getGridColumnByFieldName (java.lang.String field)`
- `java.util.List<ReportColumnConfig> getGridColumns ()`
- `Rule getInitializationRule ()`
- `Script getInitializationScript ()`
- `DynamicValue getInitializerDef ()`
- `LiveReport.LiveReportSummary getReportHeader ()`
- `LiveReport.LiveReportSummary getReportSummary ()`
- `java.lang.String getTitle ()`
- `DynamicValue getValidationDef ()`
- `Rule getValidationRule ()`
- `Script getValidationScript ()`
- `boolean hasChart ()`
- `boolean hasExtendedColumns ()`
- `boolean hasHeader ()`
- `boolean hasInitializer ()`
- `boolean hasSummary ()`
- `boolean hasValidation ()`
- `boolean isDisablePreview ()`
- `void mergeExtendedColumns (java.util.List< ReportColumnConfig > newColumns)`
- `void reorderGridColumns (java.util.List<java.lang.String> visibleColumns)`
- `void setChart ( Chart chart)`
- `void setDataSource ( ReportDataSource dataSource)`
- `void setDisablePreview (boolean disablePreview)`
- `void setDisablePreviewMessage (java.lang.String disablePreviewMessage)`
- `void setExtendedArguments (java.util.List< Argument > extendedArguments)`
- `void setExtendedColumnRule ( Rule extendedColumnRule)`
- `void setExtendedColumnScript ( Script extendedColumnScript)`
- `void setForm ( Form form)`
- `void setGridColumns (java.util.List< ReportColumnConfig > gridColumns)`
- `void setInitializationRule ( Rule initializationRule)`
- `void setInitializationScript ( Script initializationScript)`
- `void setReportHeader ( LiveReport.LiveReportSummary header)`
- `void setReportSummary ( LiveReport.LiveReportSummary summary)`
- `void setTitle (java.lang.String title)`
- `void setValidationRule ( Rule validationRule)`
- `void setValidationScript ( Script validationScript)`

---

## LocalizedAttribute

**Package:** `sailpoint.object`

**Description:** This class represents an attribute which has been localized into a specific language. For example, for an attribute description there will be multiple localized attribute objects with the same targetId, but different locales representing the various languages the system may support.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.LocalizedAttribute`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.String getAttribute ()`
- `java.lang.String getLocale ()`
- `java.lang.String getTargetClass ()`
- `java.lang.String getTargetId ()`
- `java.lang.String getTargetName ()`
- `java.lang.String getValue ()`
- `boolean hasAssignedScope ()`
- `void setAttribute (java.lang.String attribute)`
- `void setLocale (java.lang.String locale)`
- `void setTargetClass (java.lang.String targetClass)`
- `void setTargetId (java.lang.String targetId)`
- `void setTargetName (java.lang.String targetName)`
- `void setValue (java.lang.String value)`
- `void visit ( Visitor v)`

---

## LockInfo

**Package:** `sailpoint.object`

**Description:** Helper class for managing the SailPointObject.lock property. The lock property is a string formatted using a delimiter between the sub-fields. This class provides a parser for that string and a more convenient programming model.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.LockInfo`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static int DEFAULT_LOCK_TIMEOUT`
- `static int DEFAULT_LONG_LOCK_TIMEOUT`
- `static int MAX_LOCK_TIMEOUT`

**Methods:**
- `java.lang.String describe ()`
- `java.util.Date getAcquired ()`
- `java.lang.String getContext ()`
- `java.util.Date getExpiration ()`
- `int getLockTimeout ()`
- `java.lang.String getName ()`
- `static java.lang.String getThreadLockContext ()`
- `static java.lang.String getThreadLockId ()`
- `boolean isExpired ()`
- `void parse (java.lang.String src)`
- `static java.lang.String peekThreadLockId ()`
- `void print ()`
- `void refresh ()`
- `void refresh (int minutes)`
- `java.lang.String render ()`
- `void setAcquired (java.util.Date d)`
- `static void setConfiguration ( Configuration config)`
- `void setContext (java.lang.String s)`
- `void setExpiration (java.util.Date d)`
- `void setLockTimeout (int minutes)`
- `void setName (java.lang.String name)`
- `static void setThreadLockContext (java.lang.String s)`
- `static boolean verify ( SailPointObject obj, java.lang.String task)`

---

## LogField

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.LogField`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `boolean dropNulls ()`
- `boolean getDropNulls ()`
- `java.lang.String getName ()`
- `boolean getTrim ()`
- `void setDropNulls (boolean drop)`
- `void setName (java.lang.String name)`
- `void setTrim (boolean trim)`
- `boolean shouldTrim ()`

---

## MFAConfig

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.MFAConfig`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `boolean equals (java.lang.Object o)`
- `java.util.List<DynamicScope> getPopulations ()`
- `Workflow getWorkflow ()`
- `int hashCode ()`
- `boolean isEnabled ()`
- `void setEnabled (boolean enabled)`
- `void setPopulations (java.util.List< DynamicScope > populations)`
- `void setWorkflow ( Workflow workflow)`

---

## ManagedAttribute.Type

**Package:** `sailpoint.object`

**Description:** A non-permission entitlement.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ManagedAttribute.Type`
- `sailpoint.object.ManagedAttribute.Type`
- `java.io.Serializable`
- `java.lang.Comparable<ManagedAttribute.Type>`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:**
- `java.lang.String getLocalizedMessage ()`
- `java.lang.String getLocalizedMessage (java.util.Locale locale, java.util.TimeZone timezone)`
- `java.lang.String getMessageKey ()`
- `staticManagedAttribute.Type valueOf (java.lang.String name)`
- `staticManagedAttribute.Type[] values ()`

---

## ManagedAttribute

**Package:** `sailpoint.object`

**Description:** ManagedAttributes represent attribute or permission values on applications that are managed by IdentityIQ. This serves as a registry to lookup managed attributes, and also holds meta data about each attribute. Originally this was geared toward providing entitlement descriptions, but has evolved to contain other interesting information (such as owner, etc...) As of 6.0 AccountGroups and ManagedAttributes were merged and because of this ManagedAttribute grew a few new properties including a group flag to indicate if the MA was aggregate directly from a MA. Here is the mapping from AccountGroup to ManagedAttribute AccountGroup.name -> ManagedAttribute.displayName AccountGroup.nativeIdentity -> ManagedAttribute.value AccountGroup.application -> ManagedAttribute.purview(application) AccountGroup.inheritance -> ManagedAttribute.inheritance AccountGroup.permissions -> ManagedAttribute.permissions AccountGroup.targetPermissions -> ManagedAttribute.targetPermissions AccountGroup.uncorrelated -> ManagedAttribute.uncorrelated AccountGroup.lastRefresh -> ManagedAttribute.lastRefresh AccountGroup.key1 -> ManagedAttribute.key1 AccountGroup.key2 -> ManagedAttribute.key2 AccountGroup.key3 -> ManagedAttribute.key3 AccountGroup.key4 -> ManagedAttribute.key4

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.AbstractCertifiableEntity`
- `sailpoint.object.ManagedAttribute`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `Classifiable`
- `Describable`
- `EntitlementDataSource`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String CONFIG_DEFAULT_LANG`
- `static java.lang.String CONFIG_LANGUAGES`
- `static java.lang.String OLD_PERMISSION_ATTRIBUTE`
- `static java.lang.String PROV_AI_GENERATED_DESCRIPTION_LOCALES`
- `static java.lang.String PROV_ATTRIBUTE`
- `static java.lang.String[] PROV_ATTRIBUTES`
- `static java.lang.String PROV_CLASSIFICATIONS`
- `static java.lang.String PROV_DESCRIPTIONS`
- `static java.lang.String PROV_DISPLAY_NAME`
- `static java.lang.String PROV_IIQ_ELEVATED_ACCESS`
- `static java.lang.String PROV_MANAGED_ATTRIBUTE_TYPE`
- `static java.lang.String PROV_OWNER`
- `static java.lang.String PROV_REQUESTABLE`
- `static java.lang.String PROV_SCOPE`
- `static java.util.Comparator<ManagedAttribute> SP_ACCOUNTGROUP_BY_MODIFIED`
- `static java.util.Comparator<ManagedAttribute> SP_ACCOUNTGROUP_BY_NAME`
- `static java.util.Comparator<ManagedAttribute> SP_ACCOUNTGROUP_BY_NATIVE_IDENTITY`
- `static java.util.Comparator<ManagedAttribute> SP_ACCOUNTGROUP_BY_OWNER`
- `static java.lang.String[] SYSTEM_ATTRIBUTES`

**Methods:**
- `void add ( Permission p)`
- `void addDescription (java.lang.String locale, java.lang.String desc)`
- `java.lang.Object get (java.lang.String name)`
- `java.lang.String getAiGeneratedDescriptionLocales ()`
- `java.util.List<Permission> getAllPermissions ()`
- `Application getApplication ()`
- `java.lang.String getApplicationId ()`
- `java.util.List<TargetAssociation> getAssociations ()`
- `java.lang.String getAttribute ()`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `static java.lang.String getDefaultLanguage ()`
- `java.lang.String getDescription ()`
- `java.lang.String getDescription (java.lang.String locale)`
- `java.lang.String getDescription (java.lang.String locale, boolean fallbackToDefaultLang)`
- `java.lang.String getDescription (java.util.Locale locale)`
- `java.util.Map<java.lang.String,​java.lang.String> getDescriptions ()`
- `java.lang.String getDisplayableName ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `java.lang.String getDisplayName ()`
- `java.util.List<Entitlement> getEntitlements (java.util.Locale locale, java.lang.String attributeOrPermissionFilter)`
- `java.util.List<EntitlementGroup> getExceptions (java.util.List< Application > apps)`
- `Attributes<java.lang.String,​java.lang.Object> getExtendedAttributes ()`
- `java.lang.String getFullName ()`
- `java.lang.String getHash ()`
- `java.util.List<ManagedAttribute> getInheritance ()`
- `java.lang.String getInstance ()`
- `java.lang.String getKey1 ()`
- `java.lang.String getKey2 ()`
- `java.lang.String getKey3 ()`
- `java.lang.String getKey4 ()`
- `java.util.Date getLastRefresh ()`
- `java.util.Date getLastTargetAggregation ()`
- `java.lang.String getMemberAttribute ()`
- `java.lang.String getNativeIdentity ()`
- `staticObjectConfig getObjectConfig ()`
- `java.util.List<Permission> getPermissions ()`
- `static java.util.List<java.lang.String> getPropertiesForLocale (java.util.Locale locale)`
- `java.lang.String getPurview ()`
- `java.lang.String getReferenceAttribute ()`
- `Permission getSinglePermission (java.lang.String target)`
- `static java.util.List<java.lang.String> getSupportedLanguages ()`
- `java.util.List<Permission> getTargetPermissions ()`
- `java.lang.String getType ()`
- `java.lang.String getTypeFromAccountGroup ( AccountGroup ag)`
- `java.lang.String getTypeName (boolean plural)`
- `java.lang.String getUuid ()`
- `java.lang.String getValue ()`
- `boolean hasName ()`
- `boolean isAggregated ()`
- `boolean isAutoPromotion ()`
- `boolean isDifferencable ()`
- `boolean isGroup ()`
- `boolean isGroupType ()`
- `boolean isIiqElevatedAccess ()`
- `boolean isPermission ()`
- `static boolean isPermission (java.lang.String type)`
- `boolean isRequestable ()`
- `static boolean isSystemAttribute (java.lang.String name)`
- `boolean isUncorrelated ()`
- `void load ()`
- `void put (java.lang.String name, java.lang.Object value)`
- `void refresh ( AccountGroup ag)`
- `void setAggregated (boolean aggregated)`
- `void setAiGeneratedDescriptionLocales (java.lang.String locales)`
- `void setApplication ( Application application)`
- `void setAssociations (java.util.List< TargetAssociation > assocs)`
- `void setAttribute (java.lang.String att)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> atts)`
- `void setDescription (java.lang.String s)`
- `void setDescriptions (java.util.Map<java.lang.String,java.lang.String> map)`
- `void setDisplayName (java.lang.String displayName)`
- `void setGroup (boolean b)`
- `void setHash (java.lang.String s)`
- `void setIiqElevatedAccess (boolean b)`
- `void setInheritance (java.util.List< ManagedAttribute > groups)`
- `void setInstance (java.lang.String ins)`
- `void setKey1 (java.lang.String s)`
- `void setKey2 (java.lang.String s)`
- `void setKey3 (java.lang.String s)`
- `void setKey4 (java.lang.String s)`
- `void setLastRefresh (java.util.Date d)`
- `void setLastTargetAggregation (java.util.Date d)`
- `void setMemberAttribute (java.lang.String name)`
- `void setNativeIdentity (java.lang.String id)`
- `void setPermissions (java.util.List< Permission > perms)`
- `void setPurview (java.lang.String purview)`
- `void setReferenceAttribute (java.lang.String s)`
- `void setRequestable (boolean requestable)`
- `void setSinglePermission ( Permission single)`
- `void setTargetPermissions (java.util.List< Permission > perms)`
- `void setType (java.lang.String type)`
- `void setUncorrelated (boolean b)`
- `void setUuid (java.lang.String id)`
- `void setValue (java.lang.String val)`
- `java.lang.String toString ()`
- `void visit ( Visitor v)`

---

## ManagedResource.OperationTransformation

**Package:** `sailpoint.object`

**Description:** Mapping from one account operation to another account operation.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.ManagedResource.OperationTransformation`

**Attributes:** N/A

**Methods:**
- `ProvisioningPlan.AccountRequest.Operation getDestination ()`
- `ProvisioningPlan.AccountRequest.Operation getSource ()`
- `void setDestination ( ProvisioningPlan.AccountRequest.Operation destination)`
- `void setSource ( ProvisioningPlan.AccountRequest.Operation source)`

---

## ManagedResource.ResourceAttribute

**Package:** `sailpoint.object`

**Description:** Class used to represent one name mapping between an external attributes and an IdentityIQ application attribute.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.ManagedResource.ResourceAttribute`

**Attributes:** N/A

**Methods:**
- `java.lang.String getLocalName ()`
- `java.lang.String getName ()`
- `void setLocalName (java.lang.String s)`
- `void setName (java.lang.String s)`

---

## ManagedResource

**Package:** `sailpoint.object`

**Description:** Class used to define name mappings for resources. The attribute map is keyed by IdentityIQ attribute name and the value is the target attribute name. A list of these will be maintained within the IntegrationConfig, search structures are built at runtime.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.ManagedResource`

**Attributes:** N/A

**Methods:**
- `void add ( ManagedResource.ResourceAttribute att)`
- `void addOperationTransformation ( ProvisioningPlan.AccountRequest.Operation from, ProvisioningPlan.AccountRequest.Operation to)`
- `Application getApplication ()`
- `java.lang.String getIdentityAttribute ()`
- `java.lang.String getLocalName ()`
- `java.lang.String getName ()`
- `java.util.List<ManagedResource.OperationTransformation> getOperationTransformations ()`
- `ManagedResource.ResourceAttribute getRemoteResourceAttribute (java.lang.String name)`
- `ManagedResource.ResourceAttribute getResourceAttribute (java.lang.String localName)`
- `java.lang.String getResourceAttributeName (java.lang.String localName)`
- `java.util.List<ManagedResource.ResourceAttribute> getResourceAttributes ()`
- `java.lang.String getResourceName ()`
- `boolean hasResourceAttributes ()`
- `void load ()`
- `void setApplication ( Application app)`
- `void setIdentityAttribute (java.lang.String s)`
- `void setName (java.lang.String s)`
- `void setOperationTransformations (java.util.List< ManagedResource.OperationTransformation > ops)`
- `void setResourceAttributes (java.util.List< ManagedResource.ResourceAttribute > atts)`
- `ProvisioningPlan.AccountRequest.Operation transformOperation ( ProvisioningPlan.AccountRequest.Operation op)`

---

## MapDTO

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.web.PageCodeBase`
- `sailpoint.web.BaseBean`
- `sailpoint.object.MapDTO`
- `javax.faces.component.StateHolder`
- `sailpoint.web.UserContext`

**Attributes:** N/A

**Methods:**
- `java.lang.String getId ()`
- `java.lang.String getKey ()`
- `java.lang.Object getValue ()`
- `void setId (java.lang.String id)`
- `void setKey (java.lang.String key)`
- `void setValue (java.lang.Object value)`

---

## MessageTemplate

**Package:** `sailpoint.object`

**Description:** Used to define a parameterized message. This is similar to an EmailTemplate, except that it has no mail delivery baggage, it is only a string of text with optional variable references. The original use for these was to format the description and details fields for work items. The messages can be formatted with the original variable This is used less (at all?) now that there are workflows.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.MessageTemplate`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.String getText ()`
- `void load ()`
- `java.lang.String render (java.util.Map arguments)`
- `void setText (java.lang.String s)`

---

## MiningConfig.MiningAttribute

**Package:** `sailpoint.object`

**Description:** Return true if a given atomic value is allowed.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.MiningConfig.MiningAttribute`

**Attributes:** N/A

**Methods:**
- `java.lang.String getName ()`
- `java.util.List<java.lang.String> getValues ()`
- `boolean isAllowed (java.lang.Object value)`
- `boolean isNegative ()`
- `boolean isPermission ()`
- `void setName (java.lang.String s)`
- `void setNegative (boolean b)`
- `void setPermission (boolean b)`
- `void setValues (java.util.List<java.lang.String> values)`

---

## MiningConfig.MiningSource

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.MiningConfig.MiningSource`

**Attributes:** N/A

**Methods:**
- `Application getApplication ()`
- `java.util.List<MiningConfig.MiningAttribute> getAttributes ()`
- `void load ()`
- `void setApplication ( Application a)`
- `void setAttributes (java.util.List< MiningConfig.MiningAttribute > atts)`

---

## MiningConfig

**Package:** `sailpoint.object`

**Description:** An object encapsulating the parameters for one undirected role mining session.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.MiningConfig`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ALG_BUCKET`
- `static java.lang.String ALG_WEKA`
- `static java.lang.String ARG_ALGORITHM`
- `static java.lang.String ARG_APPLICATIONS`
- `static java.lang.String ARG_BINARY_SPLITS`
- `static java.lang.String ARG_CLUSTER_DEBUG`
- `static java.lang.String ARG_CONFIDENCE`
- `static java.lang.String ARG_EXT_MINING_CLASS`
- `static java.lang.String ARG_EXT_MINING_CLASSPATH`
- `static java.lang.String ARG_FOLDS`
- `static java.lang.String ARG_INCLUDE_MANAGER`
- `static java.lang.String ARG_LAPLACE`
- `static java.lang.String ARG_MAX_INSTANCES`
- `static java.lang.String ARG_MAX_ITERATIONS`
- `static java.lang.String ARG_MAX_ROLES`
- `static java.lang.String ARG_MIN_DEVIATION`
- `static java.lang.String ARG_MIN_INSTANCES`
- `static java.lang.String ARG_MIN_USAGE`
- `static java.lang.String ARG_NO_CLEANUP`
- `static java.lang.String ARG_NO_PRUNING`
- `static java.lang.String ARG_NO_SUBTREE_RAISING`
- `static java.lang.String ARG_NUM_CLUSTERS`
- `static java.lang.String ARG_POPULATION`
- `static java.lang.String ARG_REDUCED_ERROR_PRUNING`
- `static java.lang.String ARG_SEED`
- `static java.lang.String DEF_CONFIDENCE`
- `static java.lang.String DEF_FOLDS`
- `static java.lang.String DEF_MAX_INSTANCES`
- `static java.lang.String DEF_MAX_ITERATIONS`
- `static java.lang.String DEF_MIN_DEVIATION`
- `static java.lang.String DEF_MIN_INSTANCES`
- `static java.lang.String DEF_NUM_CLUSTERS`

**Methods:**
- `void add ( MiningConfig.MiningSource src)`
- `java.lang.Object get (java.lang.String name)`
- `java.lang.String getAlgorithm ()`
- `Attributes<java.lang.String,​java.lang.Object> getArguments ()`
- `boolean getBoolean (java.lang.String name)`
- `float getFloat (java.lang.String name)`
- `float getFloat (java.lang.String name, float dflt)`
- `int getInt (java.lang.String name)`
- `int getInt (java.lang.String name, int dflt)`
- `MiningConfig.MiningSource getSource ( Application app)`
- `java.util.List<MiningConfig.MiningSource> getSources ()`
- `java.util.List<MiningConfig.MiningSource> getSources ( Resolver r)`
- `java.lang.String getSourceSummary ()`
- `java.lang.String getString (java.lang.String name)`
- `void initArguments ()`
- `void load ()`
- `void put (java.lang.String name, java.lang.Object value)`
- `void setAlgorithm (java.lang.String s)`
- `void setArguments ( Attributes <java.lang.String,java.lang.Object> args)`
- `void setSources (java.util.List< MiningConfig.MiningSource > sources)`
- `void upgrade ( Resolver r)`

---

## MiningStatistics

**Package:** `sailpoint.object`

**Description:** An object used to maintain various statistics related to role mining. One of these might be attached to a Bundle object if it was defined by mining.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.MiningStatistics`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `int getMatches ()`
- `int getMatchPercentage ()`
- `void setMatches (int i)`
- `void setMatchPercentage (int i)`

---

## MitigationExpiration.Action

**Package:** `sailpoint.object`

**Description:** Enumeration of the different types of actions that can be executed when a mitigation expires.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `MitigationExpiration.Action`
- `sailpoint.object.MitigationExpiration.Action`
- `java.io.Serializable`
- `java.lang.Comparable<MitigationExpiration.Action>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticMitigationExpiration.Action valueOf (java.lang.String name)`
- `staticMitigationExpiration.Action[] values ()`

---

## MitigationExpiration

**Package:** `sailpoint.object`

**Description:** A MitigationExpiration holds information about a business role or entitlement list mitigation for the purpose of executing some action when the mitigation expires.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.MitigationExpiration`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `boolean equals (java.lang.Object o)`
- `java.lang.String getAccountDisplayName ()`
- `MitigationExpiration.Action getAction ()`
- `java.util.Map<java.lang.String,​java.lang.Object> getActionParameters ()`
- `java.lang.String getApplication ()`
- `java.lang.String getAttributeName ()`
- `java.lang.String getAttributeValue ()`
- `Bundle getBusinessRole ( Resolver resolver)`
- `CertifiableDescriptor getCertifiableDescriptor ()`
- `CertificationLink getCertificationLink ()`
- `java.lang.String getComments ()`
- `java.lang.String getConstraintName ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `EntitlementSnapshot getEntitlements ()`
- `java.util.List<EntitlementSnapshot> getEntitlementsList ()`
- `java.util.Date getExpiration ()`
- `Identity getIdentity ()`
- `java.lang.String getInstance ()`
- `java.util.Date getLastActionDate ()`
- `Identity getMitigator ()`
- `java.lang.String getNativeIdentity ()`
- `java.lang.String getPolicy ()`
- `PolicyViolation getPolicyViolation ()`
- `java.lang.String getRoleName ()`
- `boolean hasBeenActedUpon ()`
- `boolean hasName ()`
- `boolean isPermission ()`
- `void setAccountDisplayName (java.lang.String displayName)`
- `void setAction ( MitigationExpiration.Action action)`
- `void setActionParameters (java.util.Map<java.lang.String,java.lang.Object> params)`
- `void setApplication (java.lang.String application)`
- `void setAttributeName (java.lang.String value)`
- `void setAttributeValue (java.lang.String value)`
- `void setBusinessRole ( Bundle businessRole)`
- `void setCertifiableDescriptor ( CertifiableDescriptor d)`
- `void setCertificationLink ( CertificationLink link)`
- `void setComments (java.lang.String comments)`
- `void setConstraintId (java.lang.String id)`
- `void setConstraintName (java.lang.String value)`
- `void setEntitlements (java.util.List< EntitlementSnapshot > entitlements)`
- `void setExpiration (java.util.Date expiration)`
- `void setIdentity ( Identity identity)`
- `void setInstance (java.lang.String instance)`
- `void setLastActionDate (java.util.Date lastActionDate)`
- `void setMitigator ( Identity mitigator)`
- `void setNativeIdentity (java.lang.String nativeIdentity)`
- `void setPermission (boolean value)`
- `void setPolicy (java.lang.String policy)`
- `void setPolicyId (java.lang.String id)`
- `void setRoleName (java.lang.String value)`
- `void visit ( Visitor v)`

---

## Module

**Package:** `sailpoint.object`

**Description:** Configuration attribute (String) holding the name of the Java class to construct to check health.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Module`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATT_HEALTH_CHECK_CLASS`

**Methods:**
- `java.lang.Object get (java.lang.String name)`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `boolean getBoolean (java.lang.String name)`
- `java.lang.String getDescription ()`
- `int getInt (java.lang.String name)`
- `java.util.List getList (java.lang.String name)`
- `java.lang.String getString (java.lang.String name)`
- `boolean hasAssignedScope ()`
- `void put (java.lang.String name, int value)`
- `void put (java.lang.String name, java.lang.Object value)`
- `void remove (java.lang.String name)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> a)`
- `void setDescription (java.lang.String description)`

---

## MonitoringStatistic

**Package:** `sailpoint.object`

**Description:** Retrieve a String valued configuration setting.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.MonitoringStatistic`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATTR_CALL_LIBS`
- `static java.lang.String ATTR_REF_OBJECT_TYPE`
- `static java.lang.String ATTR_REFERENCED_OBJECT`
- `static java.lang.String ATTR_RULE_LIBS`
- `static java.lang.String ATTR_VALUE_RENDERER`

**Methods:**
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes getAttributes ()`
- `java.lang.String getDisplayName ()`
- `java.lang.String getStringAttributeValue (java.lang.String name)`
- `java.util.List<Tag> getTags ()`
- `java.lang.String getType ()`
- `java.lang.String getValue ()`
- `Scriptlet getValueSource ()`
- `java.lang.String getValueType ()`
- `boolean isTemplate ()`
- `void setAttributes ( Attributes attributes)`
- `void setDisplayName (java.lang.String displayName)`
- `void setTags (java.util.List< Tag > tags)`
- `void setTemplate (boolean b)`
- `void setType (java.lang.String type)`
- `void setValue (java.lang.String value)`
- `void setValueSource ( Scriptlet valueSource)`
- `void setValueType (java.lang.String valueType)`
- `void visit ( Visitor v)`

---

## NamedSnapshot

**Package:** `sailpoint.object`

**Description:** Simple interface for Snapshots used in IdentitySnapshots that have names. This is useful for stripping the names out for Differencing.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `java.lang.String getName ()`

---

## NamedTimestamp

**Package:** `sailpoint.object`

**Description:** Let the ScopeService know this class does not have a scope.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.NamedTimestamp`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.Object clone ()`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `java.util.Date getTimestamp ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `void setAttribute (java.lang.String key, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attributes)`
- `void setTimestamp (java.util.Date timestamp)`

---

## NativeChangeDetection

**Package:** `sailpoint.object`

**Description:** A class used to represent detected native changes found from aggregation to aggregation. These are stored on the identity then processed by the refresh task.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.LinkSnapshot`
- `sailpoint.object.NativeChangeDetection`
- `java.io.Serializable`
- `LinkInterface`

**Attributes:**
- `static java.lang.String FLOW_CONFIG_NAME`

**Methods:**
- `void add ( Difference d)`
- `void assimilateAccountInfo ( Link link)`
- `java.util.List<Difference> getDifferences ()`
- `ProvisioningPlan.AccountRequest.Operation getOperation ()`
- `boolean isEmpty ()`
- `boolean matches ( LinkInterface link)`
- `void setDifferences (java.util.List< Difference > differences)`
- `void setOperation ( ProvisioningPlan.AccountRequest.Operation operation)`

---

## NativeIdentityChangeEvent.EventStatus

**Package:** `sailpoint.object`

**Description:** The possible states that this event can be in as it is processed.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `NativeIdentityChangeEvent.EventStatus`
- `sailpoint.object.NativeIdentityChangeEvent.EventStatus`
- `java.io.Serializable`
- `java.lang.Comparable<NativeIdentityChangeEvent.EventStatus>`

**Attributes:** N/A

**Methods:**
- `staticNativeIdentityChangeEvent.EventStatus valueOf (java.lang.String name)`
- `staticNativeIdentityChangeEvent.EventStatus[] values ()`

---

## NativeIdentityChangeEvent.ObjectType

**Package:** `sailpoint.object`

**Description:** The type of change event: Account (for Links) or Group (for ManagedAttributes)

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `NativeIdentityChangeEvent.ObjectType`
- `sailpoint.object.NativeIdentityChangeEvent.ObjectType`
- `java.io.Serializable`
- `java.lang.Comparable<NativeIdentityChangeEvent.ObjectType>`

**Attributes:** N/A

**Methods:**
- `staticNativeIdentityChangeEvent.ObjectType valueOf (java.lang.String name)`
- `staticNativeIdentityChangeEvent.ObjectType[] values ()`

---

## NativeIdentityChangeEvent

**Package:** `sailpoint.object`

**Description:** An object that stores details of a native identity change. These changes are detected during account or group aggregation, and persisted here so that the new native identity value can be propagated through the database, ensuring all references are up to date. Since a unique identifier (UUID) is used to identify a native identity change (vs a brand new account or group), the application connector must supply a UUID in order to support native identity changes.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.NativeIdentityChangeEvent`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.String getApplicationId ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `java.lang.String getIdentityId ()`
- `java.lang.String getInstance ()`
- `java.util.Date getLaunched ()`
- `java.lang.String getLinkId ()`
- `java.lang.String getManagedAttributeId ()`
- `java.lang.String getNewNativeIdentity ()`
- `java.lang.String getOldNativeIdentity ()`
- `NativeIdentityChangeEvent.EventStatus getStatus ()`
- `NativeIdentityChangeEvent.ObjectType getType ()`
- `java.lang.String getUuid ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `void setApplicationId (java.lang.String applicationId)`
- `void setIdentityId (java.lang.String identityId)`
- `void setInstance (java.lang.String instance)`
- `void setLaunched (java.util.Date launched)`
- `void setLinkId (java.lang.String linkId)`
- `void setManagedAttributeId (java.lang.String managedAttributeId)`
- `void setNewNativeIdentity (java.lang.String newNativeIdentity)`
- `void setOldNativeIdentity (java.lang.String oldNativeIdentity)`
- `void setStatus ( NativeIdentityChangeEvent.EventStatus status)`
- `void setType ( NativeIdentityChangeEvent.ObjectType type)`
- `void setUuid (java.lang.String uuid)`
- `java.lang.String toString ()`

---

## Notifiable

**Package:** `sailpoint.object`

**Description:** Interface for objects that can be reminded, escalated, and expired.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `int getEscalationCount ()`
- `java.util.Date getExpirationDate ()`
- `java.lang.String getId ()`
- `NotificationConfig getNotificationConfig ()`
- `java.lang.String getNotificationName ()`
- `Identity getNotificationOwner ( Resolver resolver)`
- `int getRemindersSent ()`
- `java.util.Date getWakeUpDate ()`
- `void incrementEscalationCount ()`
- `void incrementRemindersSent ()`
- `boolean isEscalateOnMaxReminders ()`
- `boolean isExpirable ()`
- `boolean isExpired ()`
- `void saveEscalationError ( InvalidEscalationTargetException error)`
- `void setWakeUpDate (java.util.Date nextWakeUp)`

---

## NotificationConfig.ConfigBase

**Package:** `sailpoint.object`

**Description:** Constructor to set shared items based on the provided map data.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.NotificationConfig.ConfigBase`
- `java.io.Serializable`
- `NotificationConfig.IConfig`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.util.Date calculateNextNotificationDate (java.util.Date lastNotificationDate)`
- `java.util.List<java.lang.String> getAdditionalRecipientNames ()`
- `java.lang.String getAdditionalRecipientsRuleName ()`
- `int getCount ()`
- `java.lang.String getEmailTemplateName ()`
- `protected java.util.Date getFirstDateConsideringBeforeOrAfter (java.util.Date startDate, java.util.Date endDate)`
- `long getFrequency ()`
- `long getMillis ()`
- `boolean isAdditionalRecipientsPresent ()`
- `boolean isBefore ()`
- `boolean isEnabled ()`
- `boolean isExhausted ()`
- `boolean isSame ( NotificationConfig.IConfig otherConfig)`
- `void setAdditionalRecipientNames (java.util.List<java.lang.String> val)`
- `void setAdditionalRecipientsPresent (boolean val)`
- `void setAdditionalRecipientsRuleName (java.lang.String val)`
- `void setBefore (boolean val)`
- `void setCount (int val)`
- `void setEmailTemplateName (java.lang.String val)`
- `void setEnabled (boolean val)`
- `void setFrequency (long val)`
- `void setMillis (long val)`

---

## NotificationConfig.EscalationConfig

**Package:** `sailpoint.object`

**Description:** Constructor that creates a new EscalationConfig based on the provided map.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.NotificationConfig.ConfigBase`
- `sailpoint.object.NotificationConfig.EscalationConfig`
- `java.io.Serializable`
- `NotificationConfig.IConfig`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.util.Date calculateStartDate (java.util.Date notificationStartDate, java.util.Date notificationEndDate, NotificationConfig.IConfig previousConfig)`
- `java.lang.String getEscalationRuleName ()`
- `java.util.Date getFirstDateConsideringBeforeOrAfter (java.util.Date startDate, java.util.Date endDate)`
- `int getMaxReminders ()`
- `void setEscalationRuleName (java.lang.String val)`
- `void setMaxReminders (int val)`
- `java.lang.String toString ()`

---

## NotificationConfig.IConfig

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `java.util.Date calculateNextNotificationDate (java.util.Date lastNotificationDate)`
- `java.util.Date calculateStartDate (java.util.Date notificationStartDate, java.util.Date notificationEndDate, NotificationConfig.IConfig previousConfig)`
- `java.util.List<java.lang.String> getAdditionalRecipientNames ()`
- `java.lang.String getAdditionalRecipientsRuleName ()`
- `int getCount ()`
- `java.lang.String getEmailTemplateName ()`
- `long getFrequency ()`
- `long getMillis ()`
- `boolean isAdditionalRecipientsPresent ()`
- `boolean isBefore ()`
- `boolean isEnabled ()`
- `boolean isExhausted ()`
- `boolean isSame ( NotificationConfig.IConfig otherConfig)`
- `void setAdditionalRecipientNames (java.util.List<java.lang.String> val)`
- `void setAdditionalRecipientsPresent (boolean val)`
- `void setAdditionalRecipientsRuleName (java.lang.String val)`
- `void setBefore (boolean val)`
- `void setCount (int val)`
- `void setEmailTemplateName (java.lang.String val)`
- `void setEnabled (boolean val)`
- `void setFrequency (long val)`
- `void setMillis (long val)`

---

## NotificationConfig.ReminderConfig

**Package:** `sailpoint.object`

**Description:** Constructor that builds a new ReminderConfig based on the provided map.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.NotificationConfig.ConfigBase`
- `sailpoint.object.NotificationConfig.ReminderConfig`
- `java.io.Serializable`
- `NotificationConfig.IConfig`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.util.Date calculateStartDate (java.util.Date notificationStartDate, java.util.Date notificationEndDate, NotificationConfig.IConfig previousConfig)`
- `boolean isOnce ()`
- `void setOnce (boolean val)`
- `java.lang.String toString ()`

---

## NotificationConfig

**Package:** `sailpoint.object`

**Description:** A class holding information about when and how to execute notifications, reminders, escalations, etc... There are three modes for triggering the initial reminder or escalation: Time after start: This uses an amount of milliseconds after the item is started to kick of the first reminder/escalation. Time before expiration: This counts backwards from a specified expiration time to determine when to kick off the first reminder or escalation. Max number of reminders: This is only applicable for escalations when reminders are enabled. After a max number of reminders have been sent, the first escalation will be kicked off. IMPORTANT ADDENDUM: This model has been updated to support multiple reminders and escalations per notificationconfig. Initially only one reminder config and one escalation config were supported. Now there can be multiples of these. There are a lot of deprecated properties to maintain backward compatibility in order to support workflows etc from before.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.NotificationConfig`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void assignWakeUpDate ( Notifiable notifiable, java.util.Date expiration)`
- `java.util.Date calculateFirstEscalationDate (java.util.Date start, java.util.Date expiration)`
- `java.util.Date calculateFirstReminderDate (java.util.Date start, java.util.Date expiration)`
- `java.util.Date calculateNextNotificationDate ()`
- `staticCertificationDefinition.NotificationConfig.EscalationConfig createDefaultRestEscalationConfig ( SailPointContext context, boolean maxPresentInEscalation)`
- `staticCertificationDefinition.NotificationConfig.ReminderConfig createDefaultRestReminderConfig ( SailPointContext context)`
- `staticNotificationConfig createFromJsonObject ( Resolver resolver, CertificationDefinition.NotificationConfig jsonConfig)`
- `staticNotificationConfig createFromJsonString ( Resolver resolver, java.lang.String jsonString)`
- `static java.lang.String createJsonString ( SailPointContext context, NotificationConfig configFromDb)`
- `staticCertificationDefinition.NotificationConfig createRestNotificationConfig ( SailPointContext context, NotificationConfig dbConfig)`
- `void enableEscalation ( Resolver resolver, java.lang.String ruleName, java.lang.String emailTemplate, long escalationFrequency, int maxReminders)`
- `void enableReminders ( Resolver resolver, java.lang.String emailTemplateName, long reminderFrequency, long initialReminderMillisBeforeEnd)`
- `void enableRemindersFromStart ( Resolver resolver, java.lang.String emailTemplateName, long reminderFrequency, long initialReminderMillisAfterStart)`
- `int findConfigToUseIndex ()`
- `int findNextConfigIndex (int i)`
- `int findPreviousConfigIndex (int i)`
- `java.util.List<NotificationConfig.IConfig> getConfigs ()`
- `java.util.Date getEndDate ()`
- `EmailTemplate getEscalationEmailTemplate ()`
- `EmailTemplate getEscalationEmailTemplate ( Resolver resolver)`
- `long getEscalationFrequencyMillis ()`
- `int getEscalationMaxReminders ()`
- `long getEscalationMillisAfterStart ()`
- `long getEscalationMillisBeforeEnd ()`
- `Rule getEscalationRule ()`
- `Rule getEscalationRule ( Resolver resolver)`
- `long getInitialReminderMillisAfterStart ()`
- `long getInitialReminderMillisBeforeEnd ()`
- `EmailTemplate getReminderEmailTemplate ()`
- `EmailTemplate getReminderEmailTemplate ( Resolver resolver)`
- `long getReminderFrequency ()`
- `java.util.Date getStartDate ()`
- `boolean isEnabled ()`
- `boolean isEscalationEnabled ()`
- `boolean isNew ()`
- `boolean isRemindersEnabled ()`
- `void reAssignWakeupDate ( Notifiable notifiable, NotificationConfig oldNotificationConfig)`
- `void setConfigs (java.util.List< NotificationConfig.IConfig > val)`
- `void setEnabled (boolean val)`
- `void setEndDate (java.util.Date val)`
- `void setEscalationEmailTemplate ( EmailTemplate escalationEmailTemplate)`
- `void setEscalationEnabled (boolean val)`
- `void setEscalationFrequency (long escalationFrequency)`
- `void setEscalationFrequencyMillis (long frequency)`
- `void setEscalationMaxReminders (int val)`
- `void setEscalationMillisAfterStart (long millis)`
- `void setEscalationMillisBeforeEnd (long escalationMillisBeforeEnd)`
- `void setEscalationRule ( Rule escalationRule)`
- `void setInitialReminderMillisAfterStart (long millis)`
- `void setInitialReminderMillisBeforeEnd (long l)`
- `void setReminderEmailTemplate ( EmailTemplate val)`
- `void setReminderFrequency (long val)`
- `void setRemindersEnabled (boolean val)`
- `void setStartDate (java.util.Date val)`
- `java.lang.String toString ()`

---

## NotificationTemplate

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:** N/A

---

## OAuthClient

**Package:** `sailpoint.object`

**Description:** OAuthClient represents an OAuth configuration for a particular client.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.OAuthClient`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getClientId ()`
- `java.util.Date getCreateDate ()`
- `java.lang.String getKey ()`
- `java.lang.String getName ()`
- `java.lang.String getProxyUser ()`
- `java.lang.String getRedirectUrl ()`
- `java.lang.String getSecret ()`
- `void setClientId (java.lang.String clientId)`
- `void setCreateDate (java.util.Date createDate)`
- `void setKey (java.lang.String key)`
- `void setName (java.lang.String name)`
- `void setProxyUser (java.lang.String proxyUser)`
- `void setRedirectUrl (java.lang.String redirectUrl)`
- `void setSecret (java.lang.String secret)`

---

## OAuthConfiguration

**Package:** `sailpoint.object`

**Description:** Represents a single OAuth configuration for a set of OAuth client objects. There should only be one OAuth configuration per deployment. Multiple OAuthClient objects are children of this element.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.OAuthConfiguration`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static int DEFAULT_ACCESS_TOKEN_EXPIRES_IN_SECONDS`

**Methods:**
- `void addClient ( OAuthClient client)`
- `OAuthClient deleteClient (java.lang.String clientId)`
- `java.lang.Integer getAccessTokenExpiresInSeconds ()`
- `java.lang.String getApiAuthAudience ()`
- `java.lang.String getApiAuthIssuers ()`
- `java.lang.String getApiAuthScope ()`
- `java.lang.String getApiCorrelationVariable ()`
- `java.lang.Boolean getAudienceRequired ()`
- `OAuthClient getClient (java.lang.String id)`
- `OAuthClient getClientByName (java.lang.String name)`
- `java.lang.Boolean getIssuersRequired ()`
- `java.util.List<OAuthClient> getOAuthClients ()`
- `java.lang.Integer getRefreshTokenExpiresInSeconds ()`
- `java.lang.Boolean getScopeRequired ()`
- `void setAccessTokenExpiresInSeconds (java.lang.Integer accessTokenExpiresInSeconds)`
- `void setApiAuthAudience (java.lang.String apiAuthAudience)`
- `void setApiAuthIssuers (java.lang.String apiAuthIssuers)`
- `void setApiAuthScope (java.lang.String apiAuthScope)`
- `void setApiCorrelationVariable (java.lang.String apiCorrelationVariable)`
- `void setAudienceRequired (java.lang.Boolean audienceRequired)`
- `void setIssuersRequired (java.lang.Boolean issuersRequired)`
- `void setOAuthClients (java.util.List< OAuthClient > oAuthClients)`
- `void setRefreshTokenExpiresInSeconds (java.lang.Integer refreshTokenExpiresInSeconds)`
- `void setScopeRequired (java.lang.Boolean scopeRequired)`

---

## ObjectAttribute.EditMode

**Package:** `sailpoint.object`

**Description:** Enumeration used to indicate whether modifications to this attribute are allowed.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ObjectAttribute.EditMode`
- `sailpoint.object.ObjectAttribute.EditMode`
- `java.io.Serializable`
- `java.lang.Comparable<ObjectAttribute.EditMode>`

**Attributes:** N/A

**Methods:**
- `staticObjectAttribute.EditMode valueOf (java.lang.String name)`
- `staticObjectAttribute.EditMode[] values ()`

---

## ObjectAttribute

**Package:** `sailpoint.object`

**Description:** A class used to define a set of abstract attributes for SailPointObject subclasses. Some of these might map directly to Java properties, some might be derived at runtime, and some might be custom attributes added during a deployment.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.BaseAttributeDefinition`
- `sailpoint.object.ObjectAttribute`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void add ( AttributeSource src)`
- `void add ( AttributeTarget target)`
- `ObjectAttribute.EditMode getEditMode ()`
- `java.lang.String getEditModeString ()`
- `java.lang.String getExtendedIdentityName ()`
- `java.lang.String getExtendedName ()`
- `int getExtendedNumber ()`
- `IdentitySelector getIdentitySelector ()`
- `java.lang.String getJsonPath ()`
- `Rule getListenerRule ()`
- `Workflow getListenerWorkflow ()`
- `SearchInputDefinition.PropertyType getPropertyType ()`
- `Rule getRule ()`
- `AttributeSource getSource ( Application app)`
- `AttributeSource getSource ( AttributeMetaData metadata)`
- `AttributeSource getSource ( AttributeSource other)`
- `java.lang.String getSourceAttribute ( Application app)`
- `int getSourceOrdinal (java.lang.String key)`
- `int getSourceOrdinal ( AttributeMetaData metadata)`
- `java.util.List<AttributeSource> getSources ()`
- `AttributeTarget getTarget ( AttributeTarget other)`
- `java.util.List<AttributeTarget> getTargets ()`
- `boolean isCustom ()`
- `boolean isEditable ()`
- `boolean isExtended ()`
- `boolean isGroupFactory ()`
- `boolean isIdentity ()`
- `boolean isIdentityAttributeSyncUsingWorkflow ()`
- `boolean isNamedColumn ()`
- `boolean isSearchable ()`
- `boolean isSilent ()`
- `boolean isSourcedBy ( Application app)`
- `boolean isStandard ()`
- `boolean isSystem ()`
- `boolean remove ( AttributeSource src)`
- `boolean remove ( AttributeTarget target)`
- `void setEditMode ( ObjectAttribute.EditMode type)`
- `void setEditModeString (java.lang.String editModeString)`
- `void setExtendedNumber (int i)`
- `void setGroupFactory (boolean b)`
- `void setIdentityAttributeSyncUsingWorkflow (boolean sync)`
- `void setIdentitySelector ( IdentitySelector selector)`
- `void setJsonPath (java.lang.String jsonPath)`
- `void setListenerRule ( Rule r)`
- `void setListenerWorkflow ( Workflow w)`
- `void setNamedColumn (boolean b)`
- `void setRule ( Rule r)`
- `void setSilent (boolean b)`
- `void setSources (java.util.List< AttributeSource > sources)`
- `void setStandard (boolean b)`
- `void setSystem (boolean b)`
- `void setTargets (java.util.List< AttributeTarget > targets)`
- `java.lang.String sourcedBy ( Application app)`

---

## ObjectClassification

**Package:** `sailpoint.object`

**Description:** We override equals so that two objects will compare equal if they have the same database id or unique name, but are different Java objects.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.ObjectClassification`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `boolean equals (java.lang.Object o)`
- `Classification getClassification ()`
- `java.lang.String getOwnerId ()`
- `java.lang.String getOwnerType ()`
- `java.lang.String getSource ()`
- `boolean hasAssignedScope ()`
- `int hashCode ()`
- `boolean hasName ()`
- `boolean isEffective ()`
- `void setClassification ( Classification classification)`
- `void setEffective (boolean effective)`
- `void setOwnerId (java.lang.String ownerId)`
- `void setOwnerType (java.lang.String ownerType)`
- `void setSource (java.lang.String source)`

---

## ObjectConfig

**Package:** `sailpoint.object`

**Description:** Class used to encapsulate configuration options for a particular subclass of SailPointObject. The primary purpose is to maintain a list of ObjectAttribute definitions that define the extended and searchable attributes of the class. Additional configuration can be placed in a map.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.ObjectConfig`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `Cacheable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ALERT`
- `static java.lang.String APPLICATION`
- `static java.lang.String ATT_DEFAULT_IDENTITY_TYPE`
- `static java.lang.String ATT_IDENTITY_TYPE_DEFINITIONS`
- `static java.lang.String ATT_ROLE_TYPE_DEFINITIONS`
- `static java.lang.String BUNDLE`
- `static java.lang.String CERTIFICATION_ITEM`
- `static java.lang.String HistoricalIdentityCapture`
- `static java.lang.String HistoricalRoleCapture`
- `static java.lang.String IDENTITY`
- `static java.lang.String IDENTITY_SCOPE_CORRELATION_ATTR`
- `static java.lang.String IDENTITY_SCOPE_CORRELATION_RULE`
- `static java.lang.String IDENTITY_SCOPE_SELECTION_RULE`
- `static java.lang.String LINK`
- `static java.lang.String MANAGED_ATTRIBUTE`
- `static java.lang.String ROLE`
- `static java.lang.String SERVER`
- `static java.lang.String TARGET`

**Methods:**
- `void add ( ObjectAttribute att)`
- `java.lang.Object get (java.lang.String name)`
- `staticCacheReference getCache (java.lang.Class cls)`
- `Attributes<java.lang.String,​java.lang.Object> getConfigAttributes ()`
- `java.util.List<ObjectAttribute> getCustomAttributes ()`
- `IdentityTypeDefinition getDefaultIdentityTypeDefinition ()`
- `Attributes<java.lang.String,​java.lang.Object> getDefaultValues ()`
- `java.lang.String getDisplayName (java.lang.String name)`
- `java.lang.String getDisplayName (java.lang.String name, java.util.Locale locale)`
- `java.util.List<ObjectAttribute> getEditableAttributes ()`
- `java.util.List<ObjectAttribute> getExtendedAttributeList ()`
- `IdentityTypeDefinition getIdentityType (java.lang.String typeName)`
- `IdentityTypeDefinition getIdentityType ( Identity Identity)`
- `java.util.Collection<IdentityTypeDefinition> getIdentityTypesCollection ()`
- `java.util.List<IdentityTypeDefinition> getIdentityTypesList ()`
- `java.util.Map<java.lang.String,​IdentityTypeDefinition> getIdentityTypesMap ()`
- `java.util.List<ObjectAttribute> getMultiAttributeList ()`
- `ObjectAttribute getObjectAttribute (int number)`
- `ObjectAttribute getObjectAttribute (java.lang.String name)`
- `java.util.Map<java.lang.String,​ObjectAttribute> getObjectAttributeMap ()`
- `java.util.List<ObjectAttribute> getObjectAttributes ()`
- `java.util.Collection<ObjectAttribute> getObjectAttributesByApplication ( Application app)`
- `ObjectAttribute getObjectAttributeWithSource ( Application app, java.lang.String attrName)`
- `staticObjectConfig getObjectConfig (java.lang.Class cls)`
- `staticObjectConfig getObjectConfig (java.lang.String className)`
- `staticObjectConfig getObjectConfig ( SailPointObject obj)`
- `RoleTypeDefinition getRoleType (java.lang.String typeName)`
- `RoleTypeDefinition getRoleType ( Bundle role)`
- `java.util.Collection<RoleTypeDefinition> getRoleTypesCollection ()`
- `java.util.List<RoleTypeDefinition> getRoleTypesList ()`
- `java.util.Map<java.lang.String,​RoleTypeDefinition> getRoleTypesMap ()`
- `java.util.List<ObjectAttribute> getSearchableAttributes ()`
- `java.util.List<ObjectAttribute> getStandardAttributes ()`
- `java.lang.String getString (java.lang.String name)`
- `java.util.Map<java.lang.String,​ObjectAttribute> getTargetedAttributes ()`
- `boolean hasIdentityType (java.lang.String typeName)`
- `boolean hasObjectAttribute (java.lang.String name)`
- `boolean isExtendedIdentity ( ObjectAttribute att)`
- `void put (java.lang.String name, java.lang.Object value)`
- `void remove ( ObjectAttribute att)`
- `void replace (java.lang.String name, ObjectAttribute attribute)`
- `void setConfigAttributes ( Attributes <java.lang.String,java.lang.Object> a)`
- `void setObjectAttributes (java.util.List< ObjectAttribute > atts)`

---

## PE2SiteConfig

**Package:** `sailpoint.object`

**Description:** Configuration object that is used to drive unstructured collection from PE2 applications site collections. This is used to hold context info of TSS,ACF2,RACF and LINUX applications.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.PE2SiteConfig`
- `java.lang.Cloneable`

**Attributes:** N/A

**Methods:**
- `java.lang.Object clone ()`
- `java.lang.String getGeneric ()`
- `java.lang.String getPassword ()`
- `java.lang.String getTargetName ()`
- `java.lang.String getTargetType ()`
- `java.lang.String getType ()`
- `java.lang.String getUnit ()`
- `java.lang.String getUser ()`
- `java.lang.String getVolume ()`
- `void setGeneric (java.lang.String _generic)`
- `void setPassword (java.lang.String password)`
- `void setTargetName (java.lang.String targetName)`
- `void setTargetType (java.lang.String targetType)`
- `void setType (java.lang.String _type)`
- `void setUnit (java.lang.String _unit)`
- `void setUser (java.lang.String user)`
- `void setVolume (java.lang.String _volume)`

---

## Partition

**Package:** `sailpoint.object`

**Description:** A Partition is an XML/JSON object that is used by the connector interface to describe slices of data that can be split up.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Partition`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.Object get (java.lang.String name)`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `int getInteger (java.lang.String name)`
- `java.lang.String getName ()`
- `java.lang.String getObjectType ()`
- `int getSize ()`
- `java.lang.String getString (java.lang.String name)`
- `void put (java.lang.String name, java.lang.Object value)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attributes)`
- `void setName (java.lang.String name)`
- `void setObjectType (java.lang.String type)`
- `void setSize (int size)`
- `java.lang.String toJSONString ()`

---

## PartitionResult

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.TaskItem`
- `sailpoint.object.TaskResult`
- `sailpoint.object.PartitionResult`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.api.MessageAccumulator`
- `sailpoint.api.MessageRepository`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `TaskResult getTaskResult ()`
- `void setTaskResult ( TaskResult res)`

---

## PasswordPolicy

**Package:** `sailpoint.object`

**Description:** When a password is set/changed this is the password policy that defines the requirements for a valid password. Used by PasswordPolice object to determine password validity. Stored in Application object.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.PasswordPolicy`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `void addConstraint (java.lang.String name, java.lang.Object cons)`
- `void assimilatePolicies (java.util.List< PasswordPolicy > passwordPolicies)`
- `java.util.List<java.lang.String> convertConstraints ()`
- `java.util.List<java.lang.String> convertConstraints (java.util.Locale locale, java.util.TimeZone timeZone)`
- `java.util.List<java.lang.String> convertConstraints (java.util.Locale locale, java.util.TimeZone timeZone, boolean addNoConstraintsMessage)`
- `java.lang.String getDescription ()`
- `java.util.Map<java.lang.String,​java.lang.Object> getPasswordConstraints ()`
- `java.lang.String[] getUniqueKeyProperties ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `void load ()`
- `void setDescription (java.lang.String description)`
- `void setPasswordConstraints (java.util.Map<java.lang.String,java.lang.Object> passwordConstraints)`
- `void visit ( Visitor v)`

---

## PasswordPolicyHolder

**Package:** `sailpoint.object`

**Description:** Holds association between PasswordPolicy object and IdentitySelector

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.PasswordPolicyHolder`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `void addConstraint (java.lang.String multi, java.lang.String convertListToString)`
- `void generateNewPolicy ()`
- `java.util.Map<java.lang.String,​java.lang.Object> getPasswordConstraints ()`
- `PasswordPolicy getPolicy ()`
- `java.lang.String getPolicyDescription ()`
- `java.lang.String getPolicyName ()`
- `IdentitySelector getSelector ()`
- `java.lang.String[] getUniqueKeyProperties ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `void load ()`
- `void setPasswordConstraints (java.util.Map<java.lang.String,java.lang.Object> constraints)`
- `void setPolicy ( PasswordPolicy policy)`
- `void setPolicyDescription (java.lang.String description)`
- `void setPolicyName (java.lang.String name)`
- `void setSelector ( IdentitySelector selector)`
- `void visit ( Visitor v)`

---

## PendingRequestAttachment

**Package:** `sailpoint.object`

**Description:** Let the ScopeService know this class does not have a scope.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.PendingRequestAttachment`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.String getAttachmentId ()`
- `java.lang.String getItemId ()`
- `java.lang.String getRequesterId ()`
- `java.lang.String getTargetId ()`
- `java.lang.String getType ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `void setAttachmentId (java.lang.String attachmentId)`
- `void setItemId (java.lang.String itemId)`
- `void setRequesterId (java.lang.String requesterId)`
- `void setTargetId (java.lang.String targetId)`
- `void setType (java.lang.String type)`

---

## Permission

**Package:** `sailpoint.object`

**Description:** A representation of a application-specific permission. Permissions are modeled as a set of "rights" on a "target".

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Permission`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `java.lang.Comparable<Permission>`
- `sailpoint.tools.Localizable`
- `sailpoint.tools.xml.IXmlEqualable<Permission>`

**Attributes:**
- `static java.lang.String ATT_AGGREGATION_SOURCE`
- `static java.lang.String ATT_TARGET_HOST`
- `static java.lang.String CREATE`
- `static java.lang.String DELETE`
- `static java.lang.String EXECUTE`
- `static java.lang.String READ`
- `static java.util.Comparator<Permission> SP_PERMISSION_BY_ANNOTATION`
- `static java.util.Comparator<Permission> SP_PERMISSION_BY_RIGHT`
- `static java.util.Comparator<Permission> SP_PERMISSION_BY_TARGET`
- `static java.lang.String UPDATE`

**Methods:**
- `void addRights (java.util.List<java.lang.String> rights)`
- `java.lang.Object clone ()`
- `static java.util.List<Permission> clone (java.util.List< Permission > perms)`
- `int compareTo ( Permission perm)`
- `boolean contentEquals ( Permission other)`
- `boolean equals (java.lang.Object o)`
- `java.lang.String getAggregationSource ()`
- `java.lang.String getAnnotation ()`
- `java.lang.Object getAttribute (java.lang.String name)`
- `java.util.Map<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getLocalizedMessage ()`
- `java.lang.String getLocalizedMessage (java.util.Locale locale, java.util.TimeZone timezone)`
- `Message getMessage ()`
- `java.lang.String getRights ()`
- `java.util.List<java.lang.String> getRightsList ()`
- `java.lang.String getStringAttribute (java.lang.String name)`
- `java.lang.String getTarget ()`
- `int hashCode ()`
- `boolean hasRight (java.lang.String name)`
- `boolean hasTarget (java.lang.String name)`
- `void removeRights (java.util.List<java.lang.String> rights)`
- `void setAggregationSource (java.lang.String source)`
- `void setAnnotation (java.lang.String annotation)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes (java.util.Map<java.lang.String,java.lang.Object> attributes)`
- `protected void setPseudo (java.lang.String name, java.lang.Object value)`
- `void setRights (java.lang.String s)`
- `void setRights (java.util.List<java.lang.String> l)`
- `void setTarget (java.lang.String att)`
- `boolean subsumes ( Permission p)`
- `java.lang.String toString ()`

---

## PermissionDifference

**Package:** `sailpoint.object`

**Description:** The representation of a change in permissions held by an Identity. These are generated by the Certificationer & Differencer and stored in the CertificationIdentity for display in the certification report.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.PermissionDifference`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getApplication ()`
- `java.lang.String getRights ()`
- `java.lang.String getTarget ()`
- `boolean isRemoved ()`
- `void setApplication (java.lang.String s)`
- `void setRemoved (boolean b)`
- `void setRights (java.lang.String s)`
- `void setTarget (java.lang.String s)`

---

## PersistedFile

**Package:** `sailpoint.object`

**Description:** Simple representation of a file persisted to the database. The actual file contents are persisted in a set of associated FileBucket objects which hold the raw data.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.PersistedFile`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String CONTENT_TYPE_CSV`
- `static java.lang.String CONTENT_TYPE_PDF`

**Methods:**
- `long getContentLength ()`
- `java.lang.String getContentType ()`
- `boolean isCsv ()`
- `boolean isPdf ()`
- `void setContentLength (long contentLength)`
- `void setContentType (java.lang.String contentType)`
- `void visit ( Visitor v)`

---

## PersistenceOptions

**Package:** `sailpoint.object`

**Description:** An object encapsulating options to control how SailPointContext manages objects in the Hibernate session. To set options, create a PersistenceOptions object and call SailPointContext.setPersistenceOptions().

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.PersistenceOptions`

**Attributes:** N/A

**Methods:**
- `void clearModifiableClasses ()`
- `void clearUnModifiableClasses ()`
- `boolean isAllowImmutableModifications ()`
- `boolean isExplicitSaveMode ()`
- `boolean isOptimizeDirtyActive ()`
- `void setAllowImmutableModifications (boolean b)`
- `void setExplicitSaveMode (boolean b)`
- `void setModifiableClasses (java.lang.Class<?>... value)`
- `void setModifiableClasses (java.util.List<java.lang.Class<?>> value)`
- `void setOptimizeDirtyClasses (boolean val)`
- `void setUnModifiableClasses (java.lang.Class<?>... value)`
- `void setUnModifiableClasses (java.util.List<java.lang.Class<?>> value)`
- `boolean shouldDirtyCheck (java.lang.Object entity)`

---

## PersistentIdentityItem

**Package:** `sailpoint.object`

**Description:** Objects normally have unique user-defined names, though some like AuditRecord do not have names at all, and others like SODConstraint have names that might not be unique.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.PersistentIdentityItem`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.String getAnnotation ()`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getCsv ()`
- `java.lang.String getDisplayName ()`
- `java.util.Date getEndDate ()`
- `java.lang.String getInstance ()`
- `java.lang.String getName ()`
- `java.lang.String getNativeIdentity ()`
- `Permission getPermissionObject ()`
- `java.util.Date getStartDate ()`
- `java.lang.String getStringAttribute (java.lang.String name)`
- `java.lang.String getStringValue ()`
- `java.lang.Object getValue ()`
- `java.util.List<java.lang.String> getValueList ()`
- `boolean hasAssignedScope ()`
- `boolean isNameUnique ()`
- `void setAnnotation (java.lang.String s)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attrs)`
- `void setDisplayName (java.lang.String name)`
- `void setEndDate (java.util.Date d)`
- `void setInstance (java.lang.String s)`
- `void setName (java.lang.String s)`
- `void setNativeIdentity (java.lang.String s)`
- `protected void setPseudo (java.lang.String name, java.lang.Object value)`
- `void setStartDate (java.util.Date d)`
- `void setValue (java.lang.Object o)`

---

## Phaseable

**Package:** `sailpoint.object`

**Description:** A Phaseable object can be moved through the various certification phases.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `Certification getCertification ()`
- `Certification.Phase getNextPhase ()`
- `java.util.Date getNextPhaseTransition ()`
- `Certification.Phase getPhase ()`
- `Certification.Phase getPreviousPhase ()`
- `void setNextPhaseTransition (java.util.Date next)`
- `void setPhase ( Certification.Phase phase)`

---

## Plugin.CertificationLevel

**Package:** `sailpoint.object`

**Description:** Level of certification that this particular plugin is certified as

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Plugin.CertificationLevel`
- `sailpoint.object.Plugin.CertificationLevel`
- `java.io.Serializable`
- `java.lang.Comparable<Plugin.CertificationLevel>`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:**
- `java.lang.String getLocalizedMessage ()`
- `java.lang.String getLocalizedMessage (java.util.Locale locale, java.util.TimeZone timezone)`
- `staticPlugin.CertificationLevel valueOf (java.lang.String name)`
- `staticPlugin.CertificationLevel[] values ()`

---

## Plugin.ClassExportType

**Package:** `sailpoint.object`

**Description:** Used when asking if a class has been declared as exported for the given type of usage

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Plugin.ClassExportType`
- `sailpoint.object.Plugin.ClassExportType`
- `java.io.Serializable`
- `java.lang.Comparable<Plugin.ClassExportType>`

**Attributes:** N/A

**Methods:**
- `staticPlugin.ClassExportType valueOf (java.lang.String name)`
- `staticPlugin.ClassExportType[] values ()`

---

## Plugin

**Package:** `sailpoint.object`

**Description:** Plugin object to store information about a specific Plugin used by the Plugin framework. This class is used to describe any information about a particular plugin that is to be imported in the manifest.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Plugin`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATT_FULL_PAGE`
- `static java.lang.String ATT_MIN_UPGRADABLE_VERSION`
- `static java.lang.String ATT_POLICY_EXECUTOR_CLASS_NAMES`
- `static java.lang.String ATT_RECOMMENDER_CLASS_NAMES`
- `static java.lang.String ATT_REST_RESOURCE_CLASS_NAMES`
- `static java.lang.String ATT_SCRIPT_PACKAGE_NAMES`
- `static java.lang.String ATT_SERVICE_EXECUTOR_CLASS_NAMES`
- `static java.lang.String ATT_SETTINGS`
- `static java.lang.String ATT_SETTINGS_FORM_NAME`
- `static java.lang.String ATT_SETTINGS_PAGE_NAME`
- `static java.lang.String ATT_SNIPPETS`
- `static java.lang.String ATT_TASK_EXECUTOR_CLASS_NAMES`

**Methods:**
- `Plugin export ()`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `Plugin.CertificationLevel getCertificationLevel ()`
- `java.lang.String getDisplayableName ()`
- `java.lang.String getDisplayName ()`
- `PersistedFile getFile ()`
- `sailpoint.plugin.FullPage getFullPage ()`
- `java.util.Date getInstallDate ()`
- `long getLastModified ()`
- `java.lang.String getMaxSystemVersion ()`
- `java.lang.String getMinSystemVersion ()`
- `java.lang.String getMinUpgradableVersion ()`
- `java.util.List<java.lang.String> getPolicyExecutorClassNames ()`
- `int getPosition ()`
- `java.util.List<java.lang.String> getRecommenderClassNames ()`
- `java.util.List<java.lang.String> getResourceClassNames ()`
- `java.lang.String getRightRequired ()`
- `java.util.List<java.lang.String> getScriptPackageNames ()`
- `java.util.List<java.lang.String> getServiceExecutorClassNames ()`
- `sailpoint.plugin.Setting getSetting (java.lang.String settingName)`
- `java.util.List<sailpoint.plugin.Setting> getSettings ()`
- `Form getSettingsForm ()`
- `java.lang.String getSettingsPageName ()`
- `java.util.List<sailpoint.plugin.Snippet> getSnippets ()`
- `java.util.List<java.lang.String> getTaskExecutorClassNames ()`
- `java.lang.String getVersion ()`
- `boolean hasAssignedScope ()`
- `boolean hasPolicyExecutorClassNames ()`
- `boolean hasServiceExecutorClassNames ()`
- `boolean hasTaskExecutorClassNames ()`
- `boolean isDevelopmentVersion ()`
- `boolean isDisabled ()`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attributes)`
- `void setCertificationLevel ( Plugin.CertificationLevel certificationLevel)`
- `void setDisabled (boolean disabled)`
- `void setDisplayName (java.lang.String displayName)`
- `void setFile ( PersistedFile file)`
- `void setFullPage (sailpoint.plugin.FullPage fullPage)`
- `void setInstallDate (java.util.Date installDate)`
- `void setMaxSystemVersion (java.lang.String maxSystemVersion)`
- `void setMinSystemVersion (java.lang.String minSystemVersion)`
- `void setMinUpgradableVersion (java.lang.String minUpgradableVersion)`
- `void setPolicyExecutorClassNames (java.util.List<java.lang.String> policyExecutorClassNames)`
- `void setPosition (int position)`
- `void setRecommenderClassNames (java.util.List<java.lang.String> recommenderClassNames)`
- `void setResourceClassNames (java.util.List<java.lang.String> resourceClassNames)`
- `void setRightRequired (java.lang.String rightRequired)`
- `void setScriptPackageNames (java.util.List<java.lang.String> scriptPackageNames)`
- `void setServiceExecutorClassNames (java.util.List<java.lang.String> serviceExecutorClassNames)`
- `void setSettings (java.util.List<sailpoint.plugin.Setting> settings)`
- `void setSettingsForm ( Form form)`
- `void setSettingsPageName (java.lang.String pageName)`
- `void setSnippets (java.util.List<sailpoint.plugin.Snippet> snippets)`
- `void setTaskExecutorClassNames (java.util.List<java.lang.String> taskExecutorClassNames)`
- `void setVersion (java.lang.String version)`
- `void updateSetting (java.lang.String settingName, java.lang.Object settingValue)`
- `void updateSettings (java.util.Map<java.lang.String,java.lang.String> settings)`
- `void upgrade ( Plugin plugin)`
- `void visit ( Visitor v)`

---

## Policy.State

**Package:** `sailpoint.object`

**Description:** An enumeration of states a policy can be in.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Policy.State`
- `sailpoint.object.Policy.State`
- `java.io.Serializable`
- `java.lang.Comparable<Policy.State>`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:**
- `java.lang.String getLocalizedMessage ()`
- `java.lang.String getLocalizedMessage (java.util.Locale locale, java.util.TimeZone timezone)`
- `staticPolicy.State valueOf (java.lang.String name)`
- `staticPolicy.State[] values ()`

---

## Policy.ViolationOwnerType

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Policy.ViolationOwnerType`
- `sailpoint.object.Policy.ViolationOwnerType`
- `java.io.Serializable`
- `java.lang.Comparable<Policy.ViolationOwnerType>`

**Attributes:** N/A

**Methods:**
- `staticPolicy.ViolationOwnerType valueOf (java.lang.String name)`
- `staticPolicy.ViolationOwnerType[] values ()`

---

## Policy

**Package:** `sailpoint.object`

**Description:** A class encapsulating the definition of a policy. There are several types of policy but the same model is used to simplify persistence. Some properties defined in this class are only used with certain policy types.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Policy`
- `java.io.Serializable`
- `Describable`
- `PolicyViolation.IPolicyViolationOwnerSource`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ARG_CHECK_EFFECTIVE`
- `static java.lang.String ARG_PLUGIN_NAME`
- `static java.lang.String ARG_RISK_WEIGHT`
- `static java.lang.String POLICY_NAME_ACTIVITY`
- `static java.lang.String TYPE_ACCOUNT`
- `static java.lang.String TYPE_ACTIVITY`
- `static java.lang.String TYPE_ADVANCED`
- `static java.lang.String TYPE_CUSTOM`
- `static java.lang.String TYPE_EFFECTIVE_ENTITLEMENT_SOD`
- `static java.lang.String TYPE_ENTITLEMENT_SOD`
- `static java.lang.String TYPE_GENERIC`
- `static java.lang.String TYPE_RISK`
- `static java.lang.String TYPE_SOD`

**Methods:**
- `void addConstraint ( BaseConstraint con)`
- `void addDescription (java.lang.String locale, java.lang.String desc)`
- `<T extendsBaseConstraint>void assignConstraints (java.util.List<T> cons)`
- `Policy derive ( Resolver r)`
- `boolean equals (java.lang.Object obj)`
- `java.util.List<ActivityConstraint> getActivityConstraints ()`
- `PolicyAlert getAlert ()`
- `java.lang.Object getArgument (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getArguments ()`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getCertificationActions ()`
- `java.lang.String getConfigPage ()`
- `GenericConstraint getConstraint ()`
- `BaseConstraint getConstraint (java.lang.String constraintId, java.lang.String constraintName)`
- `BaseConstraint getConstraint ( PolicyViolation v)`
- `java.util.List getConstraints ()`
- `java.lang.String getDescription ()`
- `java.lang.String getDescription (java.lang.String locale)`
- `java.lang.String getDescription (java.util.Locale locale)`
- `java.util.Map<java.lang.String,​java.lang.String> getDescriptions ()`
- `java.lang.String getExecutor ()`
- `java.util.List<GenericConstraint> getGenericConstraints ()`
- `int getInt (java.lang.String name)`
- `Signature getSignature ()`
- `java.util.List<SODConstraint> getSODConstraints ()`
- `Policy.State getState ()`
- `java.lang.String getString (java.lang.String name)`
- `java.lang.String getType ()`
- `java.lang.String getTypeKey ()`
- `Identity getViolationOwner ()`
- `Identity getViolationOwnerForIdentity ( SailPointContext context, Identity identity)`
- `Identity getViolationOwnerForIdentity ( SailPointContext context, Identity identity, BaseConstraint constraint)`
- `Rule getViolationOwnerRule ()`
- `Policy.ViolationOwnerType getViolationOwnerType ()`
- `java.lang.String getViolationRule ()`
- `Rule getViolationRuleObject ( Resolver r)`
- `java.lang.String getViolationWorkflow ()`
- `Workflow getViolationWorkflow ( Resolver r)`
- `boolean hasConstraints ()`
- `int hashCode ()`
- `boolean isActionAllowed ( CertificationAction.Status status)`
- `boolean isNoCache ()`
- `boolean isTemplate ()`
- `boolean isType (java.lang.String type)`
- `void load ()`
- `void removeConstraint ( BaseConstraint con)`
- `void setAlert ( PolicyAlert alert)`
- `void setArgument (java.lang.String name, java.lang.Object value)`
- `void setArguments ( Attributes <java.lang.String,java.lang.Object> args)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> atts)`
- `void setCertificationActions (java.lang.String actions)`
- `void setConfigPage (java.lang.String url)`
- `void setDescription (java.lang.String s)`
- `void setDescriptions (java.util.Map<java.lang.String,java.lang.String> map)`
- `void setExecutor (java.lang.Class cls)`
- `void setExecutor (java.lang.String s)`
- `void setExecutor ( PolicyExecutor pe)`
- `void setNoCache (boolean b)`
- `void setSignature ( Signature s)`
- `void setState ( Policy.State s)`
- `void setTemplate (boolean b)`
- `void setType (java.lang.String type)`
- `void setTypeKey (java.lang.String key)`
- `void setViolationOwner ( Identity val)`
- `void setViolationOwnerRule ( Rule val)`
- `void setViolationOwnerType ( Policy.ViolationOwnerType val)`
- `void setViolationRule (java.lang.String s)`
- `void setViolationWorkflow (java.lang.String s)`
- `void visit ( Visitor v)`

---

## PolicyAlert

**Package:** `sailpoint.object`

**Description:** An object holding options for notification of policy alerts.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.WorkItemConfig`
- `sailpoint.object.PolicyAlert`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `boolean isNoPolicyViolation ()`
- `boolean isXml ()`
- `void setNoPolicyViolation (boolean b)`

---

## PolicyExecutor

**Package:** `sailpoint.object`

**Description:** The interface of a class that implements policies.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `java.util.List<PolicyViolation> evaluate ( SailPointContext context, Policy policy, Identity id)`
- `void makeAlertable ( PolicyViolation policyViolation)`
- `void setSimulating (boolean simulating)`

---

## PolicyImpactAnalysis.ViolationResult

**Package:** `sailpoint.object`

**Description:** Internal object to hold violation result statistics.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.PolicyImpactAnalysis.ViolationResult`

**Attributes:** N/A

**Methods:**
- `int getIdentityCount ()`
- `java.lang.String getRuleName ()`
- `int getViolationCount ()`
- `void setIdentityCount (int count)`
- `void setRuleName (java.lang.String rule)`
- `void setViolationCount (int count)`

---

## PolicyImpactAnalysis

**Package:** `sailpoint.object`

**Description:** Used to hold the results of an impact analysis on a Policy. These will be stored inside a TaskResult .

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.PolicyImpactAnalysis`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void addViolationResultToList (java.lang.String rule, int violationCount, int identityCount)`
- `boolean getNoActiveRules ()`
- `java.lang.String getPolicyName ()`
- `java.lang.String getPolicyType ()`
- `java.util.List<PolicyImpactAnalysis.ViolationResult> getViolationResults ()`
- `void setNoActiveRules (boolean state)`
- `void setPolicyName (java.lang.String name)`
- `void setPolicyType (java.lang.String type)`
- `void setViolationResults (java.util.List< PolicyImpactAnalysis.ViolationResult > list)`

---

## PolicyViolation.IPolicyViolationOwnerSource

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `Identity getViolationOwner ()`
- `Rule getViolationOwnerRule ()`
- `Policy.ViolationOwnerType getViolationOwnerType ()`
- `void setViolationOwner ( Identity val)`
- `void setViolationOwnerRule ( Rule val)`
- `void setViolationOwnerType ( Policy.ViolationOwnerType val)`

---

## PolicyViolation.Status

**Package:** `sailpoint.object`

**Description:** The states an violation can be in.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `PolicyViolation.Status`
- `sailpoint.object.PolicyViolation.Status`
- `java.io.Serializable`
- `java.lang.Comparable<PolicyViolation.Status>`
- `sailpoint.tools.MessageKeyHolder`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticPolicyViolation.Status valueOf (java.lang.String name)`
- `staticPolicyViolation.Status[] values ()`

---

## PolicyViolation

**Package:** `sailpoint.object`

**Description:** A class holding information about one policy violation for an Identity.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.PolicyViolation`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `Certifiable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ARG_DETAILS`
- `static java.lang.String ARG_RELEVANT_APPS`
- `static java.lang.String ARG_RISK_WEIGHT`

**Methods:**
- `void addLeftBundle (java.lang.String name)`
- `void addRightBundle (java.lang.String name)`
- `java.lang.String getActivityId ()`
- `java.lang.Object getArgument (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getArguments ()`
- `java.util.List<java.lang.String> getBundleNamesMarkedForRemediation ()`
- `java.lang.String getBundlesMarkedForRemediation ()`
- `BaseConstraint getConstraint ( Resolver r)`
- `java.lang.String getConstraintId ()`
- `java.lang.String getConstraintName ()`
- `ViolationDetails getDetails ()`
- `java.lang.String getDisplayableName ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `java.lang.String getEntitlementsMarkedForRemediation ()`
- `java.util.List<sailpoint.web.certification.PolicyTreeNode> getEntitlementsToRemediate ()`
- `Identity getIdentity ()`
- `java.lang.String getLeftBundles ()`
- `java.util.List<Bundle> getLeftBundles ( Resolver r)`
- `java.lang.String getMitigator ()`
- `Policy getPolicy ( Resolver r)`
- `java.lang.String getPolicyId ()`
- `java.lang.String getPolicyName ()`
- `static sailpoint.web.certification.PolicyTreeNode getPolicyTreeNodeFromCsv (java.lang.String csv)`
- `java.util.List<java.lang.String> getRelevantApps ()`
- `java.util.List<Application> getRelevantApps ( Resolver resolver)`
- `java.lang.String getRenderer ()`
- `java.lang.String getRightBundles ()`
- `java.util.List<Bundle> getRightBundles ( Resolver r)`
- `java.lang.String getSODSummary ()`
- `PolicyViolation.Status getStatus ()`
- `java.util.List<IdentitySelector.MatchTerm> getViolatingEntitlements ()`
- `boolean hasName ()`
- `boolean isActive ()`
- `boolean isAlertable ()`
- `boolean isConstraintEqual ( PolicyViolation other)`
- `boolean isMarkedForRemediation ( Bundle b)`
- `boolean isNameUnique ()`
- `void setActive (boolean b)`
- `void setActivityId (java.lang.String id)`
- `void setAlertable (boolean b)`
- `void setArgument (java.lang.String name, java.lang.Object value)`
- `void setArguments ( Attributes <java.lang.String,java.lang.Object> args)`
- `void setBundleNamesMarkedForRemediation (java.util.List<java.lang.String> bundles)`
- `void setBundlesMarkedForRemediation (java.lang.String names)`
- `void setBundlesMarkedForRemediation (java.util.List< Bundle > bundles)`
- `void setConstraint ( BaseConstraint c)`
- `void setConstraintId (java.lang.String id)`
- `void setConstraintName (java.lang.String name)`
- `void setDetails ( ViolationDetails details)`
- `void setEntitlementsMarkedForRemediation (java.lang.String entitlementsMarkedForRemediation)`
- `void setEntitlementsToRemediate (java.util.List<sailpoint.web.certification.PolicyTreeNode> entitlementsToRemediate)`
- `void setIdentity ( Identity id)`
- `void setLeftBundles (java.lang.String names)`
- `void setMitigator (java.lang.String name)`
- `void setNotify (boolean b)`
- `void setPolicy ( Policy p)`
- `void setPolicyId (java.lang.String id)`
- `void setPolicyName (java.lang.String id)`
- `void setRelevantApps (java.util.List<java.lang.String> apps)`
- `void setRenderer (java.lang.String s)`
- `void setRightBundles (java.lang.String names)`
- `void setStatus ( PolicyViolation.Status _status)`
- `void setViolatingEntitlements (java.util.List< IdentitySelector.MatchTerm > entitlements)`
- `void visit ( Visitor v)`

---

## PostCommitNotificationObject.Type

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `PostCommitNotificationObject.Type`
- `sailpoint.object.PostCommitNotificationObject.Type`
- `java.io.Serializable`
- `java.lang.Comparable<PostCommitNotificationObject.Type>`

**Attributes:** N/A

**Methods:**
- `staticPostCommitNotificationObject.Type valueOf (java.lang.String name)`
- `staticPostCommitNotificationObject.Type[] values ()`

---

## PostCommitNotificationObject

**Package:** `sailpoint.object`

**Description:** Convert the xml representation of the committed object into an actual object.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.PostCommitNotificationObject`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.String getClassName ()`
- `java.lang.Object getCommittedObject ()`
- `java.lang.String getCommittedObjectString ()`
- `java.lang.String getConsumer ()`
- `java.lang.String getModifiedId ()`
- `java.lang.String getSubtype ()`
- `PostCommitNotificationObject.Type getType ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `void setClassName (java.lang.String className)`
- `void setCommittedObjectString (java.lang.String committedObjectString)`
- `void setConsumer (java.lang.String consumer)`
- `void setModifiedId (java.lang.String modifiedId)`
- `void setSubtype (java.lang.String subtype)`
- `void setType ( PostCommitNotificationObject.Type type)`

---

## ProcessLog

**Package:** `sailpoint.object`

**Description:** Override the default display columns for this object type.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.ProcessLog`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `int calculateStepDuration ()`
- `java.lang.String getApprovalName ()`
- `java.lang.String getCaseId ()`
- `java.lang.String getCaseStatus ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `java.util.Date getEndTime ()`
- `int getEscalations ()`
- `java.lang.String getLauncher ()`
- `java.lang.String getOwnerName ()`
- `java.lang.String getProcessName ()`
- `java.util.Date getStartTime ()`
- `int getStepDuration ()`
- `java.lang.String getStepName ()`
- `java.lang.String getWorkflowCaseName ()`
- `boolean hasName ()`
- `void setApprovalName (java.lang.String approvalName)`
- `void setCaseId (java.lang.String caseId)`
- `void setCaseStatus (java.lang.String status)`
- `void setEndTime (java.util.Date end)`
- `void setEscalations (int escalations)`
- `void setLauncher (java.lang.String launcher)`
- `void setOwnerName (java.lang.String ownerName)`
- `void setProcessName (java.lang.String processName)`
- `void setStartTime (java.util.Date start)`
- `void setStepDuration (int stepDuration)`
- `void setStepName (java.lang.String stepName)`
- `void setWorkflowCaseName (java.lang.String workflowCaseName)`
- `java.lang.String toString ()`

---

## Profile

**Package:** `sailpoint.object`

**Description:** The definition of a collection of access rights on an account on a particular application. These are used within Bundle classes (roles) to define the detection rules.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Profile`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `Certifiable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `void addConstraint ( Filter c)`
- `void addPermission ( Permission p)`
- `java.lang.String getAccountType ()`
- `Application getApplication ()`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `Bundle getBundle ()`
- `java.util.List<Filter> getConstraints ()`
- `java.util.List<Permission> getPermissions ()`
- `int getProfileOrdinal ()`
- `boolean isNameUnique ()`
- `void load ()`
- `void resetPermissions ()`
- `void setAccountType (java.lang.String type)`
- `void setApplication ( Application r)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> a)`
- `void setBundle ( Bundle id)`
- `void setConstraints (java.util.List< Filter > cons)`
- `void setPermissions (java.util.List< Permission > perms)`
- `void visit ( Visitor v)`

---

## ProfileDifference

**Package:** `sailpoint.object`

**Description:** Class used to contain the results of a comparison between two Profile objects. This part of the model built for role impact analysis. They are calculated by the RoleLifecycler and displayed in role approval work items.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ProfileDifference`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void add ( Difference diff)`
- `java.lang.String getApplication ()`
- `java.util.List<Difference> getAttributeDifferences ()`
- `Difference getFilterDifference ()`
- `java.util.List<Difference> getPermissionDifferences ()`
- `boolean hasDifferences ()`
- `void setApplication (java.lang.String s)`
- `void setApplication ( Application app)`
- `void setAttributeDifferences (java.util.List< Difference > diffs)`
- `void setFilterDifference ( Difference diff)`
- `void setPermissionDifferences (java.util.List< Difference > diffs)`

---

## Projection.LeafProjection.Operation

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Projection.LeafProjection.Operation`
- `sailpoint.object.Projection.LeafProjection.Operation`
- `java.io.Serializable`
- `java.lang.Comparable<Projection.LeafProjection.Operation>`

**Attributes:** N/A

**Methods:**
- `staticProjection.LeafProjection.Operation valueOf (java.lang.String name)`
- `staticProjection.LeafProjection.Operation[] values ()`

---

## Projection.LeafProjection

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Projection`
- `sailpoint.object.Projection.LeafProjection`
- `java.io.Serializable`

**Attributes:** N/A

**Methods:**
- `Projection.LeafProjection.Operation getOperation ()`
- `java.lang.String getPropertyName ()`

---

## Projection.ListProjection

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Projection`
- `sailpoint.object.Projection.ListProjection`
- `java.io.Serializable`

**Attributes:** N/A

**Methods:**
- `Projection.ListProjection add ( Projection projection)`
- `java.util.List<Projection> getProjections ()`

---

## Projection

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Projection`
- `java.io.Serializable`

**Attributes:** N/A

**Methods:**
- `staticProjection.ListProjection list ( Projection ... projections)`
- `staticProjection property (java.lang.String propName)`

---

## Propagator

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Propagator`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getClassName ()`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> a)`
- `void setClassName (java.lang.String className)`

---

## PropertyInfo

**Package:** `sailpoint.object`

**Description:** Gag.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.PropertyInfo`
- `java.io.Serializable`
- `java.lang.Cloneable`

**Attributes:**
- `static java.lang.String TYPE_APPLICATION`
- `static java.lang.String TYPE_BOOLEAN`
- `static java.lang.String TYPE_DATE`
- `static java.lang.String TYPE_IDENTITY`
- `static java.lang.String TYPE_INT`
- `static java.lang.String TYPE_LONG`
- `static java.lang.String TYPE_MANAGED_ATTRIBUTE`
- `static java.lang.String TYPE_PERMISSION`
- `static java.lang.String TYPE_ROLE`
- `static java.lang.String TYPE_RULE`
- `static java.lang.String TYPE_SCOPE`
- `static java.lang.String TYPE_SCRIPT`
- `static java.lang.String TYPE_SECRET`
- `static java.lang.String TYPE_STRING`

**Methods:**
- `java.util.List<Filter.LogicalOperation> getAllowedOperations ()`
- `java.lang.String getDescription ()`
- `java.lang.String getValueType ()`
- `void setAllowedOperations (java.util.List< Filter.LogicalOperation > allowedOperations)`
- `void setDescription (java.lang.String description)`
- `void setValueType (java.lang.String type)`
- `java.lang.String toString ()`

---

## ProvisioningConfig

**Package:** `sailpoint.object`

**Description:** A subcomponent of the Application model holding information related to provisioning.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ProvisioningConfig`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void add ( ManagedResource res)`
- `Script getClusterScript ()`
- `ManagedResource getManagedResource (java.lang.String name)`
- `ManagedResource getManagedResource ( Application app)`
- `java.util.List<ManagedResource> getManagedResources ()`
- `Rule getPlanInitializer ()`
- `DynamicValue getPlanInitializerLogic ()`
- `Script getPlanInitializerScript ()`
- `int getProvisioningRequestExpiration ()`
- `ManagedResource getRemoteManagedResource (java.lang.String name)`
- `boolean isDeleteToDisable ()`
- `boolean isMetaUser ()`
- `boolean isNoPermissions ()`
- `boolean isNoProvisioningRequests ()`
- `boolean isOptimisticProvisionings ()`
- `boolean isUniversalManager ()`
- `void load ()`
- `void removeManagedResource ( Application app)`
- `void setClusterScript ( Script script)`
- `void setDeleteToDisable (boolean deleteToDisable)`
- `void setManagedResources (java.util.List< ManagedResource > resources)`
- `void setMetaUser (boolean b)`
- `void setNoPermissions (boolean b)`
- `void setNoProvisioningRequests (boolean b)`
- `void setOptimisticProvisionings (boolean b)`
- `void setPlanInitializer ( Rule rule)`
- `void setPlanInitializerScript ( Script script)`
- `void setProvisioningRequestExpiration (int i)`
- `void setUniversalManager (boolean b)`

---

## ProvisioningPlan.AbstractRequest

**Package:** `sailpoint.object`

**Description:** The common representation of a request for one resource object. This is subclassed by ObjectRequest and AccountRequest.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ProvisioningPlan.AbstractRequest`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String ATT_ALLOW_DUPLICATE_ACCOUNTS`
- `static java.lang.String ATT_SELECTOR_RULE_SRC`

**Methods:**
- `void add ( ProvisioningPlan.GenericRequest req)`
- `void addAll (java.util.Collection<? extends ProvisioningPlan.GenericRequest > reqs)`
- `void addArgument (java.lang.String key, java.lang.Object value)`
- `void addAssignmentIds (java.lang.String ids)`
- `void clone ( ProvisioningPlan.AbstractRequest src)`
- `void clone ( ProvisioningPlan.AbstractRequest src, boolean cloneResultErrors)`
- `ProvisioningPlan.AbstractRequest cloneRequest ()`
- `ProvisioningPlan.AbstractRequest cloneRequest (boolean cloneResultErrors)`
- `void cloneRequestProperties ( ProvisioningPlan.AbstractRequest src)`
- `void cloneRequestProperties ( ProvisioningPlan.AbstractRequest src, boolean cloneResultErrors)`
- `ProvisioningPlan.AbstractRequest collapse (boolean includeNullSet)`
- `boolean containsTargetCollector ()`
- `void fromMap (java.util.Map map)`
- `java.lang.Object get (java.lang.String name)`
- `Rule getAccountSelectorRule ()`
- `java.lang.String getApplication ()`
- `Application getApplication ( Resolver resolver)`
- `java.lang.String getApplicationName ()`
- `java.lang.Object getArgument (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getArguments ()`
- `java.util.List<java.lang.String> getAssignmentIdList ()`
- `java.lang.String getAssignmentIds ()`
- `ProvisioningPlan.AttributeRequest getAttributeRequest (java.lang.String name)`
- `ProvisioningPlan.AttributeRequest getAttributeRequest (java.lang.String name, java.lang.Object value)`
- `java.util.List<ProvisioningPlan.AttributeRequest> getAttributeRequests ()`
- `java.util.List<ProvisioningPlan.AttributeRequest> getAttributeRequests (java.lang.String name)`
- `java.lang.String getComments ()`
- `java.lang.String getInstance ()`
- `staticProvisioningPlan.AbstractRequest getLoggingRequest ( ProvisioningPlan.AbstractRequest req)`
- `java.lang.String getNativeIdentity ()`
- `ProvisioningPlan.ObjectOperation getOp ()`
- `ProvisioningPlan.PermissionRequest getPermissionRequest (java.lang.String target)`
- `java.util.List<ProvisioningPlan.PermissionRequest> getPermissionRequests ()`
- `java.util.List<ProvisioningPlan.PermissionRequest> getPermissionRequests (java.lang.String target)`
- `<T extendsProvisioningPlan.GenericRequest>T getRequest (java.util.List<T> reqs, java.lang.String name)`
- `<T extendsProvisioningPlan.GenericRequest>T getRequest (java.util.List<T> reqs, java.lang.String name, java.lang.Object value)`
- `ProvisioningResult getResult ()`
- `java.lang.String getSourceRole ()`
- `java.lang.String getString (java.lang.String name)`
- `java.lang.String getTargetCollector ()`
- `java.lang.String getTargetIntegration ()`
- `java.lang.String getTrackingId ()`
- `java.lang.String getType ()`
- `java.lang.String getUnmappedApplication ()`
- `boolean hasAssignmentId (java.lang.String id)`
- `boolean hasMultipleAttributesOrPermissions ()`
- `abstractProvisioningPlan.AbstractRequest instantiate ()`
- `boolean isAccountRequest ()`
- `boolean isAttributesMatch ( ProvisioningPlan.AbstractRequest other)`
- `boolean isCleanable ()`
- `boolean isEmpty ()`
- `boolean isGroupRequest ()`
- `boolean isMatch ( ProvisioningPlan.AbstractRequest other)`
- `boolean isTargetMatch ( ProvisioningPlan.AbstractRequest other)`
- `boolean needsRetry ()`
- `void put (java.lang.String name, java.lang.Object value)`
- `void remove ( ProvisioningPlan.GenericRequest req)`
- `void setAccountSelectorRule ( Rule rule)`
- `void setApplication (java.lang.String s)`
- `void setArguments ( Attributes <java.lang.String,java.lang.Object> atts)`
- `void setAssignmentIds (java.lang.String ids)`
- `void setAttributeRequests (java.util.List< ProvisioningPlan.AttributeRequest > reqs)`
- `void setCleanable (boolean b)`
- `void setComments (java.lang.String c)`
- `void setInstance (java.lang.String instance)`
- `void setNativeIdentity (java.lang.String id)`
- `void setOp ( ProvisioningPlan.ObjectOperation op)`
- `void setPermissionRequests (java.util.List< ProvisioningPlan.PermissionRequest > reqs)`
- `void setResult ( ProvisioningResult r)`
- `void setSourceRole (java.lang.String s)`
- `void setTargetIntegration (java.lang.String name)`
- `void setTrackingId (java.lang.String trackingId)`
- `void setType (java.lang.String s)`
- `void setUnmappedApplication (java.lang.String s)`
- `java.util.Map toMap ()`

---

## ProvisioningPlan.AccountRequest.Operation

**Package:** `sailpoint.object`

**Description:** Defines the operation to perform on the account. This values are the same as ObjectRequest.Operation. Either can be used when building the request. This is for backward compatibility with pre-6.0 code.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ProvisioningPlan.AccountRequest.Operation`
- `sailpoint.object.ProvisioningPlan.AccountRequest.Operation`
- `java.io.Serializable`
- `java.lang.Comparable<ProvisioningPlan.AccountRequest.Operation>`

**Attributes:** N/A

**Methods:**
- `staticProvisioningPlan.AccountRequest.Operation valueOf (java.lang.String name)`
- `staticProvisioningPlan.AccountRequest.Operation[] values ()`

---

## ProvisioningPlan.AccountRequest

**Package:** `sailpoint.object`

**Description:** Represents a request for one application account. This exists for backward compatibility with many things prior to 6.0 but it is effectively nothing more than an ObjectRequest. Some deprecated methods are carried forward for XML upgrading.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ProvisioningPlan.AbstractRequest`
- `sailpoint.object.ProvisioningPlan.AccountRequest`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String ATTACHMENT_CONFIG_LIST`
- `static java.lang.String ATTACHMENTS`
- `static java.lang.String RECOMMENDED_ACCESS`
- `static java.lang.String TYPE_ENTITLEMENT`
- `static java.lang.String TYPE_ROLE`

**Methods:**
- `ProvisioningPlan.AccountRequest clone ()`
- `void cloneAccountProperties ( ProvisioningPlan.AccountRequest src)`
- `java.util.List<ProvisioningPlan.AccountRequest> expandRequest ()`
- `ProvisioningPlan.AccountRequest.Operation getOperation ()`
- `java.lang.String getRequestID ()`
- `boolean hasNoAttributesOrPermissions ()`
- `ProvisioningPlan.AbstractRequest instantiate ()`
- `boolean isAccountRequest ()`
- `boolean isRoleExpansion ()`
- `void setOperation ( ProvisioningPlan.AccountRequest.Operation op)`
- `void setRequestID (java.lang.String id)`
- `void setRoleExpansion (boolean b)`

---

## ProvisioningPlan.AttributeRequest

**Package:** `sailpoint.object`

**Description:** Represents an operation on a single account attribute. A Script can be used if you need to calculate a value at runtime rather than defining it statically. This is intended for plans attached to roles, not the compiled plans passed to the IntegrationExecutors.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ProvisioningPlan.GenericRequest`
- `sailpoint.object.ProvisioningPlan.AttributeRequest`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String ATT_DEASSIGN_ENTITLEMENTS`
- `static java.lang.String ATT_PREFER_REMOVE_OVER_RETAIN`

**Methods:**
- `void fromMap (java.util.Map map)`
- `java.lang.Object getValue ( SailPointContext ctx)`
- `ProvisioningPlan.GenericRequest instantiate ()`
- `boolean isSecret ()`
- `java.util.Map toMap ()`

---

## ProvisioningPlan.GenericRequest

**Package:** `sailpoint.object`

**Description:** An interface implemented by both AttributeRequest and PermissionRequest so they can be treated in the same way for plan analysis and compilation. In retrospect, it would have been better just to use the same class for both of these. The name/value is rendered differently in the subclasses AttributeRequest calls these name/value and PermissionRequest calls them target/rights. There is also so work done in PermissionRequest to maintain the _value as a List for plan compilation but provide getTarget setTarget methods that take a CSV string like is use in Permission objects. The _targetCollector maintains the name of the target collector (aggregation source) used to aggregate the target permission. It is used to route the provisioning request to the same target collector during plan compilation.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ProvisioningPlan.GenericRequest`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void addValues (java.lang.Object something, boolean nocase)`
- `ProvisioningPlan.GenericRequest clone ()`
- `void clone ( ProvisioningPlan.GenericRequest src)`
- `ProvisioningPlan.GenericRequest collapse (boolean includeNullSet)`
- `boolean equals (java.lang.Object o)`
- `java.lang.Object get (java.lang.String name)`
- `java.util.Date getAddDate ()`
- `Attributes<java.lang.String,​java.lang.Object> getArgs ()`
- `Attributes<java.lang.String,​java.lang.Object> getArguments ()`
- `java.lang.String getAssignmentId ()`
- `boolean getBoolean (java.lang.String name)`
- `java.lang.String getComments ()`
- `java.lang.String getDisplayValue ()`
- `java.lang.String getName ()`
- `ProvisioningPlan.Operation getOp ()`
- `ProvisioningPlan.Operation getOperation ()`
- `java.util.Date getRemoveDate ()`
- `ProvisioningResult getResult ()`
- `Script getScript ()`
- `java.lang.String getString (java.lang.String name)`
- `java.lang.String getTargetCollector ()`
- `java.lang.String getTrackingId ()`
- `java.lang.String getUnmappedName ()`
- `java.lang.Object getValue ()`
- `int hashCode ()`
- `boolean hasTargetCollector ()`
- `abstractProvisioningPlan.GenericRequest instantiate ()`
- `boolean isAssignment ()`
- `boolean isLinkEdit ()`
- `abstract boolean isSecret ()`
- `boolean okToSimplify ()`
- `void put (java.lang.String name, java.lang.Object value)`
- `java.lang.Object remove (java.lang.String name)`
- `void removeValues (java.lang.Object something, boolean nocase)`
- `void retainValues (java.lang.Object something, boolean nocase)`
- `void setAddDate (java.util.Date d)`
- `void setArgs ( Attributes <java.lang.String,java.lang.Object> atts)`
- `void setArguments ( Attributes <java.lang.String,java.lang.Object> atts)`
- `void setAssignment (boolean b)`
- `void setAssignmentId (java.lang.String id)`
- `void setComments (java.lang.String c)`
- `void setDisplayValue (java.lang.String val)`
- `void setLinkEdit (boolean b)`
- `void setName (java.lang.String s)`
- `void setOp ( ProvisioningPlan.Operation op)`
- `void setOperation ( ProvisioningPlan.Operation op)`
- `void setRemoveDate (java.util.Date d)`
- `void setResult ( ProvisioningResult r)`
- `void setScript ( Script s)`
- `void setTargetCollector (java.lang.String targetCollector)`
- `void setTrackingId (java.lang.String id)`
- `void setUnmappedName (java.lang.String s)`
- `void setValue (java.lang.Object o)`

---

## ProvisioningPlan.ObjectOperation

**Package:** `sailpoint.object`

**Description:** Defines the operations that can be performed on a resource object. If not specified the default is assumed to be Modify. Note that "Set" is included in this list only for a temporary backward compatibility kludge when parsing old ObjectRequests created by the RemediationCalculator for role certifications. ObjectRequest.operation used to be a different enumeration but the operation was always Set. This must be parsed and upgraded to Modify.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ProvisioningPlan.ObjectOperation`
- `sailpoint.object.ProvisioningPlan.ObjectOperation`
- `java.io.Serializable`
- `java.lang.Comparable<ProvisioningPlan.ObjectOperation>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticProvisioningPlan.ObjectOperation valueOf (java.lang.String name)`
- `staticProvisioningPlan.ObjectOperation[] values ()`

---

## ProvisioningPlan.ObjectRequest

**Package:** `sailpoint.object`

**Description:** Expand an object request into multiple object requests each containing single attribute request or single permission request This is so that the ObjectRequest whose AttributeRequest or PermissionRequest contains "targetCollector" field gets routed to the pass-through proxy for the collector object for provisioning.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ProvisioningPlan.AbstractRequest`
- `sailpoint.object.ProvisioningPlan.ObjectRequest`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String ATT_OBJ_REQ_NO_PROVISIONING`

**Methods:**
- `ProvisioningPlan.ObjectRequest clone ()`
- `java.util.List<ProvisioningPlan.ObjectRequest> expandRequest ()`
- `java.lang.String getRequestID ()`
- `java.lang.String getTargetClass ()`
- `java.lang.String getTargetId ()`
- `java.lang.String getTargetName ()`
- `Reference getTargetReference ()`
- `boolean hasNoAttributesOrPermissions ()`
- `ProvisioningPlan.AbstractRequest instantiate ()`
- `boolean isGroupRequest ()`
- `boolean isMatch ( ProvisioningPlan.AbstractRequest other)`
- `void setRequestID (java.lang.String id)`
- `void setTargetClass (java.lang.String clazz)`
- `void setTargetId (java.lang.String targetId)`
- `void setTargetName (java.lang.String targetName)`
- `void setTargetReference ( Reference ref)`

---

## ProvisioningPlan.Operation

**Package:** `sailpoint.object`

**Description:** Operation codes for attributes and permissions. Set means to replace the current value (the default). Add means to incrementally add something to the current value. Remove means to incrementally remove something to the current value. Revoke is used only during certification to indicate that a role assignment should both be removed, and marked as permanently revoked so the assignment rules don't put it back. Retain means to keep the attribute values if they exist but do not add them if they do not exist. It is only used in high-level plans, never in a compiled plan. The effect is to remove the value from Remove or Revoke operations but not to leave Add operations if one did not already exist.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ProvisioningPlan.Operation`
- `sailpoint.object.ProvisioningPlan.Operation`
- `java.io.Serializable`
- `java.lang.Comparable<ProvisioningPlan.Operation>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticProvisioningPlan.Operation valueOf (java.lang.String name)`
- `staticProvisioningPlan.Operation[] values ()`

---

## ProvisioningPlan.PermissionRequest

**Package:** `sailpoint.object`

**Description:** Represents an operation on a single account permission.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ProvisioningPlan.GenericRequest`
- `sailpoint.object.ProvisioningPlan.PermissionRequest`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void fromMap (java.util.Map map)`
- `java.lang.String getRights ()`
- `java.util.List<java.lang.String> getRightsList ()`
- `java.util.List<java.lang.String> getRightsListClone ()`
- `java.lang.String getTarget ()`
- `boolean isSecret ()`
- `void setRights (java.lang.String s)`
- `void setRightsList (java.util.List<java.lang.String> list)`
- `void setTarget (java.lang.String s)`
- `java.util.Map toMap ()`

---

## ProvisioningPlan

**Package:** `sailpoint.object`

**Description:** Class used maintain a complex provisioning request involving several applications.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ProvisioningPlan`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String ACCOUNT_GROUP_APPLICATION`
- `static java.lang.String ACCOUNT_GROUP_DESCRIPTION`
- `static java.lang.String ACCOUNT_GROUP_NAME`
- `static java.lang.String ACCOUNT_GROUP_NATIVE_IDENTITY`
- `static java.lang.String ACCOUNT_GROUP_OWNER`
- `static java.lang.String ACCOUNT_GROUP_REFERENCE_ATTRIBUTE`
- `static java.lang.String ACCOUNT_GROUP_SCOPE`
- `static java.lang.String APP_IDM`
- `static java.lang.String APP_IIQ`
- `static java.lang.String ARG_ADD_DATE`
- `static java.lang.String ARG_ALLOW_SIMPLIFICATION`
- `static java.lang.String ARG_ASSIGNMENT`
- `static java.lang.String ARG_ASSIGNMENT_NOTE`
- `static java.lang.String ARG_CHECK_POLICY`
- `static java.lang.String ARG_COMMENTS`
- `static java.lang.String ARG_DESTINATION_IDENTITY`
- `static java.lang.String ARG_FORCE_NEW_ACCOUNT`
- `static java.lang.String ARG_IN_RETRY`
- `static java.lang.String ARG_LINK_EDIT`
- `static java.lang.String ARG_LOCK_TIMEOUT`
- `static java.lang.String ARG_NEGATIVE_ASSIGNMENT`
- `static java.lang.String ARG_PASSWORD_EXPIRY`
- `static java.lang.String ARG_PERMITTED_BY`
- `static java.lang.String ARG_PREVIOUS_VALUE`
- `static java.lang.String ARG_REMOVE_DATE`
- `static java.lang.String ARG_REQUESTER`
- `static java.lang.String ARG_REQUIRED`
- `static java.lang.String ARG_SECRET`
- `static java.lang.String ARG_SOURCE`
- `static java.lang.String ARG_SOURCE_ID`
- `static java.lang.String ARG_SOURCE_IDENTITY`
- `static java.lang.String ARG_SOURCE_NAME`
- `static java.lang.String ARG_TYPE`
- `static java.lang.String ARG_TYPE_DATE`
- `static java.lang.String ASSIGNMENT_ID_NEW`
- `static java.lang.Object ATT_ASSIGNED_SCOPE`
- `static java.lang.String ATT_ATTRIBUTE_NAME`
- `static java.lang.String ATT_ATTRIBUTE_VALUE`
- `static java.lang.String ATT_CURRENT_PASSWORD`
- `static java.lang.String ATT_GENERATED`
- `static java.lang.String ATT_IDM_ROLES`
- `static java.lang.String ATT_IIQ_ACTIVITY_CONFIG`
- `static java.lang.String ATT_IIQ_ARCHIVES`
- `static java.lang.String ATT_IIQ_ASSIGNED_ROLES`
- `static java.lang.String ATT_IIQ_AUTHORIZED_SCOPES`
- `static java.lang.String ATT_IIQ_CAPABILITIES`
- `static java.lang.String ATT_IIQ_CAPABILITIES_NEW`
- `static java.lang.String ATT_IIQ_CONTROLLED_SCOPES`
- `static java.lang.String ATT_IIQ_CONTROLLED_SCOPES_NEW`
- `static java.lang.String ATT_IIQ_CONTROLS_ASSIGNED_SCOPE`
- `static java.lang.String ATT_IIQ_DETECTED_ROLES`
- `static java.lang.String ATT_IIQ_EVENTS`
- `static java.lang.String ATT_IIQ_LINKS`
- `static java.lang.String ATT_IIQ_NEEDS_REFRESH`
- `static java.lang.String ATT_IIQ_PASSWORD`
- `static java.lang.String ATT_IIQ_PROVISIONING_REQUESTS`
- `static java.lang.String ATT_IIQ_ROLE_CHILD`
- `static java.lang.String ATT_IIQ_ROLE_GRANTED_CAPABILITY`
- `static java.lang.String ATT_IIQ_ROLE_GRANTED_SCOPE`
- `static java.lang.String ATT_IIQ_ROLE_PERMIT`
- `static java.lang.String ATT_IIQ_ROLE_PROFILES`
- `static java.lang.String ATT_IIQ_ROLE_REQUIREMENT`
- `static java.lang.String ATT_IIQ_SCOPE`
- `static java.lang.String ATT_IIQ_SNAPSHOTS`
- `static java.lang.String ATT_IIQ_WORKGROUPS`
- `static java.lang.String ATT_OBJECT_APPLICATION`
- `static java.lang.String ATT_OBJECT_ARGUMENTS`
- `static java.lang.String ATT_OBJECT_ATTRIBUTES`
- `static java.lang.String ATT_OBJECT_ID`
- `static java.lang.String ATT_OBJECT_INSTANCE`
- `static java.lang.String ATT_OBJECT_PERMISSIONS`
- `static java.lang.String ATT_OBJECT_TYPE`
- `static java.lang.String ATT_OP`
- `static java.lang.String ATT_PASSWORD`
- `static java.lang.String ATT_PERMISSION_RIGHTS`
- `static java.lang.String ATT_PERMISSION_TARGET`
- `static java.lang.String ATT_PLAN_ACCOUNTS`
- `static java.lang.String ATT_PLAN_ARGUMENTS`
- `static java.lang.String ATT_PLAN_IDENTITY`
- `static java.lang.String ATT_PLAN_INTEGRATION_DATA`
- `static java.lang.String ATT_PLAN_OBJECTS`
- `static java.lang.String ATT_PLAN_PROFILE_CONSTRAINTS`
- `static java.lang.String ATT_PLAN_PROFILE_DESCRIPTION`
- `static java.lang.String ATT_PLAN_PROFILE_ORDINAL`
- `static java.lang.String ATT_PLAN_REQUESTERS`
- `static java.lang.String ATT_PRE_EXPIRE`
- `static java.lang.String ATT_REQUEST_ARGUMENTS`
- `static java.lang.String ATT_REQUEST_RESULT`
- `static java.lang.String IIQ_APPLICATION_NAME`
- `static java.lang.String OBJECT_TYPE_GROUP`
- `static java.lang.String OBJECT_TYPE_MANAGED_ATTRIBUTE`

**Methods:**
- `void add (java.lang.String appname, java.lang.String attname, java.lang.Object value)`
- `ProvisioningPlan.AccountRequest add (java.lang.String appname, java.lang.String nativeIdentity, java.lang.String attname, ProvisioningPlan.Operation op, java.lang.Object value)`
- `ProvisioningPlan.AccountRequest add (java.lang.String appname, java.lang.String identity, ProvisioningPlan.AccountRequest.Operation op)`
- `void add (java.lang.String appname, java.lang.String attname, ProvisioningPlan.Operation op, java.lang.Object value)`
- `void add ( ProvisioningPlan.AccountRequest account)`
- `void add ( ProvisioningPlan.ObjectRequest object)`
- `void addFiltered ( ProvisioningPlan.AbstractRequest request)`
- `void addObjectRequest ( ProvisioningPlan.ObjectRequest request)`
- `void addRequest ( ProvisioningPlan.AbstractRequest req)`
- `void addRequester ( Identity requester)`
- `static java.lang.Object addValues (java.lang.Object something, java.lang.Object toSomething)`
- `static java.lang.Object addValues (java.lang.Object something, java.lang.Object toSomething, boolean nocase)`
- `ProvisioningPlan collapse (boolean includeNullSet)`
- `static boolean contains (java.util.List list, java.lang.Object value, boolean nocase)`
- `java.util.Collection<EntitlementSnapshot> convertToEntitlementSnapshots ()`
- `static boolean equals (java.lang.Object o1, java.lang.Object o2, boolean nocase)`
- `void fromMap (java.util.Map map)`
- `java.lang.Object get (java.lang.String name)`
- `ProvisioningPlan.AccountRequest getAccountRequest (java.lang.String appname)`
- `ProvisioningPlan.AccountRequest getAccountRequest (java.lang.String appname, java.lang.String instance, java.lang.String nativeIdentity)`
- `ProvisioningPlan.AccountRequest getAccountRequestByOperation (java.lang.String appName, java.lang.String instance, java.lang.String nativeIdentity, ProvisioningPlan.AccountRequest.Operation operation)`
- `java.util.List<ProvisioningPlan.AccountRequest> getAccountRequests ()`
- `java.util.List<ProvisioningPlan.AccountRequest> getAccountRequests (java.lang.String appname)`
- `java.util.List<ProvisioningPlan.AccountRequest> getAccountRequests (java.lang.String appname, java.lang.String nativeIdentity)`
- `java.util.List<ProvisioningPlan.AbstractRequest> getAllRequests ()`
- `java.lang.String getAppForTargetCollector ()`
- `static java.lang.String getApplicationDisplayName (java.lang.String appName)`
- `java.util.List<java.lang.String> getApplicationNames ()`
- `java.util.List<Application> getApplications ( Resolver resolver)`
- `Attributes<java.lang.String,​java.lang.Object> getArguments ()`
- `java.lang.String getComments ()`
- `java.util.List<ProvisioningPlan.AbstractRequest> getFiltered ()`
- `Identity getIdentity ()`
- `ProvisioningPlan.AccountRequest getIDMAccountRequest ()`
- `ProvisioningPlan.AccountRequest getIIQAccountRequest ()`
- `Attributes<java.lang.String,​java.lang.Object> getIntegrationData ()`
- `staticProvisioningPlan getLoggingPlan ( ProvisioningPlan src)`
- `long getMaintenanceExpiration ()`
- `ProvisioningPlan.AccountRequest getMatchingAccountRequest ( ProvisioningPlan.AccountRequest src)`
- `<T extendsProvisioningPlan.AbstractRequest>ProvisioningPlan.AbstractRequest getMatchingRequest (java.util.List<T> requests, ProvisioningPlan.AbstractRequest src)`
- `<T extendsProvisioningPlan.AbstractRequest>ProvisioningPlan.AbstractRequest getMatchingRequest (java.util.List<T> requests, ProvisioningPlan.AbstractRequest src, boolean allowGeneratedId)`
- `ProvisioningPlan.AbstractRequest getMatchingRequest ( ProvisioningPlan.AbstractRequest src)`
- `ProvisioningPlan.AbstractRequest getMatchingRequest ( ProvisioningPlan.AbstractRequest src, boolean allowGeneratedId)`
- `java.util.List<ProvisioningPlan.AccountRequest> getModifyAccountRequests ()`
- `java.lang.String getNativeIdentity ()`
- `java.util.List<ProvisioningPlan.AccountRequest> getNonModifyAccountRequests ()`
- `java.lang.String getNormalizedStatus ()`
- `ProvisioningPlan.ObjectRequest getObjectRequest (java.lang.String appName, java.lang.String instance, java.lang.String nativeIdentity)`
- `java.util.List<ProvisioningPlan.ObjectRequest> getObjectRequests ()`
- `java.util.List<ProvisioningTarget> getProvisioningTargets ()`
- `java.util.List<Question> getQuestionHistory ()`
- `java.util.List<Identity> getRequesters ()`
- `ProvisioningResult getResult ()`
- `static java.util.List<java.lang.String> getSecretProvisionAttributeNames ()`
- `java.lang.String getSource ()`
- `java.lang.String getSourceId ()`
- `java.lang.String getSourceName ()`
- `java.lang.String getSourceType ()`
- `java.lang.String getString (java.lang.String name)`
- `java.lang.String getTargetIntegration ()`
- `java.lang.String getTrackingId ()`
- `boolean hasBeenExecuted ()`
- `boolean hasRequests ()`
- `boolean isEmpty ()`
- `boolean isFullyCommitted ()`
- `boolean isIdentityPlan ()`
- `boolean isIIQ ()`
- `static boolean isIIQ (java.lang.String app)`
- `boolean isProvisioned ()`
- `static boolean isSecret (java.lang.String name)`
- `void merge ( ProvisioningPlan planToMerge)`
- `void merge ( ProvisioningPlan planToMerge, boolean removeMatches)`
- `boolean needsRetry ()`
- `void put (java.lang.String name, java.lang.Object value)`
- `void remove (java.lang.String appname, java.lang.String attname, java.lang.Object value)`
- `static void remove (java.util.List list, java.lang.Object value, boolean nocase)`
- `void remove ( ProvisioningPlan.AccountRequest account)`
- `static void removeAll (java.util.List list, java.util.List values, boolean nocase)`
- `static java.lang.Object removeValues (java.lang.Object something, java.lang.Object fromSomething)`
- `static java.lang.Object removeValues (java.lang.Object something, java.lang.Object fromSomething, boolean nocase)`
- `void resetResults ()`
- `static void retainAll (java.util.List list, java.util.List values, boolean nocase)`
- `static java.lang.Object retainValues (java.lang.Object something, java.lang.Object fromSomething, boolean nocase)`
- `void set (java.lang.String appname, java.lang.String attname, java.lang.Object value)`
- `void setAccountRequests (java.util.List< ProvisioningPlan.AccountRequest > reqs)`
- `void setArguments ( Attributes <java.lang.String,java.lang.Object> atts)`
- `void setComments (java.lang.String c)`
- `void setFiltered (java.util.List< ProvisioningPlan.AbstractRequest > filtered)`
- `void setIdentity ( Identity identity)`
- `void setIntegrationData ( Attributes <java.lang.String,java.lang.Object> integrationData)`
- `void setMaintenanceExpiration (long l)`
- `void setNativeIdentity (java.lang.String s)`
- `void setObjectRequests (java.util.List< ProvisioningPlan.ObjectRequest > reqs)`
- `void setProvisioned (boolean provisioned)`
- `void setProvisioningTargets (java.util.List< ProvisioningTarget > provisioningTargets)`
- `void setQuestionHistory (java.util.List< Question > _questionHistory)`
- `void setRequesters (java.util.List< Identity > _requesters)`
- `void setRequestTrackingId (java.lang.String id)`
- `void setResult ( ProvisioningResult r)`
- `void setSource (java.lang.String s)`
- `void setSource ( Source s)`
- `void setSourceId (java.lang.String sourceId)`
- `void setSourceName (java.lang.String sourceName)`
- `void setSourceType (java.lang.String s)`
- `void setTargetIntegration (java.lang.String name)`
- `void setTrackingId (java.lang.String id)`
- `java.util.Map toMap ()`

---

## ProvisioningProject.FilterReason

**Package:** `sailpoint.object`

**Description:** Enumeration of reasons a value can be filtered out of a plan during compilation.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ProvisioningProject.FilterReason`
- `sailpoint.object.ProvisioningProject.FilterReason`
- `java.io.Serializable`
- `java.lang.Comparable<ProvisioningProject.FilterReason>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticProvisioningProject.FilterReason valueOf (java.lang.String name)`
- `staticProvisioningProject.FilterReason[] values ()`

---

## ProvisioningProject

**Package:** `sailpoint.object`

**Description:** An object maintaining the state of a complex provisioning process. The project may include one or more plans partitioned for each IntegrationConfig, data gathered interactively for to satisfy templates, and various options. These are built and updated by the PlanCompiler, and eventually processed by the PlanEvaluator. They can be stored in workflows if approvals are necessary before the plans can be evaluated.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ProvisioningProject`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String ATT_FILTER_LOGGED`
- `static java.lang.String ATT_FILTER_REASON`

**Methods:**
- `void add ( ProvisioningPlan plan)`
- `void addAccountSelection ( ProvisioningPlan.AccountRequest request, java.util.List< Link > links)`
- `void addExpansionItem ( ExpansionItem item)`
- `void addMessage ( Message msg)`
- `void addProvisioningTarget ( ProvisioningTarget targ)`
- `void addQuestion ( Question q)`
- `void addQuestionHistory ( Question q)`
- `void addRoleAssigment ( RoleAssignment roleAssignment)`
- `void cleanupExpansionItems ()`
- `void createAttributeSyncWithWorkflowPlan ()`
- `java.lang.Object get (java.lang.String name)`
- `AccountSelection getAccountSelection ( Application app, java.lang.String sourceRole, java.lang.String assignmentId)`
- `java.util.List<AccountSelection> getAccountSelections ()`
- `Question getAnsweredQuestion ( Question.Type type, java.lang.String source, java.lang.String target, java.lang.String attributeName)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `ProvisioningPlan getAttributeSyncWithWorkflowPlan ()`
- `boolean getBoolean (java.lang.String name)`
- `ProvisioningPlan.AccountRequest getCreateOrModifyRequest ( Application application)`
- `java.util.List<Message> getErrorMessages ()`
- `ExpansionItem getExpansionItem (java.lang.String app, java.lang.String attr, java.lang.Object value)`
- `ExpansionItem getExpansionItem (java.lang.String app, java.lang.String instance, java.lang.String nativeIdentity, java.lang.String attr, java.lang.Object value)`
- `ExpansionItem getExpansionItem ( ExpansionItem item, boolean ignoreNullNativeIdentity)`
- `ExpansionItem getExpansionItem ( ProvisioningPlan.AccountRequest acctReq, ProvisioningPlan.GenericRequest req, java.lang.Object value)`
- `java.util.List<ExpansionItem> getExpansionItems ()`
- `java.util.List<ProvisioningPlan.AbstractRequest> getFiltered ()`
- `ProvisioningPlan.AbstractRequest getFiltered ( ProvisioningPlan.AbstractRequest request)`
- `java.lang.String getIdentity ()`
- `java.lang.Object getIdentityAttribute (java.lang.String attrName, Identity identity)`
- `ProvisioningPlan.AccountRequest getIIQAccountRequest ()`
- `ProvisioningPlan getIIQPlan ()`
- `java.util.List<ProvisioningPlan> getIntegrationPlans ()`
- `java.lang.Object getLinkAttribute (java.lang.String appName, java.lang.String nativeIdentity, java.lang.String instance, java.lang.String attrName, ProvisioningPlan.AbstractRequest request, Identity identity)`
- `java.lang.Object getLinkAttribute (java.lang.String appName, java.lang.String nativeIdentity, java.lang.String instance, java.lang.String attrName, ProvisioningPlan.AbstractRequest request, Identity identity, boolean masterOnly)`
- `java.lang.Object getLinkAttribute (java.lang.String appName, java.lang.String nativeIdentity, java.lang.String instance, java.lang.String attrName, ProvisioningPlan.AbstractRequest request, Identity identity, boolean masterOnly, boolean requestOnly)`
- `java.lang.Object getLinkAttribute (java.lang.String appName, java.lang.String attrName, Identity identity)`
- `ProvisioningPlan getMasterPlan ()`
- `java.util.List<Message> getMessages ()`
- `java.lang.Object getObjectAttribute (java.lang.String appName, java.lang.String attrName, ManagedAttribute object)`
- `ProvisioningPlan getPlan (java.lang.String target)`
- `java.util.List<ProvisioningPlan> getPlans ()`
- `java.util.List<ProvisioningPlan> getPlans (java.lang.String target)`
- `ProvisioningTarget getProvisioningTarget (java.lang.String id)`
- `ProvisioningTarget getProvisioningTarget ( Bundle role)`
- `java.util.List<ProvisioningTarget> getProvisioningTargets ()`
- `Question getQuestion ( Question.Type type, java.lang.String source, java.lang.String target, java.lang.String attributeName)`
- `java.util.List<Question> getQuestionHistory ()`
- `java.util.List<Question> getQuestions ()`
- `java.lang.String getRequester ()`
- `java.util.List<RoleAssignment> getRoleAssigments ()`
- `java.lang.String getString (java.lang.String name)`
- `int getTotalQuestionCount ()`
- `ProvisioningPlan getUnmanagedPlan ()`
- `boolean hasQuestions ()`
- `boolean hasUnansweredAccountSelections ()`
- `boolean hasUnansweredProvisioningTargets ()`
- `boolean hasUnfinishedIntegrationPlans ()`
- `boolean hasUnmanagedPlan ()`
- `ProvisioningPlan internIIQPlan ()`
- `ProvisioningPlan internPlan (java.lang.String target)`
- `ProvisioningPlan internPlan (java.lang.String target, java.lang.String appName)`
- `ProvisioningPlan internPlan (java.lang.String target, ProvisioningPlan.AccountRequest req)`
- `ProvisioningPlan internUnmanagedPlan ()`
- `boolean isEmpty ()`
- `boolean isExpansionSecret ( ExpansionItem item)`
- `boolean isFullyCommitted ()`
- `boolean isNullOrEmptyAttributeSyncWithWorkflowPlan ()`
- `<T extendsProvisioningPlan.GenericRequest>void logFilteredValue ( ProvisioningPlan.AbstractRequest parent, T request, java.lang.Object value, ProvisioningProject.FilterReason reason)`
- `<T extendsProvisioningPlan.GenericRequest>void logFilteredValue ( ProvisioningPlan.AbstractRequest parent, T request, ProvisioningProject.FilterReason reason)`
- `void put (java.lang.String name, java.lang.Object value)`
- `void remove ( ProvisioningPlan plan)`
- `void removeAnsweredQuestion ( Question q)`
- `void removeQuestion ( Question q)`
- `boolean replace ( ProvisioningPlan orig, ProvisioningPlan neu)`
- `void resetCompilation ()`
- `void resetEvaluation ()`
- `Identity resolveIdentity ( Resolver r)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> a)`
- `void setExpansionItems (java.util.List< ExpansionItem > items)`
- `void setFiltered (java.util.List< ProvisioningPlan.AbstractRequest > filtered)`
- `void setIdentity (java.lang.String s)`
- `void setIdentity ( Identity i)`
- `void setMasterPlan ( ProvisioningPlan plan)`
- `void setMessages (java.util.List< Message > msgs)`
- `void setPlans (java.util.List< ProvisioningPlan > plans)`
- `void setProvisioningTargets (java.util.List< ProvisioningTarget > list)`
- `void setQuestionHistory (java.util.List< Question > questions)`
- `void setQuestions (java.util.List< Question > questions)`
- `void setRoleAssigments (java.util.List< RoleAssignment > roleAssignments)`

---

## ProvisioningResult

**Package:** `sailpoint.object`

**Description:** Class used maintain results from a request to a provisioning system.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ProvisioningResult`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String STATUS_COMMITTED`
- `static java.lang.String STATUS_FAILED`
- `static java.lang.String STATUS_QUEUED`
- `static java.lang.String STATUS_RETRY`

**Methods:**
- `void addError (java.lang.String s)`
- `void addError (java.lang.Throwable t)`
- `void addError ( Message m)`
- `void addWarning (java.lang.String s)`
- `void addWarning (java.util.List< Message > m)`
- `void addWarning ( Message m)`
- `void assimilateMessages ( ProvisioningResult src)`
- `void assimilateMessages ( ProvisioningResult src, boolean before)`
- `void fail ()`
- `void fail (java.lang.Throwable t)`
- `void fromMap (java.util.Map map)`
- `java.util.List<Message> getErrors ()`
- `ResourceObject getObject ()`
- `java.lang.String getRequestID ()`
- `int getRetryInterval ()`
- `java.lang.String getStatus ()`
- `java.lang.String getTargetIntegration ()`
- `java.util.List<Message> getWarnings ()`
- `boolean hasMessages ()`
- `boolean isCommitted ()`
- `boolean isFailed ()`
- `boolean isFailure ()`
- `boolean isQueued ()`
- `boolean isRetry ()`
- `boolean isSubmitted ()`
- `void setErrors (java.util.List< Message > l)`
- `void setObject ( ResourceObject obj)`
- `void setRequestID (java.lang.String s)`
- `void setRetryInterval (int i)`
- `void setStatus (java.lang.String s)`
- `void setTargetIntegration (java.lang.String s)`
- `void setWarnings (java.util.List< Message > l)`
- `java.util.Map<java.lang.String,​java.lang.Object> toMap ()`

---

## ProvisioningTarget

**Package:** `sailpoint.object`

**Description:** An object that can be stored in a ProvisioningProject that defines the information that must be gathered from the user in order to complete provisioning for this assignment.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ProvisioningTarget`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void addAccountSelection (java.util.List< Link > links, java.lang.String sourceRole)`
- `void addAccountSelection ( AccountSelection sel)`
- `void addAccountSelection ( Application app, Link link, java.lang.String sourceRole)`
- `void addAccountSelections (java.util.List< AccountSelection > accountSelections)`
- `AccountSelection getAccountSelection ( Application app, java.lang.String sourceRole)`
- `java.util.List<AccountSelection> getAccountSelections ()`
- `java.lang.String getApplication ()`
- `java.lang.String getAssignmentId ()`
- `java.lang.String getAttribute ()`
- `java.util.List<Question> getQuestions ()`
- `java.lang.String getRole ()`
- `java.lang.String getValue ()`
- `boolean isAnswered ()`
- `boolean isRetain ()`
- `void setAccountSelections (java.util.List< AccountSelection > accounts)`
- `void setApplication (java.lang.String s)`
- `void setAssignmentId (java.lang.String s)`
- `void setAttribute (java.lang.String s)`
- `void setQuestions (java.util.List< Question > questions)`
- `void setRetain (boolean b)`
- `void setRole (java.lang.String s)`
- `void setValue (java.lang.String s)`

---

## ProvisioningTransaction.Level

**Package:** `sailpoint.object`

**Description:** The configurable logging level for users to see levels of messages. Configured levels act like log4j, where a selected level will also show the level below Can be configured in the system configuration, refresh task, and certification pages. Ex. If a sysadmin selects Retry, it also implies seeing Failure messages.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ProvisioningTransaction.Level`
- `sailpoint.object.ProvisioningTransaction.Level`
- `java.io.Serializable`
- `java.lang.Comparable<ProvisioningTransaction.Level>`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:**
- `java.lang.String getLocalizedMessage ()`
- `java.lang.String getLocalizedMessage (java.util.Locale locale, java.util.TimeZone timezone)`
- `staticProvisioningTransaction.Level valueOf (java.lang.String name)`
- `staticProvisioningTransaction.Level[] values ()`

---

## ProvisioningTransaction.Status

**Package:** `sailpoint.object`

**Description:** The provisioning transaction has failed.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ProvisioningTransaction.Status`
- `sailpoint.object.ProvisioningTransaction.Status`
- `java.io.Serializable`
- `java.lang.Comparable<ProvisioningTransaction.Status>`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:**
- `java.lang.String getLocalizedMessage ()`
- `java.lang.String getLocalizedMessage (java.util.Locale locale, java.util.TimeZone timezone)`
- `staticProvisioningTransaction.Status valueOf (java.lang.String name)`
- `staticProvisioningTransaction.Status[] values ()`

---

## ProvisioningTransaction.Type

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ProvisioningTransaction.Type`
- `sailpoint.object.ProvisioningTransaction.Type`
- `java.io.Serializable`
- `java.lang.Comparable<ProvisioningTransaction.Type>`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:**
- `java.lang.String getLocalizedMessage ()`
- `java.lang.String getLocalizedMessage (java.util.Locale locale, java.util.TimeZone timezone)`
- `staticProvisioningTransaction.Type valueOf (java.lang.String name)`
- `staticProvisioningTransaction.Type[] values ()`

---

## ProvisioningTransaction

**Package:** `sailpoint.object`

**Description:** This object that will be used to persist data to be used by the Provisioning Transaction Monitoring UI. Contains all the necessary information to represent the UI.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.ProvisioningTransaction`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATT_ACCESS_REQUEST_ID`
- `static java.lang.String ATT_CERT_NAME`
- `static java.lang.String ATT_FILTERED`
- `static java.lang.String ATT_LAST_RETRY`
- `static java.lang.String ATT_MANUAL_WORK_ITEM`
- `static java.lang.String ATT_PLAN_RESULT`
- `static java.lang.String ATT_REQUEST`
- `static java.lang.String ATT_RETRY_COUNT`
- `static java.lang.String ATT_RETRY_REQUEST_ID`
- `static java.lang.String ATT_TICKET_ID`
- `static java.lang.String ATT_TIMED_OUT`
- `static java.lang.String ATT_WAIT_WORK_ITEM_ID`
- `static java.lang.String MANUAL_INTEGRATION`

**Methods:**
- `java.lang.String getAccountDisplayName ()`
- `java.lang.String getApplicationName ()`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getCertificationId ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `java.lang.String getIdentityDisplayName ()`
- `java.lang.String getIdentityName ()`
- `java.lang.String getIntegration ()`
- `java.lang.String getNativeIdentity ()`
- `java.lang.String getOperation ()`
- `java.lang.String getSource ()`
- `ProvisioningTransaction.Status getStatus ()`
- `ProvisioningTransaction.Type getType ()`
- `boolean hasAssignedScope ()`
- `boolean isForced ()`
- `void setAccountDisplayName (java.lang.String accountDisplayName)`
- `void setApplicationName (java.lang.String applicationName)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attributes)`
- `void setCertificationId (java.lang.String certificationId)`
- `void setForced (boolean forced)`
- `void setIdentityDisplayName (java.lang.String identityDisplayName)`
- `void setIdentityName (java.lang.String identityName)`
- `void setIntegration (java.lang.String integration)`
- `void setNativeIdentity (java.lang.String nativeIdentity)`
- `void setOperation (java.lang.String operation)`
- `void setSource (java.lang.String source)`
- `void setSource ( Source source)`
- `void setStatus ( ProvisioningTransaction.Status status)`
- `void setType ( ProvisioningTransaction.Type type)`

---

## QueryInfo

**Package:** `sailpoint.object`

**Description:** This is a light-weight representation of a query that is intended for consumption by suggest components and/or LCM rules that communicate with suggest components. Unlike QueryOptions, this class carries data regarding whether or not a query is supposed to return anything. This facilitates logic in suggest components that determines whether a query should be executed or an empty Collection should be returned.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.QueryInfo`

**Attributes:** N/A

**Methods:**
- `Filter getFilter ()`
- `boolean isReturnAll ()`
- `boolean isReturnNone ()`

---

## QueryOptions.Ordering

**Package:** `sailpoint.object`

**Description:** Deprecated.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.QueryOptions.Ordering`

**Attributes:** N/A

**Methods:**
- `boolean equals (java.lang.Object o)`
- `java.lang.String getColumn ()`
- `int hashCode ()`
- `boolean isAscending ()`
- `boolean isIgnoreCase ()`
- `void setAscending (boolean ascending)`
- `void setColumn (java.lang.String column)`
- `void setIgnoreCase (boolean ignoreCase)`
- `java.lang.String toString ()`

---

## QueryOptions

**Package:** `sailpoint.object`

**Description:** Class used to specify options to a database query.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.QueryOptions`
- `java.io.Serializable`

**Attributes:**
- `static int MAX_WORKGROUPS_SIZE`

**Methods:**
- `QueryOptions add ( Filter ... res)`
- `QueryOptions addFilter ( Filter f)`
- `void addGroupBy (java.lang.String property)`
- `QueryOptions addOrdering (java.lang.Integer index, java.lang.String name, boolean ascending)`
- `QueryOptions addOrdering (java.lang.Integer index, java.lang.String name, boolean ascending, boolean ignoreCase)`
- `QueryOptions addOrdering (java.lang.String name, boolean ascending)`
- `QueryOptions addOrdering (java.lang.String name, boolean ascending, boolean ignoreCase)`
- `void addOwnerScope ( Identity user)`
- `void addOwnerScopeForLucene ( Identity user)`
- `boolean equals (java.lang.Object o)`
- `void extendScope ( Filter ... filters)`
- `java.util.List<Filter> getFilters ()`
- `int getFirstRow ()`
- `java.util.List<java.lang.String> getGroupBys ()`
- `staticQueryOptions getInstance ()`
- `int getOrderingIndex (java.lang.String name)`
- `java.util.List<QueryOptions.Ordering> getOrderings ()`
- `staticFilter getOwnerScopeFilter ( Identity user, java.lang.String ownerColumn)`
- `staticFilter getOwnerScopeFilterUsingSubqueries ( Identity user, java.lang.String ownerColumn)`
- `java.lang.String getQuery ()`
- `java.util.List<Filter> getRestrictions ()`
- `int getResultLimit ()`
- `java.util.List<Filter> getScopeExtensions ()`
- `java.lang.Boolean getScopeResults ()`
- `java.lang.Boolean getUnscopedGloballyAccessible ()`
- `int hashCode ()`
- `boolean isCacheResults ()`
- `boolean isCloneResults ()`
- `boolean isCommitOnClone ()`
- `boolean isDirtyRead ()`
- `boolean isDistinct ()`
- `boolean isFlushBeforeQuery ()`
- `java.lang.String isIdentitySearch ()`
- `boolean isIgnoreCase ()`
- `boolean isTransactionLock ()`
- `void setCacheResults (boolean cache)`
- `void setCloneResults (boolean b)`
- `void setCloneResults (boolean cloneResults, boolean commitOnClone)`
- `void setDirtyRead (boolean dirtyRead)`
- `void setDistinct (boolean b)`
- `void setFilters (java.util.List< Filter > filters)`
- `QueryOptions setFirstRow (int row)`
- `void setFlushBeforeQuery (boolean flush)`
- `void setGroupBys (java.util.List<java.lang.String> groupBys)`
- `void setIgnoreCase (boolean b)`
- `QueryOptions setOrderAscending (boolean b)`
- `QueryOptions setOrderBy (java.lang.String name)`
- `void setOrderings (java.util.List< QueryOptions.Ordering > orderings)`
- `void setQuery (java.lang.String q)`
- `void setRestrictions (java.util.List< Filter > filters)`
- `QueryOptions setResultLimit (int limit)`
- `void setScopeResults (java.lang.Boolean scopeResults)`
- `void setTransactionLock (boolean b)`
- `void setUnscopedGloballyAccessible (java.lang.Boolean b)`
- `java.lang.String toString ()`

---

## QueryResult<T extendsSailPointObject>

**Package:** `sailpoint.object`

**Description:** Returns the object or null if the query had a projection

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `T getObject ()`
- `java.lang.Object[] getProjectionResult ()`

---

## Question.QuestionTypeComparator

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Question.QuestionTypeComparator`
- `java.util.Comparator<Question.Type>`

**Attributes:** N/A

**Methods:**
- `int compare ( Question.Type t1, Question.Type t2)`

---

## Question.Type

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Question.Type`
- `sailpoint.object.Question.Type`
- `java.io.Serializable`
- `java.lang.Comparable<Question.Type>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticQuestion.Type valueOf (java.lang.String name)`
- `staticQuestion.Type[] values ()`

---

## Question

**Package:** `sailpoint.object`

**Description:** An object representing a data value that needs to be requested, typically through interactive prompting. This is part of the ProvisioningProject model, used to represent account attributes that are required to complete a provisioning event.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Question`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `boolean fieldsMatch ( Question other)`
- `java.lang.Object getAnswer ()`
- `java.lang.String getAttributeName ()`
- `Field getField ()`
- `java.lang.String getFieldName ()`
- `java.lang.String getFutureTarget ()`
- `java.lang.String getOwner ()`
- `java.lang.String getSource ()`
- `java.lang.String getTarget ()`
- `Question.Type getType ()`
- `boolean isShown ()`
- `void setAnswer (java.lang.Object o)`
- `void setAttributeName (java.lang.String attributeName)`
- `void setField ( Field f)`
- `void setFutureTarget (java.lang.String target)`
- `void setOwner (java.lang.String s)`
- `void setPreviousValue (java.lang.Object o)`
- `void setShown (boolean b)`
- `void setSource (java.lang.String _source)`
- `void setTarget (java.lang.String target)`
- `void setType ( Question.Type _type)`

---

## QuickLink

**Package:** `sailpoint.object`

**Description:** Holds a Script to evaluate for the message key or label to use for the quick link.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.QuickLink`
- `java.io.Serializable`
- `ImportMergable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ACTION_EXTERNAL`
- `static java.lang.String ACTION_WORKFLOW`
- `static java.lang.String ARG_COUNT_SCRIPT`
- `static java.lang.String ARG_DISPLAY_COUNT`
- `static java.lang.String ARG_DISPLAY_TEXT`
- `static java.lang.String ARG_FORCE_ALLOW_OTHERS`
- `static java.lang.String ARG_FORCE_ALLOW_SELF`
- `static java.lang.String ARG_HIDE_ALLOW_OTHERS`
- `static java.lang.String ARG_HIDE_ALLOW_SELF`
- `static java.lang.String ARG_LABEL_SCRIPT`
- `static java.lang.String ARG_PARAMETERS`
- `static java.lang.String ARG_TEXT_ARIA_LABEL`
- `static java.lang.String ARG_TEXT_SCRIPT`
- `static java.lang.String ARG_URL`
- `static java.lang.String ARG_WORKFLOW_NAME`
- `static java.lang.String ARG_WORKFLOW_SUCCESS`
- `static java.lang.String ARG_WORKITEM_TYPE`
- `static java.lang.String LCM_ACTION_CREATE_IDENTITY`
- `static java.lang.String LCM_ACTION_EDIT_IDENTITY`
- `static java.lang.String LCM_ACTION_MANAGE_ACCOUNTS`
- `static java.lang.String LCM_ACTION_MANAGE_PASSWORDS`
- `static java.lang.String LCM_ACTION_REQUEST_ACCESS`
- `static java.lang.String LCM_ACTION_TRACK_REQUESTS`
- `static java.lang.String LCM_ACTION_VIEW_IDENTITY`
- `static java.lang.String QUICKLINK_MANAGE_ACCOUNTS`
- `static java.lang.String QUICKLINK_MANAGE_PASSWORDS`
- `static java.lang.String QUICKLINK_REQUEST_ACCESS`

**Methods:**
- `void addQuickLinkOptions ( QuickLinkOptions opts)`
- `boolean equals (java.lang.Object o)`
- `java.lang.String getAction ()`
- `Attributes<java.lang.String,​java.lang.Object> getArguments ()`
- `java.lang.String getCategory ()`
- `java.lang.String getCssClass ()`
- `java.util.List<DynamicScope> getDynamicScopes ()`
- `java.util.Map<java.lang.String,​java.lang.Object> getEnablingAttributes ()`
- `java.lang.String getMessageKey ()`
- `int getOrdering ()`
- `java.util.List<QuickLinkOptions> getQuickLinkOptions ()`
- `QuickLinkOptions getQuickLinkOptions ( DynamicScope ds)`
- `java.lang.String getRights ()`
- `java.util.List<java.lang.String> getRightsList ()`
- `int hashCode ()`
- `boolean isBulk ()`
- `boolean isForceAllowOthers ()`
- `boolean isForceAllowSelf ()`
- `boolean isForOthers ()`
- `boolean isHidden ()`
- `boolean isHideAllowOthers ()`
- `boolean isHideAllowSelf ()`
- `boolean isOldEnabled ()`
- `boolean isSelfService ()`
- `void merge (java.lang.Object old)`
- `void remove ( DynamicScope dynamicScope)`
- `void setAction (java.lang.String action)`
- `void setArguments ( Attributes <java.lang.String,java.lang.Object> arguments)`
- `void setBulk (boolean bulk)`
- `void setCategory (java.lang.String category)`
- `void setCssClass (java.lang.String cssClass)`
- `void setDynamicScopes (java.util.List< DynamicScope > dynamicScopes)`
- `void setEnablingAttributes (java.util.Map<java.lang.String,java.lang.Object> enablingAttributes)`
- `void setHidden (boolean hidden)`
- `void setIcon (java.lang.String icon)`
- `void setMessageKey (java.lang.String messageKey)`
- `void setOldEnabled (boolean b)`
- `void setOrdering (int ordering)`
- `void setQuickLinkOptions (java.util.List< QuickLinkOptions > options)`
- `void setRights (java.lang.String rights)`
- `void visit ( Visitor v)`

---

## QuickLinkCategory

**Package:** `sailpoint.object`

**Description:** Allows SearchInputDefinitions to be sorted according to the value of their sortIndex attributes.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.QuickLinkCategory`
- `java.io.Serializable`
- `java.lang.Comparable<QuickLinkCategory>`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `int compareTo ( QuickLinkCategory cat)`
- `boolean equals (java.lang.Object o)`
- `java.lang.String getCssClass ()`
- `java.lang.String getMessageKey ()`
- `java.lang.String getName ()`
- `int getOrdering ()`
- `boolean isEnabled ()`
- `void setCssClass (java.lang.String cssClass)`
- `void setEnabled (boolean enabled)`
- `void setIcon (java.lang.String icon)`
- `void setMessageKey (java.lang.String messageKey)`
- `void setName (java.lang.String name)`
- `void setOrdering (int ordering)`

---

## QuickLinkOptions

**Package:** `sailpoint.object`

**Description:** Creates a copy of the quick link options attributes.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.QuickLinkOptions`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `void assignProperties ( QuickLink ql, DynamicScope ds)`
- `void assignProperties ( QuickLink ql, DynamicScope ds, boolean allowSelf)`
- `boolean getBooleanOption (java.lang.String requestControl)`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `DynamicScope getDynamicScope ()`
- `Attributes<java.lang.String,​java.lang.Object> getOptions ()`
- `QuickLink getQuickLink ()`
- `QuickLink getQuickLinkXml ()`
- `java.lang.String[] getUniqueKeyProperties ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `boolean isAllowBulk ()`
- `boolean isAllowOther ()`
- `boolean isAllowRemoveEntitlements ()`
- `boolean isAllowRemoveRoles ()`
- `boolean isAllowRequestEntitlements ()`
- `boolean isAllowRequestRoles ()`
- `boolean isAllowSelf ()`
- `void load ()`
- `void setAllowBulk (boolean allowBulk)`
- `void setAllowOther (boolean allowOther)`
- `void setAllowSelf (boolean allowSelf)`
- `void setBooleanOption (java.lang.String requestControl, boolean value)`
- `void setDynamicScope ( DynamicScope dynamicScope)`
- `void setOptions ( Attributes <java.lang.String,java.lang.Object> options)`
- `void setQuickLink ( QuickLink quickLink)`
- `void setQuickLinkXml ( QuickLink ql)`

---

## RapidSetupConfigUtils

**Package:** `sailpoint.object`

**Description:** Returns true if the given application mover certification includes additional entitlements

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.RapidSetupConfigUtils`

**Attributes:** N/A

**Methods:**
- `static boolean additionalEntitlementsEnabledForApplication (java.lang.String businessProcess, java.lang.String appName)`
- `static java.lang.Object get (java.lang.String csvPath)`
- `static java.lang.Object get (java.util.Map map, java.lang.String csvPath)`
- `static java.lang.Object get ( Configuration cfg, java.lang.String csvPath)`
- `static java.util.Map<java.lang.String,​java.lang.Object> getApplicationBusinessProcessConfig (java.lang.String appName, java.lang.String businessProcess)`
- `static java.util.Map<java.lang.String,​java.lang.Object> getApplicationConfig (java.lang.String appName)`
- `staticIdentitySelector getApplicationJoinerIdentitySelector (java.lang.String appName)`
- `static sailpoint.rapidsetup.model.IdentSelectorDTO getApplicationJoinerIdentSelectorDTO ( SailPointContext context, java.lang.String appName)`
- `static java.util.List<java.lang.String> getApplicationsConfiguredIncludeEntitlements (java.lang.String businessProcessName)`
- `static java.util.List<java.lang.String> getApplicationsConfiguredTargetPermission (java.lang.String businessProcessName)`
- `static boolean getBoolean (java.lang.String csvPath)`
- `static boolean getBoolean (java.util.Map map, java.lang.String csvPath)`
- `static boolean getBoolean ( Configuration cfg, java.lang.String csvPath)`
- `static java.lang.String getBusinessProcessWorkflowName (java.lang.String businessProcessName)`
- `static int getInt (java.lang.String csvPath)`
- `static int getInt (java.util.Map map, java.lang.String csvPath)`
- `static int getInt ( Configuration cfg, java.lang.String csvPath)`
- `static java.util.List<java.lang.String> getJoinerProvisioningAppNames ()`
- `static java.util.Map getMatchFilter (java.lang.String process)`
- `static java.util.Map getMatchFilter ( IdentityTrigger trigger)`
- `static java.util.List<java.lang.String> getRapidSetupBirthrightRoleTypeNames ()`
- `static java.util.Map getRapidSetupBusinessProcessConfiguration (java.lang.String businessProcessName)`
- `static java.util.Map getRapidSetupBusinessProcessConfigurationSection ()`
- `static java.util.Map getRapidSetupCertificationParams (java.lang.String businessProcessName)`
- `static java.lang.String getString (java.lang.String csvPath)`
- `static java.lang.String getString (java.util.Map map, java.lang.String csvPath)`
- `static java.lang.String getString ( Configuration cfg, java.lang.String csvPath)`
- `static boolean isApplicationConfigured (java.lang.String appName)`
- `static boolean isApplicationJoinerProducer ( Application app)`
- `static boolean isBirthrightRoleType ( RoleTypeDefinition roleType)`
- `static boolean isEnabled ()`
- `static boolean isRequireCorrelatedForLeaver ()`
- `static boolean isTriggerInactive ( IdentityTrigger trigger)`
- `static boolean moverJoinerEnabledForApplication (java.lang.String businessProcess, java.lang.String appName)`
- `static void removeApplication ( Configuration cfg, java.lang.String appName)`
- `static boolean shouldGenerateApprovals (java.lang.String process)`
- `static boolean targetPermissionEnabledForApplication (java.lang.String businessProcess, java.lang.String appName)`
- `static void validateApplicationConfig ( SailPointContext context, java.util.Map<java.lang.String,java.util.List<java.lang.String>> errs, java.util.Map appConfig, sailpoint.service.ApplicationDTO applicationDTO)`
- `static void validateScriptPermissions ( SailPointContext context, Identity loggedInUser, java.util.Map appConfig, java.lang.String appName)`

---

## Reason

**Package:** `sailpoint.object`

**Description:** Simple XML object used to store a message key and parameters used when rendering a Recommendation. The Reason object is a localizable representation of the Reasons a decision was made in a Recommendation.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Reason`
- `java.io.Serializable`
- `sailpoint.tools.MessageKeyHolder`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `java.util.List<java.lang.Object> getParameters ()`
- `void setMessageKey (java.lang.String messageKey)`
- `void setParameters (java.util.List<java.lang.Object> parameters)`

---

## Recommendation.RecommendedDecision

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Recommendation.RecommendedDecision`
- `sailpoint.object.Recommendation.RecommendedDecision`
- `java.io.Serializable`
- `java.lang.Comparable<Recommendation.RecommendedDecision>`
- `sailpoint.tools.MessageKeyHolder`

**Attributes:** N/A

**Methods:**
- `java.lang.String getLocalizedMessage (java.util.Locale locale, java.util.TimeZone timezone)`
- `java.lang.String getMessageKey ()`
- `boolean isActionable ()`
- `staticRecommendation.RecommendedDecision valueOf (java.lang.String name)`
- `staticRecommendation.RecommendedDecision[] values ()`

---

## Recommendation

**Package:** `sailpoint.object`

**Description:** Deprecated.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Recommendation`
- `java.io.Serializable`
- `sailpoint.recommender.RecommendationReasonProvider`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.util.List<Reason> getReasonMessages ()`
- `java.util.List<java.lang.String> getReasons ()`
- `Recommendation.RecommendedDecision getRecommendedDecision ()`
- `java.util.Date getTimeStamp ()`
- `void setReasonMessages (java.util.List< Reason > reasonMessages)`
- `void setReasons (java.util.List<java.lang.String> reasons)`
- `void setRecommendedDecision ( Recommendation.RecommendedDecision recommendedDecision)`
- `void setTimeStamp (java.util.Date timeStamp)`

---

## RecommenderDefinition

**Package:** `sailpoint.object`

**Description:** Configuration attribute (String) holding the name of the Java class to construct.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.RecommenderDefinition`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATT_CLASSNAME`
- `static java.lang.String ATT_IS_IAI_RECOMMENDER`
- `static java.lang.String ATT_PLUGINNAME`
- `static java.lang.String ATT_SUPPORTED_TYPES`

**Methods:**
- `java.lang.Object get (java.lang.String name)`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `boolean getBoolean (java.lang.String name)`
- `int getInt (java.lang.String name)`
- `java.util.List getList (java.lang.String name)`
- `java.lang.String getString (java.lang.String name)`
- `boolean hasAssignedScope ()`
- `void put (java.lang.String name, int value)`
- `void put (java.lang.String name, java.lang.Object value)`
- `void remove (java.lang.String name)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> a)`

---

## Reference

**Package:** `sailpoint.object`

**Description:** Class to represent references to SailPointObjects.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Reference`
- `java.io.Serializable`
- `java.lang.Cloneable`

**Attributes:** N/A

**Methods:**
- `java.lang.Object clone ()`
- `boolean equals (java.lang.Object obj)`
- `java.lang.String getClassName ()`
- `java.lang.String getId ()`
- `java.lang.String getIdOrName ()`
- `java.lang.String getName ()`
- `java.lang.String getNameOrId ()`
- `int hashCode ()`
- `SailPointObject resolve ( Resolver resolver)`
- `void setClassName (java.lang.String s)`
- `void setid (java.lang.String s)`
- `void setName (java.lang.String s)`

---

## RemediationItem.RemediationEntityType

**Package:** `sailpoint.object`

**Description:** Type type of object being remediated.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `RemediationItem.RemediationEntityType`
- `sailpoint.object.RemediationItem.RemediationEntityType`
- `java.io.Serializable`
- `java.lang.Comparable<RemediationItem.RemediationEntityType>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getDisplayName ()`
- `staticRemediationItem.RemediationEntityType valueOf (java.lang.String name)`
- `staticRemediationItem.RemediationEntityType[] values ()`

---

## RemediationItem

**Package:** `sailpoint.object`

**Description:** Used to represent a single remediation request that can be included in a work item.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.RemediationItem`
- `java.io.Serializable`
- `AssignableItem`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ARG_CONTRIBUTING_ENTS`

**Methods:**
- `void addComment (java.lang.String comment, Identity author)`
- `void assimilate ()`
- `void complete (java.lang.String comments)`
- `Identity getAssignee ()`
- `java.lang.Object getAttribute (java.lang.String key)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getCertificationItem ()`
- `CertificationItem getCertificationItem ( Resolver resolver)`
- `java.util.List<Comment> getComments ()`
- `java.lang.String getCompletionComments ()`
- `java.util.Date getCompletionDate ()`
- `java.util.List<sailpoint.web.certification.PolicyTreeNode> getContributingEntitlements ()`
- `ProvisioningPlan getRemediationDetails ()`
- `RemediationItem.RemediationEntityType getRemediationEntityType ()`
- `java.lang.String getRemediationIdentity ()`
- `WorkItem getWorkItem ()`
- `boolean hasName ()`
- `boolean isAssimilated ()`
- `boolean isComplete ()`
- `void setAssignee ( Identity assignee)`
- `void setAttribute (java.lang.String key, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> atts)`
- `void setWorkItem ( WorkItem workItem)`

---

## RemoteLoginToken

**Package:** `sailpoint.object`

**Description:** Returns if the token is expired.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.RemoteLoginToken`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.Object clone ()`
- `java.lang.String getCreator ()`
- `java.util.Date getExpiration ()`
- `java.lang.String getRemoteHost ()`
- `boolean isExpired ()`
- `void setCreator (java.lang.String creator)`
- `void setExpiration (java.util.Date expiration)`
- `void setRemoteHost (java.lang.String remoteHost)`

---

## ReportColumnConfig

**Package:** `sailpoint.object`

**Description:** Deprecated.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ReportColumnConfig`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.Integer DEFAULT_WIDTH`

**Methods:**
- `java.lang.String getDateFormat ()`
- `java.lang.Integer getDateStyle ()`
- `java.lang.String getExpression ()`
- `java.lang.String getField ()`
- `java.lang.String getHeader ()`
- `java.lang.String getIfEmpty ()`
- `net.sf.jasperreports.engine.design.JRDesignExpression getJRDesignExpression ()`
- `java.lang.String getProperty ()`
- `DynamicValue getRenderDef ()`
- `Rule getRenderRule ()`
- `Script getRenderScript ()`
- `java.lang.String getScriptArguments ()`
- `java.util.List<java.lang.String> getScriptArgumentsList ()`
- `java.lang.String getSortExpression ()`
- `java.util.List<java.lang.String> getSortProperties ()`
- `java.lang.String getSubQueryKey ()`
- `java.lang.String getTimeFormat ()`
- `java.lang.Integer getTimeStyle ()`
- `java.lang.String getValueClass ()`
- `int getWidth ()`
- `boolean hasDateFormatting ()`
- `boolean isCustomDateStyle ()`
- `boolean isCustomTimeStyle ()`
- `boolean isExtendedColumn ()`
- `boolean isHidden ()`
- `boolean isSkipLocalization ()`
- `boolean isSortable ()`
- `void setDateFormat (java.lang.String dateFormat)`
- `void setExpression (java.lang.String expression)`
- `void setExtendedColumn (boolean extendedColumn)`
- `void setField (java.lang.String field)`
- `void setHeader (java.lang.String header)`
- `void setHidden (boolean hidden)`
- `void setIfEmpty (java.lang.String ifEmpty)`
- `void setProperty (java.lang.String property)`
- `void setRenderRule ( Rule renderRule)`
- `void setRenderScript ( Script renderScript)`
- `void setScriptArguments (java.lang.String scriptArguments)`
- `void setSkipLocalization (boolean skipLocalization)`
- `void setSortable (boolean sortable)`
- `void setSortExpression (java.lang.String sortExpression)`
- `void setSubQueryKey (java.lang.String subQueryKey)`
- `void setTimeFormat (java.lang.String timeFormat)`
- `void setValueClass (java.lang.String valueClass)`
- `void setWidth (int width)`

---

## ReportDataSource.DataSourceType

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ReportDataSource.DataSourceType`
- `sailpoint.object.ReportDataSource.DataSourceType`
- `java.io.Serializable`
- `java.lang.Comparable<ReportDataSource.DataSourceType>`

**Attributes:** N/A

**Methods:**
- `staticReportDataSource.DataSourceType valueOf (java.lang.String name)`
- `staticReportDataSource.DataSourceType[] values ()`

---

## ReportDataSource.Join

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.ReportDataSource.Join`

**Attributes:** N/A

**Methods:**
- `java.lang.String getJoinProperty ()`
- `java.lang.String getProperty ()`
- `void setJoinProperty (java.lang.String joinProperty)`
- `void setProperty (java.lang.String property)`

---

## ReportDataSource.Parameter

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ReportDataSource.Parameter`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String PARAM_TYPE_DATE_RANGE`

**Methods:**
- `java.lang.String getArgument ()`
- `java.lang.String getDefaultValue ()`
- `java.lang.String getExternalAttributeClass ()`
- `java.lang.String getOperation ()`
- `java.lang.String getProperty ()`
- `DynamicValue getQueryDef ()`
- `Rule getQueryRule ()`
- `Script getQueryScript ()`
- `java.lang.String getValueClass ()`
- `DynamicValue getValueDef ()`
- `Rule getValueRule ()`
- `Script getValueScript ()`
- `boolean isDateRange ()`
- `boolean isExcludeHqlParameter ()`
- `boolean isIgnoreCase ()`
- `boolean isMulti ()`
- `void setArgument (java.lang.String argument)`
- `void setDefaultValue (java.lang.String value)`
- `void setExcludeHqlParameter (boolean excludeHqlParameter)`
- `void setExternalAttributeClass (java.lang.String externalAttributeClass)`
- `void setIgnoreCase (boolean ignoreCase)`
- `void setMulti (boolean b)`
- `void setOperation (java.lang.String operation)`
- `void setOperation ( Filter.LogicalOperation operation)`
- `void setProperty (java.lang.String property)`
- `void setQueryRule ( Rule queryRule)`
- `void setQueryScript ( Script queryScript)`
- `void setValueClass (java.lang.String valueClass)`
- `void setValueRule ( Rule valueRule)`
- `void setValueScript ( Script valueScript)`

---

## ReportDataSource

**Package:** `sailpoint.object`

**Description:** Datasource configuration object for LiveReports. The LiveReportExecutor will convert this into a LiveReportDataSource implementation based on the DataSourceType.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ReportDataSource`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void addParameter (java.lang.String name, java.lang.String property)`
- `void addParameter ( ReportDataSource.Parameter param)`
- `void addSortOrder ( Sort newSort, boolean append)`
- `java.lang.String getDataSourceClass ()`
- `java.lang.String getDefaultSort ()`
- `java.util.List<java.lang.String> getDefaultSortList ()`
- `java.lang.String getGridGrouping ()`
- `java.lang.String getGroupBy ()`
- `java.util.List<java.lang.String> getGroupByColumns ()`
- `java.util.List<ReportDataSource.Join> getJoins ()`
- `java.lang.Class<? extendsSailPointObject> getObjectClass ()`
- `java.lang.String getObjectType ()`
- `Rule getOptionsRule ()`
- `Script getOptionsScript ()`
- `ReportDataSource.Parameter getParameter (java.lang.String argument)`
- `java.lang.String getQuery ()`
- `java.util.List<ReportDataSource.Parameter> getQueryParameters ()`
- `Script getQueryScript ()`
- `java.util.List<Sort> getSortOrder ()`
- `ReportDataSource.DataSourceType getType ()`
- `boolean hasCustomOptionsHandler ()`
- `boolean hasSortOrder ()`
- `void setDataSourceClass (java.lang.String dataSourceClass)`
- `void setDefaultSort (java.lang.String defaultSort)`
- `void setGridGrouping (java.lang.String gridGrouping)`
- `void setGroupBy (java.lang.String groupBy)`
- `void setJoins (java.util.List< ReportDataSource.Join > joins)`
- `void setObjectType (java.lang.String objectType)`
- `void setOptionsRule ( Rule optionsRule)`
- `void setOptionsScript ( Script optionsScript)`
- `void setQuery (java.lang.String query)`
- `void setQueryParameters (java.util.List< ReportDataSource.Parameter > parameters)`
- `void setQueryScript ( Script queryScript)`
- `void setSortOrder (java.util.List< Sort > sort)`
- `void setType ( ReportDataSource.DataSourceType type)`

---

## Request

**Package:** `sailpoint.object`

**Description:** An object representing an active background request.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.TaskItem`
- `sailpoint.object.Request`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.api.MessageAccumulator`
- `sailpoint.api.MessageRepository`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATT_EVENT_TYPE`
- `static java.lang.String ATT_EXECUTOR_COMMAND`
- `static java.lang.String ATT_NOT_DELETE_ON_CANCEL`
- `static java.lang.String ATT_PARTITION_RESULT`
- `static java.lang.String ATT_REQUESTOR`
- `static java.lang.String ATT_RESTARTS`
- `static int MAX_LENGTH_STRING1`
- `static int PHASE_NONE`
- `static int PHASE_PENDING`
- `static java.lang.String RESULT`

**Methods:**
- `TaskResult bootstrapPartitionResult ()`
- `RequestDefinition getDefinition ()`
- `int getDependentPhase ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `java.util.Date getEventDate ()`
- `java.lang.String getExecutorCommand ()`
- `java.util.Date getNextLaunch ()`
- `TaskResult getPartitionResult ()`
- `int getPhase ()`
- `int getRetryCount ()`
- `int getRetryInterval ()`
- `java.lang.String getString1 ()`
- `TaskResult getTaskResult ()`
- `int incRetryCount ()`
- `boolean isNameUnique ()`
- `boolean isNotificationNeeded ()`
- `void setDefinition ( RequestDefinition def)`
- `void setDependentPhase (int dependentPhase)`
- `void setEventDate (java.util.Date d)`
- `void setExecutorCommand (java.lang.String cmd)`
- `void setNextLaunch (java.util.Date nextLaunch)`
- `void setNotificationNeeded (boolean notificationNeeded)`
- `void setPartitionResult ( TaskResult res)`
- `void setPhase (int i)`
- `void setRetryCount (int retryCount)`
- `void setRetryInterval (int val)`
- `void setString1 (java.lang.String string1)`
- `void setString1AndTruncate (java.lang.String string1)`
- `void setTaskResult ( TaskResult result)`
- `void visit ( Visitor v)`

---

## RequestDefinition

**Package:** `sailpoint.object`

**Description:** An object describing a background request.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.TaskItemDefinition`
- `sailpoint.object.RequestDefinition`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ARG_ERROR_ACTION`
- `static java.lang.String ARG_HOST_SPECIFIC`
- `static java.lang.String ARG_HOSTS`
- `static java.lang.String ARG_MAX_QUEUE`
- `static java.lang.String ARG_MAX_THREADS`
- `static java.lang.String ARG_ORPHAN_ACTION`
- `static java.lang.String ARG_REQUEST_PROCESSOR_NO_INTERRUPT`
- `static java.lang.String ERROR_ACTION_TERMINATE`
- `static java.lang.String ORPHAN_ACTION_DELETE`
- `static java.lang.String ORPHAN_ACTION_RESTART`
- `static java.lang.String REQ_AGGREGATION`
- `static java.lang.String REQ_MANAGER_CERT`
- `static java.lang.String REQ_REFRESH`
- `static java.lang.String REQ_SERVICE`
- `static java.lang.String REQ_TERMINATE`

**Methods:**
- `int getRetryInterval ()`
- `int getRetryMax ()`
- `boolean isHostSpecific ()`
- `void setRetryInterval (int val)`
- `void setRetryMax (int retryMax)`

---

## RequestExecutor

**Package:** `sailpoint.object`

**Description:** An interface that must be implemented by any class to be managed by the request processor.

**Inherited Classes/Interfaces:**
- `BaseExecutor`

**Attributes:** N/A

**Methods:**
- `void execute ( SailPointContext context, Request request, Attributes <java.lang.String,java.lang.Object> args)`

---

## RequestState

**Package:** `sailpoint.object`

**Description:** Holds any large data needed to restore a Request to its state upon a restart of the Request. This object is not directly referenced by the Request in order to isolate the Request from the occassional large data being persisted to its RequestState.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.RequestState`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATT_RESTART_INFO`

**Methods:**
- `java.lang.Object get (java.lang.String name)`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `int getInt (java.lang.String name)`
- `long getLong (java.lang.String name)`
- `Request getRequest ()`
- `boolean hasAssignedScope ()`
- `boolean isNameUnique ()`
- `void put (java.lang.String name, java.lang.Object value)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> a)`
- `void setInt (java.lang.String name, int value)`
- `void setRequest ( Request request)`

---

## Resolver

**Package:** `sailpoint.object`

**Description:** The interface of an object capable of resolving references to SailPointObjects. Used by a few classes that normally store references by name, but provide convenience methods to resolve the object.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `<T extendsSailPointObject>int countObjects (java.lang.Class<T> cls, QueryOptions ops)`
- `<T extendsSailPointObject>T getObject (java.lang.Class<T> cls, java.lang.String idOrName)`
- `<T extendsSailPointObject>T getObject (java.lang.Class<T> cls, QueryOptions queryOptions)`
- `<T extendsSailPointObject>T getObjectById (java.lang.Class<T> cls, java.lang.String id)`
- `<T extendsSailPointObject>T getObjectByName (java.lang.Class<T> cls, java.lang.String name)`
- `<T extendsSailPointObject>java.util.List<T> getObjects (java.lang.Class<T> cls, QueryOptions ops)`

---

## ResourceEvent

**Package:** `sailpoint.object`

**Description:** A class used to maintain a queue of change events received from Connectors that support change notification. These are normally created by the SMListenerService as it receives events from SM instances.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.ResourceEvent`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `Application getApplication ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `ProvisioningPlan getPlan ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `void setApplication ( Application app)`
- `void setPlan ( ProvisioningPlan plan)`

---

## ResourceObject

**Package:** `sailpoint.object`

**Description:** The definition of an object returned from an Application. This is not a true persistent class, it is transient and the callers typically create other objects out of the data stored in the ResourceObjects.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ResourceObject`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String ATT_IDENTITY_TYPE`

**Methods:**
- `java.lang.Object clone ()`
- `void fromMap (java.util.Map map)`
- `java.lang.Object get (java.lang.String key)`
- `java.lang.Object getAttribute (java.lang.String key)`
- `java.util.Collection<java.lang.String> getAttributeNames ()`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `boolean getBoolAttribute (java.lang.String name)`
- `java.lang.String getDisplayName ()`
- `java.lang.String getIdentity ()`
- `java.lang.String getInstance ()`
- `java.util.List<java.lang.String> getMissing ()`
- `java.lang.String getNameOrId ()`
- `java.lang.String getObjectType ()`
- `java.lang.String getPreviousIdentity ()`
- `java.lang.String getString (java.lang.String name)`
- `java.lang.String getStringAttribute (java.lang.String name)`
- `java.util.List<java.lang.String> getStringList (java.lang.String name)`
- `java.lang.String getUuid ()`
- `boolean isDelete ()`
- `boolean isFinalUpdate ()`
- `boolean isIncomplete ()`
- `boolean isIncremental ()`
- `boolean isRemove ()`
- `boolean isSparse ()`
- `void put (java.lang.String key, java.lang.Object value)`
- `void remove (java.lang.String key)`
- `void setAttribute (java.lang.String key, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attributes)`
- `void setDelete (boolean b)`
- `void setDisplayName (java.lang.String name)`
- `void setFinalUpdate (boolean finalUpdate)`
- `void setIdentity (java.lang.String identity)`
- `void setIncomplete (boolean b)`
- `void setIncremental (boolean b)`
- `void setInstance (java.lang.String ins)`
- `void setMissing (java.util.List<java.lang.String> names)`
- `void setObjectType (java.lang.String objectType)`
- `void setPreviousIdentity (java.lang.String identity)`
- `void setRemove (boolean b)`
- `void setUuid (java.lang.String id)`
- `java.util.Map<java.lang.String,​java.lang.Object> toMap ()`

---

## Right

**Package:** `sailpoint.object`

**Description:** Part of the RightConfig model, a representation of a specific right on a target object. There will be a default set of these, but the model is extensible to accommodate resources that have unusual rights.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Right`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.IXmlEqualable<Right>`

**Attributes:** N/A

**Methods:**
- `boolean contentEquals ( Right other)`
- `java.lang.String getDescription ()`
- `java.lang.String getDisplayableName (java.util.Locale locale)`
- `java.lang.String getDisplayName ()`
- `java.lang.String getName ()`
- `int getWeight ()`
- `void setDescription (java.lang.String s)`
- `void setDisplayName (java.lang.String s)`
- `void setName (java.lang.String s)`
- `void setWeight (int w)`

---

## RightConfig

**Package:** `sailpoint.object`

**Description:** The definition of the possible rights that can exist in a Permission. The Right class represents each right, they are collected here. There is normally only one of these objects in the database.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.RightConfig`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String OBJ_NAME`

**Methods:**
- `Right getRight (java.lang.String name)`
- `java.util.List<Right> getRights ()`
- `void setRights (java.util.List< Right > rights)`

---

## RoleAssignment

**Package:** `sailpoint.object`

**Description:** Used to record information about role assignments and revocations. This is similar to AttributeMetadata but different in that changes are being recorded to individual values of a single multi-valued attribute. A list of these will be stored in the preferences area of the identity cube. This was re-actored in 6.0 and now extends Assignment

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Assignment`
- `sailpoint.object.RoleAssignment`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void addPermittedRole ( RoleAssignment ra)`
- `void addRoleTarget ( RoleTarget target)`
- `void convert ( RoleRequest src)`
- `java.lang.String getComments ()`
- `java.lang.String getId ()`
- `java.lang.String getName ()`
- `RoleAssignment getPermittedRole (java.lang.String id, java.lang.String name)`
- `RoleAssignment getPermittedRole ( Bundle role)`
- `java.util.List<RoleAssignment> getPermittedRoleAssignments ()`
- `staticRoleAssignment getRoleAssignment (java.util.List< RoleAssignment > list, java.lang.String id)`
- `java.lang.String getRoleId ()`
- `java.lang.String getRoleName ()`
- `Bundle getRoleObject ( Resolver r)`
- `java.util.List<RoleTarget> getTargets ()`
- `java.lang.String getXmlId ()`
- `java.lang.String getXmlName ()`
- `boolean hasEnded ()`
- `boolean hasMatchingRoleTarget ( RoleTarget roleTarget)`
- `boolean hasStarted ()`
- `boolean isFutureAssignment ()`
- `boolean isPromotedSoftPermit ()`
- `void removePermittedRole ( RoleAssignment ra)`
- `void setComments (java.lang.String s)`
- `void setId (java.lang.String s)`
- `void setName (java.lang.String s)`
- `void setPermittedRoleAssignments (java.util.List< RoleAssignment > permits)`
- `void setRole ( Bundle role)`
- `void setRoleId (java.lang.String s)`
- `void setRoleName (java.lang.String s)`
- `void setTargets (java.util.List< RoleTarget > targets)`
- `void setXmlId (java.lang.String s)`
- `void setXmlName (java.lang.String s)`

---

## RoleAssignmentSnapshot

**Package:** `sailpoint.object`

**Description:** Light weight class containing snapshot of RoleAssignment object. Used by IdentitySnapshot.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.RoleAssignmentSnapshot`
- `java.io.Serializable`
- `NamedSnapshot`

**Attributes:** N/A

**Methods:**
- `java.lang.String getName ()`
- `java.util.List<RoleTarget> getTargets ()`
- `void setName (java.lang.String name)`
- `void setTargets (java.util.List< RoleTarget > targets)`

---

## RoleChangeEvent.Status

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `RoleChangeEvent.Status`
- `sailpoint.object.RoleChangeEvent.Status`
- `java.io.Serializable`
- `java.lang.Comparable<RoleChangeEvent.Status>`
- `sailpoint.tools.MessageKeyHolder`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `boolean isEqual (java.lang.String name)`
- `staticRoleChangeEvent.Status valueOf (java.lang.String name)`
- `staticRoleChangeEvent.Status[] values ()`

---

## RoleChangeEvent

**Package:** `sailpoint.object`

**Description:** Class used to represent role change event whenever role is modified

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.RoleChangeEvent`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `void addFailedIdentityId (java.lang.String failedIdentityId)`
- `void addSkippedIdentityId (java.lang.String skippedIdentityId)`
- `void clearFailedIdentityIds ()`
- `void clearSkippedIdentityIds ()`
- `int getAffectedIdentityCount ()`
- `java.lang.String getBundleId ()`
- `java.lang.String getBundleName ()`
- `int getFailedAttempts ()`
- `java.util.Set<java.lang.String> getFailedIdentityIds ()`
- `ProvisioningPlan getProvisioningPlan ()`
- `int getRunCount ()`
- `java.util.Set<java.lang.String> getSkippedIdentityIds ()`
- `RoleChangeEvent.Status getStatus ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `void incrementFailedAttempts ()`
- `boolean isBundleDeleted ()`
- `void removeFailedIdentityId (java.lang.String failedIdentityId)`
- `void removeSkippedIdentityId (java.lang.String skippedIdentityId)`
- `void resetFailedAttempts ()`
- `void setAffectedIdentityCount (int affectedIdentityCount)`
- `void setBundleDeleted (boolean b)`
- `void setBundleId (java.lang.String bundleId)`
- `void setBundleName (java.lang.String bundleName)`
- `void setFailedAttempts (int failedAttempts)`
- `void setFailedIdentityIds (java.util.Set<java.lang.String> failedIdentityIds)`
- `void setProvisioningPlan ( ProvisioningPlan plan)`
- `void setRunCount (int runCount)`
- `void setSkippedIdentityIds (java.util.Set<java.lang.String> skippedIdentityIds)`
- `void setStatus ( RoleChangeEvent.Status status)`

---

## RoleContainer

**Package:** `sailpoint.object`

**Description:** This simple interface is implemented by those SailPointObjects that contain roles. Currently these include Bundle and Process.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `void add ( Bundle role)`
- `java.util.List<Bundle> getRoles ()`
- `boolean remove ( Bundle role)`

---

## RoleDetection

**Package:** `sailpoint.object`

**Description:** An object used to record information about which entitlements held by the identity were used in the detection of a role. This is calculated as a side effect of entitlement correlation, and not intended to be edited manually.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.RoleDetection`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void addAssignmentId (java.lang.String id)`
- `java.util.List<java.lang.String> getAssignmentIdList ()`
- `java.lang.String getAssignmentIds ()`
- `java.util.Date getDate ()`
- `java.lang.String getDetectionId ()`
- `EntitlementCollection getEntitlementCollection ()`
- `java.lang.String getFirstAssignmentId ()`
- `java.lang.String getId ()`
- `java.util.List<IdentityItem> getItems ()`
- `java.lang.String getName ()`
- `java.lang.String getRoleId ()`
- `java.lang.String getRoleName ()`
- `Bundle getRoleObject ( Resolver r)`
- `java.util.List<RoleTarget> getTargets ()`
- `java.lang.String getXmlId ()`
- `java.lang.String getXmlName ()`
- `boolean hasAssignmentId (java.lang.String id)`
- `boolean hasAssignmentIds ()`
- `boolean hasCompatibleTargets (java.util.List< RoleTarget > other)`
- `boolean isMatch ( RoleDetection other)`
- `boolean isMatchingRole (java.lang.String id, java.lang.String name)`
- `void removeAssignmentId (java.lang.String id)`
- `void setAssignmentIds (java.lang.String ids)`
- `void setAssignmentIds (java.util.List<java.lang.String> ids)`
- `void setDate (java.util.Date d)`
- `void setDetectionId (java.lang.String s)`
- `void setEntitlementCollection ( EntitlementCollection ec)`
- `void setId (java.lang.String s)`
- `void setItems (java.util.List< IdentityItem > items)`
- `void setName (java.lang.String s)`
- `void setRole ( Bundle role)`
- `void setRoleId (java.lang.String s)`
- `void setRoleName (java.lang.String s)`
- `void setTargets (java.util.List< RoleTarget > targets)`
- `void setXmlId (java.lang.String s)`
- `void setXmlName (java.lang.String s)`

---

## RoleIndex

**Package:** `sailpoint.object`

**Description:** Class used to hold statistics about roles.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.GenericIndex`
- `sailpoint.object.RoleIndex`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `int getAssignedCount ()`
- `Bundle getBundle ()`
- `int getDetectedCount ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `int getEntitlementCount ()`
- `int getEntitlementCountInheritance ()`
- `java.util.Date getLastAssigned ()`
- `java.util.Date getLastCertifiedComposition ()`
- `java.util.Date getLastCertifiedMembership ()`
- `boolean isAssociatedToRole ()`
- `void setAssignedCount (int count)`
- `void setAssociatedToRole (boolean associatedToRole)`
- `void setBundle ( Bundle _bundle)`
- `void setDetectedCount (int count)`
- `void setEntitlementCount (int count)`
- `void setEntitlementCountInheritance (int countInheritance)`
- `void setLastAssigned (java.util.Date assigned)`
- `void setLastCertifiedComposition (java.util.Date certified)`
- `void setLastCertifiedMembership (java.util.Date certified)`
- `void visit ( Visitor v)`

---

## RoleMetadata

**Package:** `sailpoint.object`

**Description:** Holds meta-data about a role that has been detected or assigned to an identity.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.RoleMetadata`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `Bundle getRole ()`
- `boolean isAdditionalEntitlements ()`
- `boolean isAssigned ()`
- `boolean isDetected ()`
- `boolean isDetectedException ()`
- `boolean isMissingRequired ()`
- `boolean isNameUnique ()`
- `void setAdditionalEntitlements (boolean additionalEntitlements)`
- `void setAssigned (boolean assigned)`
- `void setDetected (boolean detected)`
- `void setDetectedException (boolean detectedException)`
- `void setMissingRequired (boolean missingRequired)`
- `void setRole ( Bundle role)`
- `void visit ( Visitor v)`

---

## RoleMiningResult

**Package:** `sailpoint.object`

**Description:** A container for the results of a role mining process. The creation date will be the date the mining was finished, the owner will be the identity that launched the mining process. These are a bit like task results, they are displayed and managed by the undirected mining pages.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.RoleMiningResult`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `void add (java.util.List< CandidateRole > roles)`
- `void add ( CandidateRole r)`
- `MiningConfig getConfig ()`
- `java.lang.String getConfigName ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `CandidateRole getRole (java.lang.String id)`
- `int getRoleCount ()`
- `java.util.List<CandidateRole> getRoles ()`
- `java.lang.String getStatus ()`
- `boolean isNameUnique ()`
- `boolean isPending ()`
- `void remove ( CandidateRole r)`
- `void setConfig ( MiningConfig config)`
- `void setPending (boolean b)`
- `void setRoles (java.util.List< CandidateRole > roles)`

---

## RoleOverlapResult.RoleOverlap

**Package:** `sailpoint.object`

**Description:** Represents the overlap calculations for one pair of roles.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.RoleOverlapResult.RoleOverlap`

**Attributes:** N/A

**Methods:**
- `int getAssignment ()`
- `int getAttribute ()`
- `int getLocalAssignment ()`
- `int getLocalProvisioning ()`
- `java.lang.String getName ()`
- `int getProvisioning ()`
- `java.lang.String getType ()`
- `void setAssignment (int i)`
- `void setAttribute (int i)`
- `void setLocalAssignment (int i)`
- `void setLocalProvisioning (int i)`
- `void setName (java.lang.String s)`
- `void setProvisioning (int i)`
- `void setType (java.lang.String s)`

---

## RoleOverlapResult

**Package:** `sailpoint.object`

**Description:** Represents the results of a role overlap analysis. These will be stored inside the TaskResult for role impact analysis tasks.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.RoleOverlapResult`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void add ( RoleOverlapResult.RoleOverlap r)`
- `java.lang.String getid ()`
- `java.lang.String getName ()`
- `int getRoleOverlapCount ()`
- `java.util.List<RoleOverlapResult.RoleOverlap> getRoleOverlaps ()`
- `int getRolesExamined ()`
- `void incRolesExamined ()`
- `boolean isNameUnique ()`
- `void setid (java.lang.String s)`
- `void setName (java.lang.String s)`
- `void setRoleOverlaps (java.util.List< RoleOverlapResult.RoleOverlap > overlaps)`
- `void setRolesExamined (int i)`

---

## RoleRelationships

**Package:** `sailpoint.object`

**Description:** Used to represent an analysis of the role relationships for a single identity. This is a transient object used by the UI when displaying assigned and detected roles for an identity. It is built by the Identitizer.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.RoleRelationships`

**Attributes:** N/A

**Methods:**
- `void analyze (java.util.List< Bundle > assigned, java.util.List< Bundle > detected)`
- `void analyze ( Identity ident)`
- `void dump ()`
- `java.util.List<Bundle> getMissingRequirements ( Bundle role)`
- `java.lang.String getPermittedNames ( Bundle role)`
- `java.util.List<Bundle> getPermittedRoles ( Bundle role)`
- `java.lang.String getPermittingNames ( Bundle role)`
- `java.util.List<Bundle> getPermittingRoles (java.util.List< Bundle > assigned, Bundle b)`
- `java.util.List<Bundle> getPermittingRoles ( Bundle role)`
- `java.util.List<Bundle> getRequirements ( Bundle role)`
- `java.util.List<Bundle> getRequiringRoles ( Bundle role)`
- `boolean hasRole ( Bundle role)`
- `boolean isPermitted ( Bundle assignedRole, Bundle detectedRole)`
- `boolean isRequired ( Bundle assignedRole, Bundle detectedRole)`
- `static void print (java.lang.Object o)`
- `static void println (java.lang.Object o)`

---

## RoleRequest

**Package:** `sailpoint.object`

**Description:** Used to record information about a permitted role request in an Identity. This has all of the same information as RoleAssignment, and adds some context around the request and is stored in a different preferences attribute.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Assignment`
- `sailpoint.object.RoleAssignment`
- `sailpoint.object.RoleRequest`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getPermittedById ()`
- `java.lang.String getPermittedByName ()`
- `void setPermittedById (java.lang.String s)`
- `void setPermittedByName (java.lang.String s)`

---

## RoleScorecard

**Package:** `sailpoint.object`

**Description:** Number of identities that are detected to have this IT role

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.RoleScorecard`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `int getDetected ()`
- `int getDetectedAsExceptions ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `int getMembers ()`
- `int getMembersWithAdditionalEntitlements ()`
- `int getMembersWithMissingRequiredRoles ()`
- `int getPermittedEntitlements ()`
- `int getProvisionedEntitlements ()`
- `Bundle getRole ()`
- `boolean hasName ()`
- `void setDetected (int _detected)`
- `void setDetectedAsExceptions (int asExceptions)`
- `void setMembers (int _members)`
- `void setMembersWithAdditionalEntitlements (int withAdditionalEntitlements)`
- `void setMembersWithMissingRequiredRoles (int withMissingRequiredRoles)`
- `void setPermittedEntitlements (int entitlements)`
- `void setProvisionedEntitlements (int entitlements)`
- `void setRole ( Bundle role)`
- `void visit ( Visitor v)`

---

## RoleSnapshot.ProfileSnapshot

**Package:** `sailpoint.object`

**Description:** Snapshot of a profile included in a role.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Snapshot`
- `sailpoint.object.RoleSnapshot.ProfileSnapshot`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getAccountType ()`
- `java.lang.String getApplication ()`
- `java.util.List<Filter> getConstraints ()`
- `java.util.List<Permission> getPermissions ()`
- `void setAccountType (java.lang.String accountType)`
- `void setApplication (java.lang.String application)`
- `void setConstraints (java.util.List< Filter > constraints)`
- `void setPermissions (java.util.List< Permission > permissions)`

---

## RoleSnapshot

**Package:** `sailpoint.object`

**Description:** Snapshot of the composition of a role. Used for taking snapshots of roles when creating role composition certifications.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Snapshot`
- `sailpoint.object.RoleSnapshot`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void addGrantedCapbility ( Capability capability)`
- `void addGrantedScope ( Scope scope)`
- `java.util.List<Snapshot> getGrantedCapabilities ()`
- `void getGrantedCapability ()`
- `Snapshot getGrantedCapability (java.lang.String id)`
- `Snapshot getGrantedScope (java.lang.String id)`
- `java.util.List<Snapshot> getGrantedScopes ()`
- `java.util.List<Snapshot> getInheritedRoles ()`
- `java.lang.String getOwnerDisplayName ()`
- `java.util.List<Snapshot> getPermittedRoles ()`
- `java.util.List<RoleSnapshot.ProfileSnapshot> getProfiles ()`
- `RoleSnapshot.ProfileSnapshot getProfileSnapshot (java.lang.String id)`
- `Snapshot getRelatedRoleSnapshot (java.lang.String id)`
- `java.util.List<Snapshot> getRequiredRoles ()`
- `java.lang.String getScopeDisplayName ()`
- `java.lang.String getType ()`
- `java.lang.String getTypeDisplayName ()`
- `void setGrantedCapabilities (java.util.List< Snapshot > grantedCapabilities)`
- `void setGrantedScopes (java.util.List< Snapshot > grantedScopes)`
- `void setInheritedRoles (java.util.List< Snapshot > inheritedRoles)`
- `void setOwnerDisplayName (java.lang.String ownerDisplayName)`
- `void setPermittedRoles (java.util.List< Snapshot > permittedRoles)`
- `void setProfiles (java.util.List< RoleSnapshot.ProfileSnapshot > profiles)`
- `void setRequiredRoles (java.util.List< Snapshot > requiredRoles)`
- `void setScopeDisplayName (java.lang.String scopeDisplayName)`
- `void setType (java.lang.String type)`
- `void setTypeDisplayName (java.lang.String typeDisplayName)`

---

## RoleTarget

**Package:** `sailpoint.object`

**Description:** Holds information to track down a role assignment to an account.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.RoleTarget`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void addItem ( AccountItem item)`
- `static java.util.List<RoleTarget> fromEntitlementGroups (java.util.List< EntitlementGroup > groups)`
- `java.lang.String getApplicationId ()`
- `java.lang.String getApplicationName ()`
- `java.lang.String getDisplayableName ()`
- `java.lang.String getDisplayName ()`
- `boolean getDoCreate ()`
- `java.lang.String getInstance ()`
- `java.util.List<AccountItem> getItems ()`
- `java.lang.String getNativeIdentity ()`
- `java.lang.String getRoleName ()`
- `staticRoleTarget getRoleTarget (java.lang.String id, java.lang.String name, java.lang.String sourceRole, java.util.List< RoleTarget > targets)`
- `staticRoleTarget getRoleTarget ( Application app, java.lang.String sourceRole, java.util.List< RoleTarget > targets)`
- `staticRoleTarget getRoleTarget ( Application app, java.util.List< RoleTarget > targets)`
- `staticRoleTarget getRoleTarget ( RoleTarget other, java.lang.String sourceRole, java.util.List< RoleTarget > targets)`
- `static boolean isCompatible (java.util.List< RoleTarget > list1, java.util.List< RoleTarget > list2)`
- `boolean isElevatedAccess ()`
- `static boolean isEqual (java.util.List< RoleTarget > list1, java.util.List< RoleTarget > list2)`
- `java.lang.Boolean isIiqElevatedAccess ()`
- `static boolean isMatch (java.util.List< RoleTarget > list1, java.util.List< RoleTarget > list2)`
- `boolean isMatch ( RoleTarget other)`
- `boolean isMatch ( RoleTarget other, boolean checkRoleName)`
- `boolean isMatchingApplication (java.lang.String id, java.lang.String name, java.lang.String instance)`
- `boolean isMatchingApplication ( Application app, java.lang.String instance)`
- `void setApplicationId (java.lang.String applicationId)`
- `void setApplicationName (java.lang.String applicationName)`
- `void setDisplayName (java.lang.String displayName)`
- `void setDisplayNameIfDifferent (java.lang.String name)`
- `void setDoCreate (boolean doCreate)`
- `void setIiqElevatedAccess (java.lang.Boolean iiqElevatedAccess)`
- `void setInstance (java.lang.String instance)`
- `void setItems (java.util.List< AccountItem > items)`
- `void setNativeIdentity (java.lang.String nativeIdentity)`
- `void setRoleName (java.lang.String name)`
- `static java.util.List<EntitlementGroup> toEntitlementGroups ( Resolver r, java.util.List< RoleTarget > targets)`

---

## RoleTypeDefinition

**Package:** `sailpoint.object`

**Description:** An object defining a role type. These are stored in the ObjectConfig named "Bundle".

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.RoleTypeDefinition`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getDescription ()`
- `java.util.List<java.lang.String> getDisallowedAttributes ()`
- `java.lang.String getDisplayableName ()`
- `java.lang.String getDisplayName ()`
- `java.lang.String getIcon ()`
- `java.lang.String getName ()`
- `java.util.List<SPRight> getRights ()`
- `boolean isAllowDuplicateAccounts ()`
- `boolean isAssignable ()`
- `boolean isDetectable ()`
- `boolean isManuallyAssignable ()`
- `boolean isNoAssignmentSelector ()`
- `boolean isNoAutoAssignment ()`
- `boolean isNoDetection ()`
- `boolean isNoDetectionUnlessAssigned ()`
- `boolean isNoIIQ ()`
- `boolean isNoManualAssignment ()`
- `boolean isNoPermits ()`
- `boolean isNoProfiles ()`
- `boolean isNoRequirements ()`
- `boolean isNoSubs ()`
- `boolean isNoSupers ()`
- `boolean isNotPermittable ()`
- `boolean isNotRequired ()`
- `void setDescription (java.lang.String s)`
- `void setDisallowedAttributes (java.util.List<java.lang.String> val)`
- `void setDisplayName (java.lang.String displayName)`
- `void setIcon (java.lang.String icon)`
- `void setName (java.lang.String name)`
- `void setNoAssignmentSelector (boolean b)`
- `void setNoAutoAssignment (boolean b)`
- `void setNoDetection (boolean b)`
- `void setNoDetectionUnlessAssigned (boolean b)`
- `void setNoIIQ (boolean b)`
- `void setNoManualAssignment (boolean b)`
- `void setNoPermits (boolean b)`
- `void setNoProfiles (boolean b)`
- `void setNoRequirements (boolean b)`
- `void setNoSubs (boolean b)`
- `void setNoSupers (boolean b)`
- `void setNotPermittable (boolean b)`
- `void setNotRequired (boolean b)`
- `void setRights (java.util.List< SPRight > rights)`

---

## Rule.RuleTypeComparator

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Rule.RuleTypeComparator`
- `java.util.Comparator<Rule.Type>`

**Attributes:** N/A

**Methods:**
- `int compare ( Rule.Type t1, Rule.Type t2)`

---

## Rule.Type

**Package:** `sailpoint.object`

**Description:** Rules may be typed if they are intended for use in certain parts of the system proper use of types is necessary for the rule to appear in selection menus in the UI.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Rule.Type`
- `sailpoint.object.Rule.Type`
- `java.io.Serializable`
- `java.lang.Comparable<Rule.Type>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticRule.Type valueOf (java.lang.String name)`
- `staticRule.Type[] values ()`

---

## Rule

**Package:** `sailpoint.object`

**Description:** A Rule contains a script that can be executed to perform custom logic. Each rule declares which language it uses, the source for the rule, and context about how the rule should be run.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Rule`
- `java.io.Serializable`
- `sailpoint.tools.xml.IXmlEqualable<Rule>`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String MODEL_BASE_PATH`

**Methods:**
- `void addReferencedRule ( Rule rule)`
- `int compareTo (java.lang.Object o)`
- `boolean contentEquals ( Rule other)`
- `boolean equals (java.lang.Object obj)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.Object getAttributeValue (java.lang.String name)`
- `java.lang.String getLanguage ()`
- `java.util.List<Rule> getReferencedRules ()`
- `Signature getSignature ()`
- `java.lang.String getSource ()`
- `Rule.Type getType ()`
- `int hashCode ()`
- `boolean isContentEquivalent ( Rule other)`
- `void load ()`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> config)`
- `void setLanguage (java.lang.String language)`
- `void setReferencedRules (java.util.List< Rule > referencedRules)`
- `void setSignature ( Signature s)`
- `void setSource (java.lang.String source)`
- `void setType ( Rule.Type type)`
- `void visit ( Visitor v)`

---

## RuleRegistry.Callout

**Package:** `sailpoint.object`

**Description:** Enumeration of all Callout points available in the code.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `RuleRegistry.Callout`
- `sailpoint.object.RuleRegistry.Callout`
- `java.io.Serializable`
- `java.lang.Comparable<RuleRegistry.Callout>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getDescription ()`
- `java.lang.String getDisplayName ()`
- `staticRuleRegistry.Callout valueOf (java.lang.String name)`
- `staticRuleRegistry.Callout[] values ()`

---

## RuleRegistry

**Package:** `sailpoint.object`

**Description:** A registry that stores which rule to run at certain "callout" points in the code. There is normally only one of these objects in the database.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.RuleRegistry`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String DEFAULT_RULE_REG`

**Methods:**
- `void addTemplate ( Rule template)`
- `staticRuleRegistry getInstance ( SailPointContext ctx)`
- `Rule getRule ( RuleRegistry.Callout callout)`
- `Rule getTemplate (java.lang.String type)`
- `Rule getTemplate ( Rule.Type type)`
- `Rule getTemplate ( Rule.Type type, boolean returnFull)`
- `java.util.List<Rule> getTemplates ()`
- `java.util.List<Rule.Type> getTypes ()`
- `void removeTemplate ( Rule template)`
- `void setRule ( RuleRegistry.Callout callout, Rule rule)`

---

## RuleRunner

**Package:** `sailpoint.object`

**Description:** Interface of an object that is able to execute rules and scripts.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `java.lang.Object runRule ( Rule rule, java.util.Map<java.lang.String,java.lang.Object> params)`
- `java.lang.Object runRule ( Rule rule, java.util.Map<java.lang.String,java.lang.Object> params, java.util.List< Rule > libraries)`
- `java.lang.Object runScript ( Script script, java.util.Map<java.lang.String,java.lang.Object> params)`
- `java.lang.Object runScript ( Script script, java.util.Map<java.lang.String,java.lang.Object> params, java.util.List< Rule > libraries)`

---

## SAMLConfig

**Package:** `sailpoint.object`

**Description:** Config Object used to store configuration of SAML SSO

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SAMLConfig`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `boolean equals (java.lang.Object o)`
- `java.lang.String getAddress ()`
- `java.lang.String getAssertionConsumerService ()`
- `java.lang.String getAuthnContextClassRef ()`
- `java.lang.String getAuthnContextComparison ()`
- `java.lang.String getBindingMethod ()`
- `java.lang.String getEntityId ()`
- `java.lang.String getIdpPublicKey ()`
- `java.lang.String getIdpServiceUrl ()`
- `java.lang.String getIssuer ()`
- `java.lang.String getNameIdFormat ()`
- `Rule getSamlCorrelationRule ()`
- `java.lang.String getSpNameQualifier ()`
- `int hashCode ()`
- `void setAddress (java.lang.String address)`
- `void setAssertionConsumerService (java.lang.String assertionConsumerService)`
- `void setAuthnContextClassRef (java.lang.String authnContextClassRef)`
- `void setAuthnContextComparison (java.lang.String authnContextComparison)`
- `void setBindingMethod (java.lang.String bindingMethod)`
- `void setEntityId (java.lang.String entityId)`
- `void setIdpPublicKey (java.lang.String idpPublicKey)`
- `void setIdpServiceUrl (java.lang.String idpServiceUrl)`
- `void setIssuer (java.lang.String issuer)`
- `void setNameIdFormat (java.lang.String nameIdFormat)`
- `void setSamlCorrelationRule ( Rule samlCorrelationRule)`
- `void setSpNameQualifier (java.lang.String spNameQualifier)`

---

## SAMLToken

**Package:** `sailpoint.object`

**Description:** The database id.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.SAMLToken`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.util.Date getExpiration ()`
- `java.lang.String getId ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `void setExpiration (java.util.Date expiration)`
- `void setId (java.lang.String id)`

---

## SMSResetConfig

**Package:** `sailpoint.object`

**Description:** This class is the object representing SMS text Reset Password configuration. Typically, you need all these properties, so they are consolidated into this one configuration object.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SMSResetConfig`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static int DEFAULT_MAX_FAILED_ATTEMPTS`

**Methods:**
- `boolean equals (java.lang.Object o)`
- `java.lang.String getAccountId ()`
- `java.lang.String getAuthToken ()`
- `int getDurationValid ()`
- `java.lang.String getFromPhone ()`
- `int getMaxFailedAttempts ()`
- `java.lang.String getPhoneAttribute ()`
- `int getThrottleMinutes ()`
- `int hashCode ()`
- `boolean isSmsResetEnabled ()`
- `void setAccountId (java.lang.String accountId)`
- `void setAuthToken (java.lang.String authToken)`
- `void setDurationValid (int durationValid)`
- `void setFromPhone (java.lang.String fromPhone)`
- `void setMaxFailedAttempts (int maxFailedAttempts)`
- `void setPhoneAttribute (java.lang.String phoneAttribute)`
- `void setSmsResetEnabled (boolean smsResetEnabled)`
- `void setThrottleMinutes (int span)`

---

## SODConstraint

**Package:** `sailpoint.object`

**Description:** A class defining a role SOD constraint.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.BaseConstraint`
- `sailpoint.object.SODConstraint`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `PolicyViolation.IPolicyViolationOwnerSource`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `void addLeft ( Bundle b)`
- `void addRight ( Bundle b)`
- `boolean equals (java.lang.Object obj)`
- `java.lang.String getCannonicalSummary ()`
- `java.util.List<Bundle> getLeftBundles ()`
- `java.util.List<Bundle> getRightBundles ()`
- `int hashCode ()`
- `boolean isNameUnique ()`
- `void removeLeft ( Bundle b)`
- `void removeRight ( Bundle b)`
- `void setLeftBundles (java.util.List< Bundle > bundles)`
- `void setRightBundles (java.util.List< Bundle > bundles)`

---

## SPRight.WebServiceRights

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `SPRight.WebServiceRights`
- `sailpoint.object.SPRight.WebServiceRights`
- `java.io.Serializable`
- `java.lang.Comparable<SPRight.WebServiceRights>`

**Attributes:** N/A

**Methods:**
- `staticSPRight.WebServiceRights valueOf (java.lang.String name)`
- `staticSPRight.WebServiceRights[] values ()`

---

## SPRight

**Package:** `sailpoint.object`

**Description:** A SPRight serves as a low-level task-based right within IdentityIQ. These are used by IdentityIQ to to restrict access to certain parts of the UI or to disable UI controls and make them read-only. Each right should denote both an action and a target - for example a right named ViewApplication would be required to have a read-only view of a certification, while ManageCertification would be required to see a read/write view of a certification. The "manage" right denotes create, update, and delete access. There is also the concept of a "full access" type of right that provides all-or-none access to some part of the system. In other words, FullAccessGroup will allow viewing, creating, updating, deleting groups, while lack of this right will completely disable any access to groups. These are intentionally fairly coarse-grained, but can be split out into individual rights as needed. When this happens, adding an "implied rights" list to SPRight that allows for easier upgrades should be considered. These are maintained as SailPointObjects rather than an enumeration because they are extensible. New SPRights can be added to the system by a customer to add specific access control around objects in the system (for example - reports). In addition to displayName, name and description from SailPointObject are also used.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.SPRight`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String AccessHistoryExportIdentityHistory`
- `static java.lang.String AccessHistoryFullAccessConfiguration`
- `static java.lang.String AccessHistoryViewIdentityHistory`
- `static java.lang.String AssignIdentityRole`
- `static java.lang.String CertificationCampaignsWidget`
- `static java.lang.String CertifyAllCertifications`
- `static java.lang.String CreatePAMContainer`
- `static java.lang.String CreateSCIMAccount`
- `static java.lang.String CreateSCIMAlert`
- `static java.lang.String CreateSCIMCheckedPolicyViolation`
- `static java.lang.String CreateSCIMLaunchedWorkflow`
- `static java.lang.String CreateSCIMUser`
- `static java.lang.String DeleteIdentityLink`
- `static java.lang.String DeleteIdentitySnapshot`
- `static java.lang.String DeleteSCIMAccount`
- `static java.lang.String DeleteSCIMUser`
- `static java.lang.String DeleteSignOffResult`
- `static java.lang.String EditScripts`
- `static java.lang.String FormsAdmin`
- `static java.lang.String FullAccessAboutPage`
- `static java.lang.String FullAccessAccountMapping`
- `static java.lang.String FullAccessActivityCategory`
- `static java.lang.String FullAccessAlertDefinition`
- `static java.lang.String FullAccessApplicationRisk`
- `static java.lang.String FullAccessApplicationRiskModel`
- `static java.lang.String FullAccessAuditConfig`
- `static java.lang.String FullAccessBatchRequest`
- `static java.lang.String FullAccessBeansPage`
- `static java.lang.String FullAccessCertifications`
- `static java.lang.String FullAccessCertificationSchedule`
- `static java.lang.String FullAccessDataExtractConfiguration`
- `static java.lang.String FullAccessDebugPage`
- `static java.lang.String FullAccessDynamicScope`
- `static java.lang.String FullAccessEnvironmentMonitoring`
- `static java.lang.String FullAccessFAMConfiguration`
- `static java.lang.String FullAccessForms`
- `static java.lang.String FullAccessGroup`
- `static java.lang.String FullAccessIdentityCorrelation`
- `static java.lang.String FullAccessIdentityMapping`
- `static java.lang.String FullAccessIdentityRequest`
- `static java.lang.String FullAccessIdentityRisk`
- `static java.lang.String FullAccessIdentityRiskModel`
- `static java.lang.String FullAccessLoginConfig`
- `static java.lang.String FullAccessMemoryPage`
- `static java.lang.String FullAccessMetersPage`
- `static java.lang.String FullAccessOAuthClientConfiguration`
- `static java.lang.String FullAccessPAM`
- `static java.lang.String FullAccessPlugin`
- `static java.lang.String FullAccessPolicyViolation`
- `static java.lang.String FullAccessProvisioningTransaction`
- `static java.lang.String FullAccessRapidSetup`
- `static java.lang.String FullAccessRapidSetupConfiguration`
- `static java.lang.String FullAccessReport`
- `static java.lang.String FullAccessRequest`
- `static java.lang.String FullAccessRoleMining`
- `static java.lang.String FullAccessSystemConfig`
- `static java.lang.String FullAccessTask`
- `static java.lang.String FullAccessTaskManagement`
- `static java.lang.String FullAccessTerminateIdentity`
- `static java.lang.String FullAccessThreadsPage`
- `static java.lang.String FullAccessTimePeriod`
- `static java.lang.String FullAccessWorkflows`
- `static java.lang.String FullAccessWorkItems`
- `static java.lang.String GenAIEntitlementAdministrator`
- `static java.lang.String ImportFromFile`
- `static java.lang.String ManageApplication`
- `static java.lang.String ManageBusinessProcess`
- `static java.lang.String ManageBusinessRoles`
- `static java.lang.String ManagedAttributePropertyAdministrator`
- `static java.lang.String ManagedAttributeProvisioningAdministrator`
- `static java.lang.String ManageEntitlementRoles`
- `static java.lang.String ManageITRoles`
- `static java.lang.String ManageOrganizationalRoles`
- `static java.lang.String ManagePolicy`
- `static java.lang.String ManageRapidSetupBirthrightRoles`
- `static java.lang.String ManageRole`
- `static java.lang.String ManageRules`
- `static java.lang.String ManageScope`
- `static java.lang.String ManageWorkgroup`
- `static java.lang.String MonitorIdentityActivity`
- `static java.lang.String MonitorIdentityEvents`
- `static java.lang.String MonitorIdentityHistory`
- `static java.lang.String MoveIdentityLink`
- `static java.lang.String PAMModifyIdentities`
- `static java.lang.String PAMModifyPrivilegedItems`
- `static java.lang.String ReadSCIMAccount`
- `static java.lang.String ReadSCIMAlert`
- `static java.lang.String ReadSCIMApplication`
- `static java.lang.String ReadSCIMCheckedPolicyViolation`
- `static java.lang.String ReadSCIMEntitlement`
- `static java.lang.String ReadSCIMLaunchedWorkflow`
- `static java.lang.String ReadSCIMObjectConfig`
- `static java.lang.String ReadSCIMPolicyViolation`
- `static java.lang.String ReadSCIMResourceType`
- `static java.lang.String ReadSCIMRole`
- `static java.lang.String ReadSCIMSchema`
- `static java.lang.String ReadSCIMTaskResult`
- `static java.lang.String ReadSCIMUser`
- `static java.lang.String ReadSCIMWorkflow`
- `static java.lang.String ReadTaskResults`
- `static java.lang.String RunRoleImpactAnalysis`
- `static java.lang.String SetIdentityCapability`
- `static java.lang.String SetIdentityControlledScope`
- `static java.lang.String SetIdentityForwarding`
- `static java.lang.String SetIdentityPassword`
- `static java.lang.String SetWorkgroupCapability`
- `static java.lang.String SetWorkgroupControlledScope`
- `static java.lang.String UnlockIdentity`
- `static java.lang.String UpdateSCIMAccount`
- `static java.lang.String UpdateSCIMUser`
- `static java.lang.String ViewAccessAboutPage`
- `static java.lang.String ViewAccessBeansPage`
- `static java.lang.String ViewAccessCachesPage`
- `static java.lang.String ViewAccessConnectionsPage`
- `static java.lang.String ViewAccessCountPage`
- `static java.lang.String ViewAccessDatabasePage`
- `static java.lang.String ViewAccessDebugPage`
- `static java.lang.String ViewAccessLoggingPage`
- `static java.lang.String ViewAccessMemoryPage`
- `static java.lang.String ViewAccessMetersGridPage`
- `static java.lang.String ViewAccessMetersPage`
- `static java.lang.String ViewAccessThreadsPage`
- `static java.lang.String ViewAccountGroups`
- `static java.lang.String ViewActivity`
- `static java.lang.String ViewAlert`
- `static java.lang.String ViewAlertDefinition`
- `static java.lang.String ViewApplication`
- `static java.lang.String ViewApplicationRiskScoreChart`
- `static java.lang.String ViewAttributeDetails`
- `static java.lang.String ViewAuditLog`
- `static java.lang.String ViewBusinessProcess`
- `static java.lang.String ViewCertifications`
- `static java.lang.String ViewEnvironmentMonitoring`
- `static java.lang.String ViewFAMAdminWidgets`
- `static java.lang.String ViewFAMNavigationMenu`
- `static java.lang.String ViewGroupCertification`
- `static java.lang.String ViewGroups`
- `static java.lang.String ViewIdentity`
- `static java.lang.String ViewIdentityRequest`
- `static java.lang.String ViewLink`
- `static java.lang.String ViewOAuthClientConfiguration`
- `static java.lang.String ViewPAMDetail`
- `static java.lang.String ViewPolicy`
- `static java.lang.String ViewPopulations`
- `static java.lang.String ViewProcessInstrumentation`
- `static java.lang.String ViewProvisioningTransaction`
- `static java.lang.String ViewQuickLinks`
- `static java.lang.String ViewRapidSetup`
- `static java.lang.String ViewRapidSetupConfiguration`
- `static java.lang.String ViewRiskScoreChart`
- `static java.lang.String ViewRole`
- `static java.lang.String ViewRoles`
- `static java.lang.String ViewScope`
- `static java.lang.String ViewSyslog`
- `static java.lang.String ViewTaskManagement`
- `static java.lang.String ViewWorkgroup`
- `static java.lang.String WebServices`

**Methods:**
- `java.lang.String getDisplayName ()`
- `void setDisplayName (java.lang.String displayName)`

---

## SailPointObject

**Package:** `sailpoint.object`

**Description:** Common base class for all SailPoint objects with identity in the persistent store.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `java.util.List<ObjectClassification> _classifications`
- `static java.lang.String ATT_AI_GENERATED_DESCRIPTION_LOCALES`
- `static java.lang.String ATT_DESCRIPTIONS`
- `static int MAX_EXTENDED_ATTRIBUTES`
- `static int MAX_EXTENDED_IDENTITY_ATTRIBUTES`

**Methods:**
- `void addAttributeMetaData ( AttributeMetaData amd)`
- `boolean addClassification ( ObjectClassification classification)`
- `void addSignOff ( SignOffHistory esig)`
- `void clearDirtyProperties ()`
- `void clearPersistentIdentity ()`
- `java.lang.Object deepCopy ( Resolver res)`
- `java.lang.Object deepCopy (sailpoint.tools.xml.XMLReferenceResolver res)`
- `java.lang.Object derive ( Resolver res)`
- `boolean equals (java.lang.Object o)`
- `java.lang.Boolean getAllowSignificantModifiedUpdate ()`
- `Scope getAssignedScope ()`
- `java.lang.String getAssignedScopePath ()`
- `java.util.List<AttributeMetaData> getAttributeMetaData ()`
- `AttributeMetaData getAttributeMetaData (java.lang.String attrName)`
- `AttributeMetaData getAttributeMetaData ( ObjectAttribute def)`
- `java.lang.String getAuditClassName ()`
- `static java.util.Comparator<SailPointObject> getByNameComparator ()`
- `java.util.List<ObjectClassification> getClassifications ()`
- `java.util.Date getCreated ()`
- `java.lang.String getDescription ()`
- `java.util.Set<java.lang.String> getDirtyProperties ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `java.lang.String getExtended (int index)`
- `java.lang.String getExtended1 ()`
- `java.lang.String getExtended10 ()`
- `java.lang.String getExtended11 ()`
- `java.lang.String getExtended12 ()`
- `java.lang.String getExtended13 ()`
- `java.lang.String getExtended14 ()`
- `java.lang.String getExtended15 ()`
- `java.lang.String getExtended16 ()`
- `java.lang.String getExtended17 ()`
- `java.lang.String getExtended18 ()`
- `java.lang.String getExtended19 ()`
- `java.lang.String getExtended2 ()`
- `java.lang.String getExtended20 ()`
- `java.lang.String getExtended3 ()`
- `java.lang.String getExtended4 ()`
- `java.lang.String getExtended5 ()`
- `java.lang.String getExtended6 ()`
- `java.lang.String getExtended7 ()`
- `java.lang.String getExtended8 ()`
- `java.lang.String getExtended9 ()`
- `java.lang.Object getExtendedAttribute (java.lang.String key)`
- `java.util.Map<java.lang.String,​java.lang.Object> getExtendedAttributes ()`
- `Identity getExtendedIdentity (int number)`
- `Identity getExtendedIdentity1 ()`
- `Identity getExtendedIdentity10 ()`
- `Identity getExtendedIdentity11 ()`
- `Identity getExtendedIdentity12 ()`
- `Identity getExtendedIdentity13 ()`
- `Identity getExtendedIdentity14 ()`
- `Identity getExtendedIdentity15 ()`
- `Identity getExtendedIdentity16 ()`
- `Identity getExtendedIdentity17 ()`
- `Identity getExtendedIdentity18 ()`
- `Identity getExtendedIdentity19 ()`
- `Identity getExtendedIdentity2 ()`
- `Identity getExtendedIdentity20 ()`
- `Identity getExtendedIdentity3 ()`
- `Identity getExtendedIdentity4 ()`
- `Identity getExtendedIdentity5 ()`
- `Identity getExtendedIdentity6 ()`
- `Identity getExtendedIdentity7 ()`
- `Identity getExtendedIdentity8 ()`
- `Identity getExtendedIdentity9 ()`
- `java.util.Map<java.lang.String,​java.lang.String> getExternalAttributes ()`
- `java.lang.String getId ()`
- `java.util.List<InterceptedDelete> getInterceptedDeletes ()`
- `java.lang.String getLock ()`
- `LockInfo getLockInfo ()`
- `java.util.Date getModified ()`
- `java.lang.String getName ()`
- `Identity getOwner ()`
- `WorkflowCase getPendingWorkflow ()`
- `java.util.Date getPriorSignificantModified ()`
- `java.lang.String getReferenceClass ()`
- `java.lang.String getReferenceId ()`
- `java.lang.String getReferenceName ()`
- `java.util.Set<Reference> getReferenceSet (java.util.Set< SailPointObject > objs)`
- `java.util.Date getSignificantModified ()`
- `java.util.List<SignOffHistory> getSignOffs ()`
- `java.lang.String getUid ()`
- `java.lang.String[] getUniqueKeyProperties ()`
- `boolean hasAssignedScope ()`
- `int hashCode ()`
- `boolean hasName ()`
- `boolean isAutoCreated ()`
- `boolean isDirty ()`
- `boolean isDisabled ()`
- `boolean isExtendedIdentityType ( ObjectAttribute attributeDefinition)`
- `boolean isImmutable ()`
- `boolean isLocked ()`
- `boolean isNameUnique ()`
- `boolean isPersisted ()`
- `boolean isRefreshedExistingLock ()`
- `void load ()`
- `void remove ( AttributeMetaData md)`
- `void removeAttributeMetaData (java.lang.String attrName)`
- `boolean removeClassification ( ObjectClassification classification)`
- `void setAllowSignificantModifiedUpdate (java.lang.Boolean allowSignificantModifiedUpdate)`
- `void setAssignedScope ( Scope scope)`
- `void setAssignedScopePath (java.lang.String path)`
- `void setAttributeMetaData (java.util.List< AttributeMetaData > meta)`
- `void setClassifications (java.util.List< ObjectClassification > c)`
- `void setCreated (java.util.Date created)`
- `void setDescription (java.lang.String s)`
- `void setDirty (boolean b)`
- `void setDirtyProperties (java.lang.String[] propertyNames, int[] dirtyProperties)`
- `void setDirtyProperties (java.util.Set<java.lang.String> dirtyProperties)`
- `void setDisabled (boolean b)`
- `void setExtended (int index, java.lang.String value)`
- `void setExtended1 (java.lang.String s)`
- `void setExtended10 (java.lang.String s)`
- `void setExtended11 (java.lang.String s)`
- `void setExtended12 (java.lang.String s)`
- `void setExtended13 (java.lang.String s)`
- `void setExtended14 (java.lang.String s)`
- `void setExtended15 (java.lang.String s)`
- `void setExtended16 (java.lang.String s)`
- `void setExtended17 (java.lang.String s)`
- `void setExtended18 (java.lang.String s)`
- `void setExtended19 (java.lang.String s)`
- `void setExtended2 (java.lang.String s)`
- `void setExtended20 (java.lang.String s)`
- `void setExtended3 (java.lang.String s)`
- `void setExtended4 (java.lang.String s)`
- `void setExtended5 (java.lang.String s)`
- `void setExtended6 (java.lang.String s)`
- `void setExtended7 (java.lang.String s)`
- `void setExtended8 (java.lang.String s)`
- `void setExtended9 (java.lang.String s)`
- `void setExtendedIdentity ( Identity val, int number)`
- `void setExtendedIdentity1 ( Identity val)`
- `void setExtendedIdentity10 ( Identity val)`
- `void setExtendedIdentity11 ( Identity val)`
- `void setExtendedIdentity12 ( Identity val)`
- `void setExtendedIdentity13 ( Identity val)`
- `void setExtendedIdentity14 ( Identity val)`
- `void setExtendedIdentity15 ( Identity val)`
- `void setExtendedIdentity16 ( Identity val)`
- `void setExtendedIdentity17 ( Identity val)`
- `void setExtendedIdentity18 ( Identity val)`
- `void setExtendedIdentity19 ( Identity val)`
- `void setExtendedIdentity2 ( Identity val)`
- `void setExtendedIdentity20 ( Identity val)`
- `void setExtendedIdentity3 ( Identity val)`
- `void setExtendedIdentity4 ( Identity val)`
- `void setExtendedIdentity5 ( Identity val)`
- `void setExtendedIdentity6 ( Identity val)`
- `void setExtendedIdentity7 ( Identity val)`
- `void setExtendedIdentity8 ( Identity val)`
- `void setExtendedIdentity9 ( Identity val)`
- `void setExternalAttributes (java.util.Map<java.lang.String,java.lang.String> atts)`
- `void setId (java.lang.String id)`
- `void setImmutable (boolean immutable)`
- `void setInterceptedDeletes (java.util.List< InterceptedDelete > interceptedDeletes)`
- `void setLock (java.lang.String lock)`
- `void setModified (java.util.Date d)`
- `void setName (java.lang.String name)`
- `void setOwner ( Identity owner)`
- `void setPendingWorkflow ( WorkflowCase wfcase)`
- `void setPriorSignificantModified (java.util.Date priorSignificantModified)`
- `void setRefreshedExistingLock (boolean b)`
- `void setSignificantModified (java.util.Date significantModified)`
- `void setUid (java.lang.String id)`
- `boolean supportsExtendedIdentity ()`
- `java.lang.String toString ()`
- `void visit ( Visitor v)`

---

## SaveObjectOptions

**Package:** `sailpoint.object`

**Description:** An object encapsulating options to pass to PersistenceManager.saveObject(SailPointObject, SaveObjectOptions)

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.SaveObjectOptions`

**Attributes:**
- `staticSaveObjectOptions RELAX_MOD`

**Methods:**
- `boolean isRelaxSignificantModTimeUpdate ()`
- `SaveObjectOptions setRelaxSignificantModTimeUpdate (boolean _relaxModTimeUpdate)`

---

## Schema

**Package:** `sailpoint.object`

**Description:** Class used to describe each object type supported by an application.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Schema`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATTR_ASSOCIATION_ATTRIBUTE`
- `static java.lang.String ATTR_NOT_REQUESTABLE`
- `static java.lang.String TYPE_ACCOUNT`
- `static java.lang.String TYPE_ALERT`
- `static java.lang.String TYPE_GROUP`
- `static java.lang.String TYPE_UNSTRUCTURED`

**Methods:**
- `void addAttributeDefinition (java.lang.String name, java.lang.String type)`
- `void addAttributeDefinition (java.lang.String name, java.lang.String type, java.lang.String description)`
- `void addAttributeDefinition (java.lang.String name, java.lang.String type, java.lang.String description, boolean isRequired)`
- `void addAttributeDefinition ( AttributeDefinition def)`
- `void addConfig (java.lang.String name, java.lang.Object value)`
- `void addFeature ( Application.Feature feature)`
- `void addMultiValuedAttributeDefinition (java.lang.String name, java.lang.String type, java.lang.String description)`
- `boolean assignCorrelationKeys (int maximum)`
- `boolean containsConfig (java.lang.String name)`
- `boolean equals (java.lang.Object o)`
- `java.lang.String getAggregationType ()`
- `java.lang.String getAssociationSchemaName ()`
- `AttributeDefinition getAttributeBySource (java.lang.String sourceApp, java.lang.String sourceAttr)`
- `AttributeDefinition getAttributeDefinition (java.lang.String name)`
- `java.util.List<java.lang.String> getAttributeInternalNames ()`
- `java.util.List<java.lang.String> getAttributeInternalOrNames ()`
- `java.util.Map<java.lang.String,​AttributeDefinition> getAttributeMap ()`
- `java.util.List<java.lang.String> getAttributeNames ()`
- `java.util.HashSet<java.lang.String> getAttributeNamesHashSet ()`
- `java.util.List<AttributeDefinition> getAttributes ()`
- `java.lang.String getAttributeType (java.lang.String attributeName)`
- `AttributeDefinition getAttributeWithInternalName (java.lang.String internalName)`
- `boolean getBooleanAttributeValue (java.lang.String name)`
- `AttributeDefinition.CloudAccessManagementType getCloudAccessType ()`
- `Attributes<java.lang.String,​java.lang.Object> getConfig ()`
- `Rule getCorrelationRule ()`
- `Rule getCreationRule ()`
- `Rule getCustomizationRule ()`
- `java.util.Date getDateAttributeValue (java.lang.String name)`
- `java.lang.Object getDefaultValue (java.lang.String attributeName)`
- `java.lang.String getDescription (java.lang.String attributeName)`
- `java.lang.String getDescriptionAttribute ()`
- `java.util.List<java.lang.String> getDisplayableEntitlementAttributeNames (java.util.Locale locale)`
- `java.lang.String getDisplayAttribute ()`
- `java.util.List<java.lang.String> getEntitlementAttributeNames ()`
- `java.util.List<AttributeDefinition> getEntitlementAttributes ()`
- `java.util.List<Application.Feature> getFeatures ()`
- `java.lang.String getFeaturesString ()`
- `java.lang.String getGroupAttribute ()`
- `java.lang.String getGroupAttribute (java.lang.String objectType)`
- `java.util.List<java.lang.String> getGroupAttributes ()`
- `java.lang.String getHierarchyAttribute ()`
- `java.lang.String getIdentityAttribute ()`
- `boolean getIncludePermissions ()`
- `java.lang.String getInstanceAttribute ()`
- `int getIntAttributeValue (java.lang.String name)`
- `java.util.Map<java.lang.String,​AttributeDefinition> getInternalAttributeMap ()`
- `java.util.List getListAttributeValue (java.lang.String name)`
- `java.lang.Long getLongAttributeValue (java.lang.String name)`
- `java.util.List<java.lang.String> getMinableAttributeNames ()`
- `java.lang.String getNativeObjectType ()`
- `java.lang.String getObjectType ()`
- `AttributeDefinition.UserInterfaceInputType getPermissionsRemediationModificationType ()`
- `Rule getRefreshRule ()`
- `java.lang.String getStringAttributeValue (java.lang.String name)`
- `boolean hasDirectPermissions ()`
- `int hashCode ()`
- `boolean hasIndexedAttribute ()`
- `boolean includePermissions ()`
- `void initCorrelationKeys ()`
- `static boolean isAggregationType (java.lang.String type)`
- `boolean isChildHierarchy ()`
- `boolean isGroupAggregation ()`
- `static boolean isGroupAggregation (java.lang.String objectType, java.lang.String aggregationType)`
- `boolean isIndexPermissions ()`
- `boolean isMultiValued (java.lang.String attributeName)`
- `boolean isNameUnique ()`
- `boolean isNoPermissionPromotion ()`
- `boolean isPermissionRemediationModifiable ()`
- `boolean isRequired (java.lang.String attributeName)`
- `void removeAttribute (java.lang.String name)`
- `boolean removeFeature ( Application.Feature feature)`
- `void setAggregationType (java.lang.String type)`
- `void setAssociationSchemaName (java.lang.String s)`
- `void setAttributes (java.util.List< AttributeDefinition > attributes)`
- `void setChildHierarchy (boolean b)`
- `void setCloudAccessType ( AttributeDefinition.CloudAccessManagementType type)`
- `void setConfig ( Attributes <java.lang.String,java.lang.Object> _config)`
- `void setCorrelationRule ( Rule _correlationRule)`
- `void setCreationRule ( Rule _creationRule)`
- `void setCustomizationRule ( Rule _customizationRule)`
- `void setDescriptionAttribute (java.lang.String s)`
- `void setDisplayAttribute (java.lang.String attributeName)`
- `void setFeatures (java.util.List< Application.Feature > features)`
- `void setFeaturesString (java.lang.String features)`
- `void setGroupAttribute (java.lang.String s)`
- `void setGroupAttribute (java.lang.String attrName, java.lang.String objectType)`
- `void setHierarchyAttribute (java.lang.String s)`
- `void setIdentityAttribute (java.lang.String attributeName)`
- `void setIncludePermissions (boolean includePermissions)`
- `void setIndexPermissions (boolean b)`
- `void setInstanceAttribute (java.lang.String attributeName)`
- `void setNativeObjectType (java.lang.String nativeType)`
- `void setNoPermissionPromotion (boolean b)`
- `void setObjectType (java.lang.String objectType)`
- `void setPermissionsRemediationModificationType ( AttributeDefinition.UserInterfaceInputType type)`
- `void setRefreshRule ( Rule r)`
- `boolean supportsFeature ( Application.Feature feature)`

---

## Scope

**Package:** `sailpoint.object`

**Description:** A Scope is a container within the system that in which any SailPointObject can live (via an assigned scope). This is used to scope access to objects so that on a user that controls a scope can see the objects in that scope.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Scope`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `void addScope ( Scope scope)`
- `java.util.List<Scope> getChildScopes ()`
- `java.lang.String getDisplayableName ()`
- `java.lang.String getDisplayablePath ()`
- `java.lang.String getDisplayName ()`
- `Scope getParent ()`
- `java.lang.String getPath ()`
- `java.lang.String[] getUniqueKeyProperties ()`
- `boolean isDenormalizationPending ()`
- `boolean isDormant ()`
- `boolean isManuallyCreated ()`
- `boolean isNameUnique ()`
- `boolean isXmlDirty ()`
- `void removeScope ( Scope scope)`
- `void setChildScopes (java.util.List< Scope > childScopes)`
- `void setDenormalizationPending (boolean b)`
- `void setDisplayName (java.lang.String displayName)`
- `void setDormant (boolean dormant)`
- `void setManuallyCreated (boolean manuallyCreated)`
- `void setPath (java.lang.String path)`
- `void setXmlDirty (boolean b)`
- `void updateSubtreePaths ()`
- `void visit ( Visitor v)`

---

## ScoreBandConfig

**Package:** `sailpoint.object`

**Description:** Defines a band range within a ScoreConfig.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ScoreBandConfig`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.util.List<java.lang.String> LIGHT_COLORS`

**Methods:**
- `java.lang.String getColor ()`
- `java.lang.String getLabel ()`
- `int getLowerBound ()`
- `java.lang.String getTextColor ()`
- `int getUpperBound ()`
- `void setColor (java.lang.String c)`
- `void setLabel (java.lang.String d)`
- `void setLowerBound (int i)`
- `void setTextColor (java.lang.String c)`
- `void setUpperBound (int i)`
- `java.lang.String toString ()`

---

## ScoreConfig

**Package:** `sailpoint.object`

**Description:** A class holding global configurations for scoring. There is only one of these, referenced through a constant name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.ScoreConfig`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String OBJ_NAME`
- `static java.lang.String SCORE_CERT`
- `static java.lang.String SCORE_COMPOSITE`
- `static java.lang.String SCORE_ENTITLEMENT`
- `static java.lang.String SCORE_POLICY`
- `static java.lang.String SCORE_RAW_ENTITLEMENT`
- `static java.lang.String SCORE_RAW_POLICY`
- `static java.lang.String SCORE_RAW_ROLE`
- `static java.lang.String SCORE_ROLE`

**Methods:**
- `void addApplicationScore ( ScoreDefinition d)`
- `void addIdentityScore ( ScoreDefinition d)`
- `ApplicationConfig getApplicationConfig ( Application a, ScoreDefinition scoreDef)`
- `java.util.List<ApplicationConfig> getApplicationConfigs ()`
- `ScoreDefinition getApplicationScore (java.lang.String name)`
- `java.util.List<ScoreDefinition> getApplicationScores ()`
- `java.util.List<ScoreBandConfig> getBands ()`
- `Attributes<java.lang.String,​java.lang.Object> getEffectiveArguments ( ScoreDefinition def)`
- `void getEffectiveArguments ( ScoreDefinition def, Attributes <java.lang.String,java.lang.Object> effective)`
- `ScoreDefinition getIdentityScore (java.lang.String name)`
- `java.util.List<ScoreDefinition> getIdentityScores ()`
- `int getMaximumNumberOfBands ()`
- `int getMaximumScore ()`
- `int getNumberOfBands ()`
- `RightConfig getRightConfig ()`
- `void load ()`
- `void removeApplicationScore (java.lang.String name)`
- `void removeIdentityScore (java.lang.String name)`
- `void setApplicationConfigs (java.util.List< ApplicationConfig > configs)`
- `void setApplicationScores (java.util.List< ScoreDefinition > scores)`
- `void setBands (java.util.List< ScoreBandConfig > bands)`
- `void setIdentityScores (java.util.List< ScoreDefinition > scores)`
- `void setMaximumNumberOfBands (int maximumNumberOfBands)`
- `void setMaximumScore (int maximumScore)`
- `void setRightConfig ( RightConfig rc)`

---

## ScoreDefinition

**Package:** `sailpoint.object`

**Description:** The definition of one scoring algorithm. These were designed a SailPointObject subclasses, but they are only stored as XML within the ScoreConfig.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.ScoreDefinition`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ARG_COMPENSATED`
- `static int DEFAULT_RANGE`

**Methods:**
- `java.lang.Object getArgument (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getArguments ()`
- `boolean getBoolean (java.lang.String name)`
- `java.lang.String getConfigPage ()`
- `java.lang.String getDescription ()`
- `java.lang.String getDisplayableName ()`
- `java.lang.String getDisplayName ()`
- `float getFloat (java.lang.String name)`
- `int getInt (java.lang.String name)`
- `java.lang.String getParent ()`
- `int getRange ()`
- `staticScoreDefinition getScore (java.util.List< ScoreDefinition > scores, java.lang.String name)`
- `java.lang.String getScorer ()`
- `Scorer getScorerInstance ()`
- `java.lang.String getShortName ()`
- `Signature getSignature ()`
- `java.lang.String getString (java.lang.String name)`
- `java.lang.String getType ()`
- `int getWeight ()`
- `boolean isCompensated ()`
- `boolean isComponent ()`
- `boolean isComposite ()`
- `void setArgument (java.lang.String name, java.lang.Object value)`
- `void setArguments ( Attributes <java.lang.String,java.lang.Object> args)`
- `void setComponent (boolean b)`
- `void setComposite (boolean b)`
- `void setConfigPage (java.lang.String configPage)`
- `void setDescription (java.lang.String d)`
- `void setDisplayName (java.lang.String displayName)`
- `void setParent (java.lang.String s)`
- `void setRange (int i)`
- `void setScorer (java.lang.Class cls)`
- `void setScorer (java.lang.String s)`
- `void setScorer ( Scorer s)`
- `void setShortName (java.lang.String s)`
- `void setSignature ( Signature s)`
- `void setType (java.lang.String t)`
- `void setWeight (int i)`

---

## ScoreItem

**Package:** `sailpoint.object`

**Description:** A class holding information about one contributing factor to a risk score. These can be generated as a side effect of scoring, and displayed so that the viewer is given some indication of what they can do to lower the score.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ScoreItem`
- `java.io.Serializable`
- `sailpoint.tools.xml.IXmlEqualable<ScoreItem>`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `boolean contentEquals ( ScoreItem other)`
- `int getCompositePercentage ()`
- `java.lang.String getDisplayName ()`
- `int getScore ()`
- `int getScorePercentage ()`
- `Message getSuggestionMessage ()`
- `Message getTargetMessage ()`
- `java.lang.String getType ()`
- `boolean isRelated ( ScoreDefinition def)`
- `void setCompositePercentage (int i)`
- `void setDisplayName (java.lang.String s)`
- `void setScore (int i)`
- `void setScorePercentage (int i)`
- `void setSuggestionMessage ( Message suggestionMessage)`
- `void setTargetMessage ( Message targetMessage)`
- `void setType (java.lang.String s)`

---

## Scorecard

**Package:** `sailpoint.object`

**Description:** A class holding scores and statistics for one Identity.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.GenericIndex`
- `sailpoint.object.BaseIdentityIndex`
- `sailpoint.object.Scorecard`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `Identity getIdentity ()`
- `void setIdentity ( Identity id)`
- `void visit ( Visitor v)`

---

## Scorer

**Package:** `sailpoint.object`

**Description:** The interface of a class that provides scoring services.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `void finish ( SailPointContext context, ScoreConfig config, ScoreDefinition def, GenericIndex index)`
- `int getScore ( ScoreDefinition def, GenericIndex card)`
- `ScoreItem isMatch ( SailPointObject obj)`
- `void prepare ( SailPointContext context, ScoreConfig config, ScoreDefinition def, GenericIndex index)`
- `void score ( SailPointContext context, ScoreConfig config, ScoreDefinition def, SailPointObject src, GenericIndex card)`
- `void update ( SailPointContext context, ScoreConfig scoreConfig)`

---

## Script

**Package:** `sailpoint.object`

**Description:** An embedded script. These are similar to Rules but they do not have database identity. They are embedded in other objects that need a fragment of logic but do not need the overhead of a Rule.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Script`

**Attributes:**
- `static java.lang.String ARG_NO_COMPILATION_CACHE`
- `static java.lang.String LANG_BEANSHELL`
- `static java.lang.String LANG_JAVA`
- `static java.lang.String LANG_JAVASCRIPT`

**Methods:**
- `java.lang.ThreadLocal<java.lang.Object> getCompilation ()`
- `java.util.List<Rule> getIncludes ()`
- `java.lang.String getLanguage ()`
- `java.lang.String getSource ()`
- `void setCompilation (java.lang.ThreadLocal<java.lang.Object> o)`
- `void setIncludes (java.util.List< Rule > rules)`
- `void setLanguage (java.lang.String language)`
- `void setSource (java.lang.String source)`

---

## Scriptlet

**Package:** `sailpoint.object`

**Description:** This define a transient object used to parse scriptlets. It is not persisted, the workflow/forms engines will build these at runtime when they need to evaluate a scriptlet. Most classes allow either a scriptlet represented as an XML attribute and a Script represented as an element. The Script element is normally used of you have complex multi-line scripts, the attribute if you have simple boolean expressions. You are not supposed to have both. If a class does have values for both the Script is preferred.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Scriptlet`
- `java.io.Serializable`

**Attributes:**
- `static java.lang.String METHOD_CALL`
- `static java.lang.String METHOD_REF`
- `static java.lang.String METHOD_RULE`
- `static java.lang.String METHOD_SCRIPT`
- `static java.lang.String METHOD_STRING`

**Methods:**
- `java.lang.String getCall ()`
- `java.lang.String getReference ()`
- `java.lang.String getRule ()`
- `Script getScript ()`
- `java.lang.String getString ()`
- `boolean isEmpty ()`
- `boolean isLiteral ()`
- `boolean isNot ()`
- `java.lang.Object toValue ()`

---

## SearchInputDefinition.InputType

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `SearchInputDefinition.InputType`
- `sailpoint.object.SearchInputDefinition.InputType`
- `java.io.Serializable`
- `java.lang.Comparable<SearchInputDefinition.InputType>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticSearchInputDefinition.InputType valueOf (java.lang.String name)`
- `staticSearchInputDefinition.InputType[] values ()`

---

## SearchInputDefinition.PropertyType

**Package:** `sailpoint.object`

**Description:** Convenience method to try to map this property type to a real class.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `SearchInputDefinition.PropertyType`
- `sailpoint.object.SearchInputDefinition.PropertyType`
- `java.io.Serializable`
- `java.lang.Comparable<SearchInputDefinition.PropertyType>`

**Attributes:** N/A

**Methods:**
- `java.lang.Class getTypeClazz ()`
- `staticSearchInputDefinition.PropertyType valueOf (java.lang.String name)`
- `staticSearchInputDefinition.PropertyType[] values ()`

---

## SearchItem.Type

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `SearchItem.Type`
- `sailpoint.object.SearchItem.Type`
- `java.io.Serializable`
- `java.lang.Comparable<SearchItem.Type>`

**Attributes:** N/A

**Methods:**
- `staticSearchItem.Type valueOf (java.lang.String name)`
- `staticSearchItem.Type[] values ()`

---

## SelfCertificationException

**Package:** `sailpoint.object`

**Description:** Exception thrown when an action occurs that would cause a user to certify themselves.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `java.lang.Throwable`
- `java.lang.Exception`
- `sailpoint.tools.AbstractLocalizableException`
- `sailpoint.tools.GeneralException`
- `sailpoint.object.SelfCertificationException`
- `java.io.Serializable`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:**
- `Identity getSelfCertifier ()`

---

## Server

**Package:** `sailpoint.object`

**Description:** Class used represent an instance of the IdentityIQ server. One of these will be created automatically as servers are started, once created they will be left in place and can be used to store server-specific configuration.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Server`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ARG_MAX_REQUEST_THREADS`
- `static java.lang.String ATT_APP_STATUS`
- `static java.lang.String ATT_APP_STATUS_DATE`
- `static java.lang.String ATT_APP_STATUS_ERROR`
- `static java.lang.String ATT_APPLICATION_STATUS`
- `static java.lang.String ATT_CPU_USAGE`
- `static java.lang.String ATT_DATABASE_RESPONSE_TIME`
- `static java.lang.String ATT_EXCL_SERVICES`
- `static java.lang.String ATT_INCL_SERVICES`
- `static java.lang.String ATT_LAST_STATS_UPDATE`
- `static java.lang.String ATT_MEMORY_USAGE`
- `static java.lang.String ATT_MEMORY_USAGE_PERCENTAGE`
- `static java.lang.String ATT_MOD_STATUS`
- `static java.lang.String ATT_MOD_STATUS_DATE`
- `static java.lang.String ATT_MOD_STATUS_ERROR`
- `static java.lang.String ATT_MODULE_STATUS`
- `static java.lang.String ATT_MONITORING_CFG`
- `static java.lang.String ATT_MONITORING_CFG_APPS`
- `static java.lang.String ATT_MONITORING_CFG_MODULES`
- `static java.lang.String ATT_MONITORING_CFG_POLL_INTERVAL`
- `static java.lang.String ATT_MONITORING_CFG_RETENTION`
- `static java.lang.String ATT_MONITORING_CFG_STATS`
- `static java.lang.String ATT_OPEN_FILE_COUNT`
- `static java.lang.String ATT_REQUEST_SERVICE_STARTED`
- `static java.lang.String ATT_REQUEST_THREADS`
- `static java.lang.String ATT_TASK_THREADS`
- `static java.util.List<java.lang.String> EXPORTABLE_ATTRIBUTES`

**Methods:**
- `java.lang.Object get (java.lang.String name)`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `boolean getBoolean (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getExtendedAttributes ()`
- `java.util.Date getHeartbeat ()`
- `int getInt (java.lang.String name)`
- `java.util.List getList (java.lang.String name)`
- `staticObjectConfig getObjectConfig ()`
- `java.lang.String getString (java.lang.String name)`
- `boolean hasAssignedScope ()`
- `boolean isInactive ()`
- `void put (java.lang.String name, int value)`
- `void put (java.lang.String name, java.lang.Object value)`
- `void remove (java.lang.String name)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> a)`
- `void setHeartbeat (java.util.Date d)`
- `void setInactive (boolean b)`
- `void visit ( Visitor v)`

---

## ServerStatistic

**Package:** `sailpoint.object`

**Description:** Let the ScopeService know this class does not have a scope.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.ServerStatistic`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `Attributes getAttributes ()`
- `Server getHost ()`
- `MonitoringStatistic getMonitoringStatistic ()`
- `java.lang.String getSnapshotName ()`
- `java.lang.String getTarget ()`
- `java.lang.String getTargetType ()`
- `java.lang.String getValue ()`
- `java.lang.String getValueType ()`
- `boolean hasAssignedScope ()`
- `boolean isNameUnique ()`
- `void setAttributes ( Attributes attributes)`
- `void setHost ( Server host)`
- `void setMonitoringStatistic ( MonitoringStatistic stat)`
- `void setSnapshotName (java.lang.String snapshotName)`
- `void setTarget (java.lang.String target)`
- `void setTargetType (java.lang.String targetType)`
- `void setValue (java.lang.String value)`
- `void setValueType (java.lang.String valueType)`

---

## ServiceDefinition.ServiceType

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ServiceDefinition.ServiceType`
- `sailpoint.object.ServiceDefinition.ServiceType`
- `java.io.Serializable`
- `java.lang.Comparable<ServiceDefinition.ServiceType>`

**Attributes:** N/A

**Methods:**
- `staticServiceDefinition.ServiceType valueOf (java.lang.String name)`
- `staticServiceDefinition.ServiceType[] values ()`

---

## ServiceDefinition

**Package:** `sailpoint.object`

**Description:** The plugin name argument.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.ServiceDefinition`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ARG_PLUGIN_NAME`
- `static java.lang.String HOST_GLOBAL`
- `static java.lang.String REQUIRED_SERVICE_FLAG`
- `static java.lang.String STARTUP_TIMEOUT_MILLIS`

**Methods:**
- `void addHosts (java.lang.String hosts)`
- `java.lang.Object get (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `boolean getBoolean (java.lang.String name)`
- `java.lang.String getExecutor ()`
- `java.lang.String getHosts ()`
- `int getInt (java.lang.String name)`
- `int getInterval ()`
- `java.lang.String getLock ()`
- `long getLong (java.lang.String name)`
- `ServiceDefinition.ServiceType getServiceType ()`
- `java.lang.String getString (java.lang.String name)`
- `boolean hasAssignedScope ()`
- `boolean isConsole ()`
- `boolean isHostAllowed (java.lang.String hostName)`
- `boolean isThisHostAllowed ()`
- `void put (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> a)`
- `void setConsole (boolean b)`
- `void setExecutor (java.lang.String s)`
- `void setHosts (java.lang.String s)`
- `void setInterval (int i)`
- `void setLock (java.lang.String lock)`
- `void setServiceType ( ServiceDefinition.ServiceType serviceType)`
- `void visit ( Visitor v)`

---

## ServiceLock

**Package:** `sailpoint.object`

**Description:** Let the ScopeService know this class does not have a scope.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.ServiceLock`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.String getHost ()`
- `java.util.Date getLastExecute ()`
- `java.util.Date getLastStart ()`
- `java.lang.String getLocker ()`
- `ServiceDefinition getServiceDefinition ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `void setHost (java.lang.String host)`
- `void setLastExecute (java.util.Date lastExecute)`
- `void setLastStart (java.util.Date lastStart)`
- `void setLocker (java.lang.String locker)`
- `void setServiceDefinition ( ServiceDefinition serviceDefinition)`

---

## ServiceStatus

**Package:** `sailpoint.object`

**Description:** A few SailPointObjects do not have assigned scopes.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.ServiceStatus`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `ServiceDefinition getDefinition ()`
- `java.lang.String getHost ()`
- `java.util.Date getLastEnd ()`
- `java.util.Date getLastStart ()`
- `boolean hasAssignedScope ()`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> a)`
- `void setDefinition ( ServiceDefinition def)`
- `void setHost (java.lang.String s)`
- `void setLastEnd (java.util.Date d)`
- `void setLastStart (java.util.Date d)`

---

## SharePointSiteConfig

**Package:** `sailpoint.object`

**Description:** Configuration object that is used to drive unstructured collection from SharePoint site collections. A SharePoint target collector config contains a list of these objects. It encapsulates the information necessary to traverse through a tree of sites in a sharepoint environment.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.SharePointSiteConfig`
- `java.lang.Cloneable`

**Attributes:** N/A

**Methods:**
- `java.lang.Object clone ()`
- `java.lang.String getFilterType ()`
- `boolean getIncludeInheritedListPermissions ()`
- `java.lang.String getListInclusionFilter ()`
- `java.lang.String getPassword ()`
- `java.lang.String getSiteCollectionUrl ()`
- `java.lang.String getSiteInclusionFilter ()`
- `java.lang.String getTargetTypesFilter ()`
- `java.lang.String getUser ()`
- `void setFilterType (java.lang.String filterType)`
- `void setIncludeInheritedListPermissions (boolean inherited)`
- `void setListInclusionFilter (java.lang.String listInclusionFilter)`
- `void setPassword (java.lang.String password)`
- `void setSiteCollectionUrl (java.lang.String site)`
- `void setSiteInclusionFilter (java.lang.String siteInclusionFilter)`
- `void setTargetTypesFilter (java.lang.String targetTypesFilter)`
- `void setUser (java.lang.String user)`

---

## SignOffHistory

**Package:** `sailpoint.object`

**Description:** This is the object to store SailPointObject signoffs. This was previously used strictly for Certification signoffs, but has now been extended to include all SailPointObject signoffs. If a signoff includes text/application/account, this signoff is considered to be an "electronic signature" signoff. This means that a user had to successfully provide login credentials in order to signoff.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.SignOffHistory`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `boolean equals (java.lang.Object o)`
- `java.lang.String getAccount ()`
- `java.lang.String getApplication ()`
- `java.util.Date getDate ()`
- `Identity getSigner ( Resolver resolver)`
- `java.lang.String getSignerDisplayableName ()`
- `java.lang.String getSignerDisplayName ()`
- `java.lang.String getSignerId ()`
- `java.lang.String getSignerName ()`
- `java.lang.String getText ()`
- `int hashCode ()`
- `boolean hasName ()`
- `boolean isElectronicSign ()`
- `void setAccount (java.lang.String s)`
- `void setApplication (java.lang.String s)`
- `void setElectronicSign (boolean eSigned)`
- `void setSignerDisplayName (java.lang.String signerDisplayName)`
- `void setSignerId (java.lang.String signerId)`
- `void setSignerName (java.lang.String signerName)`
- `void setText (java.lang.String s)`

---

## Signature

**Package:** `sailpoint.object`

**Description:** Performance experiment to fully load the Rule so the cache can be cleared.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Signature`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `boolean equals (java.lang.Object obj)`
- `java.util.List<Argument> getArguments ()`
- `java.lang.String getDescription ()`
- `java.lang.String getName ()`
- `java.util.List<Argument> getReturns ()`
- `java.lang.String getReturnType ()`
- `boolean hasArgument (java.lang.String name)`
- `boolean isEmpty ()`
- `void load ()`
- `boolean removeArgument (java.lang.String name)`
- `void setArguments (java.util.List< Argument > args)`
- `void setDescription (java.lang.String s)`
- `void setName (java.lang.String s)`
- `void setReturns (java.util.List< Argument > args)`
- `void setReturnType (java.lang.String s)`

---

## Signoff.Signatory

**Package:** `sailpoint.object`

**Description:** Inner class to represent the signoff of a particular user.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Signoff.Signatory`

**Attributes:** N/A

**Methods:**
- `java.lang.String getComments ()`
- `java.util.Date getDate ()`
- `java.lang.String getDisplayName ()`
- `java.lang.String getName ()`
- `java.lang.String getWorkItemId ()`
- `boolean isApproved ()`
- `boolean isPending ()`
- `boolean isRejected ()`
- `void setApproved (boolean b)`
- `void setComments (java.lang.String s)`
- `void setDate (java.util.Date d)`
- `void setDisplayName (java.lang.String s)`
- `void setName (java.lang.String s)`
- `void setOwner ( Identity owner)`
- `void setWorkItemId (java.lang.String s)`

---

## Signoff

**Package:** `sailpoint.object`

**Description:** Inner class to represent the signoff of a particular user.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Signoff`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void add ( Signoff.Signatory sig)`
- `Signoff.Signatory add ( WorkItem item)`
- `Signoff.Signatory find (java.lang.String name)`
- `Signoff.Signatory find ( WorkItem item)`
- `Signoff.Signatory finish ( WorkItem item)`
- `int getPendingSignoffs ()`
- `java.util.List<Signoff.Signatory> getSignatories ()`
- `void setSignatories (java.util.List< Signoff.Signatory > sigs)`

---

## SimpleXMLReferenceResolver

**Package:** `sailpoint.object`

**Description:** A class that will return very basic objects with just the name and ID fields populated for any reference objects.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.SimpleXMLReferenceResolver`
- `sailpoint.tools.xml.XMLReferenceResolver`

**Attributes:** N/A

**Methods:**
- `java.lang.Object getReferencedObject (java.lang.String className, java.lang.String id, java.lang.String name)`

---

## Snapshot

**Package:** `sailpoint.object`

**Description:** Snapshot of a the basic details of a SailPoint object.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Snapshot`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void addAttribute (java.lang.String attribute, java.lang.Object value)`
- `java.util.List<java.lang.String> getAttributeKeys ()`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.util.List<java.lang.String> getDisplayableAttributeKeys ()`
- `java.lang.String getObjectDescription ()`
- `java.lang.String getObjectDescription (java.util.Locale locale)`
- `java.util.Map<java.lang.String,​java.lang.String> getObjectDescriptions ()`
- `java.lang.String getObjectDisplayableName ()`
- `java.lang.String getObjectId ()`
- `java.lang.String getObjectName ()`
- `boolean hasAttribute (java.lang.String attribute)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attributes)`
- `void setObjectDescription (java.lang.String objectDescription)`
- `void setObjectDescriptions (java.util.Map<java.lang.String,java.lang.String> val)`
- `void setObjectDisplayableName (java.lang.String objectDisplayableName)`
- `void setObjectId (java.lang.String objectId)`
- `void setObjectName (java.lang.String objectName)`

---

## Sort

**Package:** `sailpoint.object`

**Description:** Compare two Sort objects to see if they are the same.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Sort`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getField ()`
- `boolean isAscending ()`
- `boolean isSame ( Sort sort)`
- `void setAscending (boolean ascending)`
- `void setField (java.lang.String field)`

---

## Source

**Package:** `sailpoint.object`

**Description:** Constant definitions for "sources", used in several places in the model to record the origin of something.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Source`
- `sailpoint.object.Source`
- `java.io.Serializable`
- `java.lang.Comparable<Source>`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:**
- `staticSource fromString (java.lang.String str)`
- `java.lang.String getLocalizedMessage ()`
- `java.lang.String getLocalizedMessage (java.util.Locale locale, java.util.TimeZone timezone)`
- `staticSource valueOf (java.lang.String name)`
- `staticSource[] values ()`

---

## SyslogEvent

**Package:** `sailpoint.object`

**Description:** The SyslogEvent contains information about a serious error that occurred somewhere in IdentityIQ.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.SyslogEvent`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.String getClassname ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `java.lang.String getEventLevel ()`
- `java.lang.String getLineNumber ()`
- `java.lang.String getMessage ()`
- `java.lang.String getQuickKey ()`
- `java.lang.String getServer ()`
- `java.lang.String getStacktrace ()`
- `java.lang.String getThread ()`
- `java.lang.String getUsername ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `void setClassname (java.lang.String classname)`
- `void setEventLevel (java.lang.String eventLevel)`
- `void setLineNumber (java.lang.String lineNumber)`
- `void setMessage (java.lang.String message)`
- `void setQuickKey (java.lang.String quickKey)`
- `void setServer (java.lang.String server)`
- `void setStacktrace (java.lang.String stacktrace)`
- `void setThread (java.lang.String thread)`
- `void setUsername (java.lang.String username)`

---

## TableColumnPreference

**Package:** `sailpoint.object`

**Description:** XML data holder for users table column preference data. Users UIPreferences will contain a map of these keyed by a table identifier. We keep track of the unselected columns to do lazy column upgrades.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.TableColumnPreference`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.util.List<sailpoint.service.TableColumnDTO> getOrderedColumns ()`
- `java.util.List<java.lang.String> getSelectedColumns ()`
- `java.util.List<java.lang.String> getUnSelectedColumns ()`
- `void setOrderedColumns (java.util.List<sailpoint.service.TableColumnDTO> orderedColumns)`
- `void setSelectedColumns (java.util.List<java.lang.String> selectedColumns)`
- `void setUnSelectedColumns (java.util.List<java.lang.String> unSelectedColumns)`

---

## Tag

**Package:** `sailpoint.object`

**Description:** A tag is simply a name that you can associate with objects in the system. One or more tags are usually set on an object, which can later be used for displaying and searching. Think tagging a blog post.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Tag`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `void visit ( Visitor visitor)`

---

## Target

**Package:** `sailpoint.object`

**Description:** Set the unique hash on this Target.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Target`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `void addAccountAccess ( AccessMapping mapping)`
- `void addGroupAccess ( AccessMapping mapping)`
- `void assignUniqueHash ()`
- `static java.lang.String createUniqueHash (java.lang.String s)`
- `static java.lang.String createUniqueName (java.lang.String name, java.lang.String fullPath, java.lang.String targetHost)`
- `java.util.List<AccessMapping> getAccountAccess ()`
- `Application getApplication ()`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getDisplayableName ()`
- `java.lang.String getDisplayName ()`
- `Attributes<java.lang.String,​java.lang.Object> getExtendedAttributes ()`
- `java.lang.String getFullPath ()`
- `java.util.List<AccessMapping> getGroupAccess ()`
- `java.util.Date getLastAggregation ()`
- `java.lang.String getNativeObjectId ()`
- `java.lang.String getNativeOwnerId ()`
- `staticObjectConfig getObjectConfig ()`
- `Target getParent ()`
- `java.lang.String getTargetHost ()`
- `long getTargetSize ()`
- `TargetSource getTargetSource ()`
- `java.lang.String getUniqueName ()`
- `java.lang.String getUniqueNameHash ()`
- `boolean isNameUnique ()`
- `void setAccountAccess (java.util.List< AccessMapping > mapping)`
- `void setApplication ( Application app)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> atts)`
- `void setDisplayName (java.lang.String displayName)`
- `void setFullPath (java.lang.String path)`
- `void setFullPathHash (java.lang.String hash)`
- `void setGroupAccess (java.util.List< AccessMapping > mapping)`
- `void setLastAggregation (java.util.Date _lastAggregation)`
- `void setNativeObjectId (java.lang.String id)`
- `void setNativeOwnerId (java.lang.String owner)`
- `void setParent ( Target targ)`
- `void setTargetHost (java.lang.String targetHost)`
- `void setTargetSize (long size)`
- `void setTargetSource ( TargetSource targetSource)`
- `void setUniqueNameHash (java.lang.String hash)`
- `void visit ( Visitor v)`

---

## TargetAssociation.OwnerType

**Package:** `sailpoint.object`

**Description:** Value for _type (referencing object type)

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `TargetAssociation.OwnerType`
- `sailpoint.object.TargetAssociation.OwnerType`
- `java.io.Serializable`
- `java.lang.Comparable<TargetAssociation.OwnerType>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getType ()`
- `staticTargetAssociation.OwnerType valueOf (java.lang.String name)`
- `staticTargetAssociation.OwnerType[] values ()`

---

## TargetAssociation.TargetType

**Package:** `sailpoint.object`

**Description:** Values for targetType to denote what type of Target referenced

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `TargetAssociation.TargetType`
- `sailpoint.object.TargetAssociation.TargetType`
- `java.io.Serializable`
- `java.lang.Comparable<TargetAssociation.TargetType>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getDisplayName ()`
- `java.lang.String getDisplayName (java.util.Locale loc, java.util.TimeZone tz)`
- `staticTargetAssociation.TargetType valueOf (java.lang.String name)`
- `staticTargetAssociation.TargetType[] values ()`

---

## TargetAssociation

**Package:** `sailpoint.object`

**Description:** Value for _type (referencing object type)

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.TargetAssociation`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATT_CLASSIFICATIONS`
- `static java.lang.String ATT_IIQ_ELEVATED_ACCESS`

**Methods:**
- `java.lang.String getApplicationName ()`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `int getEffective ()`
- `java.lang.String getEffectiveTargetName ()`
- `java.lang.String getHierarchy ()`
- `java.util.Date getLastAggregation ()`
- `java.lang.String getObjectId ()`
- `java.lang.String getOwnerId ()`
- `java.lang.String getOwnerType ()`
- `java.lang.String getRights ()`
- `Target getTarget ()`
- `java.lang.String getTargetName ()`
- `java.lang.String getTargetType ()`
- `java.lang.String getUniqueTargetName ()`
- `boolean hasName ()`
- `boolean isAccount ()`
- `boolean isAllowPermission ()`
- `boolean isAttribute ()`
- `boolean isDenyPermission ()`
- `boolean isFlattened ()`
- `boolean isIiqElevatedAccess ()`
- `boolean isInherited ()`
- `boolean isPermission ()`
- `boolean isUnstructured ()`
- `void load ()`
- `void setAllowPermission (boolean b)`
- `void setApplicationName (java.lang.String id)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> atts)`
- `void setDenyPermission (boolean _isDeny)`
- `void setEffective (int _effective)`
- `void setFlattened (boolean b)`
- `void setHierarchy (java.lang.String s)`
- `void setIiqElevatedAccess (boolean elevatedAccess)`
- `void setInherited (boolean b)`
- `void setLastAggregation (java.util.Date _lastAggregation)`
- `void setObjectId (java.lang.String id)`
- `void setOwnerId (java.lang.String id)`
- `void setOwnerType (java.lang.String type)`
- `void setRights (java.lang.String rights)`
- `void setTarget ( Target target)`
- `void setTargetName (java.lang.String rights)`
- `void setTargetType (java.lang.String type)`

---

## TargetHostConfig

**Package:** `sailpoint.object`

**Description:** Created by ryan.pickens on 9/11/15.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.TargetHostConfig`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getHostId ()`
- `java.lang.String getHostName ()`
- `java.util.List<java.lang.String> getPaths ()`
- `boolean isPathCaseSensitive ()`
- `void setHostId (java.lang.String id)`
- `void setHostName (java.lang.String host)`
- `void setPathCaseSensitive (boolean b)`
- `void setPaths (java.util.List<java.lang.String> paths)`

---

## TargetSource

**Package:** `sailpoint.object`

**Description:** This represents an overridden provisioning action in which a Manual Work Item needs to be created.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.TargetSource`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String AD_ACCOUNT_SEARCH_ATT`
- `static java.lang.String AD_APP`
- `static java.lang.String AD_GROUP_SEARCH_ATT`
- `static java.lang.String APP_TYPE`
- `static java.lang.String ARG_MANUAL_WORK_ITEM`
- `static java.lang.String ATT_HIERARCHY`
- `static java.lang.String ATT_PROVISIONING_DISABLED`
- `static java.lang.String ATT_PROVISIONING_OVERRIDDEN`
- `static java.lang.String ATT_SEARCH_ACCOUNT`
- `static java.lang.String ATT_SEARCH_GROUP`
- `static java.lang.String ATT_TARGET_COLLECTOR`
- `static java.lang.String ATT_TARGET_HOSTS`
- `static java.lang.String SHAREPOINT_COLLECTOR`
- `static java.lang.String SHAREPOINT_NEW_VER`
- `static java.lang.String SHAREPOINT_VERSION`
- `static java.lang.String TARGET_TYPE`
- `static java.lang.String WINLOCAL_COLLECTOR`

**Methods:**
- `void addTarget (java.lang.String target)`
- `java.lang.Object clone ()`
- `java.lang.Object getAttributeValue (java.lang.String name)`
- `java.lang.String getCollector ()`
- `Attributes<java.lang.String,​java.lang.Object> getConfiguration ()`
- `Rule getCorrelationRule ()`
- `Rule getCreationRule ()`
- `java.util.Date getLastRefresh ()`
- `java.lang.String getOverridingAction ()`
- `Rule getRefreshRule ()`
- `java.util.List<java.lang.String> getTargets ()`
- `Rule getTransformationRule ()`
- `boolean isProvisioningOverridden ()`
- `void removeTarget (java.lang.String target)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setCollector (java.lang.String collector)`
- `void setConfiguration ( Attributes <java.lang.String,java.lang.Object> config)`
- `void setCorrelationRule ( Rule rule)`
- `void setCreationRule ( Rule rule)`
- `void setLastRefresh (java.util.Date date)`
- `void setRefreshRule ( Rule r)`
- `void setTargets (java.util.List<java.lang.String> targets)`
- `void setTransformationRule ( Rule rule)`
- `boolean supportsProvisioning ()`
- `void visit ( Visitor v)`

---

## TaskDefinition.ResultAction

**Package:** `sailpoint.object`

**Description:** Specifies how TaskResult objects for previous tasks are handled when launching a new task.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `TaskDefinition.ResultAction`
- `sailpoint.object.TaskDefinition.ResultAction`
- `java.io.Serializable`
- `java.lang.Comparable<TaskDefinition.ResultAction>`

**Attributes:** N/A

**Methods:**
- `staticTaskDefinition.ResultAction valueOf (java.lang.String name)`
- `staticTaskDefinition.ResultAction[] values ()`

---

## TaskDefinition

**Package:** `sailpoint.object`

**Description:** Specifies how TaskResult objects for previous tasks are handled when launching a new task.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.TaskItemDefinition`
- `sailpoint.object.TaskDefinition`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ARG_PLUGIN_NAME`
- `static java.lang.String ARG_RUN_LENGTH_AVERAGE`
- `static java.lang.String ARG_RUN_LENGTH_TOTAL`
- `static java.lang.String ARG_RUNS`
- `static java.lang.String ARG_TASK_SCOPE`
- `static java.util.Comparator<TaskDefinition> EFFECTIV_DEF_COMPARATOR`
- `static java.util.Comparator<TaskDefinition> EFFECTIV_TYPE_COMPARATOR`
- `static java.lang.String TASK_DEFINITION_RESULT_SCOPE`

**Methods:**
- `void addRun (int time)`
- `static void cascadeScopeToObject ( TaskDefinition sourceScoped, SailPointObject targetToScope)`
- `java.lang.String getEffectiveResultRenderer ()`
- `java.lang.String getHost ()`
- `TaskDefinition.ResultAction getResultAction ()`
- `java.lang.String getResultRenderer ()`
- `int getRunLengthAverage ()`
- `int getRunLengthTotal ()`
- `int getRuns ()`
- `WorkItemConfig getSignoffConfig ()`
- `boolean isConcurrent ()`
- `boolean isDeprecated ()`
- `void load ()`
- `void resetRunStatistics ()`
- `void setConcurrent (boolean b)`
- `void setDeprecated (boolean deprecated)`
- `void setHost (java.lang.String s)`
- `void setResultAction ( TaskDefinition.ResultAction a)`
- `void setResultRenderer (java.lang.String s)`
- `void setRunLengthAverage (int i)`
- `void setRunLengthTotal (int i)`
- `void setRuns (int i)`
- `void setSignoffConfig ( WorkItemConfig c)`
- `void visit ( Visitor v)`

---

## TaskEvent

**Package:** `sailpoint.object`

**Description:** Events marked with this phase will be processed once the task is completed.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.TaskEvent`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATTR_EMAIL_RECIP`
- `static java.lang.String PHASE_COMPLETION`
- `static java.lang.String RULE_RETURN_TASK_RESULT`

**Methods:**
- `void addAttribute (java.lang.String name, java.lang.Object value)`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getPhase ()`
- `Rule getRule ()`
- `TaskResult getTaskResult ()`
- `boolean hasName ()`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attributes)`
- `void setPhase (java.lang.String phase)`
- `void setRule ( Rule rule)`
- `void setTaskResult ( TaskResult taskResult)`

---

## TaskExecutor

**Package:** `sailpoint.object`

**Description:** Execute the task.

**Inherited Classes/Interfaces:**
- `BaseExecutor`

**Attributes:** N/A

**Methods:**
- `void execute ( SailPointContext context, TaskSchedule schedule, TaskResult result, Attributes <java.lang.String,java.lang.Object> args)`

---

## TaskItem

**Package:** `sailpoint.object`

**Description:** The name of an attribute in the _attributes map that holds an ElectronicSignature for signed results.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.TaskItem`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.api.MessageAccumulator`
- `sailpoint.api.MessageRepository`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATT_SIGNATURE`

**Methods:**
- `void addAttribute (java.lang.String attr, java.lang.Object val)`
- `void addException (java.lang.Throwable t)`
- `void addInt (java.lang.String name, int value)`
- `void addMessage (java.lang.String message)`
- `void addMessage ( Message message)`
- `void addMessages (java.util.List< Message > messages)`
- `void clear ()`
- `java.lang.Object clone ()`
- `java.lang.Object get (java.lang.String name)`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `boolean getBoolean (java.lang.String name)`
- `java.util.Date getCompleted ()`
- `TaskResult.CompletionStatus getCompletionStatus ()`
- `java.util.Date getDate (java.lang.String name)`
- `long getDuration ()`
- `java.util.List<Message> getErrors ()`
- `java.util.Date getExpiration ()`
- `java.lang.String getHost ()`
- `int getInt (java.lang.String name)`
- `java.util.Date getLaunched ()`
- `java.lang.String getLauncher ()`
- `java.util.List<Message> getMessages ()`
- `java.util.List<Message> getMessagesByType ( Message.Type type)`
- `int getPercentComplete ()`
- `java.lang.String getProgress ()`
- `java.lang.String getStack ()`
- `java.lang.String getString (java.lang.String name)`
- `TaskItemDefinition.Type getType ()`
- `java.util.List<Message> getWarnings ()`
- `boolean hasErrors ()`
- `boolean hasWarnings ()`
- `boolean isComplete ()`
- `boolean isError ()`
- `boolean isLive ()`
- `boolean isSuccess ()`
- `boolean isTerminated ()`
- `boolean isWarning ()`
- `void put (java.lang.String name, java.lang.Object value)`
- `void remove (java.lang.String name)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> atts)`
- `void setAttributes ( TaskItemDefinition def, java.util.Map<java.lang.String,java.lang.Object> args)`
- `void setCompleted (java.util.Date d)`
- `void setCompletionStatus ( TaskResult.CompletionStatus completionStatus)`
- `void setExpiration (java.util.Date d)`
- `void setHost (java.lang.String s)`
- `void setInt (java.lang.String name, int value)`
- `void setLaunched (java.util.Date d)`
- `void setLauncher (java.lang.String s)`
- `void setLive (boolean live)`
- `void setMessages (java.util.List< Message > messages)`
- `void setPercentComplete (int percentComplete)`
- `void setProgress (java.lang.String progress)`
- `void setStack (java.lang.String stack)`
- `void setTerminated (boolean b)`
- `void setType ( TaskItemDefinition.Type type)`

---

## TaskItemDefinition.ProgressMode

**Package:** `sailpoint.object`

**Description:** Specifies how a task updates TaskResults, about the execution progress while running.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `TaskItemDefinition.ProgressMode`
- `sailpoint.object.TaskItemDefinition.ProgressMode`
- `java.io.Serializable`
- `java.lang.Comparable<TaskItemDefinition.ProgressMode>`

**Attributes:** N/A

**Methods:**
- `staticTaskItemDefinition.ProgressMode valueOf (java.lang.String name)`
- `staticTaskItemDefinition.ProgressMode[] values ()`

---

## TaskItemDefinition.Type

**Package:** `sailpoint.object`

**Description:** Types. This includes all of the types from the classes that implement this class.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `TaskItemDefinition.Type`
- `sailpoint.object.TaskItemDefinition.Type`
- `java.io.Serializable`
- `java.lang.Comparable<TaskItemDefinition.Type>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticTaskItemDefinition.Type valueOf (java.lang.String name)`
- `staticTaskItemDefinition.Type[] values ()`

---

## TaskItemDefinition

**Package:** `sailpoint.object`

**Description:** Specifies how a task updates TaskResults, about the execution progress while running.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.TaskItemDefinition`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `protected java.util.List<SPRight> _rights`
- `static java.lang.String ARG_LOSS_LIMIT`
- `static int DEFAULT_LOSS_LIMIT`
- `static java.lang.String TASK_SUB_TYPE_SEARCH`
- `static java.lang.String TASK_TYPE_SEARCH_NAME`

**Methods:**
- `void add ( SPRight right)`
- `boolean containsKey (java.lang.String name)`
- `java.lang.Object getArgument (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getArguments ()`
- `boolean getBoolean (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getEffectiveArguments ()`
- `void getEffectiveArguments ( Attributes <java.lang.String,java.lang.Object> args)`
- `java.lang.String getEffectiveDefinitionName ()`
- `java.lang.String getEffectiveExecutor ()`
- `java.lang.String getEffectiveFormPath ()`
- `int getEffectiveProgressInterval ()`
- `TaskItemDefinition.ProgressMode getEffectiveProgressMode ()`
- `java.util.List<SPRight> getEffectiveRights ()`
- `Signature getEffectiveSignature ()`
- `int getEffectiveStateUpdateInterval ()`
- `Message getEffectiveSubType ()`
- `TaskItemDefinition.Type getEffectiveType ()`
- `java.lang.String getExecutor ()`
- `java.lang.String getFormPath ()`
- `int getInt (java.lang.String name)`
- `TaskItemDefinition getParent ()`
- `TaskItemDefinition getParentRoot ()`
- `int getProgressInterval ()`
- `TaskItemDefinition.ProgressMode getProgressMode ()`
- `boolean getReportsProgress ()`
- `int getResultExpiration ()`
- `java.util.List<SPRight> getRights ()`
- `java.lang.String getRootDefinitionName ()`
- `Signature getSignature ()`
- `java.lang.String getString (java.lang.String name)`
- `java.lang.String getSubType ()`
- `TaskItemDefinition.Type getType ()`
- `boolean hasRight ( SPRight right)`
- `boolean isHidden ()`
- `boolean isTemplate ()`
- `void remove ( SPRight right)`
- `void removeArgument (java.lang.String name)`
- `void setArgument (java.lang.String name, java.lang.Object value)`
- `void setArguments ( Attributes <java.lang.String,java.lang.Object> args)`
- `void setExecutor (java.lang.Class cls)`
- `void setExecutor (java.lang.String s)`
- `void setFormPath (java.lang.String path)`
- `void setHidden (boolean b)`
- `void setParent ( TaskItemDefinition def)`
- `void setProgressInterval (int interval)`
- `void setProgressMode ( TaskItemDefinition.ProgressMode mode)`
- `void setResultExpiration (int i)`
- `void setRights (java.util.List< SPRight > rights)`
- `void setSignature ( Signature s)`
- `void setSubType (java.lang.String type)`
- `void setTemplate (boolean b)`
- `void setType ( TaskItemDefinition.Type type)`

---

## TaskResult.CompletionStatus

**Package:** `sailpoint.object`

**Description:** List of final statuses a task can have.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `TaskResult.CompletionStatus`
- `sailpoint.object.TaskResult.CompletionStatus`
- `java.io.Serializable`
- `java.lang.Comparable<TaskResult.CompletionStatus>`
- `sailpoint.tools.MessageKeyHolder`

**Attributes:** N/A

**Methods:**
- `boolean getIsInvisible ()`
- `java.lang.String getMessageKey ()`
- `boolean isEqual (java.lang.String name)`
- `staticTaskResult.CompletionStatus valueOf (java.lang.String name)`
- `staticTaskResult.CompletionStatus[] values ()`

---

## TaskResult

**Package:** `sailpoint.object`

**Description:** List of final statuses a task can have.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.TaskItem`
- `sailpoint.object.TaskResult`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.api.MessageAccumulator`
- `sailpoint.api.MessageRepository`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ARG_PROFILE`
- `static java.lang.String ATT_CONSOLIDATED_PARTITION_RESULTS`
- `static java.lang.String ATT_HIDDEN_PARTITION`
- `static java.lang.String ATT_PARTITIONS`
- `static java.lang.String ATT_RESTARTABLE`
- `static java.util.Comparator<TaskResult> EFFECTIV_DEF_COMPARATOR`

**Methods:**
- `void assimilateResult ( TaskResult partitionResult)`
- `void assimilateResults (java.util.List< TaskResult > others)`
- `TaskResult.CompletionStatus calculateCompletionStatus ()`
- `boolean canRestart ()`
- `TaskDefinition getDefinition ()`
- `java.lang.String getDefinitionDescription ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `TaskResult getPartitionResult (java.lang.String partitionName)`
- `TaskResult getPartitionResult ( Resolver r, java.lang.String partitionName)`
- `java.util.List<TaskResult> getPartitionResults ()`
- `java.util.List<TaskResult> getPartitionResults ( Resolver r)`
- `int getPendingSignoffs ()`
- `java.lang.Object getProfile ()`
- `JasperResult getReport ()`
- `int getRunLength ()`
- `int getRunLengthAverage ()`
- `int getRunLengthDeviation ()`
- `java.lang.String getSchedule ()`
- `java.lang.String getSequentialMonitorId ()`
- `Signoff getSignoff ()`
- `java.lang.String getTargetClass ()`
- `java.lang.String getTargetId ()`
- `java.lang.String getTargetName ()`
- `TaskSchedule getTaskSchedule ( Resolver r)`
- `java.util.Date getVerified ()`
- `boolean isConsolidatedPartitionResults ()`
- `boolean isPartitioned ()`
- `boolean isRestartable ()`
- `boolean isTerminateRequested ()`
- `boolean isTransferred ()`
- `void merge ( TaskResult taskResult)`
- `TaskResult mergePartitionResults ()`
- `TaskResult mergePartitionResults ( Resolver r)`
- `sailpoint.api.Meter.MeterSet mergeTaskMeters ()`
- `void replacePartitionResult (java.lang.String partitionName, TaskResult newResult)`
- `void setConsolidatedPartitionResults (boolean b)`
- `void setDefinition ( TaskDefinition def)`
- `void setPartitioned (boolean b)`
- `void setPendingSignoffs (int i)`
- `void setProfile (java.lang.Object o)`
- `void setReport ( JasperResult r)`
- `void setRestartable (boolean b)`
- `void setRunLength (int i)`
- `void setRunLengthAverage (int i)`
- `void setRunLengthDeviation (int i)`
- `void setSchedule (java.lang.String name)`
- `void setSequentialMonitorId (java.lang.String sequentialMonitorId)`
- `void setSignoff ( Signoff s)`
- `void setTargetClass (java.lang.String targetClass)`
- `void setTargetId (java.lang.String targetId)`
- `void setTargetName (java.lang.String targetName)`
- `void setTaskSchedule ( TaskSchedule sched)`
- `void setTerminateRequested (boolean terminateRequested)`
- `void setTransferred (boolean b)`
- `void setVerified (java.util.Date verified)`
- `void visit ( Visitor v)`

---

## TaskSchedule.State

**Package:** `sailpoint.object`

**Description:** An enumeration of states the job can be in. Used to both return the current state, and request a new state. In the quartz implementation these have the following meanings: Current State Suspended - no Trigger exists, or Trigger is "paused" Ready - a Trigger exists but the Job is not executing Executing - the Job is currently executing Terminated - used with setNewState to ask that a job stop execution Error - the last attempted execution of this schedule failed when getting launched (not during execution). Requested State Suspended stop the job if possible and prevent the trigger from firing again, in Quartz this means we "pause" the trigger Ready if the Quartz trigger is paused, resume it Executing if the job is not currently executing, execute it as soon as possible, ignoring the trigger Terminated if the job is currently executing, stop it if possible.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `TaskSchedule.State`
- `sailpoint.object.TaskSchedule.State`
- `java.io.Serializable`
- `java.lang.Comparable<TaskSchedule.State>`

**Attributes:** N/A

**Methods:**
- `staticTaskSchedule.State valueOf (java.lang.String name)`
- `staticTaskSchedule.State[] values ()`

---

## TaskSchedule

**Package:** `sailpoint.object`

**Description:** An enumeration of states the job can be in.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.TaskSchedule`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ARG_CERTIFICATION_DEFINITION_ID`
- `static java.lang.String ARG_EXECUTOR`
- `static java.lang.String ARG_HOST`
- `static java.lang.String ARG_LAUNCHER`
- `static java.lang.String ARG_NEXT_ACTUAL_FIRE`
- `static java.lang.String ARG_RESULT_ID`
- `static java.lang.String ARG_RESULT_NAME`
- `static java.lang.String ARG_RESUME_DATE`
- `static java.util.Comparator<TaskSchedule> LATEST_RESULT_COMPARATOR`

**Methods:**
- `void addCronExpression (java.lang.String expression)`
- `java.lang.String getArgument (java.lang.String name)`
- `java.util.Map<java.lang.String,​java.lang.Object> getArguments ()`
- `Scope getAssignedScope ()`
- `java.lang.String getAssignedScopePath ()`
- `java.lang.String getCronExpression (int index)`
- `java.util.List<java.lang.String> getCronExpressions ()`
- `TaskDefinition getDefinition ()`
- `TaskDefinition getDefinition ( Resolver r)`
- `java.lang.String getDefinitionName ()`
- `java.lang.String getDescription ()`
- `java.lang.String getHost ()`
- `java.util.Date getLastExecution ()`
- `java.lang.String getLastLaunchError ()`
- `TaskResult getLatestResult ()`
- `java.lang.String getLatestResultId ()`
- `TaskResult.CompletionStatus getLatestResultStatus ()`
- `java.lang.String getLauncher ()`
- `TaskSchedule.State getNewState ()`
- `java.util.Date getNextActualExecution ()`
- `java.util.Date getNextExecution ()`
- `java.util.List<TaskResult> getResults ( Resolver r)`
- `java.util.Date getResumeDate ()`
- `TaskSchedule.State getState ()`
- `java.lang.String getTaskDefinitionName ( Resolver r)`
- `Scope getTaskScopeArgument ( SailPointContext context)`
- `boolean isDeleteOnFinish ()`
- `void setArgument (java.lang.String name, java.lang.String value)`
- `void setArguments (java.util.Map<java.lang.String,java.lang.Object> args)`
- `void setAssignedScope ( Scope scope)`
- `void setAssignedScopePath (java.lang.String path)`
- `void setCronExpressions (java.util.List<java.lang.String> cronExpressions)`
- `void setDefinitionName (java.lang.String name)`
- `void setDeleteOnFinish (boolean deleteOnFinish)`
- `void setDescription (java.lang.String s)`
- `void setHost (java.lang.String value)`
- `void setLastExecution (java.util.Date d)`
- `void setLastLaunchError (java.lang.String e)`
- `void setLauncher (java.lang.String value)`
- `void setNewState ( TaskSchedule.State s)`
- `void setNextActualExecution (java.util.Date d)`
- `void setNextExecution (java.util.Date d)`
- `void setResumeDate (java.util.Date d)`
- `void setState ( TaskSchedule.State s)`
- `void setTaskDefinition ( TaskDefinition def)`
- `void visit ( Visitor v)`

---

## TaskStatistics.TaskStatistic

**Package:** `sailpoint.object`

**Description:** Note the value is a String object.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.TaskStatistics.TaskStatistic`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getData ()`
- `java.lang.String getName ()`
- `void setData (java.lang.String data)`
- `void setName (java.lang.String name)`

---

## TaskStatistics

**Package:** `sailpoint.object`

**Description:** This object is used to represent advanced task statistics. We could have used a map of maps instead though that makes creating and accessing the data more cumbersome. Typical usage of this object would be in Account Group Aggregation where the application, application schema object type and group details are stored for each application aggregated. Serializing this into XML would look like: <TaskStatistics name="application name"> <TaskStatistics name="schema name"> <TaskStatistic name="task_out_account_group_aggregation_application_object_total" data="45"/> <TaskStatistic name="task_out_account_group_aggregation_application_object_created" data="21"/> </TaskStatistics> </TaskStatistics>

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.TaskStatistics`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getName ()`
- `java.util.List<TaskStatistics.TaskStatistic> getStatistics ()`
- `java.util.List<TaskStatistics> getTaskStatistics ()`
- `void setName (java.lang.String name)`
- `void setStatistics (java.util.List< TaskStatistics.TaskStatistic > statistics)`
- `void setTaskStatistics (java.util.List< TaskStatistics > statistics)`

---

## Template.Usage

**Package:** `sailpoint.object`

**Description:** An enumeration of usage constants for for application templates.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `Template.Usage`
- `sailpoint.object.Template.Usage`
- `java.io.Serializable`
- `java.lang.Comparable<Template.Usage>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticTemplate.Usage valueOf (java.lang.String name)`
- `staticTemplate.Usage[] values ()`

---

## Template

**Package:** `sailpoint.object`

**Description:** An enumeration of usage constants for for application templates.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Template`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String OWNER_APPLICATION`
- `static java.lang.String OWNER_PARENT`
- `static java.lang.String OWNER_ROLE`

**Methods:**
- `static java.util.List<Template> convertForms (java.util.List< Form > forms)`
- `Application getApplication ()`
- `java.lang.String getDescription ()`
- `java.util.List<Field> getFields ()`
- `java.util.List<Field> getFields ( Resolver resolver)`
- `java.util.List<FormItem> getFormItems ()`
- `FormRef getFormRef ()`
- `java.lang.String getName ()`
- `DynamicValue getOwnerDefinition ()`
- `Script getOwnerScript ()`
- `Script getOwnerScriptXml ()`
- `java.lang.String getPurview ()`
- `java.lang.String getSchemaObjectType ()`
- `Template.Usage getUsage ()`
- `boolean isMerge ()`
- `void load ()`
- `void setApplication ( Application a)`
- `void setDescription (java.lang.String s)`
- `void setFields (java.util.List< Field > fields)`
- `void setFormRef ( FormRef frmRef)`
- `void setMerge (boolean merge)`
- `void setName (java.lang.String s)`
- `void setOwnerDefinition ( DynamicValue def)`
- `void setOwnerScript ( Script s)`
- `void setOwnerScriptXml ( Script s)`
- `void setPurview (java.lang.String s)`
- `void setSchemaObjectType (java.lang.String val)`
- `void setUsage ( Template.Usage usage)`

---

## TimePeriod.ClassifierType

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `TimePeriod.ClassifierType`
- `sailpoint.object.TimePeriod.ClassifierType`
- `java.io.Serializable`
- `java.lang.Comparable<TimePeriod.ClassifierType>`

**Attributes:** N/A

**Methods:**
- `staticTimePeriod.ClassifierType valueOf (java.lang.String name)`
- `staticTimePeriod.ClassifierType[] values ()`

---

## TimePeriod

**Package:** `sailpoint.object`

**Description:** This helper method returns a formatted version of the initParameters for display in the UI

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.TimePeriod`
- `java.io.Serializable`
- `java.lang.Comparable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `int compareTo (java.lang.Object arg0)`
- `TimePeriod.ClassifierType getClassifier ()`
- `Attributes getFormattedInitParameters ()`
- `Attributes getInitParameters ()`
- `java.util.Date getTimeStringAsDate (java.lang.String whichAttribute)`
- `void setClassifier ( TimePeriod.ClassifierType classifier)`
- `void setInitParameters ( Attributes initParameters)`
- `void setTimeAttribute (java.lang.String whichAttribute, java.util.Date whatTime)`

---

## UIConfig

**Package:** `sailpoint.object`

**Description:** List of AccountIconConfig objects that describe the icons that should be displayed for extended attributes.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.UIConfig`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `Cacheable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ACCOUNT_GROUP_ACCESS_TABLE_COLUMNS`
- `static java.lang.String ACCOUNT_GROUP_ASSOC_ROLES_TABLE_COLUMNS`
- `static java.lang.String ACCOUNT_GROUP_IDENTITY_TABLE_COLUMNS`
- `static java.lang.String ACCOUNT_GROUP_PERMISSION_TABLE_COLUMNS`
- `static java.lang.String ACCOUNT_GROUP_TABLE_COLUMNS`
- `static java.lang.String ACCOUNT_GRP_MEMBERSHIP_EXCLUSIONS_COLUMNS`
- `static java.lang.String ACCOUNT_GRP_PERMISSIONS_EXCLUSIONS_COLUMNS`
- `static java.lang.String ACCOUNT_ICON_CONFIG`
- `static java.lang.String ALERT_COLUMNS`
- `static java.lang.String ALERT_DEF_COLUMNS`
- `static java.lang.String APPLICATION_ACCOUNTS_COLUMNS`
- `static java.lang.String APPLICATION_TABLE_COLUMNS`
- `static java.lang.String APPLICATIONS_ACTIVITY_DATA_TABLE_COLUMNS`
- `static java.lang.String APPLICATIONS_PASSWORD_POLICY_TABLE_COLUMNS`
- `static java.lang.String APPLICATIONS_TABLE_COLUMNS`
- `static java.lang.String APPLICATIONS_UNSTRUCTURED_TABLE_COLUMNS`
- `static java.lang.String BATCH_REQUEST_ITEMS_TABLE_COLUMNS`
- `static java.lang.String BATCHREQUEST_TABLE_COLUMNS`
- `static java.lang.String BULK_CUSTOM_ENTITY_FIELDS_INCLUDE`
- `static java.lang.String BUSINESS_ROLE_REMEDIATION_ITEM_TABLE_COLUMNS`
- `static java.lang.String CERT_DETAIL_ACCT_GRP_MEMBERSHIPS`
- `static java.lang.String CERT_DETAIL_ACCT_GRP_PERMISSIONS`
- `static java.lang.String CERT_DETAIL_ACCT_GRP_PERMISSIONS_APP_GRANULATIRY`
- `static java.lang.String CERT_DETAIL_DATA_OWNER`
- `static java.lang.String CERT_DETAIL_ENTITLEMENTS`
- `static java.lang.String CERT_DETAIL_ENTITLEMENTS_APP_GRANULARITY`
- `static java.lang.String CERT_DETAIL_MGR_ROLES`
- `static java.lang.String CERT_DETAIL_PROFILES`
- `static java.lang.String CERT_DETAIL_RELATED_ROLES`
- `static java.lang.String CERT_DETAIL_SCOPE_AND_CAPS`
- `static java.lang.String CERT_DETAIL_VIOLATIONS`
- `static java.lang.String CERTIFICATION_ACCOUNT_GROUP_TABLE_COLUMNS`
- `static java.lang.String CERTIFICATION_BUSINESS_ROLE_COMPOSITION_TABLE_COLUMNS`
- `static java.lang.String CERTIFICATION_BUSINESS_ROLE_MEMBERSHIP_COLUMNS`
- `static java.lang.String CERTIFICATION_ENTITY_DATA_OWNER_TABLE_COLUMNS`
- `static java.lang.String CERTIFICATION_ENTITY_TABLE_COLUMNS`
- `static java.lang.String CERTIFICATION_EVENTS_TABLE_COLUMNS`
- `static java.lang.String CERTIFICATION_ITEM_DATA_OWNER_TABLE_COLUMNS`
- `static java.lang.String CERTIFICATION_ITEM_TABLE_COLUMNS`
- `static java.lang.String CERTIFICATION_REVOCATION_DETAIL_TABLE_COLUMNS`
- `static java.lang.String CERTIFICATION_SCHEDULE_TABLE_COLUMNS`
- `static java.lang.String CERTIFICATIONS_TABLE_COLUMNS`
- `static java.lang.String CONTEXTUAL_HELP`
- `static java.lang.String CUSTOM_CERTIFICATION_ENTITY_PAGE_INCLUDE`
- `static java.lang.String CUSTOM_CERTIFICATION_ITEM_ROWS_INCLUDE`
- `static java.lang.String DASHBOARD_APPLICATION_STATISTICS_TABLE_COLUMNS`
- `static java.lang.String DASHBOARD_CERTIFICATION_COMPLETION_TABLE_COLUMNS`
- `static java.lang.String DASHBOARD_INBOX_TABLE_COLUMNS`
- `static java.lang.String DASHBOARD_OUTBOX_TABLE_COLUMNS`
- `static java.lang.String DASHBOARD_SIGNOFF_TABLE_COLUMNS`
- `static java.lang.String DATA_OWNER_EXCLUSIONS_COLUMNS`
- `static java.lang.String DISABLE_ENTITLEMENTS_CLASSIFICATIONS_FILTER`
- `static java.lang.String DISABLE_ROLE_CLASSIFICATIONS_FILTER`
- `static java.lang.String DISABLE_ROLE_EDITOR_IMPACT_ANALYSIS`
- `static java.lang.String ENTITLEMENT_CATALOG_TABLE_COLUMNS`
- `static java.lang.String FORMS_COLUMNS`
- `static java.lang.String GEN_AI_ENTITLEMENT_DESCRIPTION_TABLE_COLUMNS`
- `static java.lang.String GROUP_TABLE_COLUMNS`
- `static java.lang.String IDENTITY_EXCLUSIONS_COLUMNS`
- `static java.lang.String IDENTITY_HISTORY_BY_ITEM_TABLE_COLUMNS`
- `static java.lang.String IDENTITY_HISTORY_TABLE_COLUMNS`
- `static java.lang.String IDENTITY_INDIRECT_ENTITLEMENT_COLUMNS`
- `static java.lang.String IDENTITY_SEARCH_ATTRIBUTES`
- `static java.lang.String IDENTITY_TABLE_COLUMNS`
- `static java.lang.String IDENTITY_VIEW_ATTRIBUTES`
- `static java.lang.String LCM_CREATE_IDENTITY_POLICY`
- `static java.lang.String LCM_CREATE_IDENTITY_POLICY_REQUIRED_FIELDS`
- `static java.lang.String LCM_SEARCH_ENTITLEMENT_ATTRIBUTES`
- `static java.lang.String LCM_SEARCH_IDENTITY_ATTRIBUTES`
- `static java.lang.String LCM_SEARCH_ROLE_ATTRIBUTES`
- `static java.lang.String LCM_UPDATE_IDENTITY_POLICY`
- `static java.lang.String MANAGE_WORKITEMS_TABLE_COLUMNS`
- `static java.lang.String MANUAL_CORRELATION_IDENTITY_COLUMNS`
- `static java.lang.String MINING_RESULTS_TABLE_COLUMNS`
- `static java.lang.String MODULE_TABLE_COLUMNS`
- `static java.lang.String MON_STAT_COLUMNS`
- `static java.lang.String MY_CERTIFICATIONS_TABLE_COLUMNS`
- `static java.lang.String NAME_ONLY_ACCOUNT_GROUP_TABLE_COLUMNS`
- `static java.lang.String OBJ_NAME`
- `static java.lang.String POLICIES_TABLE_COLUMNS`
- `static java.lang.String POLICY_VIOLATION_COLUMNS`
- `static java.lang.String POPULATION_EDIT_TABLE_COLUMNS`
- `static java.lang.String POPULATION_TABLE_COLUMNS`
- `static java.lang.String PROVISIONING_TRANSACTION_COLUMNS`
- `static java.lang.String REMEDIATION_TABLE_COLUMNS`
- `static java.lang.String REQUESTS_TABLE_COLUMNS`
- `static java.lang.String RISK_SCORE_TABLE_COLUMNS`
- `static java.lang.String ROLE_EXCLUSIONS_COLUMNS`
- `static java.lang.String ROLE_METRICS_IDENTITIES_COLUMNS`
- `static java.lang.String SERVER_COLUMNS`
- `static java.lang.String SERVER_STATISTIC_COLUMNS`
- `static java.lang.String SUB_GROUP_DEF_TABLE_COLUMNS`
- `static java.lang.String TASK_DEFINITION_TABLE_COLUMNS`
- `static java.lang.String TASK_RESULTS_TABLE_COLUMNS`
- `static java.lang.String TASK_SCHEDULE_TABLE_COLUMNS`
- `static java.lang.String UI_ACCESS_HISTORY_ACCOUNT_CAPTURE_TABLE_COLUMNS`
- `static java.lang.String UI_ACCESS_HISTORY_ENTITLEMENT_CAPTURE_TABLE_COLUMNS`
- `static java.lang.String UI_ACCESS_HISTORY_ROLE_CAPTURE_TABLE_COLUMNS`
- `static java.lang.String UI_APPROVALS_LIST_COLUMNS`
- `static java.lang.String UI_BATCH_REQUEST_ITEMS_TABLE_COLUMNS`
- `static java.lang.String UI_CERTIFICATION_CARD_COLUMNS`
- `static java.lang.String UI_CERTIFICATION_ENTITIES_COLUMNS`
- `static java.lang.String UI_CERTIFICATION_ITEM_DETAIL_VIEW_POLICY_VIOLATION_COLUMNS`
- `static java.lang.String UI_CERTIFICATION_ITEM_DETAIL_VIEW_RETURNED_ITEMS_COLUMNS`
- `static java.lang.String UI_CERTIFICATION_ITEM_DETAIL_VIEW_WORKSHEET_COLUMNS`
- `static java.lang.String UI_CERTIFICATION_ITEM_EXPORT_COLUMNS`
- `static java.lang.String UI_CERTIFICATION_ITEM_POLICY_VIOLATION_COLUMNS`
- `static java.lang.String UI_CERTIFICATION_ITEM_RETURNED_ITEMS_COLUMNS`
- `static java.lang.String UI_CERTIFICATION_ITEM_WORKSHEET_COLUMNS`
- `static java.lang.String UI_CLASSIFICATIONS_COLUMNS`
- `static java.lang.String UI_ENTITLEMENT_CERTIFICATION_ENTITIES_COLUMNS`
- `static java.lang.String UI_HISTORICAL_IDENTITY_EVENT_LIST_COLUMNS`
- `static java.lang.String UI_HISTORICAL_IDENTITY_LIST_ITEM_COLUMNS`
- `static java.lang.String UI_IDENTITY_HISTORY_BY_ITEM_TABLE_COLUMNS`
- `static java.lang.String UI_IDENTITY_REQUEST_CARD_COLUMNS`
- `static java.lang.String UI_IDENTITY_REQUEST_CHANGE_ITEMS_COLUMNS`
- `static java.lang.String UI_IDENTITY_REQUEST_ITEMS_COLUMNS`
- `static java.lang.String UI_MANAGE_ACCOUNTS_ATTRIBUTE`
- `static java.lang.String UI_MANAGE_EDIT_IDENTITY`
- `static java.lang.String UI_MANAGE_PASSWORDS_ATTRIBUTE`
- `static java.lang.String UI_MANAGE_VIEW_IDENTITY`
- `static java.lang.String UI_POLICY_VIOLATIONS_COLUMNS`
- `static java.lang.String UI_WORK_ITEM_LIST_CARD_COLUMNS`
- `static java.lang.String WORKGROUP_MEMBER_COLUMNS`
- `static java.lang.String WORKGROUP_TABLE_COLUMNS`
- `static java.lang.String WORKITEM_VIOLATIONS`
- `static java.lang.String WORKITEMS_ARCHIVE_TABLE_COLUMNS`

**Methods:**
- `java.lang.Object clone ()`
- `java.lang.String get (java.lang.String name)`
- `java.util.List<ColumnConfig> getAccountGroupIdentityTableColumns ()`
- `java.util.List<ColumnConfig> getAccountGroupPermissionTableColumns ()`
- `java.util.List<ColumnConfig> getAccountGroupTableColumns ()`
- `java.util.List<AccountIconConfig> getAccountIcons ()`
- `java.util.List<ColumnConfig> getApplicationsTableColumns ()`
- `java.util.List<ColumnConfig> getApplicationTableColumns ()`
- `Attributes getAttributes ()`
- `java.util.List<ColumnConfig> getBatchRequestItemsTableColumns ()`
- `java.util.List<ColumnConfig> getBatchRequestTableColumns ()`
- `java.lang.String getBulkCustomEntityFieldsInclude ()`
- `java.util.List<ColumnConfig> getBusinessRoleRemediationItemTableColumns ()`
- `java.util.List<ColumnConfig> getCertificationAccountGroupTableColumns ()`
- `java.util.List<ColumnConfig> getCertificationBusinessRoleCompositionTableColumns ()`
- `java.util.List<ColumnConfig> getCertificationBusinessRoleMembershipTableColumns ()`
- `java.util.List<ColumnConfig> getCertificationEntityDataOwnerTableColumns ()`
- `java.util.List<ColumnConfig> getCertificationEntityTableColumns ()`
- `java.util.List<ColumnConfig> getCertificationEventsTableColumns ()`
- `java.util.List<ColumnConfig> getCertificationItemDataOwnerTableColumns ()`
- `java.util.List<ColumnConfig> getCertificationItemTableColumns ()`
- `java.util.List<ColumnConfig> getCertificationScheduleTableColumns ()`
- `java.util.Map<java.lang.String,​sailpoint.web.help.ContextualHelpItem> getContextualHelp ()`
- `java.lang.String getCustomCertificationEntityPageInclude ()`
- `java.lang.String getCustomCertificationItemRowsInclude ()`
- `java.util.List<ColumnConfig> getDashboardApplicatonStatisticsTableColumns ()`
- `java.util.List<ColumnConfig> getDashboardCertificationStatusTableColumns ()`
- `java.util.List<ColumnConfig> getDashboardInboxTableColumns ()`
- `java.util.List<ColumnConfig> getDashboardOutboxTableColumns ()`
- `java.util.List<ColumnConfig> getDashboardSignoffTableColumns ()`
- `java.util.List<ColumnConfig> getEntitlementCatalogTableColumns ()`
- `java.util.List<ColumnConfig> getGenAIColumns ()`
- `java.util.List<ColumnConfig> getGroupTableColumns ()`
- `java.util.List<ColumnConfig> getIdentityHistoryTableColumns ()`
- `java.lang.String getIdentitySearchAttributes ()`
- `java.util.List<java.lang.String> getIdentitySearchAttributesList ()`
- `java.util.List<ColumnConfig> getIdentityTableColumns ()`
- `java.lang.String getIdentityViewAttributes ()`
- `java.util.List<java.lang.String> getIdentityViewAttributesList ()`
- `java.util.List<java.lang.String> getList (java.lang.String name)`
- `java.util.List<ColumnConfig> getManageWorkItemsTableColumns ()`
- `java.util.List<ColumnConfig> getManualCorrelationIdentityTableColumns ()`
- `java.util.List<ColumnConfig> getMiningResultsTableColumns ()`
- `java.util.List<ColumnConfig> getMyCertificationsTableColumns ()`
- `java.util.List<ColumnConfig> getNameOnlyAccountGroupTableColumns ()`
- `java.lang.Object getObject (java.lang.String name)`
- `java.util.List<ColumnConfig> getPoliciesTableColumns ()`
- `java.util.List<ColumnConfig> getPolicyViolationTableColumns ()`
- `java.util.List<ColumnConfig> getPopulationEditTableColumns ()`
- `java.util.List<ColumnConfig> getPopulationTableColumns ()`
- `java.util.List<ColumnConfig> getRemediationTableColumns ()`
- `java.util.List<ColumnConfig> getRequestsTableColumns ()`
- `java.util.List<ColumnConfig> getRiskScoreTableColumns ()`
- `java.util.List<ColumnConfig> getRoleMetricsIdentitiesColumns ()`
- `java.util.List<ColumnConfig> getSubGroupDefinitionTableColumns ()`
- `java.util.List<ColumnConfig> getTaskDefinitionTableColumns ()`
- `java.util.List<ColumnConfig> getTaskResultsTableColumns ()`
- `java.util.List<ColumnConfig> getTaskScheduleTableColumns ()`
- `staticUIConfig getUIConfig ()`
- `java.util.List<ColumnConfig> getWorkgroupMemberTableColumns ()`
- `java.util.List<ColumnConfig> getWorkgroupTableColumns ()`
- `java.util.List<ColumnConfig> getWorkItemsArchiveTableColumns ()`
- `boolean isRoleEditorImpactAnalysisDisabled ()`
- `void put (java.lang.String name, java.lang.Object value)`
- `void putList (java.lang.String name, java.util.List<java.lang.String> values)`
- `void setAccountGroupIdentityTableColumns (java.util.List< ColumnConfig > columns)`
- `void setAccountGroupPermissionTableColumns (java.util.List< ColumnConfig > columns)`
- `void setAccountGroupTableColumns (java.util.List< ColumnConfig > columns)`
- `void setApplicationsTableColumns (java.util.List< ColumnConfig > columns)`
- `void setApplicationTableColumns (java.util.List< ColumnConfig > columns)`
- `void setAttributes ( Attributes a)`
- `void setBatchRequestItemsTableColumns (java.util.List< ColumnConfig > columns)`
- `void setBusinessRoleRemediationItemTableColumns (java.util.List< ColumnConfig > columns)`
- `void setCertificationAccountGroupTableColumns (java.util.List< ColumnConfig > columns)`
- `void setCertificationBusinessRoleCompositionTableColumns (java.util.List< ColumnConfig > columns)`
- `void setCertificationBusinessRoleMembershipTableColumns (java.util.List< ColumnConfig > columns)`
- `void setCertificationEntityDataOwnerTableColumns (java.util.List< ColumnConfig > columns)`
- `void setCertificationEntityTableColumns (java.util.List< ColumnConfig > columns)`
- `void setCertificationEventsTableColumns (java.util.List< ColumnConfig > columns)`
- `void setCertificationItemDataOwnerTableColumns (java.util.List< ColumnConfig > columns)`
- `void setCertificationItemTableColumns (java.util.List< ColumnConfig > columns)`
- `void setCertificationScheduleTableColumns (java.util.List< ColumnConfig > columns)`
- `void setDashboardApplicatonStatisticsTableColumns (java.util.List< ColumnConfig > columns)`
- `void setDashboardCertificationStatusTableColumns (java.util.List< ColumnConfig > columns)`
- `void setDashboardInboxTableColumns (java.util.List< ColumnConfig > columns)`
- `void setDashboardOutboxTableColumns (java.util.List< ColumnConfig > columns)`
- `void setDashboardSignoffTableColumns (java.util.List< ColumnConfig > columns)`
- `void setEntitlementCatalogTableColumns (java.util.List< ColumnConfig > columns)`
- `void setGroupTableColumns (java.util.List< ColumnConfig > columns)`
- `void setIdentityHistoryTableColumns (java.util.List< ColumnConfig > columns)`
- `void setIdentitySearchAttributes (java.lang.String names)`
- `void setIdentitySearchAttributesList (java.util.List<java.lang.String> l)`
- `void setIdentityTableColumns (java.util.List< ColumnConfig > columns)`
- `void setIdentityViewAttributes (java.lang.String names)`
- `void setIdentityViewAttributesList (java.util.List<java.lang.String> l)`
- `void setManageWorkItemTableColumns (java.util.List< ColumnConfig > columns)`
- `void setManualCorrelationIdentityTableColumns (java.util.List< ColumnConfig > columns)`
- `void setMyCertificationsTableColumns (java.util.List< ColumnConfig > columns)`
- `void setNameOnlyAccountGroupTableColumns (java.util.List< ColumnConfig > columns)`
- `void setPoliciesTableColumns (java.util.List< ColumnConfig > columns)`
- `void setPolicyViolationTableColumns (java.util.List< ColumnConfig > columns)`
- `void setPopulationEditTableColumns (java.util.List< ColumnConfig > columns)`
- `void setPopulationTableColumns (java.util.List< ColumnConfig > columns)`
- `void setRemediationTableColumns (java.util.List< ColumnConfig > columns)`
- `void setRequestsTableColumns (java.util.List< ColumnConfig > columns)`
- `void setRiskScoreTableColumns (java.util.List< ColumnConfig > columns)`
- `void setRoleMetricsIdentitiesColumns (java.util.List< ColumnConfig > columns)`
- `void setSubGroupDefinitionTableColumns (java.util.List< ColumnConfig > columns)`
- `void setTaskDefinitionTableColumns (java.util.List< ColumnConfig > columns)`
- `void setTaskResultsTableColumns (java.util.List< ColumnConfig > columns)`
- `void setTaskScheduleTableColumns (java.util.List< ColumnConfig > columns)`
- `void setWorkgroupMemberTableColumns (java.util.List< ColumnConfig > columns)`
- `void setWorkgroupTableColumns (java.util.List< ColumnConfig > columns)`
- `void setWorkItemsArchiveTableColumns (java.util.List< ColumnConfig > columns)`

---

## UIPreferences.StartUpHelp

**Package:** `sailpoint.object`

**Description:** Start up helps to be displayed or not again tracker This is persisted based on what the user does.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `UIPreferences.StartUpHelp`
- `sailpoint.object.UIPreferences.StartUpHelp`
- `java.io.Serializable`
- `java.lang.Comparable<UIPreferences.StartUpHelp>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getKey ()`
- `staticUIPreferences.StartUpHelp valueOf (java.lang.String name)`
- `staticUIPreferences.StartUpHelp[] values ()`

---

## UIPreferences

**Package:** `sailpoint.object`

**Description:** An object encapsulating various UI preferences associated with an identity.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.UIPreferences`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String[] PREFERENCE_NAMES`
- `static java.lang.String PRF_ADV_SEARCH_ITEMS`
- `static java.lang.String PRF_CERT_PAGE_LIST_ITEMS`
- `static java.lang.String PRF_CERTIFICATION_DETAILED_VIEW_FILTER_SET`
- `static java.lang.String PRF_CERTIFICATION_SUMMARY_DISPLAY_MINIMIZED`
- `static java.lang.String PRF_DASHBOARD`
- `static java.lang.String PRF_DASHBOARD_COMPLIANCE`
- `static java.lang.String PRF_DASHBOARD_LIFECYCLE`
- `static java.lang.String PRF_DISPLAY_ENTITLEMENT_DESC`
- `static java.lang.String PRF_EXT_STATES`
- `static java.lang.String PRF_GRID_STATES`
- `static java.lang.String PRF_HOME_CONTENT_ORDER`
- `static java.lang.String PRF_HOME_WIDGETS`
- `static java.lang.String PRF_QUICKLINK_CARDS`
- `static java.lang.String PRF_TABLE_COLUMN_PREFERENCES`
- `static java.lang.String PRF_TABLE_GROUPING_PREFERENCES`
- `static java.lang.String PRF_TABLE_ITEM_COUNT_PREFERENCES`
- `static java.lang.String PRF_TABLE_SORTING_PREFERENCES`

**Methods:**
- `java.lang.Object get (java.lang.String name)`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `Attributes<java.lang.String,​java.lang.Object> getPreferences ()`
- `boolean hasAssignedScope ()`
- `boolean hasName ()`
- `void put (java.lang.String name, java.lang.Object value)`
- `void replace ( UIPreferences src)`
- `void setPreferences ( Attributes <java.lang.String,java.lang.Object> preferences)`
- `void visit ( Visitor v)`

---

## VerificationToken

**Package:** `sailpoint.object`

**Description:** This is the object used to store an SMS Password Reset Token.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.VerificationToken`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.util.Date getCreateDate ()`
- `java.util.Date getExpireDate ()`
- `int getFailedAttempts ()`
- `java.lang.String getTextCode ()`
- `void setCreateDate (java.util.Date createDate)`
- `void setExpireDate (java.util.Date expireDate)`
- `void setFailedAttempts (int failedAttempts)`
- `void setTextCode (java.lang.String textCode)`

---

## ViolationDetails

**Package:** `sailpoint.object`

**Description:** A class holding optional information about a PolicyViolation. These can be created by the PolicyExecutors, saved in the PolicyViolation attributes map, then used when rendering information about the violation. Currently the main consumer of this is sailpoint.api.PolicyUtil.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.ViolationDetails`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void addLeft (java.util.List< IdentityItem > items)`
- `void addLeft ( IdentityItem item)`
- `void addRight (java.util.List< IdentityItem > items)`
- `void addRight ( IdentityItem item)`
- `java.util.List<IdentityItem> getLeft ()`
- `java.util.List<IdentityItem> getRight ()`
- `void setLeft (java.util.List< IdentityItem > items)`
- `void setRight (java.util.List< IdentityItem > items)`

---

## Visitor

**Package:** `sailpoint.object`

**Description:** Base visitor for objects in the SailPoint model.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.Visitor`

**Attributes:** N/A

**Methods:**
- `void visit ( SailPointObject obj)`
- `void visitAccountGroup ( AccountGroup obj)`
- `void visitApplication ( Application obj)`
- `void visitApplicationScorecard ( ApplicationScorecard obj)`
- `void visitAuthenticationAnswer ( AuthenticationAnswer obj)`
- `void visitAuthenticationQuestion ( AuthenticationQuestion obj)`
- `void visitBatchRequest ( BatchRequest batchRequest)`
- `void visitBatchRequestItem ( BatchRequestItem batchRequestItem)`
- `void visitBundle ( Bundle obj)`
- `void visitCertification ( Certification obj)`
- `void visitCertificationDefinition ( CertificationDefinition obj)`
- `void visitCertificationEntity ( CertificationEntity certificationEntity)`
- `void visitCertificationGroup ( CertificationGroup certGroup)`
- `void visitCertificationItem ( CertificationItem certificationItem)`
- `void visitClassification ( Classification classification)`
- `void visitCloudAccessGroup ( CloudAccessGroup obj)`
- `void visitCloudAccessRole ( CloudAccessRole obj)`
- `void visitCloudAccessScope ( CloudAccessScope obj)`
- `void visitConfiguration ( Configuration configuration)`
- `void visitCorrelationConfig ( CorrelationConfig obj)`
- `void visitDynamicScope ( DynamicScope dynamicScope)`
- `void visitGroupDefinition ( GroupDefinition obj)`
- `void visitGroupFactory ( GroupFactory obj)`
- `void visitGroupIndex ( GroupIndex obj)`
- `void visitIdentity ( Identity obj)`
- `void visitIdentityEntitlement ( IdentityEntitlement obj)`
- `void visitIdentityRequest ( IdentityRequest ir)`
- `void visitIdentityRequestItem ( IdentityRequestItem item)`
- `void visitIdentityTrigger ( IdentityTrigger obj)`
- `void visitIntegrationConfig ( IntegrationConfig obj)`
- `void visitJasperResult ( JasperResult obj)`
- `void visitLink ( Link obj)`
- `void visitLocalizedAttribute ( LocalizedAttribute obj)`
- `void visitManagedAttribute ( ManagedAttribute obj)`
- `void visitMitigationExpiration ( MitigationExpiration obj)`
- `void visitMonitoringStatistic ( MonitoringStatistic obj)`
- `void visitPasswordPolicy ( PasswordPolicy obj)`
- `void visitPasswordPolicyHolder ( PasswordPolicyHolder obj)`
- `void visitPersistedFile ( PersistedFile obj)`
- `void visitPlugin ( Plugin plugin)`
- `void visitPolicy ( Policy obj)`
- `void visitPolicyViolation ( PolicyViolation obj)`
- `void visitProfile ( Profile obj)`
- `void visitQuickLink ( QuickLink quickLink)`
- `void visitQuickLinkOptions ( QuickLinkOptions qlo)`
- `void visitRequest ( Request obj)`
- `void visitRoleIndex ( RoleIndex roleIndex)`
- `void visitRoleMetadata ( RoleMetadata roleMetadata)`
- `void visitRoleScorecard ( RoleScorecard roleScorecard)`
- `void visitRule ( Rule obj)`
- `void visitSailPointObject ( SailPointObject obj)`
- `void visitScope ( Scope obj)`
- `void visitScorecard ( Scorecard obj)`
- `void visitServer ( Server obj)`
- `void visitServiceDefinition ( ServiceDefinition obj)`
- `void visitTag ( Tag obj)`
- `void visitTarget ( Target obj)`
- `void visitTargetSource ( TargetSource source)`
- `void visitTaskDefinition ( TaskDefinition obj)`
- `void visitTaskResult ( TaskResult obj)`
- `void visitTaskSchedule ( TaskSchedule obj)`
- `void visitUIPreferences ( UIPreferences obj)`
- `void visitWorkflow ( Workflow obj)`
- `void visitWorkflowCase ( WorkflowCase obj)`
- `void visitWorkItem ( WorkItem obj)`
- `void visitWorkItemConfig ( WorkItemConfig obj)`

---

## WebResource

**Package:** `sailpoint.object`

**Description:** Defines what is required to view a given url as well as methods to validate access.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.WebResource`
- `java.io.Serializable`
- `ImportMergable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `boolean equals (java.lang.Object o)`
- `java.util.List<java.lang.String> getChildResources ()`
- `java.util.Map<java.lang.String,​java.lang.Object> getEnablingAttributes ()`
- `java.lang.String getRights ()`
- `java.util.List<java.lang.String> getRightsList ()`
- `java.lang.String getUrl ()`
- `boolean hasAccess (java.util.List< Capability > identityCaps, java.util.Collection<java.lang.String> identityRights, java.util.Map<java.lang.String,java.lang.Object> identityAttributes)`
- `boolean hasAccess ( Identity identity)`
- `int hashCode ()`
- `void merge (java.lang.Object obj)`
- `void setChildResources (java.util.List<java.lang.String> childResources)`
- `void setEnablingAttributes (java.util.Map<java.lang.String,java.lang.Object> enablingAttributes)`
- `void setRights (java.lang.String rights)`
- `void setUrl (java.lang.String url)`

---

## Widget

**Package:** `sailpoint.object`

**Description:** Model object for home page widget.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Widget`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `IdentitySelector getSelector ()`
- `java.lang.String getTitle ()`
- `void setSelector ( IdentitySelector selector)`
- `void setTitle (java.lang.String title)`

---

## WindowsEventLogEntry

**Package:** `sailpoint.object`

**Description:** Sub-category for this event.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.WindowsEventLogEntry`

**Attributes:** N/A

**Methods:**
- `java.lang.Integer getCategory ()`
- `java.lang.String getCategoryStr ()`
- `java.lang.String getCategoryString ()`
- `java.lang.String getComputerName ()`
- `java.lang.Integer getEventCode ()`
- `java.lang.String getEventCodeString ()`
- `java.lang.Integer getEventId ()`
- `java.lang.String getEventIdentifier ()`
- `java.lang.Integer getEventType ()`
- `java.lang.String getEventTypeString ()`
- `java.lang.String getLogFile ()`
- `java.lang.String getMessage ()`
- `java.lang.Integer getRecordNumber ()`
- `java.lang.String getRecordNumberStr ()`
- `java.lang.String getSourceName ()`
- `java.util.Date getTimeWrittenDate ()`
- `java.lang.String getTimeWrittenGMT ()`
- `java.lang.String getTimeWrittenString ()`
- `java.lang.String getUser ()`
- `void setCategoryStr (java.lang.String category)`
- `void setCategoryString (java.lang.String categoryString)`
- `void setComputerName (java.lang.String computerName)`
- `void setEventCodeString (java.lang.String eventCode)`
- `void setEventIdentifier (java.lang.String id)`
- `void setEventTypeString (java.lang.String eventType)`
- `void setLogFile (java.lang.String log)`
- `void setMessage (java.lang.String message)`
- `void setRecordNumberStr (java.lang.String str)`
- `void setSourceName (java.lang.String source)`
- `void setTimeWrittenGMT (java.lang.String gmtWritten)`
- `void setTimeWrittenString (java.lang.String written)`
- `void setUser (java.lang.String user)`

---

## WindowsShare

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.WindowsShare`
- `java.lang.Cloneable`

**Attributes:** N/A

**Methods:**
- `java.lang.Object clone ()`
- `int getDepth ()`
- `java.lang.String getFilter ()`
- `boolean getIncludeExplicitPermissions ()`
- `boolean getIncludeInheritedPermissions ()`
- `java.lang.String getPassword ()`
- `java.lang.String getPath ()`
- `java.lang.String getUser ()`
- `boolean isDirectoriesOnly ()`
- `void setDepth (int depth)`
- `void setDirectoriesOnly (boolean dirsOnly)`
- `void setFilter (java.lang.String filter)`
- `void setIncludeExplicitPermissions (boolean explicit)`
- `void setIncludeInheritedPermissions (boolean inherited)`
- `void setPassword (java.lang.String password)`
- `void setPath (java.lang.String path)`
- `void setUser (java.lang.String user)`

---

## WorkItem.Level

**Package:** `sailpoint.object`

**Description:** Work item significance levels. The absence of a level implies "normal".

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `WorkItem.Level`
- `sailpoint.object.WorkItem.Level`
- `java.io.Serializable`
- `java.lang.Comparable<WorkItem.Level>`
- `sailpoint.tools.MessageKeyHolder`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticWorkItem.Level valueOf (java.lang.String name)`
- `staticWorkItem.Level[] values ()`

---

## WorkItem.OwnerHistory

**Package:** `sailpoint.object`

**Description:** An entry in the forwarding history of a work item.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.WorkItem.OwnerHistory`

**Attributes:** N/A

**Methods:**
- `java.lang.String getComment ()`
- `java.lang.String getEffectiveSource ()`
- `java.lang.String getEffectiveSourceDisplayName ()`
- `java.lang.String getNewOwner ()`
- `java.lang.String getNewOwnerDisplayName ()`
- `java.lang.String getOldOwner ()`
- `java.lang.String getOldOwnerDisplayName ()`
- `java.lang.String getSource ()`
- `java.lang.String getSourceDisplayName ()`
- `java.util.Date getStartDate ()`
- `Identity getXMLNewOwner ()`
- `Identity getXMLOldOwner ()`
- `void setComment (java.lang.String comment)`
- `void setNewOwner (java.lang.String newOwner)`
- `void setNewOwnerDisplayName (java.lang.String newOwnerDisplayName)`
- `void setOldOwner (java.lang.String oldOwner)`
- `void setOldOwnerDisplayName (java.lang.String oldOwnerDisplayName)`
- `void setSource (java.lang.String source)`
- `void setSourceDisplayName (java.lang.String sourceDisplayName)`
- `void setStartDate (java.util.Date startDate)`
- `void setXMLNewOwner ( Identity identity)`
- `void setXMLOldOwner ( Identity identity)`

---

## WorkItem.State

**Package:** `sailpoint.object`

**Description:** Work item completion states.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `WorkItem.State`
- `sailpoint.object.WorkItem.State`
- `java.io.Serializable`
- `java.lang.Comparable<WorkItem.State>`
- `sailpoint.tools.MessageKeyHolder`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `static java.util.List<java.lang.String> getWorkItemStatesList ()`
- `staticWorkItem.State valueOf (java.lang.String name)`
- `staticWorkItem.State[] values ()`

---

## WorkItem.Type

**Package:** `sailpoint.object`

**Description:** Work item types.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `WorkItem.Type`
- `sailpoint.object.WorkItem.Type`
- `java.io.Serializable`
- `java.lang.Comparable<WorkItem.Type>`
- `sailpoint.tools.MessageKeyHolder`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticWorkItem.Type valueOf (java.lang.String name)`
- `staticWorkItem.Type[] values ()`

---

## WorkItem

**Package:** `sailpoint.object`

**Description:** Work item significance levels.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.WorkItem`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `AssignableItem`
- `Notifiable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATT_APPROVAL_SET`
- `static java.lang.String ATT_ARCHIVE`
- `static java.lang.String ATT_CHANGE_SUMMARY`
- `static java.lang.String ATT_COMPLETER`
- `static java.lang.String ATT_ELECTRONIC_SIGNATURE`
- `static java.lang.String ATT_FORM`
- `static java.lang.String ATT_FORM_CHANGED`
- `static java.lang.String ATT_POLICY_VIOLATIONS`
- `static java.lang.String ATT_SIGNATURE`
- `static java.lang.String ATT_SUMMARY_NAME`
- `static java.lang.String ATT_TASK_RESULT`

**Methods:**
- `void addComment (java.lang.String comment)`
- `void addComment (java.lang.String comment, java.lang.String author)`
- `void addComment (java.lang.String comment, Identity commentator)`
- `void addOwnerHistory ( WorkItem.OwnerHistory history)`
- `RemediationItem addRemediationItem ( Certification cert, java.lang.String certItemId, java.lang.String identity, RemediationItem.RemediationEntityType entityType, CertificationAction action, ProvisioningPlan plan, java.util.List<sailpoint.web.certification.PolicyTreeNode> contributingEntitlements)`
- `void addRemediationItem ( Identity actor, RemediationItem.RemediationEntityType remediationType, java.lang.String remediationIdentity, ProvisioningPlan plan, java.lang.String description, java.lang.String comments, java.util.List<sailpoint.web.certification.PolicyTreeNode> contributingEntitlements)`
- `void addSignOff ( SignOffHistory esig)`
- `Attributes<java.lang.String,​java.lang.Object> allocAttributes ()`
- `void copyLifecycleInfo ( WorkItem item)`
- `java.lang.Object get (java.lang.String name)`
- `ApprovalSet getApprovalSet ()`
- `Identity getAssignee ()`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `boolean getBoolean (java.lang.String name)`
- `java.lang.String getCertification ()`
- `Certification getCertification ( Resolver resolver)`
- `java.lang.String getCertificationEntity ()`
- `CertificationEntity getCertificationEntity ( Resolver resolver)`
- `java.lang.String getCertificationItem ()`
- `CertificationItem getCertificationItem ( Resolver resolver)`
- `java.util.List<Comment> getComments ()`
- `java.lang.String getCompleter ()`
- `java.lang.String getCompletionComments ()`
- `java.util.Date getDate (java.lang.String name)`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `CertificationEntity.Type getEntityType ()`
- `int getEscalationCount ()`
- `java.util.Date getExpiration ()`
- `java.util.Date getExpirationDate ()`
- `Form getForm ()`
- `java.lang.String getHandler ()`
- `WorkItemHandler getHandlerInstance ()`
- `java.lang.String getIdentityRequestId ()`
- `int getInt (java.lang.String name)`
- `WorkItem.Level getLevel ()`
- `java.util.List getList (java.lang.String name)`
- `java.util.Date getNotification ()`
- `NotificationConfig getNotificationConfig ()`
- `java.lang.String getNotificationName ()`
- `Identity getNotificationOwner ( Resolver resolver)`
- `java.util.List<WorkItem.OwnerHistory> getOwnerHistory ()`
- `java.util.List<RemediationItem> getRemediationItems ()`
- `int getReminders ()`
- `int getRemindersSent ()`
- `java.lang.String getRenderer ()`
- `Identity getRequester ()`
- `java.lang.String getShortName ( Resolver resolver)`
- `java.util.List<SignOffHistory> getSignOffs ()`
- `WorkItem.State getState ()`
- `java.lang.String getString (java.lang.String name)`
- `java.lang.String getTargetClass ()`
- `java.lang.String getTargetId ()`
- `java.lang.String getTargetName ()`
- `TaskResult getTaskResult ( Resolver r)`
- `WorkItem.Type getType ()`
- `java.util.Date getWakeUpDate ()`
- `WorkflowCase getWorkflowCase ()`
- `boolean hasLifecycleInfo ()`
- `void incrementEscalationCount ()`
- `void incrementRemindersSent ()`
- `boolean isCertificationRelated ()`
- `boolean isEscalateOnMaxReminders ()`
- `boolean isExpirable ()`
- `boolean isExpired ()`
- `boolean isNameUnique ()`
- `boolean isTargetClass (java.lang.Class cls)`
- `boolean isTargetClass (java.lang.String cls)`
- `boolean isType ( WorkItem.Type t)`
- `void load ()`
- `void put (java.lang.String name, java.lang.Object value)`
- `java.lang.Object removeAttribute (java.lang.String name)`
- `void resetRemindersSent ()`
- `void saveEscalationError ( InvalidEscalationTargetException error)`
- `void setAbstractCertificationItem ( AbstractCertificationItem item)`
- `void setApprovalSet ( ApprovalSet aset)`
- `void setAssignee ( Identity assignee)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> a)`
- `void setCertification (java.lang.String certification)`
- `void setCertification ( Certification a)`
- `void setCertificationEntity (java.lang.String id)`
- `void setCertificationEntity ( CertificationEntity id)`
- `void setCertificationItem (java.lang.String item)`
- `void setCertificationItem ( CertificationItem item)`
- `void setComments (java.util.List< Comment > comments)`
- `void setCompleter (java.lang.String completedBy)`
- `void setCompletionComments (java.lang.String s)`
- `void setEntityType ( CertificationEntity.Type entityType)`
- `void setEscalationCount (int i)`
- `void setExpiration (java.util.Date d)`
- `void setForm ( Form f)`
- `void setHandler (java.lang.Class c)`
- `void setHandler (java.lang.String s)`
- `void setIdentityRequestId (java.lang.String id)`
- `void setLevel ( WorkItem.Level type)`
- `void setNotification (java.util.Date d)`
- `void setNotificationConfig ( NotificationConfig val)`
- `void setOwnerHistory (java.util.List< WorkItem.OwnerHistory > history)`
- `void setRemediationItems (java.util.List< RemediationItem > items)`
- `void setReminders (int i)`
- `void setRenderer (java.lang.String s)`
- `void setRequester ( Identity i)`
- `void setState ( WorkItem.State type)`
- `void setTarget ( SailPointObject obj)`
- `void setTargetClass (java.lang.Class cls)`
- `void setTargetClass (java.lang.String name)`
- `void setTargetId (java.lang.String id)`
- `void setTargetName (java.lang.String name)`
- `void setType ( WorkItem.Type type)`
- `void setupNotificationConfig ( Resolver resolver, java.util.Date expiration, NotificationConfig notifConfig)`
- `void setWakeUpDate (java.util.Date d)`
- `void setWorkflowCase ( WorkflowCase wf)`
- `java.lang.String toString ()`
- `void visit ( Visitor v)`

---

## WorkItemArchive

**Package:** `sailpoint.object`

**Description:** Add a signoff to the archive

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.WorkItemArchive`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String SYSATT_CERTIFICATION`
- `static java.lang.String SYSATT_CERTIFICATION_ENTITY`
- `static java.lang.String SYSATT_CERTIFICATION_ITEM`
- `static java.lang.String SYSATT_COMMENTS`
- `static java.lang.String SYSATT_COMPLETION_COMMENTS`
- `static java.lang.String SYSATT_E_SIGNATURE`
- `static java.lang.String SYSATT_OWNER_HISTORY`
- `static java.lang.String SYSATT_REMEDIATION_ITEMS`

**Methods:**
- `void addMultipleSignOff (java.util.List< SignOffHistory > sigs)`
- `void addOwnerHistory ( WorkItem.OwnerHistory history)`
- `void addSignOff ( SignOffHistory esig)`
- `void clone ( WorkItem src)`
- `java.lang.Object get (java.lang.String name)`
- `java.util.Date getArchived ()`
- `java.lang.String getAssignee ()`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `boolean getBoolean (java.lang.String name)`
- `java.lang.String getCertification ()`
- `Certification getCertification ( Resolver resolver)`
- `java.lang.String getCertificationEntity ()`
- `CertificationEntity getCertificationEntity ( Resolver resolver)`
- `java.lang.String getCertificationItem ()`
- `CertificationItem getCertificationItem ( Resolver resolver)`
- `java.util.List<Comment> getComments ()`
- `java.lang.String getCompleter ()`
- `java.lang.String getCompletionComments ()`
- `java.util.Date getDate (java.lang.String name)`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `CertificationEntity.Type getEntityType ()`
- `java.util.Date getExpiration ()`
- `Form getForm ()`
- `java.lang.String getHandler ()`
- `WorkItemHandler getHandlerInstance ()`
- `java.lang.String getIdentityRequestId ()`
- `int getInt (java.lang.String name)`
- `WorkItem.Level getLevel ()`
- `java.util.List getList (java.lang.String name)`
- `java.util.List<WorkItem.OwnerHistory> getOwnerHistory ()`
- `java.lang.String getOwnerName ()`
- `java.util.List<RemediationItem> getRemediationItems ()`
- `java.lang.String getRenderer ()`
- `java.lang.String getRequester ()`
- `java.util.List<SignOffHistory> getSignOffs ()`
- `WorkItem.State getState ()`
- `java.lang.String getString (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getSystemAttributes ()`
- `java.lang.String getTargetClass ()`
- `java.lang.String getTargetId ()`
- `java.lang.String getTargetName ()`
- `TaskResult getTaskResult ( Resolver r)`
- `WorkItem.Type getType ()`
- `java.util.Date getWakeUpDate ()`
- `java.lang.String getWorkItemId ()`
- `boolean isNameUnique ()`
- `boolean isSigned ()`
- `void setArchived (java.util.Date created)`
- `void setAssignee (java.lang.String name)`
- `void setAttribute (java.lang.String name, java.lang.Object value)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> a)`
- `void setCertification (java.lang.String id)`
- `void setCertificationEntity (java.lang.String id)`
- `void setCertificationItem (java.lang.String id)`
- `void setComments (java.util.List< Comment > comments)`
- `void setCompleter (java.lang.String _completer)`
- `void setCompletionComments (java.lang.String s)`
- `void setEntityType ( CertificationEntity.Type entityType)`
- `void setExpiration (java.util.Date d)`
- `void setHandler (java.lang.String s)`
- `void setIdentityRequestId (java.lang.String id)`
- `void setLevel ( WorkItem.Level type)`
- `void setOwnerHistory (java.util.List< WorkItem.OwnerHistory > history)`
- `void setOwnerName (java.lang.String name)`
- `void setRemediationItems (java.util.List< RemediationItem > items)`
- `void setRenderer (java.lang.String s)`
- `void setRequester (java.lang.String name)`
- `void setSigned (boolean signed)`
- `void setState ( WorkItem.State state)`
- `void setSystemAttributes ( Attributes <java.lang.String,java.lang.Object> a)`
- `void setTargetClass (java.lang.String name)`
- `void setTargetId (java.lang.String id)`
- `void setTargetName (java.lang.String name)`
- `void setType ( WorkItem.Type type)`
- `void setWakeUpDate (java.util.Date d)`
- `void setWorkItemId (java.lang.String workItemId)`

---

## WorkItemConfig

**Package:** `sailpoint.object`

**Description:** Called by the UI when changes are ready to be save and perform validation relevant to the selected style.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.WorkItemConfig`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static int DEFAULT_HOURS_BETWEEN_REMINDERS`
- `static int DEFAULT_HOURS_TILL_ESCALATION`
- `static int DEFAULT_MAX_REMINDERS`
- `static java.lang.String STYLE_BOTH`
- `static java.lang.String STYLE_ESCALATION`
- `static java.lang.String STYLE_NONE`
- `static java.lang.String STYLE_REMINDER`

**Methods:**
- `void addOwner ( Identity id)`
- `void cleanupStyleProperties ()`
- `void defaultStyleProperties ()`
- `java.lang.String getDescriptionTemplate ()`
- `EmailTemplate getEscalationEmail ()`
- `Rule getEscalationRule ()`
- `java.lang.String getEscalationStyle ()`
- `int getHoursBetweenReminders ()`
- `int getHoursTillEscalation ()`
- `int getMaxReminders ()`
- `EmailTemplate getNotificationEmail ()`
- `Rule getOwnerRule ()`
- `java.util.List<Identity> getOwners ()`
- `WorkItemConfig getParent ()`
- `EmailTemplate getReminderEmail ()`
- `boolean isEmpty ()`
- `boolean isNameUnique ()`
- `boolean isNoWorkItem ()`
- `void load ()`
- `void setDescriptionTemplate (java.lang.String s)`
- `void setEscalationEmail ( EmailTemplate et)`
- `void setEscalationRule ( Rule r)`
- `void setEscalationStyle (java.lang.String style)`
- `void setHoursBetweenReminders (int i)`
- `void setHoursTillEscalation (int i)`
- `void setMaxReminders (int i)`
- `void setNotificationEmail ( EmailTemplate et)`
- `void setNoWorkItem (boolean b)`
- `void setOwnerRule ( Rule rule)`
- `void setOwners (java.util.List< Identity > owners)`
- `void setParent ( WorkItemConfig config)`
- `void setReminderEmail ( EmailTemplate et)`
- `void visit ( Visitor v)`

---

## WorkItemMonitor

**Package:** `sailpoint.object`

**Description:** Clear all fields because the decision is being changed.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.WorkItemMonitor`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `protected void clearData ()`
- `java.lang.String getActingWorkItem ()`
- `Identity getActor ( Resolver r)`
- `java.lang.String getActorDisplayName ()`
- `java.lang.String getActorName ()`
- `java.lang.String getComments ()`
- `java.lang.String getCompletionComments ()`
- `WorkItem.State getCompletionState ()`
- `java.lang.String getCompletionUser ()`
- `java.lang.String getEmailTemplate ()`
- `java.util.Date getExpiration ()`
- `java.lang.String getOwnerName ()`
- `java.lang.String getWorkItem ()`
- `WorkItem getWorkItem ( Resolver resolver)`
- `boolean hasName ()`
- `boolean isActive ()`
- `boolean isReturned ()`
- `protected void saveContext ( Identity who, java.lang.String workItem)`
- `void setActingWorkItem (java.lang.String workItem)`
- `void setActor ( Identity actor)`
- `void setActorDisplayName (java.lang.String name)`
- `void setActorName (java.lang.String actorName)`
- `void setComments (java.lang.String s)`
- `void setCompletionComments (java.lang.String s)`
- `void setCompletionState ( WorkItem.State s)`
- `void setCompletionUser (java.lang.String s)`
- `void setEmailTemplate (java.lang.String s)`
- `void setExpiration (java.util.Date d)`
- `void setOwnerName (java.lang.String s)`
- `void setWorkItem (java.lang.String s)`

---

## WorkItemOwnerChangeListener

**Package:** `sailpoint.object`

**Description:** A listener interface that classes can implement to be able to handle work items changing owners. This is not a typical listener or observer pattern in that the listener cannot register interest in the work item. The work item holds weak references (by ID) to the objects that can serve as listeners, so it must explicitly enumerate all possible listeners. If you implement this interface, you will need to modify some code around WorkItem.notifyOwnerChangeListeners() so that your class is notified when a work item owner is changed.

**Inherited Classes/Interfaces:** N/A

**Attributes:** N/A

**Methods:**
- `void workItemOwnerChanged ( Resolver resolver, WorkItem item, Identity newOwner, Identity previousOwner)`

---

## Workflow.Approval

**Package:** `sailpoint.object`

**Description:** Argument name used to pass a base path into a given approval.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Workflow.Approval`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String ARG_BASE_PATH`

**Methods:**
- `void add ( Workflow.Arg arg)`
- `void add ( Workflow.Return ret)`
- `void addArg (java.lang.String name, java.lang.String value)`
- `Attributes<java.lang.String,​java.lang.Object> bootstrapVariables ()`
- `boolean containsApprovalItems ()`
- `Workflow.Approval findApproval ( WorkItem item)`
- `java.lang.Object get (java.lang.String name)`
- `Script getAfterScript ()`
- `ApprovalSet getApprovalSet ()`
- `java.util.List<Workflow.Arg> getArgs ()`
- `java.util.List<Workflow.Approval> getChildren ()`
- `WorkItem.State getCompletionState ()`
- `java.lang.String getDescription ()`
- `Scriptlet getDescriptionSource ()`
- `boolean getEffectiveArchiveOption ()`
- `Workflow.Arg getEffectiveArg (java.lang.String name)`
- `Scriptlet getEffectiveDescriptionSource ()`
- `Form getEffectiveForm ()`
- `java.lang.String getEffectiveRenderer ()`
- `java.util.List<Workflow.Return> getEffectiveReturns ()`
- `java.util.List<java.lang.String> getEffectiveSends ()`
- `Workflow.Step getEffectiveStep ()`
- `Scriptlet getEffectiveValidationSource ()`
- `WorkItemConfig getEffectiveWorkItemConfig ()`
- `java.util.Date getEndDate ()`
- `Form getForm ()`
- `Identity getIdentity ()`
- `Script getInterceptorScript ()`
- `java.lang.String getMode ()`
- `Script getModeScript ()`
- `Scriptlet getModeSource ()`
- `java.lang.String getName ()`
- `java.lang.String getOriginalOwner ()`
- `java.lang.String getOwner ()`
- `Script getOwnerScript ()`
- `Scriptlet getOwnerSource ()`
- `Workflow.Approval getParent ()`
- `java.lang.String getRenderer ()`
- `java.lang.String getReturn ()`
- `java.util.List<java.lang.String> getReturnList ()`
- `java.util.List<Workflow.Return> getReturns ()`
- `java.lang.String getSend ()`
- `java.util.List<java.lang.String> getSendList ()`
- `java.util.Date getStartDate ()`
- `long getStartTime ()`
- `WorkItem.State getState ()`
- `Workflow.Step getStep ()`
- `java.lang.String getTag1 ()`
- `java.lang.String getTag2 ()`
- `java.lang.String getValidation ()`
- `Script getValidationScript ()`
- `Scriptlet getValidationSource ()`
- `java.lang.String getValidator ()`
- `Script getValidatorScript ()`
- `Attributes<java.lang.String,​java.lang.Object> getVariables ()`
- `WorkItem getWorkItem ()`
- `WorkItemConfig getWorkItemConfig ()`
- `java.lang.String getWorkItemDescription ()`
- `java.lang.String getWorkItemId ()`
- `void getWorkItems (java.util.List<java.lang.String> ids)`
- `WorkItem.Type getWorkItemType ()`
- `boolean isAny ()`
- `boolean isArchive ()`
- `boolean isAssimilated ()`
- `boolean isComplete ()`
- `boolean isMonitored ()`
- `boolean isParallel ()`
- `boolean isPoll ()`
- `boolean isRejected ()`
- `boolean isStarted ()`
- `void load ()`
- `void put (java.lang.String name, java.lang.Object value)`
- `void setAfterScript ( Script s)`
- `void setApprovalSet ( ApprovalSet set)`
- `void setArchive (boolean val)`
- `void setArgs (java.util.List< Workflow.Arg > args)`
- `void setAssimilated (boolean b)`
- `void setChildren (java.util.List< Workflow.Approval > l)`
- `void setComplete (boolean b)`
- `void setDescription (java.lang.String s)`
- `void setEndDate (java.util.Date d)`
- `void setForm ( Form f)`
- `void setIdentity ( Identity ident)`
- `void setInterceptorScript ( Script s)`
- `void setMode (java.lang.String mode)`
- `void setModeScript ( Script s)`
- `void setMonitored (boolean val)`
- `void setName (java.lang.String name)`
- `void setOriginalOwner (java.lang.String s)`
- `void setOwner (java.lang.String spec)`
- `void setOwnerScript ( Script s)`
- `void setParent ( Workflow.Approval a)`
- `void setRenderer (java.lang.String s)`
- `void setReturn (java.lang.String csv)`
- `void setReturns (java.util.List< Workflow.Return > returns)`
- `void setSend (java.lang.String csv)`
- `void setStartDate (java.util.Date d)`
- `void setStarted (boolean b)`
- `void setStartTime (long val)`
- `void setState ( WorkItem.State state)`
- `void setStep ( Workflow.Step s)`
- `void setTag1 (java.lang.String s)`
- `void setTag2 (java.lang.String s)`
- `void setValidation (java.lang.String s)`
- `void setValidationScript ( Script s)`
- `void setValidator (java.lang.String s)`
- `void setValidatorScript ( Script s)`
- `void setVariables ( Attributes <java.lang.String,java.lang.Object> vars)`
- `void setWorkItem ( WorkItem item)`
- `void setWorkItemConfig ( WorkItemConfig config)`
- `void setWorkItemDescription (java.lang.String s)`
- `void setWorkItemId (java.lang.String id)`
- `void setWorkItemType ( WorkItem.Type t)`

---

## Workflow.Arg

**Package:** `sailpoint.object`

**Description:** The representation of a argument whose value can be calculated at runtime. Do not confuse this with the Argument class which is used for the *definition* of arguments in a Signature which is not part of the workflow definition. There are three ways to specify the value of an argument: - a literal Object - a scriptlet to calculate the value - a Script to calculate the value Literal values are unique to Arg, you cannot specify literal values in the GWE, they are intended for use only with scripts or WorkflowHandler code that constructs Approval objects at runtime. When constructing runtime Approvals, you sometimes need to pass in information that is already represented as a Java object, such as a List or an ApprovalSet. Converting this into a Beanshell script that constructs a clone of that object is awkward instead the Arg can just be given the desired value which will then be passed along when the WorkItem is created.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Workflow.Arg`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.Object getLiteral ()`
- `java.lang.String getName ()`
- `Script getScript ()`
- `java.lang.String getValue ()`
- `Scriptlet getValueSource ()`
- `void load ()`
- `void setLiteral (java.lang.Object o)`
- `void setName (java.lang.String s)`
- `void setScript ( Script s)`
- `void setValue (java.lang.String s)`

---

## Workflow.Replicator

**Package:** `sailpoint.object`

**Description:** Class used to define a step replicator. Repliation is the process of repeating a step multiple times in parallel for each element of a list.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Workflow.Replicator`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getArg ()`
- `java.lang.String getItems ()`
- `void setArg (java.lang.String s)`
- `void setItems (java.lang.String s)`

---

## Workflow.Return

**Package:** `sailpoint.object`

**Description:** The representation of a return value from a step or approval. For Approval what you are doing is defining the things that will be copied from the WorkItem back into the workflow case. This is an alternative to using the "return" property that allows transformation of the name or value. For Step this is relevant only for subprocess calls, it defines the variables in the subcase to be copied up to the parent case.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Workflow.Return`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getEffectiveTo ()`
- `java.lang.String getName ()`
- `Script getScript ()`
- `java.lang.String getTo ()`
- `java.lang.String getValue ()`
- `Scriptlet getValueSource ()`
- `boolean isLocal ()`
- `boolean isMerge ()`
- `boolean isValueScripted ()`
- `void load ()`
- `void setLocal (boolean b)`
- `void setMerge (boolean b)`
- `void setName (java.lang.String s)`
- `void setScript ( Script s)`
- `void setTo (java.lang.String s)`
- `void setValue (java.lang.String s)`

---

## Workflow.Step.Icon

**Package:** `sailpoint.object`

**Description:** Icons for the UI - See workflow-editor.css for icon classes

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Workflow.Step.Icon`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getName ()`
- `java.lang.String getStyleClass ()`
- `java.lang.String getText ()`
- `boolean isDefaultIcon ()`
- `void setDefaultIcon (boolean defaultIcon)`
- `void setName (java.lang.String name)`
- `void setStyleClass (java.lang.String styleClass)`
- `void setText (java.lang.String text)`

---

## Workflow.Step

**Package:** `sailpoint.object`

**Description:** Structurally a step can be one of three types: action - an immediate action workflow - the invocation of a workflow subprocess approval - model representing a complex approval process All step types can contain a list of Arg objects that define names and values of attributes to be passed into the step handler. Step handler is an abstract concept not a Java interface. Step handlers are all implemented by the Workflower class. Action steps can use either a scriptlet or a Script to define the action. When using scriptlets, the "string" and "ref" method are not relevant. The default method is "call". The list of Args is evaluated and passed to the action handler or workflow subprocess.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Workflow.Step`
- `java.io.Serializable`
- `sailpoint.tools.xml.IXmlEqualable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void add ( Workflow.Transition t)`
- `void addWorkflowCase ( WorkflowCase wfcase)`
- `boolean areSubcasesComplete ()`
- `boolean contentEquals (java.lang.Object other)`
- `Workflow.Approval findApproval ( WorkItem item)`
- `java.lang.String getAction ()`
- `Scriptlet getActionSource ()`
- `Workflow.Approval getApproval ()`
- `java.util.List<Workflow.Arg> getArgs ()`
- `java.lang.String getCatches ()`
- `java.lang.String getCondition ()`
- `Script getConditionScript ()`
- `Scriptlet getConditionSource ()`
- `java.lang.String getConfigForm ()`
- `java.lang.String getDescription ()`
- `java.lang.String getIcon ()`
- `java.lang.String getId ()`
- `java.lang.String getName ()`
- `java.lang.String getNameOrId ()`
- `int getPosX ()`
- `int getPosY ()`
- `Workflow.Replicator getReplicator ()`
- `java.lang.String getResultVariable ()`
- `java.util.List<Workflow.Return> getReturns ()`
- `Script getScript ()`
- `long getStartTime ()`
- `Workflow getSubProcess ()`
- `java.util.List<Workflow.Transition> getTransitions ()`
- `java.lang.String getWait ()`
- `Scriptlet getWaitSource ()`
- `Workflow getWorkflow ()`
- `java.util.List<WorkflowCase> getWorkflowCases ()`
- `java.lang.String getWorkItemId ()`
- `void getWorkItems (java.util.List<java.lang.String> ids)`
- `boolean hasWaitTimeout ()`
- `boolean isBackground ()`
- `boolean isComplete ()`
- `boolean isHidden ()`
- `boolean isMonitored ()`
- `void load ()`
- `void remove ( Workflow.Transition t)`
- `void setAction (java.lang.String s)`
- `void setApproval ( Workflow.Approval app)`
- `void setArgs (java.util.List< Workflow.Arg > args)`
- `void setBackground (boolean b)`
- `void setCatches (java.lang.String s)`
- `void setComplete (boolean b)`
- `void setCondition (java.lang.String s)`
- `void setConditionScript ( Script s)`
- `void setConfigForm (java.lang.String configForm)`
- `void setDescription (java.lang.String s)`
- `void setHidden (boolean b)`
- `void setIcon (java.lang.String _icon)`
- `void setId (java.lang.String id)`
- `void setMonitored (boolean val)`
- `void setName (java.lang.String name)`
- `void setPosX (int _posx)`
- `void setPosY (int _posy)`
- `void setReplicator ( Workflow.Replicator r)`
- `void setResultVariable (java.lang.String name)`
- `void setReturns (java.util.List< Workflow.Return > returns)`
- `void setScript ( Script app)`
- `void setStartTime (long val)`
- `void setSubProcess ( Workflow wf)`
- `void setTransitions (java.util.List< Workflow.Transition > trans)`
- `void setWait (java.lang.String wait)`
- `void setWaitSource ( Scriptlet source)`
- `void setWaitTimeout (boolean waitTimeout)`
- `void setWorkflow ( Workflow wf)`
- `void setWorkflowCases (java.util.List< WorkflowCase > l)`
- `void setWorkItemId (java.lang.String workItemId)`

---

## Workflow.Transition

**Package:** `sailpoint.object`

**Description:** Represents a transition from one step to another. The transition can be conditional. Conditions are specified either as a scriptlet using the "when" property, or as a complex multi-line script using the "script" property. The default evaluation method for the when property is script: This is equivalent:

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.Workflow.Transition`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `Script getScript ()`
- `java.lang.String getTo ()`
- `Scriptlet getToSource ()`
- `java.lang.String getWhen ()`
- `Scriptlet getWhenSource ()`
- `boolean isTo ( Workflow.Step s)`
- `boolean isUnconditional ()`
- `void load ()`
- `void setScript ( Script s)`
- `void setTo (java.lang.String s)`
- `void setWhen (java.lang.String s)`

---

## Workflow.Variable

**Package:** `sailpoint.object`

**Description:** Definition of a workflow variable. You do not have to define variables, but it is good for documentation and the inevitable UI. BaseAttributeDefinition gives us name, displayName, type, multi, description, and defaultValue. Argument provides required, prompt, helpKey, and filter.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.BaseAttributeDefinition`
- `sailpoint.object.Argument`
- `sailpoint.object.Workflow.Variable`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getInitializer ()`
- `Scriptlet getInitializerSource ()`
- `Script getScript ()`
- `boolean isEditable ()`
- `boolean isInput ()`
- `boolean isOutput ()`
- `boolean isTransient ()`
- `void setEditable (boolean b)`
- `void setInitializer (java.lang.String s)`
- `void setInput (boolean b)`
- `void setOutput (boolean b)`
- `void setScript ( Script s)`
- `void setTransient (boolean b)`

---

## Workflow

**Package:** `sailpoint.object`

**Description:** The representation of a argument whose value can be calculated at runtime.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.Workflow`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String APPROVAL_TYPE_DELETE`
- `static java.lang.String APPROVAL_TYPE_ROLLBACK`
- `static java.lang.String ApprovalModeAny`
- `static java.lang.String ApprovalModeParallel`
- `static java.lang.String ApprovalModeParallelPoll`
- `static java.lang.String ApprovalModeSerial`
- `static java.lang.String ApprovalModeSerialPoll`
- `static java.lang.String ARG_INTEGRATION`
- `static java.lang.String ARG_METHOD`
- `static java.lang.String ARG_WORK_ITEM_ARCHIVE`
- `static java.lang.String ARG_WORK_ITEM_DESCRIPTION`
- `static java.lang.String ARG_WORK_ITEM_DISABLE_NOTIFICATION`
- `static java.lang.String ARG_WORK_ITEM_ESCALATION_RULE`
- `static java.lang.String ARG_WORK_ITEM_ESCALATION_STYLE`
- `static java.lang.String ARG_WORK_ITEM_ESCALATION_TEMPLATE`
- `static java.lang.String ARG_WORK_ITEM_HOURS_BETWEEN_REMINDERS`
- `static java.lang.String ARG_WORK_ITEM_HOURS_TILL_ESCALATION`
- `static java.lang.String ARG_WORK_ITEM_IDENTITY_REQUEST_ID`
- `static java.lang.String ARG_WORK_ITEM_MAX_REMINDERS`
- `static java.lang.String ARG_WORK_ITEM_NOTIFICATION_TEMPLATE`
- `static java.lang.String ARG_WORK_ITEM_PRIORITY`
- `static java.lang.String ARG_WORK_ITEM_REMINDER_TEMPLATE`
- `static java.lang.String ARG_WORK_ITEM_REQUESTER`
- `static java.lang.String ARG_WORK_ITEM_TARGET_CLASS`
- `static java.lang.String ARG_WORK_ITEM_TARGET_ID`
- `static java.lang.String ARG_WORK_ITEM_TARGET_NAME`
- `static java.lang.String ARG_WORK_ITEM_TYPE`
- `static java.lang.String ATT_BACKGROUNDED_ORIGINAL_ITEM_TYPE`
- `static java.lang.String CATCH_COMPLETE`
- `static java.lang.String DEFAULT_ARGUMENT_NAME_DELIMITER`
- `static java.lang.String INTERCEPTOR_ARCHIVE`
- `static java.lang.String INTERCEPTOR_CANCEL_APPROVAL`
- `static java.lang.String INTERCEPTOR_END_APPROVAL`
- `static java.lang.String INTERCEPTOR_OPEN_WORK_ITEM`
- `static java.lang.String INTERCEPTOR_POST_ASSIMILATION`
- `static java.lang.String INTERCEPTOR_PRE_ASSIMILATION`
- `static java.lang.String INTERCEPTOR_START_APPROVAL`
- `static java.lang.String MS_TEAMS`
- `static java.lang.String TYPE_ALERT_PROCESSING`
- `static java.lang.String TYPE_ATTRIBUTE_SYNC`
- `static java.lang.String TYPE_IDENTITY_CORRELATION`
- `static java.lang.String TYPE_IDENTITY_EVENT`
- `static java.lang.String TYPE_IDENTITY_LIFECYCLE`
- `static java.lang.String TYPE_IDENTITY_REFRESH`
- `static java.lang.String TYPE_IDENTITY_UPDATE`
- `static java.lang.String TYPE_LCM_IDENTITY`
- `static java.lang.String TYPE_LCM_PROVISIONING`
- `static java.lang.String TYPE_LCM_SELF_SERVICE_REGISTRATION`
- `static java.lang.String TYPE_MANAGED_ATTRIBUTE`
- `static java.lang.String TYPE_MULTI_FACTOR_AUTHENTICATION`
- `static java.lang.String TYPE_PAM_PROVISIONING`
- `static java.lang.String TYPE_PASSWORD_INTERCEPT`
- `static java.lang.String TYPE_POLICY_VIOLATION`
- `static java.lang.String TYPE_ROLE_MODELER`
- `static java.lang.String TYPE_SCHEDULED_ASSIGNMENT`
- `static java.lang.String TYPE_SCHEDULED_ROLE_ACTIVATION`
- `static java.lang.String TYPE_SUBPROCESS`
- `static java.lang.String VAR_APPROVAL_OBJECT`
- `static java.lang.String VAR_APPROVAL_SET`
- `static java.lang.String VAR_APPROVAL_TYPE`
- `static java.lang.String VAR_APPROVED`
- `static java.lang.String VAR_APPROVER`
- `static java.lang.String VAR_ARGUMENT_NAME_DELIMITER`
- `static java.lang.String VAR_BACKGROUND_APPROVAL_COMPLETION`
- `static java.lang.String VAR_BACKGROUND_APPROVAL_COMPLETION_IF_LOCKED`
- `static java.lang.String VAR_BACKGROUND_THREAD_TIMEOUT`
- `static java.lang.String VAR_CAPTURE`
- `static java.lang.String VAR_CAPTURE_FILE`
- `static java.lang.String VAR_CAPTURE_OBJECT`
- `static java.lang.String VAR_CASE_RESULT`
- `static java.lang.String VAR_CASE_STATUS`
- `static java.lang.String VAR_INITIAL_COMMENT`
- `static java.lang.String VAR_LAST_APPROVAL_STATE`
- `static java.lang.String VAR_LAUNCHER`
- `static java.lang.String VAR_NO_SUBCASE_PRUNING`
- `static java.lang.String VAR_PUBLISH_CALL_TIMINGS`
- `static java.lang.String VAR_RESULT_EXPIRATION`
- `static java.lang.String VAR_SESSION_OWNER`
- `static java.lang.String VAR_TASK_RESULT`
- `static java.lang.String VAR_TERMINATED`
- `static java.lang.String VAR_TRACE`
- `static java.lang.String VAR_TRANSIENT`
- `static java.lang.String VAR_WORK_ITEM_COMMENTS`

**Methods:**
- `void add ( Workflow.Variable var)`
- `Attributes<java.lang.String,​java.lang.Object> bootstrapVariables ()`
- `Workflow.Approval findApproval ( WorkItem item)`
- `Workflow.Step findStepById (java.lang.String id)`
- `Workflow.Step findStepById (java.lang.String id, boolean recurse)`
- `Workflow.Step findStepByName (java.lang.String name)`
- `java.lang.Object get (java.lang.String name)`
- `SailPointObject getApprovalObject ()`
- `java.lang.String getArgumentNameDelimiter ()`
- `boolean getBoolean (java.lang.String name)`
- `Workflow.Step getCatchStep (java.lang.String condition)`
- `java.lang.String getConfigForm ()`
- `java.lang.String getCurrentStep ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `java.lang.String getHandler ()`
- `int getInt (java.lang.String name)`
- `java.lang.String getLibraries ()`
- `java.lang.String getProcessLogId ()`
- `int getResultExpiration ()`
- `java.util.List<Rule> getRuleLibraries ()`
- `long getStartTime ()`
- `sailpoint.tools.StateDiagram getStateDiagram ()`
- `Workflow.Step getStep (java.lang.String name)`
- `java.util.List<Workflow.Step> getSteps ()`
- `java.lang.String getString (java.lang.String name)`
- `TaskItemDefinition.Type getTaskType ()`
- `java.lang.String getType ()`
- `Workflow.Variable getVariableDefinition (java.lang.String name)`
- `java.util.List<Workflow.Variable> getVariableDefinitions ()`
- `Attributes<java.lang.String,​java.lang.Object> getVariables ()`
- `WorkItemConfig getWorkItemConfig ()`
- `java.lang.String getWorkItemRenderer ()`
- `java.util.List<java.lang.String> getWorkItems ()`
- `void getWorkItems (java.util.List<java.lang.String> ids)`
- `boolean isAnyMonitoring ()`
- `boolean isComplete ()`
- `boolean isDeleteApproval ()`
- `boolean isExplicitTransitions ()`
- `boolean isMonitored ()`
- `boolean isRollbackApproval ()`
- `boolean isTemplate ()`
- `void layout ()`
- `void layout (sailpoint.tools.StateDiagram diagram)`
- `void promoteImplicitTransitions ()`
- `void put (java.lang.String name, java.lang.Object value)`
- `void restoreImplicitTransitions ()`
- `void setComplete (boolean b)`
- `void setConfigForm (java.lang.String configForm)`
- `void setCurrentStep (java.lang.String id)`
- `void setExplicitTransitions (boolean transitions)`
- `void setHandler (java.lang.String s)`
- `void setLibraries (java.lang.String s)`
- `void setMonitored (boolean val)`
- `void setProcessLogId (java.lang.String val)`
- `void setResultExpiration (int i)`
- `void setRuleLibraries (java.util.List< Rule > ruleLibraries)`
- `void setStartTime (long val)`
- `void setSteps (java.util.List< Workflow.Step > steps)`
- `void setTaskType ( TaskItemDefinition.Type type)`
- `void setTemplate (boolean b)`
- `void setType (java.lang.String s)`
- `void setVariableDefinitions (java.util.List< Workflow.Variable > vars)`
- `void setVariables ( Attributes <java.lang.String,java.lang.Object> vars)`
- `void setWorkItemConfig ( WorkItemConfig config)`
- `void setWorkItemRenderer (java.lang.String s)`
- `void visit ( Visitor v)`

---

## WorkflowCase

**Package:** `sailpoint.object`

**Description:** The name of a TaskResult variable that holds the database id of the WorkflowCase.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.TaskItem`
- `sailpoint.object.WorkflowCase`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.api.MessageAccumulator`
- `sailpoint.api.MessageRepository`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String RES_WORKFLOW_CASE`
- `static java.lang.String RES_WORKFLOW_PROCESS_ID`
- `static java.lang.String RES_WORKFLOW_SUMMARY`

**Methods:**
- `java.util.List<ProcessLog> clearQueuedProcessLog ()`
- `java.lang.Object get (java.lang.String name)`
- `SailPointObject getApprovalObject ()`
- `java.lang.String getBackgroundItemId ()`
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `java.util.List<ProcessLog> getQueuedProcessLog ()`
- `java.util.List<WorkflowTarget> getSecondaryTargets ()`
- `java.lang.String getString (java.lang.String name)`
- `java.lang.String getTargetClass ()`
- `java.lang.String getTargetId ()`
- `java.lang.String getTargetName ()`
- `TaskResult getTaskResult ()`
- `TaskResult getTaskResult ( Resolver r)`
- `java.lang.String getTaskResultId ()`
- `Workflow getWorkflow ()`
- `void initWorkflow ( Workflow src, sailpoint.tools.xml.XMLReferenceResolver r)`
- `boolean isAutoCreated ()`
- `boolean isComplete ()`
- `boolean isDeleteApproval ()`
- `boolean isRollbackApproval ()`
- `void load ()`
- `void put (java.lang.String name, java.lang.Object value)`
- `void queueProcessLog ( ProcessLog pl)`
- `void setBackgroundItemId (java.lang.String id)`
- `void setQueuedProcessLog (java.util.List< ProcessLog > processLog)`
- `void setSecondaryTargets (java.util.List< WorkflowTarget > val)`
- `void setTargetClass (java.lang.String targetClass)`
- `void setTargetId (java.lang.String targetId)`
- `void setTargetName (java.lang.String _targetName)`
- `void setTaskResult ( TaskResult res)`
- `void setTaskResultId (java.lang.String id)`
- `void setVariables (java.util.Map<java.lang.String,java.lang.Object> vars)`
- `void visit ( Visitor v)`

---

## WorkflowLaunch

**Package:** `sailpoint.object`

**Description:** Indicates that the case ran to an approval and is now suspended.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.WorkflowLaunch`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:**
- `static java.lang.String STATUS_APPROVING`
- `static java.lang.String STATUS_COMPLETE`
- `static java.lang.String STATUS_EXECUTING`
- `static java.lang.String STATUS_FAILED`
- `static java.lang.String STATUS_UNDEFINED`

**Methods:**
- `void addMessage ( Message msg)`
- `void addMessages (java.util.List< Message > msgs)`
- `java.lang.Object get (java.lang.String name)`
- `java.lang.String getBackgroundItemId ()`
- `java.lang.String getCaseName ()`
- `java.lang.String getLauncher ()`
- `java.util.List<Message> getMessages ()`
- `java.util.List<WorkflowTarget> getSecondaryTargets ()`
- `java.lang.String getSessionOwner ()`
- `java.lang.String getStatus ()`
- `java.lang.String getTargetClass ()`
- `java.lang.String getTargetId ()`
- `java.lang.String getTargetName ()`
- `TaskResult getTaskResult ()`
- `java.util.Map<java.lang.String,​java.lang.Object> getVariables ()`
- `WorkflowCase getWorkflowCase ()`
- `WorkflowContext getWorkflowContext ()`
- `java.lang.String getWorkflowName ()`
- `java.lang.String getWorkflowRef ()`
- `boolean isApproving ()`
- `boolean isComplete ()`
- `boolean isExecuting ()`
- `boolean isFailed ()`
- `boolean isPrivateSailPointContext ()`
- `boolean isUndefined ()`
- `void put (java.lang.String name, java.lang.Object value)`
- `void setBackgroundItemId (java.lang.String id)`
- `void setCaseName (java.lang.String s)`
- `void setLauncher (java.lang.String s)`
- `void setMessages (java.util.List< Message > messages)`
- `void setPrivateSailPointContext (boolean b)`
- `void setSecondaryTargets (java.util.List< WorkflowTarget > val)`
- `void setSessionOwner (java.lang.String s)`
- `void setStatus (java.lang.String s)`
- `void setTarget ( SailPointObject obj)`
- `void setTargetClass (java.lang.Class cls)`
- `void setTargetClass (java.lang.String s)`
- `void setTargetId (java.lang.String s)`
- `void setTargetName (java.lang.String s)`
- `void setTaskResult ( TaskResult result)`
- `void setVariables (java.util.Map<java.lang.String,java.lang.Object> vars)`
- `void setWorkflow ( Workflow wf)`
- `void setWorkflowCase ( WorkflowCase wc)`
- `void setWorkflowContext ( WorkflowContext wfc)`
- `void setWorkflowName (java.lang.String s)`
- `void setWorkflowRef (java.lang.String s)`

---

## WorkflowRegistry.Callable

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.WorkflowRegistry.Callable`
- `java.io.Serializable`
- `sailpoint.tools.xml.IXmlEqualable<WorkflowRegistry.Callable>`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `boolean contentEquals ( WorkflowRegistry.Callable other)`
- `boolean equals (java.lang.Object o)`
- `java.lang.String getDescriptionKey ()`
- `WorkflowRegistry.Library getLibrary ()`
- `java.lang.String getName ()`
- `java.util.List<Argument> getRequiredArguments ()`
- `WorkflowRegistry.CallableType getType ()`
- `void setDescriptionKey (java.lang.String description)`
- `void setLibrary ( WorkflowRegistry.Library library)`
- `void setName (java.lang.String name)`
- `void setRequiredArguments (java.util.List< Argument > requiredArguments)`
- `void setType ( WorkflowRegistry.CallableType type)`

---

## WorkflowRegistry.CallableType

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `WorkflowRegistry.CallableType`
- `sailpoint.object.WorkflowRegistry.CallableType`
- `java.io.Serializable`
- `java.lang.Comparable<WorkflowRegistry.CallableType>`

**Attributes:** N/A

**Methods:**
- `staticWorkflowRegistry.CallableType valueOf (java.lang.String name)`
- `staticWorkflowRegistry.CallableType[] values ()`

---

## WorkflowRegistry.Library

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `WorkflowRegistry.Library`
- `sailpoint.object.WorkflowRegistry.Library`
- `java.io.Serializable`
- `java.lang.Comparable<WorkflowRegistry.Library>`

**Attributes:** N/A

**Methods:**
- `staticWorkflowRegistry.Library valueOf (java.lang.String name)`
- `staticWorkflowRegistry.Library[] values ()`

---

## WorkflowRegistry.WorkflowType

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.WorkflowRegistry.WorkflowType`
- `java.io.Serializable`
- `sailpoint.tools.xml.IXmlEqualable<WorkflowRegistry.WorkflowType>`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `boolean contentEquals ( WorkflowRegistry.WorkflowType other)`
- `boolean equals (java.lang.Object o)`
- `java.lang.String getDisplayNameKey ()`
- `java.lang.String getHelpKey ()`
- `java.util.List<WorkflowRegistry.Library> getLibraries ()`
- `java.lang.String getName ()`
- `java.lang.String getStepLibraries ()`
- `boolean isLCM ()`
- `void setDisplayNameKey (java.lang.String displayNameKey)`
- `void setHelpKey (java.lang.String helpKey)`
- `void setLCM (boolean val)`
- `void setLibraries (java.util.List< WorkflowRegistry.Library > libraries)`
- `void setName (java.lang.String name)`
- `void setStepLibraries (java.lang.String stepLibraries)`

---

## WorkflowRegistry

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.WorkflowRegistry`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:**
- `static java.lang.String ATTR_APPROVAL_MODES`
- `static java.lang.String ATTR_ICONS`
- `static java.util.Comparator<WorkflowRegistry.Callable> CALLABLE_COMPARATOR`
- `static java.lang.String DEFAULT_WORKFLOW_REG`
- `static java.lang.String WORKFLOW_ICON_CATCHES`
- `static java.lang.String WORKFLOW_ICON_START`
- `static java.lang.String WORKFLOW_ICON_STOP`

**Methods:**
- `java.lang.Object getAttribute (java.lang.String attributeName)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.util.List<WorkflowRegistry.Callable> getCallables ()`
- `java.util.List<WorkflowRegistry.Callable> getCallables (java.lang.String typeString)`
- `staticWorkflowRegistry getInstance ( Resolver ctx)`
- `java.util.List<Workflow.Step> getTemplates ()`
- `java.util.List<WorkflowRegistry.WorkflowType> getTypes ()`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attributes)`
- `void setCallables (java.util.List< WorkflowRegistry.Callable > callables)`
- `void setTemplates (java.util.List< Workflow.Step > templates)`
- `void setTypes (java.util.List< WorkflowRegistry.WorkflowType > types)`

---

## WorkflowSummary.ApprovalSummary

**Package:** `sailpoint.object`

**Description:** Helper class to represent the status of a single approval.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.WorkflowSummary.ApprovalSummary`

**Attributes:** N/A

**Methods:**
- `void addComment ( Comment comments)`
- `void assimilate ( Workflow.Approval app)`
- `ApprovalSet getApprovalSet ()`
- `java.util.List<Comment> getComments ()`
- `java.lang.String getCompleter ()`
- `java.util.Date getEndDate ()`
- `java.lang.String getOwner ()`
- `java.lang.String getOwnerId ()`
- `java.lang.String getRequest ()`
- `SignOffHistory getSignOff ()`
- `java.util.Date getStartDate ()`
- `WorkItem.State getState ()`
- `java.lang.String getStateKey ()`
- `java.lang.String getTypeKey ()`
- `java.lang.String getWorkItemId ()`
- `WorkItem.Type getWorkItemType ()`
- `boolean isApproved ()`
- `void setApprovalSet ( ApprovalSet set)`
- `void setComments (java.util.List< Comment > comments)`
- `void setCompleter (java.lang.String _completer)`
- `void setEndDate (java.util.Date d)`
- `void setOwner (java.lang.String s)`
- `void setOwnerId (java.lang.String s)`
- `void setRequest (java.lang.String s)`
- `void setSignOff ( SignOffHistory signOff)`
- `void setStartDate (java.util.Date d)`
- `void setState ( WorkItem.State s)`
- `void setWorkItemId (java.lang.String s)`
- `void setWorkItemType ( WorkItem.Type type)`

---

## WorkflowSummary

**Package:** `sailpoint.object`

**Description:** Helper class to represent the status of a single approval.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.WorkflowSummary`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void addInteraction ( Workflow.Approval app)`
- `void addInteraction ( WorkflowSummary.ApprovalSummary sum)`
- `java.lang.String getApproval ()`
- `java.util.List<WorkflowSummary.ApprovalSummary> getApprovals ()`
- `ApprovalSet getApprovalSet ()`
- `java.util.List<Message> getErrors ()`
- `int getInteractionCount ()`
- `java.util.List<WorkflowSummary.ApprovalSummary> getInteractions ()`
- `java.util.List<WorkflowSummary.ApprovalSummary> getPending ()`
- `java.util.List<WorkflowSummary.ApprovalSummary> getRejections ()`
- `java.lang.String getStep ()`
- `void internInteraction ( Workflow.Approval app)`
- `void replaceInteraction ( WorkflowSummary.ApprovalSummary neu)`
- `void setApproval (java.lang.String phase)`
- `void setApprovals (java.util.List< WorkflowSummary.ApprovalSummary > apps)`
- `void setApprovalSet ( ApprovalSet set)`
- `void setErrors (java.util.List< Message > errors)`
- `void setInteractions (java.util.List< WorkflowSummary.ApprovalSummary > apps)`
- `void setPending (java.util.List< WorkflowSummary.ApprovalSummary > apps)`
- `void setRejections (java.util.List< WorkflowSummary.ApprovalSummary > apps)`
- `void setStep (java.lang.String name)`

---

## WorkflowTarget

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.WorkflowTarget`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `java.lang.String getClassName ()`
- `java.lang.String getObjectId ()`
- `java.lang.String getObjectName ()`
- `WorkflowCase getWorkflowCase ()`
- `void setClassName (java.lang.String className)`
- `void setObjectId (java.lang.String objectId)`
- `void setObjectName (java.lang.String objectName)`
- `void setWorkflowCase ( WorkflowCase workflowCase)`

---

## WorkflowTestSuite.WorkItemAction

**Package:** `sailpoint.object`

**Description:** An object that defines one action to take on the work item. There are thre styles of action: variable, field, and approval. Variable actions set the value of one work item variable. Field actions set the value of one Form Field. Approval actions set things in one ApprovalItem. Approval actions need to be able to set these things in an ApprovalItem. state - approved or rejected comments - comments added during approval approver - who actually approved rejecters - csv of people who rejected Everything else in an Approval Item is read-only as far as I can tell. State will be taken from our _value, set it to the Strings "approved" or "rejected". We could probably simplify comments and just have a List

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.WorkflowTestSuite.WorkItemAction`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `java.lang.String getApproval ()`
- `java.lang.String getApprover ()`
- `java.lang.String getAssignmentId ()`
- `java.util.List<Comment> getComments ()`
- `java.lang.String getField ()`
- `java.lang.String getRejecters ()`
- `WorkItem.State getState ()`
- `java.lang.Object getValue ()`
- `java.lang.String getVariable ()`
- `void setApproval (java.lang.String s)`
- `void setApprover (java.lang.String s)`
- `void setAssignmentId (java.lang.String s)`
- `void setComments (java.util.List< Comment > comments)`
- `void setField (java.lang.String s)`
- `void setRejecters (java.lang.String s)`
- `void setState ( WorkItem.State s)`
- `void setValue (java.lang.Object value)`
- `void setVariable (java.lang.String s)`

---

## WorkflowTestSuite.WorkItemResponse

**Package:** `sailpoint.object`

**Description:** An object that defines the response to one work item.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.WorkflowTestSuite.WorkItemResponse`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void add ( WorkflowTestSuite.WorkItemAction action)`
- `java.util.List<WorkflowTestSuite.WorkItemAction> getActions ()`
- `java.util.List<Comment> getComments ()`
- `java.lang.String getCompletionComments ()`
- `java.lang.String getInclude ()`
- `java.lang.String getName ()`
- `java.lang.String getOwner ()`
- `WorkItem.State getState ()`
- `java.lang.String getWorkItemId ()`
- `void setActions (java.util.List< WorkflowTestSuite.WorkItemAction > actions)`
- `void setComments (java.util.List< Comment > comments)`
- `void setCompletionComments (java.lang.String s)`
- `void setInclude (java.lang.String s)`
- `void setName (java.lang.String s)`
- `void setOwner (java.lang.String s)`
- `void setState ( WorkItem.State s)`
- `void setWorkItemId (java.lang.String s)`

---

## WorkflowTestSuite.WorkflowTest

**Package:** `sailpoint.object`

**Description:** A suite consists of one or more tests. The test defines the workflow definition to execute, the input variables, and the sequence of work item responses.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.WorkflowTestSuite.WorkflowTest`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`

**Attributes:** N/A

**Methods:**
- `void add ( WorkflowTestSuite.WorkItemResponse res)`
- `void addFinishedResponse ( WorkflowTestSuite.WorkItemResponse finished)`
- `void captureWorkflowLaunch (sailpoint.tools.xml.XMLReferenceResolver resolver, WorkflowLaunch src)`
- `void clearStubResponses ()`
- `java.lang.String getName ()`
- `WorkflowTestSuite.WorkItemResponse getNextResponse ()`
- `int getNextResponseIndex ()`
- `WorkflowTestSuite.WorkItemResponse getResponse (java.lang.String name)`
- `java.util.List<WorkflowTestSuite.WorkItemResponse> getResponses ()`
- `WorkflowLaunch getWorkflowLaunch ()`
- `boolean hasMoreResponses ()`
- `WorkflowTestSuite.WorkItemResponse removeStubResponse (java.lang.String id)`
- `void resetResponses ()`
- `void setName (java.lang.String s)`
- `void setNextResponseIndex (int i)`
- `void setResponses (java.util.List< WorkflowTestSuite.WorkItemResponse > responses)`
- `void setWorkflowLaunch ( WorkflowLaunch launch)`

---

## WorkflowTestSuite

**Package:** `sailpoint.object`

**Description:** A suite consists of one or more tests.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.WorkflowTestSuite`
- `java.io.Serializable`
- `java.lang.Cloneable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `void add ( WorkflowTestSuite.WorkflowTest test)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `java.lang.String getCaseName ()`
- `java.lang.String getFile ()`
- `WorkflowTestSuite.WorkflowTest getPrimaryTest ()`
- `WorkflowTestSuite.WorkItemResponse getResponse (java.lang.String name)`
- `java.util.List<WorkflowTestSuite.WorkItemResponse> getResponses ()`
- `WorkflowTestSuite.WorkflowTest getTest (java.lang.String name)`
- `java.util.List<WorkflowTestSuite.WorkflowTest> getTests ()`
- `boolean hasAssignedScope ()`
- `boolean isReplicated ()`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> a)`
- `void setCaseName (java.lang.String s)`
- `void setFile (java.lang.String s)`
- `void setReplicated (boolean b)`
- `void setResponses (java.util.List< WorkflowTestSuite.WorkItemResponse > responses)`
- `void setTests (java.util.List< WorkflowTestSuite.WorkflowTest > tests)`

---

## XMLResolverProxy

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.object.XMLResolverProxy`
- `sailpoint.tools.xml.XMLReferenceResolver`

**Attributes:** N/A

**Methods:**
- `java.lang.Class getClass (java.lang.String cls)`
- `java.lang.Object getReferencedObject (java.lang.String className, java.lang.String id, java.lang.String name)`

---

## YAMLConfig.SubType

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `YAMLConfig.SubType`
- `sailpoint.object.YAMLConfig.SubType`
- `java.io.Serializable`
- `java.lang.Comparable<YAMLConfig.SubType>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticYAMLConfig.SubType valueOf (java.lang.String name)`
- `staticYAMLConfig.SubType[] values ()`

---

## YAMLConfig.Type

**Package:** `sailpoint.object`

**Description:** Returns the enum constant of this type with the specified name.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `YAMLConfig.Type`
- `sailpoint.object.YAMLConfig.Type`
- `java.io.Serializable`
- `java.lang.Comparable<YAMLConfig.Type>`

**Attributes:** N/A

**Methods:**
- `java.lang.String getMessageKey ()`
- `staticYAMLConfig.Type valueOf (java.lang.String name)`
- `staticYAMLConfig.Type[] values ()`

---

## YAMLConfig

**Package:** `sailpoint.object`

**Description:** N/A

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.tools.xml.AbstractXmlObject`
- `sailpoint.object.SailPointObject`
- `sailpoint.object.YAMLConfig`
- `java.io.Serializable`
- `sailpoint.tools.xml.PersistentXmlObject`
- `sailpoint.tools.xml.XMLReferenceTarget`

**Attributes:** N/A

**Methods:**
- `static java.util.Map<java.lang.String,​java.lang.String> getDisplayColumns ()`
- `static java.lang.String getDisplayFormat ()`
- `YAMLConfig.SubType getSubtype ()`
- `YAMLConfig.Type getType ()`
- `java.lang.String getYamlText ()`
- `void setSubtype ( YAMLConfig.SubType subtype)`
- `void setType ( YAMLConfig.Type type)`
- `void setYamlText (java.lang.String yamlText)`

---

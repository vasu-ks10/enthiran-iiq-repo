# SailPoint Connector Classes Details

## AbstractConnector

**Package:** `sailpoint.connector`

**Description:** A base abstract connector that is intended to be extended by all Connector classes. Extending this class instead of implementing the Connector interface directly will allow the Connector interface to be extended without breaking old code. All of the Connectors that extend this class will call the one of the two constructors that take an Application and an optional instance. The application object will configure the runtime Attributes and Features of the connector. This class will implement any new methods that are added over time and in most cases will just throw UnsupportedOperation exception when the methods has been stubbed out. Along with stubbing out the Connector interface it also provides methods for the following common services: Reading and coercing configuration attributes from Application data CollectorServices.getAttribute(String) CollectorServices.getStringAttribute(String) CollectorServices.getBooleanAttribute(String) CollectorServices.getListAttribute(String) CollectorServices.getEncryptedAttribute(String) CollectorServices.getRequiredAttribute(String) CollectorServices.getRequiredStringAttribute(String) CollectorServices.getRequiredListAttribute(String) CollectorServices.getRequiredEncryptedAttribute(String) CollectorServices.getRequiredListAttribute(String) CollectorServices.getSchemaConfig(Schema, String) Permissions Merging mergePermissions(List, List) Map Merging mergeMaps(Schema, Map, Map, List) defaultMergeMaps(Map, Map, List) Building ResourceObjects from java.util.Map objects defaultTransformObject(Schema, Map) defaultTransformObject(Schema, Map, boolean) defaultTransformObject(Schema, Map, boolean, List) Coercing attribute values based on AttributeDefinition CollectorServices.coerceValue(AttributeDefinition, Object)

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.connector.CollectorServices`
- `sailpoint.connector.AbstractConnector`
- `Connector`

**Attributes:**
- `protected java.util.Map<java.lang.String,​java.lang.Object> _state`
- `static java.lang.String CONFIG_DONT_TRANSFORM_CSV`
- `static java.lang.String CONFIG_DONT_TRANSFORM_CSV_ATTRS`
- `static java.lang.String CONFIG_FILTER_STRING`
- `static java.lang.String CONFIG_PAGE_SIZE`
- `static java.lang.String CONFIG_RETRYABLE_ERRORS`
- `static int DEFAULT_PAGE_SIZE`
- `static java.lang.String RESPONSE_DATA_KEY`

**Methods:**
- `ResourceObject authenticate (java.lang.String username, java.lang.String password)`
- `ResourceObject authenticate (java.lang.String accountId, java.util.Map<java.lang.String,java.lang.Object> options)`
- `ResourceObject buildResourceObjectFromMap ( Schema schema, java.util.Map<java.lang.String,java.lang.Object> mergedObject)`
- `ProvisioningResult checkStatus (java.lang.String id)`
- `static java.util.Map<java.lang.String,​java.lang.Object> defaultMergeMaps (java.util.Map<java.lang.String,java.lang.Object> obj1, java.util.Map<java.lang.String,java.lang.Object> obj2, java.util.List<java.lang.String> mergeAttrs)`
- `staticResourceObject defaultTransformObject ( Schema schema, java.util.Map<java.lang.String,java.lang.Object> object)`
- `staticResourceObject defaultTransformObject ( Schema schema, java.util.Map<java.lang.String,java.lang.Object> object, boolean coerceCsvsToList)`
- `staticResourceObject defaultTransformObject ( Schema schema, java.util.Map<java.lang.String,java.lang.Object> object, boolean coerceCsvsToList, java.util.List<java.lang.String> attrsToLeaveAlone)`
- `void destroy (java.util.Map<java.lang.String,java.lang.Object> optionsMap)`
- `java.util.Map<java.lang.String,​java.lang.Object> discoverApplicationAttributes (java.util.Map<java.lang.String,java.lang.Object> options)`
- `CloseableIterator<connector.common.DiscoveredApplication> discoverApplications ()`
- `Schema discoverSchema (java.lang.String objectType, java.util.Map<java.lang.String,java.lang.Object> options)`
- `java.util.Map doHealthCheck (java.util.Map<java.lang.String,java.lang.Object> options)`
- `protected java.util.List<Permission> filterPermissions (java.util.List< Permission > unfiltered)`
- `protected static java.util.List<Permission> filterPermissions (java.util.List< Permission > configFilters, java.util.List< Permission > unfiltered)`
- `Application getApplication ()`
- `java.util.List<java.lang.String> getAttributeNames ( Schema schema, java.util.Map<java.lang.String,java.lang.Object> options)`
- `protected java.util.List<java.lang.String> getAttributesToRetrieve (java.lang.String objectType, java.util.Map<java.lang.String,java.lang.Object> options)`
- `java.util.Iterator<java.util.Map<java.lang.String,​java.lang.Object>> getChangeLogExtract (java.util.Map<java.lang.String,java.lang.Object> requestParams)`
- `java.util.Map<java.lang.String,​java.lang.Object> getConfigOptions (java.lang.String configOptionsKey)`
- `java.lang.String getConnectorType ()`
- `java.util.List<AttributeDefinition> getDefaultAttributes ()`
- `java.util.List<Schema> getDefaultSchemas ()`
- `java.util.Map<java.lang.String,​java.lang.Object> getDependencyData ()`
- `protected static java.lang.String getEffectiveAttribute ( Schema schema, java.lang.String name)`
- `java.util.List<java.util.Map<java.lang.String,​java.lang.Object>> getExtractPartitions (java.util.Map<java.lang.String,java.lang.Object> requestParams, java.lang.String extractType)`
- `java.lang.Boolean getFeatureFlagValue (java.lang.String name, boolean defaultValue)`
- `java.lang.String getInstance ()`
- `java.util.List<Partition> getIteratorPartitions (java.lang.String objectType, int suggestedPartitionCount, Filter filter, java.util.Map<java.lang.String,java.lang.Object> ops)`
- `Application getLocalApplication ()`
- `ProvisioningPlan getLoggingPlan ( ProvisioningPlan src)`
- `boolean getProductFlagValue (java.lang.String name, boolean defaultValue)`
- `Application getProxiedApplication (java.lang.String name, java.util.Map<java.lang.String,java.lang.Object> options)`
- `protectedConnector getRealConnector (java.lang.String clazzName)`
- `java.lang.Object getRequiredSchemaConfig ( Schema schema, java.lang.String name)`
- `Schema getSchema (java.lang.String objectType)`
- `Schema getSchema (java.lang.String objectType, boolean throwIfMissing)`
- `java.util.List<java.lang.String> getSchemaAttributeNames (java.lang.String objectType)`
- `java.util.List<AttributeDefinition> getSchemaAttributes (java.lang.String objectType)`
- `java.lang.String getSchemaNativeObjectType (java.lang.String objectType)`
- `java.util.List<java.lang.String> getSchemaPrototypeAttributeNames (java.lang.String objectType)`
- `java.util.List<Schema> getSchemas ()`
- `java.util.Iterator<java.util.Map<java.lang.String,​java.lang.Object>> getSecurityExtract (java.util.Map<java.lang.String,java.lang.Object> requestParams)`
- `connector.common.statisticscollector.StatisticsCollector getStatisticsCollector ()`
- `java.util.List<Application.Feature> getSupportedFeatures ()`
- `java.lang.String getSystemIdentity ()`
- `Application getTargetApplication ()`
- `java.lang.String getTargetInstance ()`
- `java.util.Iterator<java.util.Map<java.lang.String,​java.lang.Object>> getUtilizationExtract (java.util.Map<java.lang.String,java.lang.Object> requestParams)`
- `static boolean isAccount ( Schema schema)`
- `static boolean isGroup ( Schema schema)`
- `protected boolean isSecret (java.lang.String name)`
- `CloseableIterator<ResourceObject> iterateObjects ( Partition partition)`
- `void logApplication ( Application src)`
- `ProvisioningPlan logPlan ( ProvisioningPlan src)`
- `java.util.Map<java.lang.String,​java.lang.Object> mergeMaps ( Schema schema, java.util.Map<java.lang.String,java.lang.Object> current, java.util.Map<java.lang.String,java.lang.Object> newObject, java.util.List<java.lang.String> mergeAttrs)`
- `static java.util.List<Permission> mergePermissions (java.util.List< Permission > currentPerms, java.util.List< Permission > newPerms)`
- `ProvisioningResult provision ( ProvisioningPlan plan)`
- `void saveConnectorState ()`
- `void saveConnectorState (java.util.Map<java.lang.String,java.lang.Object> stateMap)`
- `void setApplication ( Application application)`
- `void setConnectorState (java.lang.String attribute, java.lang.Object val)`
- `void setInstance (java.lang.String ins)`
- `void setStatisticsCollector (connector.common.statisticscollector.StatisticsCollector statisticsCollector)`
- `void setSystemIdentity (java.lang.String id)`
- `void setTargetApplication ( Application app)`
- `void setTargetInstance (java.lang.String inst)`
- `boolean shouldRetry (java.lang.Exception ex, java.lang.String error, ProvisioningResult result)`
- `protectedSchema stringListToSchema (java.lang.String objectType, java.util.List<java.lang.String> columns)`
- `boolean supportsFeature ( Application.Feature feature)`
- `boolean supportsPartitionedDeltaAggregation ()`
- `void updateApplicationConfig ()`

---

## AbstractFileBasedConnector

**Package:** `sailpoint.connector`

**Description:** A class that offers file transport services for File Based Connectors. Classes that extend this class can be easily ftp and scp transport enabled to allow for files being parsed to be stored remotely.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.connector.CollectorServices`
- `sailpoint.connector.AbstractConnector`
- `sailpoint.connector.AbstractFileBasedConnector`
- `Connector`

**Attributes:**
- `static java.lang.String CONFIG_DEST_DIR`
- `static java.lang.String CONFIG_FILE`
- `static java.lang.String CONFIG_PORT`
- `static java.lang.String CONFIG_REGULAR_EXPRESSION`
- `static java.lang.String CONFIG_SCP_PRIVATE_KEY`
- `static java.lang.String CONFIG_TRANSPORT`
- `static java.lang.String CONFIG_TRANSPORT_USER`
- `static java.lang.String CONFIG_TRANSPORT_USER_PW`
- `static java.lang.String TRANSPORT_TYPE_FTP`
- `static java.lang.String TRANSPORT_TYPE_FTPS`
- `static java.lang.String TRANSPORT_TYPE_LOCAL`
- `static java.lang.String TRANSPORT_TYPE_SCP`
- `static java.lang.String TRANSPORT_TYPE_SFTP`

**Methods:**
- `protected void closeResources ()`
- `protected java.io.InputStream getFileStream (java.lang.String fileName)`
- `protected java.io.InputStream getFileStream (java.lang.String fileName, java.lang.String destination)`
- `static void skipLines (java.io.BufferedReader reader, int toSkip)`

---

## AuthenticationFailedException

**Package:** `sailpoint.connector`

**Description:** The base exception thrown by components.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `java.lang.Throwable`
- `java.lang.Exception`
- `sailpoint.tools.AbstractLocalizableException`
- `sailpoint.connector.ConnectorException`
- `sailpoint.connector.AuthenticationFailedException`
- `java.io.Serializable`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:** N/A

---

## CollectorServices

**Package:** `sailpoint.connector`

**Description:** A class that offers services that are common for all Connectors and Collectors in IdentityIQ. It has utility methods for coercing values, running rules and getting values out of the Configuration Attributes. It requires an instance of ConnectorService to decrypt() and an instance of ExtendedConnectorService to runRule(Rule, ...).

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.connector.CollectorServices`

**Attributes:** N/A

**Methods:**
- `void addSchemaConfigs ( Schema s)`
- `static java.util.List buildList (java.lang.Object value)`
- `static java.util.List<java.lang.String> buildStringList (java.lang.String string)`
- `static java.util.List<java.lang.String> buildStringList (java.lang.String string, boolean csv)`
- `static java.lang.Object coerceValue ( AttributeDefinition def, java.lang.Object value)`
- `java.lang.Object getAttribute (java.lang.String name)`
- `Attributes<java.lang.String,​java.lang.Object> getAttributes ()`
- `boolean getBooleanAttribute (java.lang.String name)`
- `openconnector.ConnectorServices getConnectorServices ()`
- `java.lang.String getDecryptedAttributeValue (java.lang.String name)`
- `java.lang.String getEncryptedAttr (java.lang.String name)`
- `java.lang.String getEncryptedAttribute (java.lang.String name)`
- `java.lang.String getEncryptedSchemaConfig ( Schema schema, java.lang.String name)`
- `int getIntAttribute (java.lang.String name)`
- `java.util.List getListAttribute (java.lang.String name)`
- `java.lang.Long getLongAttribute (java.lang.String name)`
- `java.lang.String getObligatoryEncryptedAttr (java.lang.String name)`
- `java.lang.String getObligatoryStringAttribute (java.lang.String name)`
- `java.lang.Object getRequiredAttribute (java.lang.String name)`
- `java.lang.String getRequiredEncryptedAttribute (java.lang.String name)`
- `java.lang.Integer getRequiredIntAttribute (java.lang.String name)`
- `java.util.List getRequiredListAttribute (java.lang.String name)`
- `java.lang.String getRequiredStringAttribute (java.lang.String name)`
- `java.lang.Object getSchemaConfig ( Schema schema, java.lang.String name)`
- `java.lang.Object getSchemaConfig ( Schema schema, java.lang.String name, boolean defaultToUnprefixed)`
- `java.util.List getSchemaConfigList ( Schema schema, java.lang.String name)`
- `java.lang.String getSchemaConfigString ( Schema schema, java.lang.String name)`
- `java.lang.String getStringAttribute (java.lang.String name)`
- `java.util.List getStringListAttribute (java.lang.String name)`
- `java.lang.Object runRule (java.lang.String ruleName, java.util.Map<java.lang.String,java.lang.Object> ruleContext)`
- `void setAttributes ( Attributes <java.lang.String,java.lang.Object> attributes)`
- `void setConnectorServices (openconnector.ConnectorServices connServices)`
- `java.lang.String toXml (java.util.Map map)`
- `java.lang.String toXml ( AbstractXmlObject obj)`

---

## ConnectionFailedException

**Package:** `sailpoint.connector`

**Description:** The base exception thrown by components.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `java.lang.Throwable`
- `java.lang.Exception`
- `sailpoint.tools.AbstractLocalizableException`
- `sailpoint.connector.ConnectorException`
- `sailpoint.connector.ConnectionFailedException`
- `java.io.Serializable`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:** N/A

---

## Connector

**Package:** `sailpoint.connector`

**Description:** The Connector interface allows IIQ to authenticate and read data from to enterprise applications. It can be used used to communicate with applications such as LDAP, JDBC Or SAP. There are several built in connectors, but the interface can be used to create Connectors for home-grown applications too. Connectors will return ResourceObjects to represent application objects. All ResourceObjects have a type that is either account or group. The definition of the object attributes will be defined by a Schema objects that holds a list of AttributeDefinitions. The individual AttributeDefinition objects define an attribute's type, name, description and value length. The AbstractConnector class provides many of the necessary services that span across all connectors. It is highly recommended that all connectors extend AbstractConnector instead implementing this interface directly. This will help avoid incompatibilities when changes are made to the interface from release to release. In some cases when a connector reads from a single source and defines objects that span multiple Applications they will also participate in generating Proxied Applications. In 5.2 many of the methods that were used to describe default Applications were deprecated and replaced with specified with Template applications defined in the ConnectorRegistry Configuration object.

**Inherited Classes/Interfaces:** N/A

**Attributes:**
- `static java.lang.String ATT_CHILD_OBJECTS`
- `static java.lang.String ATT_CIQ_MULTIPLEX_IDENTITY`
- `static java.lang.String ATT_CIQ_SOURCE_APPLICATION`
- `static java.lang.String ATT_IIQ_DISABLED`
- `static java.lang.String ATT_IIQ_LOCKED`
- `static java.lang.String ATT_MULTIPLEX_IDENTITY`
- `static java.lang.String ATT_PRIVILEGED`
- `static java.lang.String ATT_SOURCE_APPLICATION`
- `static java.lang.String ATTR_DIRECT_PERMISSIONS`
- `static java.lang.String ATTR_GROUPS`
- `static java.lang.String ATTR_TARGET_PERMISSIONS`
- `static java.lang.String CONFIG_AGGREGATION_MODE`
- `static java.lang.String CONFIG_AUTH_SEARCH_ATTRIBUTES`
- `static java.lang.String CONFIG_BUILD_MAP_RULE`
- `static java.lang.String CONFIG_GROUP_HIERARCHY_ATTRIBUTE`
- `static java.lang.String CONFIG_HOST`
- `static java.lang.String CONFIG_JDBC_BUILD_MAP_RULE`
- `static java.lang.String CONFIG_JDBC_CREATE_PROVISION_RULE`
- `static java.lang.String CONFIG_JDBC_DELETE_PROVISION_RULE`
- `static java.lang.String CONFIG_JDBC_DISABLE_PROVISION_RULE`
- `static java.lang.String CONFIG_JDBC_ENABLE_PROVISION_RULE`
- `static java.lang.String CONFIG_JDBC_MODIFY_PROVISION_RULE`
- `static java.lang.String CONFIG_JDBC_PROVISION_RULE`
- `static java.lang.String CONFIG_JDBC_UNLOCK_PROVISION_RULE`
- `static java.lang.String CONFIG_MERGE_MAPS_RULE`
- `static java.lang.String CONFIG_OBJECT_FILTERS`
- `static java.lang.String CONFIG_PARTITION_MODE`
- `static java.lang.String CONFIG_PASSWORD`
- `static java.lang.String CONFIG_PEOPLESOFTHRMS_CREATE_PROVISION_RULE`
- `static java.lang.String CONFIG_PEOPLESOFTHRMS_DELETE_PROVISION_RULE`
- `static java.lang.String CONFIG_PEOPLESOFTHRMS_DISABLE_PROVISION_RULE`
- `static java.lang.String CONFIG_PEOPLESOFTHRMS_ENABLE_PROVISION_RULE`
- `static java.lang.String CONFIG_PEOPLESOFTHRMS_MODIFY_PROVISION_RULE`
- `static java.lang.String CONFIG_PEOPLESOFTHRMS_PROVISION_RULE`
- `static java.lang.String CONFIG_PEOPLESOFTHRMS_UNLOCK_PROVISION_RULE`
- `static java.lang.String CONFIG_PERMISSION_SCOPE`
- `static java.lang.String CONFIG_PORT`
- `static java.lang.String CONFIG_PROVIDER`
- `static java.lang.String CONFIG_PROXY_GENERATOR_RULE`
- `static java.lang.String CONFIG_RWS_AFTER_OPERATION_RULE`
- `static java.lang.String CONFIG_RWS_BEFORE_OPERATION_RULE`
- `static java.lang.String CONFIG_SAPHR_CREATE_PROVISION_RULE`
- `static java.lang.String CONFIG_SAPHR_DELETE_PROVISION_RULE`
- `static java.lang.String CONFIG_SAPHR_DISABLE_PROVISION_RULE`
- `static java.lang.String CONFIG_SAPHR_ENABLE_PROVISION_RULE`
- `static java.lang.String CONFIG_SAPHR_MODIFY_PROVISION_RULE`
- `static java.lang.String CONFIG_SAPHR_PROVISION_RULE`
- `static java.lang.String CONFIG_SAPHR_UNLOCK_PROVISION_RULE`
- `static java.lang.String CONFIG_SUCCESSFACTORS_PROVISION_RULE`
- `static java.lang.String CONFIG_TRANSFORMATION_RULE`
- `static java.lang.String CONFIG_USER`
- `static java.lang.String OP_AGGREGATION_TYPE`
- `static java.lang.String OP_ALLOW_BRUTE_FORCE_SEARCH`
- `static java.lang.String OP_ATTRIBUTE_NAMES`
- `static java.lang.String OP_DELTA_AGGREGATION`
- `static java.lang.String OP_INCLUDE_ACCOUNTS`
- `static java.lang.String OP_IS_PARTITIONED`
- `static java.lang.String OP_IS_TERMINATE`
- `static java.lang.String OP_PHASE_NAME`
- `static java.lang.String OP_UNIQUENESS_CHECK`
- `static java.lang.String PROVISION_GLOBAL_RULE`
- `static java.lang.String PROVISION_OPERATION_RULE`
- `static java.lang.String PROVISION_RULE_TYPE`
- `static java.lang.String SAPHR_CUSTOM_MANAGER_MODEL_RULE`
- `static java.lang.String SAPHR_CUSTOM_MANAGER_RULE`
- `static java.lang.String TYPE_ACCOUNT`
- `static java.lang.String TYPE_GROUP`

**Methods:**
- `ResourceObject authenticate (java.lang.String username, java.lang.String password)`
- `ResourceObject authenticate (java.lang.String accountId, java.util.Map<java.lang.String,java.lang.Object> options)`
- `ProvisioningResult checkStatus (java.lang.String id)`
- `void destroy (java.util.Map<java.lang.String,java.lang.Object> optionsMap)`
- `java.util.Map<java.lang.String,​java.lang.Object> discoverApplicationAttributes (java.util.Map<java.lang.String,java.lang.Object> options)`
- `CloseableIterator<connector.common.DiscoveredApplication> discoverApplications ()`
- `Schema discoverSchema (java.lang.String objectType, java.util.Map<java.lang.String,java.lang.Object> options)`
- `java.util.Map doHealthCheck (java.util.Map<java.lang.String,java.lang.Object> options)`
- `Application getApplication ()`
- `java.util.Iterator<java.util.Map<java.lang.String,​java.lang.Object>> getChangeLogExtract (java.util.Map<java.lang.String,java.lang.Object> requestParams)`
- `java.util.Map<java.lang.String,​java.lang.Object> getConfigOptions (java.lang.String configOptionsKey)`
- `openconnector.ConnectorServices getConnectorServices ()`
- `java.lang.String getConnectorType ()`
- `java.util.List<AttributeDefinition> getDefaultAttributes ()`
- `java.util.List<Schema> getDefaultSchemas ()`
- `java.util.Map<java.lang.String,​java.lang.Object> getDependencyData ()`
- `java.util.List<java.util.Map<java.lang.String,​java.lang.Object>> getExtractPartitions (java.util.Map<java.lang.String,java.lang.Object> requestParams, java.lang.String extractType)`
- `java.lang.String getInstance ()`
- `java.util.List<Partition> getIteratorPartitions (java.lang.String objectType, int suggestedPartitionCount, Filter filter, java.util.Map<java.lang.String,java.lang.Object> ops)`
- `Application getLocalApplication ()`
- `ResourceObject getObject (java.lang.String objectType, java.lang.String identity, java.util.Map<java.lang.String,java.lang.Object> options)`
- `Application getProxiedApplication (java.lang.String name, java.util.Map<java.lang.String,java.lang.Object> options)`
- `java.util.Iterator<java.util.Map<java.lang.String,​java.lang.Object>> getSecurityExtract (java.util.Map<java.lang.String,java.lang.Object> requestParams)`
- `connector.common.statisticscollector.StatisticsCollector getStatisticsCollector ()`
- `java.util.List<Application.Feature> getSupportedFeatures ()`
- `java.lang.String getSystemIdentity ()`
- `Application getTargetApplication ()`
- `java.lang.String getTargetInstance ()`
- `java.util.Iterator<java.util.Map<java.lang.String,​java.lang.Object>> getUtilizationExtract (java.util.Map<java.lang.String,java.lang.Object> requestParams)`
- `CloseableIterator<ResourceObject> iterateObjects (java.lang.String objectType, Filter filter, java.util.Map<java.lang.String,java.lang.Object> options)`
- `CloseableIterator<ResourceObject> iterateObjects ( Partition partition)`
- `ProvisioningResult provision ( ProvisioningPlan plan)`
- `void setApplication ( Application application)`
- `void setConnectorServices (openconnector.ConnectorServices connServices)`
- `void setInstance (java.lang.String instance)`
- `void setStatisticsCollector (connector.common.statisticscollector.StatisticsCollector statisticsCollector)`
- `void setSystemIdentity (java.lang.String id)`
- `void setTargetApplication ( Application app)`
- `void setTargetInstance (java.lang.String inst)`
- `boolean supportsPartitionedDeltaAggregation ()`
- `void testConfiguration ()`
- `void updateApplicationConfig ()`

---

## ConnectorException

**Package:** `sailpoint.connector`

**Description:** The base exception thrown by all connectors.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `java.lang.Throwable`
- `java.lang.Exception`
- `sailpoint.tools.AbstractLocalizableException`
- `sailpoint.connector.ConnectorException`
- `java.io.Serializable`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:**
- `java.lang.String getErrorCode ()`

---

## ConnectorFactory

**Package:** `sailpoint.connector`

**Description:** The ConnectorFactory factory to aid in getting connectors.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.connector.ConnectorFactory`

**Attributes:** N/A

**Methods:**
- `staticConnector createConnector (java.lang.String name, Application app, java.lang.String instance)`
- `static openconnector.Connector createConnector ( Attributes <java.lang.String,java.lang.Object> configuration, java.lang.String name)`
- `static void destroyConnector ( Application application, java.util.Map<java.lang.String,java.lang.Object> optionsMap)`
- `staticApplication getApplication ( Application originalApp)`
- `static sailpoint.connector.LogicalConnector getCompositeConnector ( Application app)`
- `staticConnector getConnector ( Application applicationToClone, java.lang.String instance)`
- `static openconnector.Connector getConnector ( Attributes <java.lang.String,java.lang.Object> configuration, java.lang.String instance)`
- `staticConnector getConnectorNoClone ( Application application, java.lang.String instance)`

---

## DelimitedFileConnector.DelimitedContentsIterator

**Package:** `sailpoint.connector`

**Description:** Assemble a resource object from the ResultSet.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ResourceObject`
- `sailpoint.connector.DelimitedFileConnector.FileContentsIterator`
- `sailpoint.connector.DelimitedFileConnector.DelimitedContentsIterator`
- `CloseableIterator`

**Attributes:** N/A

**Methods:**
- `java.util.Map<java.lang.String,​java.lang.Object> assembleObject ( Schema schema)`
- `void close ()`
- `java.util.Map<java.lang.String,​java.lang.Object> getNextCompleteRecord ()`

---

## DelimitedFileConnector.FileContentsIterator

**Package:** `sailpoint.connector`

**Description:** Flag to indicate if maps built with no keys should be filtered.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ResourceObject`
- `sailpoint.connector.DelimitedFileConnector.FileContentsIterator`
- `CloseableIterator`

**Attributes:**
- `protected java.util.Date _blockStart`
- `protected java.util.List<java.lang.String> _columns`
- `protected boolean _filterEmptyRecords`
- `protected boolean _iteratedToEnd`
- `protected long _merged`
- `protectedResourceObject _next`
- `protectedFilter _objectFilter`
- `protectedAttributes<java.lang.String,​java.lang.Object> _options`
- `protected long _processed`
- `protected long _returned`
- `protected java.lang.String _simpleSearchString`
- `protected java.util.Map<java.lang.String,​java.lang.Object> _state`

**Methods:**
- `java.util.Map<java.lang.String,​java.lang.Object> buildMap (java.util.List<java.lang.String> record, java.util.List<java.lang.String> cols)`
- `void close ()`
- `java.io.BufferedReader getBufferedReader ()`
- `abstract java.util.Map<java.lang.String,​java.lang.Object> getNextCompleteRecord ()`
- `boolean hasNext ()`
- `ResourceObject next ()`
- `protected void printProgress ()`
- `boolean shouldFilter (java.util.Map<java.lang.String,java.lang.Object> map)`
- `protected boolean shouldFilterSimpleString (java.util.List<java.lang.String> line)`
- `protected void skipLines ( Schema schema, java.io.BufferedReader reader)`

---

## DelimitedFileConnector.PartitionIterator

**Package:** `sailpoint.connector`

**Description:** Wrapper iterator implementation that knows how to read partitions of a file. The partitionConfig will give the details of which slice of the data should be read giving both the starting point and where to stop. When not in merge mode we can assume a single line per object. Merging rows makes this more complicated since the data can span multiple rows of data. Further, because the buildMap rule can influence how the merge works it has to be executed when merging is enabled. The same is true with regexp, which can also span multiple files. For all others for the first pass during partitioning AND when seeking to the correct place in the file it will just read lines from the file until the correct position. Then process them as usual.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.connector.DelimitedFileConnector.PartitionIterator`
- `CloseableIterator<ResourceObject>`

**Attributes:** N/A

**Methods:**
- `void close ()`
- `boolean hasNext ()`
- `ResourceObject next ()`

---

## DelimitedFileConnector.RegExSingleLinedIterator

**Package:** `sailpoint.connector`

**Description:** Iterator returned from the regex parser.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ResourceObject`
- `sailpoint.connector.DelimitedFileConnector.FileContentsIterator`
- `sailpoint.connector.DelimitedFileConnector.RegExSingleLinedIterator`
- `CloseableIterator`

**Attributes:**
- `protectedCloseableIterator<java.util.List<java.lang.String>> _lines`
- `protected java.util.Map<java.lang.String,​java.lang.Object> _nextMap`

**Methods:**
- `void close ()`
- `java.util.Map<java.lang.String,​java.lang.Object> getNextCompleteRecord ()`

---

## DelimitedFileConnector.RegExSortedMultiLinedIterator

**Package:** `sailpoint.connector`

**Description:** In this case we go through the file and look for new key'ed values.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ResourceObject`
- `sailpoint.connector.DelimitedFileConnector.FileContentsIterator`
- `sailpoint.connector.DelimitedFileConnector.RegExSingleLinedIterator`
- `sailpoint.connector.DelimitedFileConnector.RegExSortedMultiLinedIterator`
- `CloseableIterator`

**Attributes:**
- `protected java.lang.String _indexColumn`
- `protected java.util.List<java.lang.String> _mergeColumns`

**Methods:**
- `java.util.Map<java.lang.String,​java.lang.Object> getNextCompleteRecord ()`

---

## DelimitedFileConnector.RegExUnSortedMultiLinedIterator

**Package:** `sailpoint.connector`

**Description:** In this case we go through the file and look for new key'ed values.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ResourceObject`
- `sailpoint.connector.DelimitedFileConnector.FileContentsIterator`
- `sailpoint.connector.DelimitedFileConnector.RegExSingleLinedIterator`
- `sailpoint.connector.DelimitedFileConnector.RegExSortedMultiLinedIterator`
- `sailpoint.connector.DelimitedFileConnector.RegExUnSortedMultiLinedIterator`
- `CloseableIterator`

**Attributes:** N/A

**Methods:**
- `java.util.Map<java.lang.String,​java.lang.Object> getNextCompleteRecord ()`

---

## DelimitedFileConnector

**Package:** `sailpoint.connector`

**Description:** A connector that can be used to read data from one or more delimited text files. There are two parsing modes for this connector. RFC4180 Delimited text More specific information see RFC4180 it is the basis for most of the parsing. In this mode you can specify a single character to break the contents of the file line by line into tokens. Then a BeanShell rule is called for each of the lines in the file so transformations on the data can be performed as the data is being read from the file. RegularExpression Grouping - Using Java's regexp library In this mode must specify a regular expressions using regular expression groups the connector will break up the contents of the file into tokens.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.connector.CollectorServices`
- `sailpoint.connector.AbstractConnector`
- `sailpoint.connector.AbstractFileBasedConnector`
- `sailpoint.connector.DelimitedFileConnector`
- `Connector`

**Attributes:**
- `static java.util.Map<java.lang.String,​java.util.Map<java.lang.String,​sailpoint.connector.DelimitedFileConnector.DataCache>> _dataCaches`
- `static java.lang.String CONFIG_COLUMN_LENGTH_STRICT`
- `static java.lang.String CONFIG_COLUMN_NAMES`
- `static java.lang.String CONFIG_COMMENT_CHARACTER`
- `static java.lang.String CONFIG_DELIMITED_PARSE_TYPE`
- `static java.lang.String CONFIG_DELIMITER`
- `static java.lang.String CONFIG_FILE_DESTINATION`
- `static java.lang.String CONFIG_FILE_ENCODING`
- `static java.lang.String CONFIG_FILENAME`
- `static java.lang.String CONFIG_FILTER`
- `static java.lang.String CONFIG_FILTER_EMPTY_RECORDS`
- `static java.lang.String CONFIG_HAS_HEADER`
- `static java.lang.String CONFIG_IGNORE_QUOTES`
- `static java.lang.String CONFIG_INDEX_COLUMN`
- `static java.lang.String CONFIG_IS_CASE_INSENSITIVE_MERGE`
- `static java.lang.String CONFIG_IS_SORTED`
- `static java.lang.String CONFIG_LINES_TO_SKIP`
- `static java.lang.String CONFIG_MERGE_COLUMNS`
- `static java.lang.String CONFIG_MERGE_ROWS`
- `static java.lang.String CONFIG_PARSE_TYPE`
- `static java.lang.String CONFIG_PARTITION_OBJECT_COUNT`
- `static java.lang.String CONFIG_POST_ITERATE_RULE`
- `static java.lang.String CONFIG_PRE_ITERATE_RULE`
- `static java.lang.String CONFIG_REGEX`
- `static java.lang.String CONFIG_REGEX_MULTILINED_MODE`
- `static java.lang.String CONFIG_REGEXP_PARSE_TYPE`
- `static java.lang.String CONFIG_SIMPLE_SEARCH_STRING`
- `static java.lang.String CONFIG_SPACE`
- `static java.lang.String CONFIG_USE_CACHE`
- `static java.lang.String CONNECTOR_TYPE`
- `boolean isAggregation`
- `static java.lang.String OPTION_CLEAR_CACHE`

**Methods:**
- `ResourceObject buildResourceObjectFromMap ( Schema schema, java.util.Map<java.lang.String,java.lang.Object> mergedObject)`
- `static void clearDataCache ()`
- `java.io.BufferedReader createBufferedReader (java.io.BufferedInputStream bis)`
- `static java.util.Map<java.lang.String,​java.lang.Object> defaultBuildMap (java.util.List<java.lang.String> cols, java.util.List<java.lang.String> record)`
- `static java.util.Map<java.lang.String,​java.lang.Object> defaultBuildMap (java.util.List<java.lang.String> cols, java.util.List<java.lang.String> record, boolean trimValues)`
- `Schema discoverSchema (java.lang.String objectType, java.util.Map<java.lang.String,java.lang.Object> options)`
- `boolean filterEmptyRecords ( Schema schema)`
- `java.util.List<AttributeDefinition> getBaseAttributes ()`
- `java.util.List<java.lang.String> getColumnNames ( Schema schema)`
- `java.lang.String getCommentCharacter ( Schema schema)`
- `java.lang.String getConnectorType ()`
- `java.util.List<AttributeDefinition> getDefaultAttributes ()`
- `java.util.List<Schema> getDefaultSchemas ()`
- `protected java.lang.Character getDelimiter ( Schema schema)`
- `java.lang.String getFileDestination ( Schema schema)`
- `java.lang.String getFileName ( Schema schema)`
- `protectedCloseableIterator<ResourceObject> getIterator (java.io.InputStream stream, Schema schema, java.util.Map<java.lang.String,java.lang.Object> options)`
- `java.util.List<Partition> getIteratorPartitions (java.lang.String objectType, int suggestedPartitionCount, Filter filter, java.util.Map<java.lang.String,java.lang.Object> ops)`
- `protected java.util.List<AttributeDefinition> getMergeAttributess ()`
- `ResourceObject getObject (java.lang.String objectType, java.lang.String identity, java.util.Map<java.lang.String,java.lang.Object> options)`
- `protected java.util.List<AttributeDefinition> getPartitionConfigs ()`
- `java.util.List<Application.Feature> getSupportedFeatures ()`
- `boolean isGroupSchema ( Schema schema)`
- `CloseableIterator<ResourceObject> iterateObjects (java.lang.String objectType, Filter filter, java.util.Map<java.lang.String,java.lang.Object> options)`
- `CloseableIterator<ResourceObject> iterateObjects ( Partition partition)`
- `protected java.util.List<java.lang.String> readColumnsFromHeader (sailpoint.tools.RFC4180LineParser parser, java.io.BufferedReader buffer)`
- `protected java.io.InputStream runPreIterateRule ( Schema schema)`
- `void testConfiguration ()`
- `java.lang.String uncompressString (java.lang.String compressedData)`

---

## ExpiredPasswordException

**Package:** `sailpoint.connector`

**Description:** A connector exception indicating that authentication failed because of an expired password. Note that this can be thrown from two contexts. It is thrown from Authenticator to the UI tier when either the native IIQ password policy or the pass-through auth application says the password is expired. The UI uses this to transition to the password reset pages. It is also thrown by Connectors to the Authenticator to indicate that the the password is considered expired on the managed system. In this case, the exception may be decorated with information about the native account. Created by Jeff, Ketan

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `java.lang.Throwable`
- `java.lang.Exception`
- `sailpoint.tools.AbstractLocalizableException`
- `sailpoint.connector.ConnectorException`
- `sailpoint.connector.AuthenticationFailedException`
- `sailpoint.connector.ExpiredPasswordException`
- `java.io.Serializable`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:**
- `java.lang.String getAppName ()`
- `Identity getIdentity ()`
- `java.lang.String getNativeIdentity ()`
- `ResourceObject getResourceObject ()`
- `void setAppName (java.lang.String appName)`
- `void setIdentity ( Identity ident)`
- `void setNativeIdentity (java.lang.String id)`
- `void setResourceObject ( ResourceObject ro)`

---

## InsufficientPermissionException

**Package:** `sailpoint.connector`

**Description:** InsufficientPermissionException thrown when an user has insufficient permissions to perform any operation. During any operation if connector gets a known Managed System exception indicating lack of permission, then use this exception to be thrown to the IIQ layer.InsufficientPermissionException will be extended from ConnectorException. This class will entertain the message string, Message object and throwable object.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `java.lang.Throwable`
- `java.lang.Exception`
- `sailpoint.tools.AbstractLocalizableException`
- `sailpoint.connector.ConnectorException`
- `sailpoint.connector.InsufficientPermissionException`
- `java.io.Serializable`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:** N/A

---

## InvalidConfigurationException

**Package:** `sailpoint.connector`

**Description:** This exception thrown when an application lacking some configuration. During any operation if connector requires certain configuration to connect to the managed-system which is not provided or is faulty. This could happen before/after sending a request to the managed system.When a connector receives any error/exception of the managed system, and to fix such error if there is a need to correct the application configuration. This could take place when the managed system provides a response to a request. InvalidConfigurationException is extended from ConnectorException. This class will entertain the message string, Message object and throwable object.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `java.lang.Throwable`
- `java.lang.Exception`
- `sailpoint.tools.AbstractLocalizableException`
- `sailpoint.connector.ConnectorException`
- `sailpoint.connector.InvalidConfigurationException`
- `java.io.Serializable`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:** N/A

---

## InvalidRequestException

**Package:** `sailpoint.connector`

**Description:** InvalidRequestException thrown when the invalid input request is provided to the managed system which is not compatible with the standards.this exception can be thrown when the format or the input value will be wrong. InvalidRequestException is extended from ConnectorException. This class will entertain the message string, Message object and throwable object.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `java.lang.Throwable`
- `java.lang.Exception`
- `sailpoint.tools.AbstractLocalizableException`
- `sailpoint.connector.ConnectorException`
- `sailpoint.connector.InvalidRequestException`
- `java.io.Serializable`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:** N/A

---

## InvalidResponseException

**Package:** `sailpoint.connector`

**Description:** InvalidResponseException thrown when an invalid response is detected. 1)During aggregation or in the getObject when the connector is unable to parse a data received from Managed System. If something fails, when converting managed system response to ResourceObject. for e.g. a) Connector receives a malformed response from the managed system which is not understood by the connector. 2)When aggregating records from managed system if connectors receives only some part of the record which is unacceptable, then we can have this exception telling IdentityIQ about the record containing partial information. InvalidResponseException will be extended from ConnectorException. This class will entertain the message String, Message object and throwable object.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `java.lang.Throwable`
- `java.lang.Exception`
- `sailpoint.tools.AbstractLocalizableException`
- `sailpoint.connector.ConnectorException`
- `sailpoint.connector.InvalidResponseException`
- `java.io.Serializable`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:** N/A

---

## JDBCConnector.JDBCObjectIterator

**Package:** `sailpoint.connector`

**Description:** This method is where if necessary can disconnect and cleanup any connections etc.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `ResourceObject`
- `sailpoint.connector.JDBCConnector.JDBCObjectIterator`
- `CloseableIterator`

**Attributes:**
- `protected java.sql.Connection _connection`
- `protected int _exceptionSimulationCount`
- `protectedResourceObject _next`
- `protected java.sql.ResultSet _result`
- `protectedSchema _schema`
- `protected java.sql.Statement _statement`

**Methods:**
- `void close ()`
- `protectedResourceObject getNext ()`
- `protectedResourceObject getNextForJDBC ()`
- `boolean hasNext ()`
- `ResourceObject next ()`
- `protected void printProgress ()`
- `void setExceptionSimulationCount (int i)`

---

## JDBCConnector

**Package:** `sailpoint.connector`

**Description:** A connector that can be used to read data from JDBC enabled database engines. This connector using configuration options to drive the data that is fetched from the database. For simple single table implementations the schema can be used exclusively to configure the connector. The native ObjectType in the schema defines the table name when generating the sql. For more complex situations the sql can manually be assigned using the sql configuration parameter. CONFIG_SQL_STATEMENT The select statement for the statement will drive the ResultSet that is returned from the query. For each ResultSet returned by the sql a buildMap rule is called to transform the ResultSet into a Map object. The buildMap is where all of the per row transformations can take place and there is a default static method buildMapFromResultSet(ResultSet) that can be called from rules to transform the data into a Map. Once each row has been transformed into a Map object it is then transformed to a ResourceObject which is used to represent each unique user or group in the data source. The default methods use the Application's Schema to coerce the sql datatype values into our simple Boolean, String, Long, Integer and Date values. These behaviors can be overridden using the Connector.CONFIG_TRANSFORMATION_RULE configuration item.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `sailpoint.connector.CollectorServices`
- `sailpoint.connector.AbstractConnector`
- `sailpoint.connector.JDBCConnector`
- `Connector`

**Attributes:**
- `static java.lang.String ARG_CON_PROPERTIES`
- `static java.lang.String CONFIG_CONN_MAX_RETRY`
- `static java.lang.String CONFIG_CONN_RETRY_ENABLE`
- `static java.lang.String CONFIG_CONN_RETRY_EXCEPTION_LIST`
- `static java.lang.String CONFIG_CONN_WAIT_TIME_FOR_RETRY`
- `static java.lang.String CONFIG_CONVERT_LIST_TO_CSV`
- `static java.lang.String CONFIG_DBURL`
- `static java.lang.String CONFIG_DELTA_AGGREGATION`
- `static java.lang.String CONFIG_DELTA_TABLE`
- `static java.lang.String CONFIG_DIRECT_PERMISSIOB_SQL`
- `static java.lang.String CONFIG_DISABLE_ORDERING_CHECK`
- `static java.lang.String CONFIG_ENABLE_GROUP_HIERARCHY`
- `static java.lang.String CONFIG_EXCEPTION_SIMULATION_COUNT`
- `static java.lang.String CONFIG_GET_DELTA_SQL_STATEMENT`
- `static java.lang.String CONFIG_GET_OBJECT_SQL_STATEMENT`
- `static java.lang.String CONFIG_INDEX_COLUMNS`
- `static java.lang.String CONFIG_IS_DIRECT_PERMISSIOB_ENABLED`
- `static java.lang.String CONFIG_MERGE_COLUMNS`
- `static java.lang.String CONFIG_MERGE_ROWS`
- `static java.lang.String CONFIG_PARTITION_NAMES`
- `static java.lang.String CONFIG_PARTITION_SQL_STATEMENTS`
- `static java.lang.String CONFIG_PARTITION_STATEMENT`
- `static java.lang.String CONFIG_RESULT_SET_CONCURANCY`
- `static java.lang.String CONFIG_RESULT_SET_FETCH_SIZE`
- `static java.lang.String CONFIG_RESULT_SET_TYPE`
- `static java.lang.String CONFIG_SORT_DESCENDING`
- `static java.lang.String CONFIG_SQL_STATEMENT`
- `static java.lang.String CONFIG_STATEMENT_FETCH_SIZE`
- `static java.lang.String CONFIG_SUPPORT_UNSTRUCTURED_DATA`
- `static java.lang.String CONFIG_TEST_SQL_STATEMENT`
- `static java.lang.String CONFIG_USE_EXEC_QUERY`
- `static java.lang.String CONNECTOR_SQLLOADER_TYPE`
- `static java.lang.String CONNECTOR_TYPE`
- `static java.lang.String POOL_PREFIX`
- `static java.lang.String SENSITIVE_ATTR_IDENTIFIER`

**Methods:**
- `java.util.List<Permission> addDirectPermissions ( Schema schema, java.sql.Connection connection, ResourceObject object, java.lang.String sql, java.lang.String identity)`
- `protectedResourceObject assembleObject ( Schema schema, java.sql.ResultSet result, java.sql.Connection conn, java.util.Map<java.lang.String,java.lang.Object> ruleState, java.lang.String last)`
- `protected java.util.Map<java.lang.String,​java.lang.Object> buildMap (java.sql.ResultSet result, Schema schema, java.util.Map<java.lang.String,java.lang.Object> ruleState, java.sql.Connection conn)`
- `static java.util.Map<java.lang.String,​java.lang.Object> buildMapFromResultSet (java.sql.ResultSet result)`
- `static java.util.Map<java.lang.String,​java.lang.Object> buildMapFromResultSet (java.sql.ResultSet result, Schema schema)`
- `ResourceObject buildResourceObjectFromMap ( Schema schema, java.util.Map<java.lang.String,java.lang.Object> mergedObject)`
- `protected void closeConnection (java.sql.Connection connection)`
- `protected void closeResult (java.sql.ResultSet resultset)`
- `protected void closeStatement (java.sql.Statement statement)`
- `Schema discoverSchema (java.lang.String objectType, java.util.Map<java.lang.String,java.lang.Object> options)`
- `protected java.sql.ResultSet executeStatement (java.sql.PreparedStatement statement, boolean throwIfResultNull)`
- `protected static java.util.List<java.lang.String> getColumnNames (java.sql.ResultSet result)`
- `protected java.sql.Connection getConnection ( Schema schema, java.util.Map<java.lang.String,java.lang.Object> options)`
- `java.lang.String getConnectorType ()`
- `java.util.List<AttributeDefinition> getDefaultAttributes ()`
- `protected java.lang.String getDefaultFetchSQL ( Schema schema, java.lang.String identity)`
- `java.util.List<Schema> getDefaultSchemas ()`
- `protected java.lang.String getDeleteSQL ( Schema schema, java.sql.ResultSet result, java.lang.String identity, java.lang.String action)`
- `protected java.lang.String getDeltaFetchSQL ( Schema schema, java.lang.String identity)`
- `protected java.lang.String getDeltaSQL ( Schema schema, Filter filter)`
- `protected java.lang.String getFetchSQL ( Schema schema, java.lang.String identity)`
- `protected java.util.List<java.lang.String> getIndexColumns ( Schema schema)`
- `protected java.lang.String getIterateSQL ( Schema schema, Filter filter)`
- `java.util.List<Partition> getIteratorPartitions (java.lang.String objectType, int suggestedPartitionCount, Filter filter, java.util.Map<java.lang.String,java.lang.Object> ops)`
- `java.lang.String getMaskedSQL ()`
- `protected java.util.List<java.lang.String> getMergeColumns ( Schema schema)`
- `ResourceObject getObject (java.lang.String objectType, java.lang.String identity, java.util.Map<java.lang.String,java.lang.Object> options)`
- `protectedJDBCConnector.JDBCObjectIterator getObjectIterator ( Schema schema, java.sql.Connection connection, java.sql.PreparedStatement statement, java.sql.ResultSet result)`
- `protected java.sql.PreparedStatement getStatement (java.sql.Connection connection, java.lang.String sql)`
- `java.util.List<Application.Feature> getSupportedFeatures ()`
- `protected boolean isRetriedOperation ()`
- `CloseableIterator<ResourceObject> iterateObjects (java.lang.String objectType, Filter filter, java.util.Map<java.lang.String,java.lang.Object> options)`
- `CloseableIterator<ResourceObject> iterateObjects ( Partition partition)`
- `static java.util.Map listToMap (java.util.List<java.lang.String> ListOfValues)`
- `protected boolean mergeRows ( Schema schema)`
- `ProvisioningResult provision ( ProvisioningPlan plan)`
- `ProvisioningResult ProvisionByRule ( ProvisioningPlan plan)`
- `protected void resetIsRetriedOperation ()`
- `CloseableIterator<ResourceObject> retryIterateObjects (java.lang.String objectType, Filter filter, java.util.Map<java.lang.String,java.lang.Object> options)`
- `void setMaskedSQL (java.lang.String maskedSql)`
- `protected void setRetryErrorList (java.util.List<java.lang.String> retryErrorList)`
- `protected boolean shouldRetryCPError (java.lang.Exception e)`
- `void testConfiguration ()`
- `protected void updateConnectionMapWithProperties (java.util.HashMap<java.lang.String,java.lang.Object> connectionMap, java.util.List<java.lang.String> propertiesList)`

---

## ObjectAlreadyExistsException

**Package:** `sailpoint.connector`

**Description:** ObjectAlreadyExistsException thrown when object we are trying to create is already exist on Managed System. During provisioning operation of type create(only) the connector is trying to create an entity on the managed system but the same entity is already existing on the managed system. for e.g. a) During provisioning operation create an account, the connector receives the known exception/error "Object Already exist" from the managed system. ObjectAlreadyExistsException will be extended from ConnectorException. This class will entertain the message String, Message object and throwable object.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `java.lang.Throwable`
- `java.lang.Exception`
- `sailpoint.tools.AbstractLocalizableException`
- `sailpoint.connector.ConnectorException`
- `sailpoint.connector.ObjectAlreadyExistsException`
- `java.io.Serializable`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:** N/A

---

## ObjectNotFoundException

**Package:** `sailpoint.connector`

**Description:** The base exception thrown by components.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `java.lang.Throwable`
- `java.lang.Exception`
- `sailpoint.tools.AbstractLocalizableException`
- `sailpoint.connector.ConnectorException`
- `sailpoint.connector.ObjectNotFoundException`
- `java.io.Serializable`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:** N/A

---

## SchemaNotDefinedException

**Package:** `sailpoint.connector`

**Description:** The base exception thrown by components.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `java.lang.Throwable`
- `java.lang.Exception`
- `sailpoint.tools.AbstractLocalizableException`
- `sailpoint.connector.ConnectorException`
- `sailpoint.connector.SchemaNotDefinedException`
- `java.io.Serializable`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:** N/A

---

## TimeoutException

**Package:** `sailpoint.connector`

**Description:** TimeoutException thrown when the managed system does not respond and number of attempts to connect are failed. TimeoutException is extended from ConnectionFailedException. This class will entertain the message string, Message object and throwable object.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `java.lang.Throwable`
- `java.lang.Exception`
- `sailpoint.tools.AbstractLocalizableException`
- `sailpoint.connector.ConnectorException`
- `sailpoint.connector.ConnectionFailedException`
- `sailpoint.connector.TimeoutException`
- `java.io.Serializable`
- `sailpoint.tools.Localizable`

**Attributes:** N/A

**Methods:** N/A

---

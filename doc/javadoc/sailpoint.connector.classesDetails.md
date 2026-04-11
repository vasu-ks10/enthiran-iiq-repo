* Class Name: InvalidRequestException
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, sailpoint.connector.ConnectorException, java.lang.Throwable, sailpoint.connector.ConnectorException, java.lang.Exception, sailpoint.connector.ConnectorException, sailpoint.tools.AbstractLocalizableException, sailpoint.connector.ConnectorException, sailpoint.connector.InvalidRequestException
* Description: InvalidRequestException thrown when the invalid input request is provided to  the managed system which is not compatible with the standards.this exception  can be thrown when the format or the input value will be wrong.  InvalidRequestException is extended from ConnectorException. This class will  entertain the message string, Message object and throwable object.
* Attributes:
  - None
* Methods:
  - Constructor: InvalidRequestException() - InvalidRequestException constructor will be called by the connector components to throw an exception.
  - Constructor: InvalidRequestException​(java.lang.String message) - InvalidRequestException constructor will be called by passing the message String.
  - Constructor: InvalidRequestException​(java.lang.String error, java.lang.String suggestion, java.lang.Throwable t) - Create a new InvalidRequestException from an error text, suggestion text and existing exception.
  - Constructor: InvalidRequestException​(java.lang.String message, java.lang.Throwable t) - InvalidRequestException constructor will be called by passing the throwable object and message string.
  - Constructor: InvalidRequestException​(java.lang.Throwable t) - InvalidRequestException constructor will be called by passing the throwable object.
  - Constructor: InvalidRequestException​(Message message) - InvalidRequestException constructor will be called by passing the Message object.
  - Constructor: InvalidRequestException​(Message message, java.lang.Throwable t) - InvalidRequestException constructor will be called by passing the throwable object and Message object.

* Class Name: CollectorServices
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, sailpoint.connector.CollectorServices
* Description: A class that offers services that are common for all  Connectors and Collectors in IdentityIQ. It has utility methods  for coercing values, running rules and getting values  out of the Configuration Attributes.  It requires an instance of ConnectorService to decrypt() and an instance of  ExtendedConnectorService to runRule(Rule, ...).
* Attributes:
  - None
* Methods:
  - void addSchemaConfigs​(Schema s) - Add all of the given schema's attributes to the _config map in "dotKeyName" notation
  - static java.util.List buildList​(java.lang.Object value) - Build a List from a single object value.
  - static java.util.List<java.lang.String> buildStringList​(java.lang.String string) - Build a list of strings from a single string.
  - static java.util.List<java.lang.String> buildStringList​(java.lang.String string, boolean csv) - Build a list of strings from a single string.
  - static java.lang.Object coerceValue​(AttributeDefinition def, java.lang.Object value) - Given the attribute definition and the stored value of the attribute coerce the value into the value specified by the schema.
  - java.lang.Object getAttribute​(java.lang.String name) - Return a Object value from the configuration attributes.
  - Attributes<java.lang.String,​java.lang.Object> getAttributes() - Returns the configuration Attributes (Map) from the Application.
  - boolean getBooleanAttribute​(java.lang.String name) - Return a boolean value from the configuration attributes.
  - openconnector.ConnectorServices getConnectorServices() -
  - java.lang.String getDecryptedAttributeValue​(java.lang.String name) - Return a decrypted string value for the given string value.
  - java.lang.String getEncryptedAttr​(java.lang.String name) - Return a decrypted string value from the configuration attributes.
  - java.lang.String getEncryptedAttribute​(java.lang.String name) - Return a decrypted string value from the configuration attributes.
  - java.lang.String getEncryptedSchemaConfig​(Schema schema, java.lang.String name) - Return an decrypted string value from the requested Schema.
  - int getIntAttribute​(java.lang.String name) - Return an int value from the configuration attributes.
  - java.util.List getListAttribute​(java.lang.String name) - Return a List value from the configuration attributes.
  - java.lang.Long getLongAttribute​(java.lang.String name) - Return a Long value from the configuration attributes.
  - java.lang.String getObligatoryEncryptedAttr​(java.lang.String name) - Return a required decrypted string value from the configuration attributes.
  - java.lang.String getObligatoryStringAttribute​(java.lang.String name) - Return a required String value from the configuration attributes.
  - java.lang.Object getRequiredAttribute​(java.lang.String name) - Return a required value from the configuration attributes.
  - java.lang.String getRequiredEncryptedAttribute​(java.lang.String name) - Return a required String value from the configuration attributes.
  - java.lang.Integer getRequiredIntAttribute​(java.lang.String name) - Return a required Integer value from the configuration attributes.
  - java.util.List getRequiredListAttribute​(java.lang.String name) - Return a required List value from the configuration attributes.
  - java.lang.String getRequiredStringAttribute​(java.lang.String name) - Return a required String value from the configuration attributes.
  - java.lang.Object getSchemaConfig​(Schema schema, java.lang.String name) - Get an attribute from the configuration that has been scoped to a schema.
  - java.lang.Object getSchemaConfig​(Schema schema, java.lang.String name, boolean defaultToUnprefixed) - Get an attribute from the configuration that has been scoped to a schema.
  - java.util.List getSchemaConfigList​(Schema schema, java.lang.String name) - Return an attribute value as a List from the requested Schema.
  - java.lang.String getSchemaConfigString​(Schema schema, java.lang.String name) -
  - java.lang.String getStringAttribute​(java.lang.String name) - Return a String value from the configuration attributes.
  - java.util.List getStringListAttribute​(java.lang.String name) -
  - java.lang.Object runRule​(java.lang.String ruleName, java.util.Map<java.lang.String,​java.lang.Object> ruleContext) - Deprecated. As of release 7.2.
  - void setAttributes​(Attributes<java.lang.String,​java.lang.Object> attributes) -
  - void setConnectorServices​(openconnector.ConnectorServices connServices) - Sets the ConnectorServices object, provided by ConnectorFactory.
  - java.lang.String toXml​(java.util.Map map) - Convert the given Map to XML.
  - java.lang.String toXml​(AbstractXmlObject obj) - Convert the given object to XML.
  - Constructor: CollectorServices​(Attributes<java.lang.String,​java.lang.Object> config) - Construct a new connector with the given Resource object.

* Class Name: ConnectorFactory
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, sailpoint.connector.ConnectorFactory
* Description: The ConnectorFactory factory to aid in getting connectors.
* Attributes:
  - None
* Methods:
  - static Connector createConnector​(java.lang.String name, Application app, java.lang.String instance) - Method will create a new Connector instance, calling the constructor that takes in an application.
  - static openconnector.Connector createConnector​(Attributes<java.lang.String,​java.lang.Object> configuration, java.lang.String name) -
  - static void destroyConnector​(Application application, java.util.Map<java.lang.String,​java.lang.Object> optionsMap) - Some connectors may hold onto resources when iterating across multiple partitions (even after close() is called on the CloseableIterators).
  - static Application getApplication​(Application originalApp) - Clone the application ( deep-copy using xml ) and then decrypt any of the passwords on the application.
  - static sailpoint.connector.LogicalConnector getCompositeConnector​(Application app) - Special factory method to see if the connector supports the CompositeConnector interface and returns that instead of Connector.
  - static Connector getConnector​(Application applicationToClone, java.lang.String instance) - Build a connector object using a clone of the given application. This method would normally be called getConnectorWithClone, but remains getConnector for backward compatibility.
  - static openconnector.Connector getConnector​(Attributes<java.lang.String,​java.lang.Object> configuration, java.lang.String instance) -
  - static Connector getConnectorNoClone​(Application application, java.lang.String instance) - Build a connector object directly from the given application
  - Constructor: ConnectorFactory() -

* Class Name: DelimitedFileConnector.RegExSingleLinedIterator
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, ResourceObject, sailpoint.connector.DelimitedFileConnector.FileContentsIterator, sailpoint.connector.DelimitedFileConnector.RegExSingleLinedIterator
* Description:
* Attributes:
  - protected CloseableIterator<java.util.List<java.lang.String>> _lines - Iterator returned from the regex parser.
  - protected java.util.Map<java.lang.String,​java.lang.Object> _nextMap -
* Methods:
  - void close() - Close the iterator, subclasses should override this method and either call closeResources to get the file transport stuff cleaned up or call this close method.
  - java.util.Map<java.lang.String,​java.lang.Object> getNextCompleteRecord() - Only required method, and must returned a map that represents the next object from the file.
  - Constructor: RegExSingleLinedIterator​(java.lang.String regEx, java.io.InputStream is, Schema schema, java.util.Map<java.lang.String,​java.lang.Object> options) -

* Class Name: ObjectAlreadyExistsException
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, sailpoint.connector.ConnectorException, java.lang.Throwable, sailpoint.connector.ConnectorException, java.lang.Exception, sailpoint.connector.ConnectorException, sailpoint.tools.AbstractLocalizableException, sailpoint.connector.ConnectorException, sailpoint.connector.ObjectAlreadyExistsException
* Description: ObjectAlreadyExistsException thrown when object we are trying to create is  already exist on Managed System.    During provisioning operation of type create(only) the connector is trying to  create an entity on the managed system but the same entity is already  existing on the managed system. for e.g. a) During provisioning operation  create an account, the connector receives the known exception/error  "Object Already exist" from the managed system. ObjectAlreadyExistsException  will be extended from ConnectorException. This class will entertain the  message String, Message object and throwable object.
* Attributes:
  - None
* Methods:
  - Constructor: ObjectAlreadyExistsException() - Construct a ExceptionWrapper with no message or nested throwable.
  - Constructor: ObjectAlreadyExistsException​(java.lang.String message) - Create a new ObjectAlreadyExistsException instance from a detailed message.
  - Constructor: ObjectAlreadyExistsException​(java.lang.String error, java.lang.String suggestion, java.lang.Throwable t) - Create a new ObjectAlreadyExistsException from an error text, suggestion text and existing exception.
  - Constructor: ObjectAlreadyExistsException​(java.lang.String message, java.lang.Throwable t) - Create a new ObjectAlreadyExistsException from an existing exception and with a detailed message.
  - Constructor: ObjectAlreadyExistsException​(java.lang.Throwable t) - Construct a new ObjectAlreadyExistsException wrapping an existing exception.
  - Constructor: ObjectAlreadyExistsException​(Message message) - Create a new ObjectAlreadyExistsException from an existing Message object.
  - Constructor: ObjectAlreadyExistsException​(Message message, java.lang.Throwable t) - Create a new ObjectAlreadyExistsException from an existing exception and with a Message object.

* Class Name: InsufficientPermissionException
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, sailpoint.connector.ConnectorException, java.lang.Throwable, sailpoint.connector.ConnectorException, java.lang.Exception, sailpoint.connector.ConnectorException, sailpoint.tools.AbstractLocalizableException, sailpoint.connector.ConnectorException, sailpoint.connector.InsufficientPermissionException
* Description: InsufficientPermissionException thrown when an user has  insufficient permissions to perform any operation. During any operation if  connector gets a known Managed System exception indicating lack of  permission, then use this exception to be thrown to the IIQ  layer.InsufficientPermissionException will be extended from  ConnectorException. This class will entertain the message string, Message  object and throwable object.
* Attributes:
  - None
* Methods:
  - Constructor: InsufficientPermissionException() - InsufficientPermissionException constructor will be called by the connector components to throw an exception.
  - Constructor: InsufficientPermissionException​(java.lang.String message) - InsufficientPermissionException constructor will be called by passing the message.
  - Constructor: InsufficientPermissionException​(java.lang.String error, java.lang.String suggestion, java.lang.Throwable t) - Create a new InsufficientPermissionException from an error text, suggestion text and existing exception.
  - Constructor: InsufficientPermissionException​(java.lang.String message, java.lang.Throwable t) - InsufficientPermissionException constructor will be called by passing the throwable object and message string.
  - Constructor: InsufficientPermissionException​(java.lang.Throwable t) - InsufficientPermissionException constructor will be called by passing the throwable object.
  - Constructor: InsufficientPermissionException​(Message message) - InsufficientPermissionException constructor will be called by passing the Message object.
  - Constructor: InsufficientPermissionException​(Message message, java.lang.Throwable t) - InsufficientPermissionException constructor will be called by passing the throwable object and Message object.

* Class Name: DelimitedFileConnector.RegExUnSortedMultiLinedIterator
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, ResourceObject, sailpoint.connector.DelimitedFileConnector.FileContentsIterator, sailpoint.connector.DelimitedFileConnector.RegExSingleLinedIterator, sailpoint.connector.DelimitedFileConnector.RegExSortedMultiLinedIterator, sailpoint.connector.DelimitedFileConnector.RegExUnSortedMultiLinedIterator
* Description:
* Attributes:
  - RegExUnSortedMultiLinedIterator​(java.lang.String regEx, java.io.InputStream is, Schema schema, java.util.Map<java.lang.String,​java.lang.Object> opts)
* Methods:
  - java.util.Map<java.lang.String,​java.lang.Object> getNextCompleteRecord() - In this case we go through the file and look for new key'ed values.
  - Constructor: RegExUnSortedMultiLinedIterator​(java.lang.String regEx, java.io.InputStream is, Schema schema, java.util.Map<java.lang.String,​java.lang.Object> opts) -

* Class Name: DelimitedFileConnector.DelimitedContentsIterator
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, ResourceObject, sailpoint.connector.DelimitedFileConnector.FileContentsIterator, sailpoint.connector.DelimitedFileConnector.DelimitedContentsIterator
* Description:
* Attributes:
  - DelimitedContentsIterator​(char delimiter, java.io.InputStream is, Schema schema, java.util.Map<java.lang.String,​java.lang.Object> options)
* Methods:
  - java.util.Map<java.lang.String,​java.lang.Object> assembleObject​(Schema schema) - Assemble a resource object from the ResultSet.
  - void close() - Close the iterator, subclasses should override this method and either call closeResources to get the file transport stuff cleaned up or call this close method.
  - java.util.Map<java.lang.String,​java.lang.Object> getNextCompleteRecord() - Only required method, and must returned a map that represents the next object from the file.
  - Constructor: DelimitedContentsIterator​(char delimiter, java.io.InputStream is, Schema schema, java.util.Map<java.lang.String,​java.lang.Object> options) -

* Class Name: ObjectNotFoundException
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, sailpoint.connector.ConnectorException, java.lang.Throwable, sailpoint.connector.ConnectorException, java.lang.Exception, sailpoint.connector.ConnectorException, sailpoint.tools.AbstractLocalizableException, sailpoint.connector.ConnectorException, sailpoint.connector.ObjectNotFoundException
* Description: The base exception thrown by components.
* Attributes:
  - None
* Methods:
  - Constructor: ObjectNotFoundException() - Construct a ExceptionWrapper with no message or nested throwable.
  - Constructor: ObjectNotFoundException​(java.lang.String message) - Construct a new ObjectNotFoundException with a detailed message.
  - Constructor: ObjectNotFoundException​(java.lang.String error, java.lang.String suggestion, java.lang.Throwable t) - Create a new ObjectNotFoundException from an error text, suggestion text and existing exception.
  - Constructor: ObjectNotFoundException​(java.lang.String message, java.lang.Throwable t) - Create a new ObjectNotFoundException from an existing exception.
  - Constructor: ObjectNotFoundException​(java.lang.Throwable t) - Construct a new ObjectNotFoundException wrapping an existing exception.
  - Constructor: ObjectNotFoundException​(Message message) - ObjectNotFoundException constructor will be called by passing the throwable object and Message object.
  - Constructor: ObjectNotFoundException​(Message message, java.lang.Throwable t) - ObjectNotFoundException constructor will be called by passing the throwable object and Message object.

* Class Name: ExpiredPasswordException
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, sailpoint.connector.ConnectorException, java.lang.Throwable, sailpoint.connector.ConnectorException, java.lang.Exception, sailpoint.connector.ConnectorException, sailpoint.tools.AbstractLocalizableException, sailpoint.connector.ConnectorException, sailpoint.connector.AuthenticationFailedException, sailpoint.connector.ExpiredPasswordException
* Description: A connector exception indicating that authentication failed because of an expired password.   Note that this can be thrown from two contexts. It is thrown from Authenticator to the UI tier  when either the native IIQ password policy or the pass-through auth application says the  password is expired. The UI uses this to transition to the password reset pages.   It is also thrown by Connectors to the Authenticator to indicate that the the password is  considered expired on the managed system. In this case, the exception may be decorated with  information about the native account.   Created by Jeff, Ketan
* Attributes:
  - None
* Methods:
  - java.lang.String getAppName() -
  - Identity getIdentity() -
  - java.lang.String getNativeIdentity() -
  - ResourceObject getResourceObject() -
  - void setAppName​(java.lang.String appName) -
  - void setIdentity​(Identity ident) -
  - void setNativeIdentity​(java.lang.String id) -
  - void setResourceObject​(ResourceObject ro) -
  - Constructor: ExpiredPasswordException() - Construct ExpiredPasswordException with no message or nested throwable.
  - Constructor: ExpiredPasswordException​(java.lang.String username) - Construct ExpiredPasswordException with the name of the account with the expired password.
  - Constructor: ExpiredPasswordException​(java.lang.String username, java.lang.Throwable t) - Create a new ExpiredPasswordException from an existing exception.
  - Constructor: ExpiredPasswordException​(java.lang.String username, java.lang.Throwable t, ResourceObject ro) - Construct ExpiredPasswordException with the name of the account with the expired password, password expired exception from application and an account object with the expired password.
  - Constructor: ExpiredPasswordException​(java.lang.String username, ResourceObject ro) - Construct ExpiredPasswordException with the name of the account with the expired password and an account object with the expired password.

* Class Name: InvalidConfigurationException
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, sailpoint.connector.ConnectorException, java.lang.Throwable, sailpoint.connector.ConnectorException, java.lang.Exception, sailpoint.connector.ConnectorException, sailpoint.tools.AbstractLocalizableException, sailpoint.connector.ConnectorException, sailpoint.connector.InvalidConfigurationException
* Description: This exception thrown when an application lacking some configuration. During  any operation if connector requires certain configuration to connect to the  managed-system which is not provided or is faulty. This could happen  before/after sending a request to the managed system.When a connector  receives any error/exception of the managed system, and to fix such error if  there is a need to correct the application configuration. This could take  place when the managed system provides a response to a request.  InvalidConfigurationException is extended from ConnectorException. This class  will entertain the message string, Message object and throwable object.
* Attributes:
  - None
* Methods:
  - Constructor: InvalidConfigurationException() - InvalidConfigurationException constructor will be called by the connector components to throw an exception.
  - Constructor: InvalidConfigurationException​(java.lang.String message) - InvalidConfigurationException constructor will be called by passing the message String.
  - Constructor: InvalidConfigurationException​(java.lang.String error, java.lang.String suggestion, java.lang.Throwable t) - Create a new InvalidConfigurationException from an error text, suggestion text and existing exception.
  - Constructor: InvalidConfigurationException​(java.lang.String message, java.lang.Throwable t) - InvalidConfigurationException constructor will be called by passing the throwable object and message string.
  - Constructor: InvalidConfigurationException​(java.lang.Throwable t) - InvalidConfigurationException constructor will be called by passing the throwable object.
  - Constructor: InvalidConfigurationException​(Message message) - InvalidConfigurationException constructor will be called by passing the Message object.
  - Constructor: InvalidConfigurationException​(Message message, java.lang.Throwable t) - InvalidConfigurationException constructor will be called by passing the throwable object and Message object.

* Class Name: AbstractFileBasedConnector
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, sailpoint.connector.CollectorServices, sailpoint.connector.AbstractConnector, sailpoint.connector.AbstractFileBasedConnector
* Description: A class that offers file transport services for File Based Connectors.  Classes that extend this class can be easily ftp and scp transport   enabled to allow for files being parsed to be stored remotely.
* Attributes:
  - static java.lang.String CONFIG_DEST_DIR - Deprecated. Unused
  - static java.lang.String CONFIG_FILE - Configuration attribute that specifies the file to use.
  - static java.lang.String CONFIG_PORT - Configuration attribute that specifies the port to use for remote transports.
  - static java.lang.String CONFIG_REGULAR_EXPRESSION - Configuration attribute that specifies the regular expression to use to parse the file contents.
  - static java.lang.String CONFIG_SCP_PRIVATE_KEY - Configuration attribute that specifies the scp private key to use for the scp transport.
  - static java.lang.String CONFIG_TRANSPORT - Configuration attribute that specifies the transport type.
  - static java.lang.String CONFIG_TRANSPORT_USER - Configuration attribute that specifies the username to use for remote transports.
  - static java.lang.String CONFIG_TRANSPORT_USER_PW - Configuration attribute that specifies the password to use for remote transports.
  - static java.lang.String TRANSPORT_TYPE_FTP - Value to specify using ftp for CONFIG_TRANSPORT.
  - static java.lang.String TRANSPORT_TYPE_FTPS - Value to specify using ftps for CONFIG_TRANSPORT.
  - static java.lang.String TRANSPORT_TYPE_LOCAL - Value to specify a local file for CONFIG_TRANSPORT.
  - static java.lang.String TRANSPORT_TYPE_SCP - Value to specify using scp for CONFIG_TRANSPORT.
  - static java.lang.String TRANSPORT_TYPE_SFTP - Value to specify using sftp for CONFIG_TRANSPORT.
* Methods:
  - protected void closeResources() - Close all resources that need to be closed.
  - protected java.io.InputStream getFileStream​(java.lang.String fileName) - Return an InputStream for reading the file with the given name, using the configured transport.
  - protected java.io.InputStream getFileStream​(java.lang.String fileName, java.lang.String destination) - Return an InputStream for reading the file with the given name, using the configured transport and copying the file into the given destination for a remote transport.
  - static void skipLines​(java.io.BufferedReader reader, int toSkip) - Skip the number of lines specified from the current reader position.
  - Constructor: AbstractFileBasedConnector​(Application application) -

* Class Name: ConnectorException
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, java.lang.Throwable, java.lang.Exception, sailpoint.tools.AbstractLocalizableException, sailpoint.connector.ConnectorException
* Description: The base exception thrown by all connectors.
* Attributes:
  - None
* Methods:
  - java.lang.String getErrorCode() - This function return the error code
  - Constructor: ConnectorException() - Construct a ExceptionWrapper with no message or nested throwable.
  - Constructor: ConnectorException​(java.lang.String message) - Construct a new ConnectorException with a detailed message.
  - Constructor: ConnectorException​(java.lang.String error, java.lang.String suggestion, java.lang.Throwable t) - Create a new ConnectorException from an error text, suggestion text and existing exception.
  - Constructor: ConnectorException​(java.lang.String message, java.lang.Throwable t) - Create a new ConnectorException from an existing exception.
  - Constructor: ConnectorException​(java.lang.Throwable t) - Construct a new ConnectorException wrapping an existing exception.
  - Constructor: ConnectorException​(java.lang.Throwable t, java.lang.String errorCode) - This constructor is used for passing error code
  - Constructor: ConnectorException​(Message message) - Construct a new ConnectorException with a detailed message.
  - Constructor: ConnectorException​(Message message, java.lang.Throwable t) - Create a new ConnectorException from an existing exception and object Message.

* Class Name: ConnectionFailedException
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, sailpoint.connector.ConnectorException, java.lang.Throwable, sailpoint.connector.ConnectorException, java.lang.Exception, sailpoint.connector.ConnectorException, sailpoint.tools.AbstractLocalizableException, sailpoint.connector.ConnectorException, sailpoint.connector.ConnectionFailedException
* Description: The base exception thrown by components.
* Attributes:
  - None
* Methods:
  - Constructor: ConnectionFailedException() - Construct a ExceptionWrapper with no message or nested throwable.
  - Constructor: ConnectionFailedException​(java.lang.String message) - Construct a new ConnectionFailedException with a detailed message.
  - Constructor: ConnectionFailedException​(java.lang.String error, java.lang.String suggestion, java.lang.Throwable t) - Create a new ConnectionFailedException from an error text, suggestion text and existing exception.
  - Constructor: ConnectionFailedException​(java.lang.String message, java.lang.Throwable t) - Create a new ConnectionFailedException from an existing exception.
  - Constructor: ConnectionFailedException​(java.lang.Throwable t) - Construct a new ConnectionFailedException wrapping an existing exception.
  - Constructor: ConnectionFailedException​(Message message) - Construct a new ConnectionFailedException with a detailed message.
  - Constructor: ConnectionFailedException​(Message message, java.lang.Throwable t) - Create a new ConnectionFailedException from an existing exception and object Message.

* Class Name: TimeoutException
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, sailpoint.connector.ConnectorException, java.lang.Throwable, sailpoint.connector.ConnectorException, java.lang.Exception, sailpoint.connector.ConnectorException, sailpoint.tools.AbstractLocalizableException, sailpoint.connector.ConnectorException, sailpoint.connector.ConnectionFailedException, sailpoint.connector.TimeoutException
* Description: TimeoutException thrown when the managed system does not respond and number of attempts to connect are failed.  TimeoutException is extended from ConnectionFailedException.  This class will entertain the message string, Message object and throwable object.
* Attributes:
  - None
* Methods:
  - Constructor: TimeoutException() - TimeoutException constructor will be called by the connector components to throw an exception.
  - Constructor: TimeoutException​(java.lang.String message) - TimeoutException constructor will be called by passing the message String.
  - Constructor: TimeoutException​(java.lang.String error, java.lang.String suggestion, java.lang.Throwable t) - Create a new TimeoutException from an error text, suggestion text and existing exception.
  - Constructor: TimeoutException​(java.lang.String message, java.lang.Throwable t) - TimeoutException constructor will be called by passing the throwable object and message string.
  - Constructor: TimeoutException​(java.lang.Throwable t) - TimeoutException constructor will be called by passing the throwable object.
  - Constructor: TimeoutException​(Message message) - TimeoutException constructor will be called by passing the Message object.
  - Constructor: TimeoutException​(Message message, java.lang.Throwable t) - TimeoutException constructor will be called by passing the throwable object and Message object.

* Class Name: AuthenticationFailedException
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, sailpoint.connector.ConnectorException, java.lang.Throwable, sailpoint.connector.ConnectorException, java.lang.Exception, sailpoint.connector.ConnectorException, sailpoint.tools.AbstractLocalizableException, sailpoint.connector.ConnectorException, sailpoint.connector.AuthenticationFailedException
* Description: The base exception thrown by components.
* Attributes:
  - None
* Methods:
  - Constructor: AuthenticationFailedException() - Construct a ExceptionWrapper with no message or nested throwable.
  - Constructor: AuthenticationFailedException​(java.lang.String message) - Construct a new AuthenticationFailedException with a detailed message.
  - Constructor: AuthenticationFailedException​(java.lang.String error, java.lang.String suggestion, java.lang.Throwable t) - Create a new AuthenticationFailedException from an error text, suggestion text and existing exception.
  - Constructor: AuthenticationFailedException​(java.lang.String message, java.lang.Throwable t) - Create a new AuthenticationFailedException from an existing exception.
  - Constructor: AuthenticationFailedException​(java.lang.Throwable t) - Construct a new AuthenticationFailedException wrapping an existing exception.
  - Constructor: AuthenticationFailedException​(Message message) - Create a new AuthenticationFailedException with Message instance.
  - Constructor: AuthenticationFailedException​(Message message, java.lang.Throwable t) - Create a new AuthenticationFailedException from an existing exception.

* Class Name: DelimitedFileConnector.FileContentsIterator
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, ResourceObject, sailpoint.connector.DelimitedFileConnector.FileContentsIterator
* Description:
* Attributes:
  - protected java.util.Date _blockStart -
  - protected java.util.List<java.lang.String> _columns -
  - protected boolean _filterEmptyRecords - Flag to indicate if maps built with no keys should be filtered.
  - protected boolean _iteratedToEnd -
  - protected long _merged -
  - protected ResourceObject _next -
  - protected Filter _objectFilter -
  - protected Attributes<java.lang.String,​java.lang.Object> _options -
  - protected long _processed -
  - protected long _returned - Debug/Performance counters
  - protected java.lang.String _simpleSearchString -
  - protected java.util.Map<java.lang.String,​java.lang.Object> _state - Give each iteration process its own state, so it can be given to the rules then clear it when closed.
* Methods:
  - java.util.Map<java.lang.String,​java.lang.Object> buildMap​(java.util.List<java.lang.String> record, java.util.List<java.lang.String> cols) -
  - void close() - Close the iterator, subclasses should override this method and either call closeResources to get the file transport stuff cleaned up or call this close method.
  - java.io.BufferedReader getBufferedReader() -
  - abstract java.util.Map<java.lang.String,​java.lang.Object> getNextCompleteRecord() - Only required method, and must returned a map that represents the next object from the file.
  - boolean hasNext() - Returns true if there is another object in the iterator.
  - ResourceObject next() - Returns the next element in the iterator.
  - protected void printProgress() -
  - boolean shouldFilter​(java.util.Map<java.lang.String,​java.lang.Object> map) - Apply the FilterString and if the line matches it will be filtered.
  - protected boolean shouldFilterSimpleString​(java.util.List<java.lang.String> line) - If the line matches the simpleSearchString defined this method will return true.
  - protected void skipLines​(Schema schema, java.io.BufferedReader reader) - If called, the reader will be skipped forward the number of lines configured for the "linesToBeSkipped" configuration attribute.
  - Constructor: FileContentsIterator​(java.io.InputStream is, Schema schema, java.util.Map<java.lang.String,​java.lang.Object> options) -

* Class Name: AbstractConnector
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, sailpoint.connector.CollectorServices, sailpoint.connector.AbstractConnector
* Description: A base abstract connector that is intended to be extended by  all Connector classes.  Extending this class instead of  implementing the Connector interface directly will allow the  Connector interface to be extended without breaking old code.    All of the Connectors that extend this class will call  the one of the two constructors that take an Application  and an optional instance.  The application object will  configure the runtime Attributes and Features of the  connector.     This class will implement any new methods that are added over time  and in most cases will just throw UnsupportedOperation exception  when the methods has been stubbed out.     Along with stubbing out the Connector interface it also  provides methods for the following common services:     Reading and coercing configuration attributes from Application data          CollectorServices.getAttribute(String)   CollectorServices.getStringAttribute(String)   CollectorServices.getBooleanAttribute(String)   CollectorServices.getListAttribute(String)   CollectorServices.getEncryptedAttribute(String)   CollectorServices.getRequiredAttribute(String)   CollectorServices.getRequiredStringAttribute(String)   CollectorServices.getRequiredListAttribute(String)   CollectorServices.getRequiredEncryptedAttribute(String)   CollectorServices.getRequiredListAttribute(String)   CollectorServices.getSchemaConfig(Schema, String)    Permissions Merging          mergePermissions(List, List)    Map Merging           mergeMaps(Schema, Map, Map, List)   defaultMergeMaps(Map, Map, List)    Building ResourceObjects from java.util.Map objects          defaultTransformObject(Schema, Map)   defaultTransformObject(Schema, Map, boolean)   defaultTransformObject(Schema, Map, boolean, List)     Coercing attribute values based on AttributeDefinition          CollectorServices.coerceValue(AttributeDefinition, Object)
* Attributes:
  - protected java.util.Map<java.lang.String,​java.lang.Object> _state -
  - static java.lang.String CONFIG_DONT_TRANSFORM_CSV - The name of the configuration attribute that is used when transforming a Map to ResourceObject in #buildResourceObjectFromMap(Schema schema, Map mergedObject) By default attributes marked multi-valued and in csv format will be transformed from csv to a List of strings.
  - static java.lang.String CONFIG_DONT_TRANSFORM_CSV_ATTRS - The name of the configuration attribute that is used when transforming a Map to ResourceObject in #buildResourceObjectFromMap(Schema schema, Map mergedObject) By default attributes marked multi-valued and in csv format will be transformed from csv to a List of strings.
  - static java.lang.String CONFIG_FILTER_STRING - The name of a common configuration item which specifies the string version of a sailpoint.object.Filter to help filter out unnecessary objects.
  - static java.lang.String CONFIG_PAGE_SIZE - The name of a common configuration attribute that specifies the number of objects that should be returned per page when the back-end application has the concept of paging.
  - static java.lang.String CONFIG_RETRYABLE_ERRORS - The name of the configuration attribute that is used when shouldRetry method is called by the connector implementation to Check if the error message is configured so that it can be retried.
  - static int DEFAULT_PAGE_SIZE - The default value used when paging is being implemented during object iteration.
  - static java.lang.String RESPONSE_DATA_KEY - Key that holds the response value that is returned from the respective connector during aggregation/provisioning/update(getObject)
* Methods:
  - ResourceObject authenticate​(java.lang.String username, java.lang.String password) - Default implementation of the authenticate method, which throws a UnsupportedOperationException exception.
  - ResourceObject authenticate​(java.lang.String accountId, java.util.Map<java.lang.String,​java.lang.Object> options) - Default implementation of the authenticate method with options, which throws a UnsupportedOperationException exception.
  - ResourceObject buildResourceObjectFromMap​(Schema schema, java.util.Map<java.lang.String,​java.lang.Object> mergedObject) - Given a Map, build a ResourceObject from the keys/values of the Map.
  - ProvisioningResult checkStatus​(java.lang.String id) - New in 5.5 this method can be used by async provisioning implementations to check the status of a queued request.
  - static java.util.Map<java.lang.String,​java.lang.Object> defaultMergeMaps​(java.util.Map<java.lang.String,​java.lang.Object> obj1, java.util.Map<java.lang.String,​java.lang.Object> obj2, java.util.List<java.lang.String> mergeAttrs) - Method to merge to map objects, designed initially for use in the DelimitedFileConnector and the JDBCConnector - but general enough for use elsewhere.
  - static ResourceObject defaultTransformObject​(Schema schema, java.util.Map<java.lang.String,​java.lang.Object> object) - Build a resource object from a map, coercing csvs to lists.
  - static ResourceObject defaultTransformObject​(Schema schema, java.util.Map<java.lang.String,​java.lang.Object> object, boolean coerceCsvsToList) - Build a resource object from a map, optionally coercing csvs to lists.
  - static ResourceObject defaultTransformObject​(Schema schema, java.util.Map<java.lang.String,​java.lang.Object> object, boolean coerceCsvsToList, java.util.List<java.lang.String> attrsToLeaveAlone) - Build a resource object from a map optionally using the schema attribute definitions to drive coercion.
  - void destroy​(java.util.Map<java.lang.String,​java.lang.Object> optionsMap) - Called by aggregator at the end of aggregation
  - java.util.Map<java.lang.String,​java.lang.Object> discoverApplicationAttributes​(java.util.Map<java.lang.String,​java.lang.Object> options) - By default throw an exception.
  - CloseableIterator<connector.common.DiscoveredApplication> discoverApplications() -
  - Schema discoverSchema​(java.lang.String objectType, java.util.Map<java.lang.String,​java.lang.Object> options) - By default throw an exception.
  - java.util.Map doHealthCheck​(java.util.Map<java.lang.String,​java.lang.Object> options) - Light Weight Test Connection
  - protected java.util.List<Permission> filterPermissions​(java.util.List<Permission> unfiltered) - Default implementation of filtering permissions.
  - protected static java.util.List<Permission> filterPermissions​(java.util.List<Permission> configFilters, java.util.List<Permission> unfiltered) - Filter a list of permissions given the configuredFilters, which is a list of special Permissions AND the un-filtered list.
  - Application getApplication() - Returns the Application associated with this Connector.
  - java.util.List<java.lang.String> getAttributeNames​(Schema schema, java.util.Map<java.lang.String,​java.lang.Object> options) - First check for OP_ATTRIBUTE_NAMES in the options list, if present use the defined names.
  - protected java.util.List<java.lang.String> getAttributesToRetrieve​(java.lang.String objectType, java.util.Map<java.lang.String,​java.lang.Object> options) - A convenience method used to compute which attributes should be included on returned resource objects.
  - java.util.Iterator<java.util.Map<java.lang.String,​java.lang.Object>> getChangeLogExtract​(java.util.Map<java.lang.String,​java.lang.Object> requestParams) - Default implementation of the getChangeLogExtract method, which throws a UnsupportedOperationException exception.
  - java.util.Map<java.lang.String,​java.lang.Object> getConfigOptions​(java.lang.String configOptionsKey) - Default implementation of getConfigOptions method that does nothing.
  - java.lang.String getConnectorType() - Returns a meaningful nice to display String to describe the connector.
  - java.util.List<AttributeDefinition> getDefaultAttributes() - Returns a list of AttributeDefinitions for the configuration attributes.
  - java.util.List<Schema> getDefaultSchemas() - Returns a list of Schemas objects, each of which describes a separate objectType.
  - java.util.Map<java.lang.String,​java.lang.Object> getDependencyData() - Get the Map of details, status of the dependent component on which the Connector is dependent.
  - protected static java.lang.String getEffectiveAttribute​(Schema schema, java.lang.String name) - Attempt to find the named attribute in the schema, if its found check if it has an internal name.
  - java.util.List<java.util.Map<java.lang.String,​java.lang.Object>> getExtractPartitions​(java.util.Map<java.lang.String,​java.lang.Object> requestParams, java.lang.String extractType) - This method will be called to get extract Partition for ARM extract requests
  - java.lang.Boolean getFeatureFlagValue​(java.lang.String name, boolean defaultValue) - This method will return value of featureFlag name provided.
  - java.lang.String getInstance() -
  - java.util.List<Partition> getIteratorPartitions​(java.lang.String objectType, int suggestedPartitionCount, Filter filter, java.util.Map<java.lang.String,​java.lang.Object> ops) - Default implementation returns null to indicate the connector does not have any partitions defined.
  - Application getLocalApplication() - Returns the application associated with this Connector depending upon whether its a cloud based application or not.
  - ProvisioningPlan getLoggingPlan​(ProvisioningPlan src) - Return loggable plan removing secret attributes.
  - boolean getProductFlagValue​(java.lang.String name, boolean defaultValue) - Returns requested Product Flag set by CCG, if not set then return default value.
  - Application getProxiedApplication​(java.lang.String name, java.util.Map<java.lang.String,​java.lang.Object> options) - Default implementation of the proxied application constructor.
  - protected Connector getRealConnector​(java.lang.String clazzName) - Method that is used in cases where the "real" connector must be wrapped in case dependent jars are not always presents.
  - java.lang.Object getRequiredSchemaConfig​(Schema schema, java.lang.String name) - Throw and exception if a configuration attribute is not found.
  - Schema getSchema​(java.lang.String objectType) - Get the Schema object for a given objectType.
  - Schema getSchema​(java.lang.String objectType, boolean throwIfMissing) - Given the objectType returned the Schema stored on the application.
  - java.util.List<java.lang.String> getSchemaAttributeNames​(java.lang.String objectType) - Returns the list of names contained in the Schema definition for a given objectType.
  - java.util.List<AttributeDefinition> getSchemaAttributes​(java.lang.String objectType) - Returns the list of schema attributes associated with the supplied objectType.
  - java.lang.String getSchemaNativeObjectType​(java.lang.String objectType) - Returns the list of schema attributes associated with the supplied objectType.
  - java.util.List<java.lang.String> getSchemaPrototypeAttributeNames​(java.lang.String objectType) - Returns a list of attribute names from the schema that are marked as "prototype" relevant.
  - java.util.List<Schema> getSchemas() - Returns a list of the Schema objects defined on the application that configured this connector.
  - java.util.Iterator<java.util.Map<java.lang.String,​java.lang.Object>> getSecurityExtract​(java.util.Map<java.lang.String,​java.lang.Object> requestParams) - Default implementation of the getSecurityExtract method, which throws a UnsupportedOperationException exception.
  - connector.common.statisticscollector.StatisticsCollector getStatisticsCollector() - Retrive the StatisticsCollector object which is stored at Connector proxy.
  - java.util.List<Application.Feature> getSupportedFeatures() - Every connector needs to register which sailpoint.object.Application.Feature are supported.
  - java.lang.String getSystemIdentity() -
  - Application getTargetApplication() -
  - java.lang.String getTargetInstance() -
  - java.util.Iterator<java.util.Map<java.lang.String,​java.lang.Object>> getUtilizationExtract​(java.util.Map<java.lang.String,​java.lang.Object> requestParams) - Default implementation of the getUtilizationExtract method, which throws a UnsupportedOperationException exception.
  - static boolean isAccount​(Schema schema) - Test the schema and returns true if the schema's objectType is Connector.TYPE_ACCOUNT
  - static boolean isGroup​(Schema schema) - Test the schema and returns true if the schema's defined objectType is Connector.TYPE_GROUP group
  - protected boolean isSecret​(java.lang.String name) - Return if name is a secret attribute.
  - CloseableIterator<ResourceObject> iterateObjects​(Partition partition) - Method that gets called when partitioning during iteration, throws an exception by default.
  - void logApplication​(Application src) - Deprecated.
  - ProvisioningPlan logPlan​(ProvisioningPlan src) - Deprecated. in CONVASHI-413, replaced by getLoggingPlan(ProvisioningPlan)
  - java.util.Map<java.lang.String,​java.lang.Object> mergeMaps​(Schema schema, java.util.Map<java.lang.String,​java.lang.Object> current, java.util.Map<java.lang.String,​java.lang.Object> newObject, java.util.List<java.lang.String> mergeAttrs) - When in "merge" mode, merge the specified attributes.
  - static java.util.List<Permission> mergePermissions​(java.util.List<Permission> currentPerms, java.util.List<Permission> newPerms) - Given a new list of permissions merge them into the currentPermissions list.
  - ProvisioningResult provision​(ProvisioningPlan plan) - New in 5.2.
  - void saveConnectorState() - Save the new connector state values into the app config of the target application
  - void saveConnectorState​(java.util.Map<java.lang.String,​java.lang.Object> stateMap) - Save the connector state values into the app config
  - void setApplication​(Application application) - Set the Application associated with this object.
  - void setConnectorState​(java.lang.String attribute, java.lang.Object val) - Interface to set new connector config value
  - void setInstance​(java.lang.String ins) - Set the instance for template applications.
  - void setStatisticsCollector​(connector.common.statisticscollector.StatisticsCollector statisticsCollector) - Set the StatisticsCollector object require for underlying connector to push the aggreagtion statistics.
  - void setSystemIdentity​(java.lang.String id) - Sets the target "meta" user id if this application is a multiplexer or bridge that requires operations be redirected through a meta user.
  - void setTargetApplication​(Application app) - Sets the target application if this application is a multiplexer or bridge.
  - void setTargetInstance​(java.lang.String inst) - Sets the target application instance if this application is a multiplexer or bridge.
  - boolean shouldRetry​(java.lang.Exception ex, java.lang.String error, ProvisioningResult result) - Helper for checking if the provisioning error can be retried - 1.
  - protected Schema stringListToSchema​(java.lang.String objectType, java.util.List<java.lang.String> columns) - Build a list of schema attributes from list of attribute names.
  - boolean supportsFeature​(Application.Feature feature) - Returns true if the passed in Feature is supported by a connector.
  - boolean supportsPartitionedDeltaAggregation() - Gets if the connector supports partitioned delta aggregation
  - void updateApplicationConfig() - Updates the application config if the connectorStateMap value is updated.
  - Constructor: AbstractConnector​(Application application) - Construct a new connector with the given Application object.
  - Constructor: AbstractConnector​(Application application, java.lang.String instance) - Construct a new connector with the given Application object and instance.

* Class Name: DelimitedFileConnector.RegExSortedMultiLinedIterator
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, ResourceObject, sailpoint.connector.DelimitedFileConnector.FileContentsIterator, sailpoint.connector.DelimitedFileConnector.RegExSingleLinedIterator, sailpoint.connector.DelimitedFileConnector.RegExSortedMultiLinedIterator
* Description:
* Attributes:
  - protected java.lang.String _indexColumn -
  - protected java.util.List<java.lang.String> _mergeColumns -
* Methods:
  - java.util.Map<java.lang.String,​java.lang.Object> getNextCompleteRecord() - In this case we go through the file and look for new key'ed values.
  - Constructor: RegExSortedMultiLinedIterator​(java.lang.String regEx, java.io.InputStream is, Schema schema, java.util.Map<java.lang.String,​java.lang.Object> options) -

* Class Name: DelimitedFileConnector
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, sailpoint.connector.CollectorServices, sailpoint.connector.AbstractConnector, sailpoint.connector.AbstractFileBasedConnector, sailpoint.connector.DelimitedFileConnector
* Description: A connector that can be used to read data from  one or more delimited text files.   There are two parsing modes for this connector.     RFC4180 Delimited text      More specific information see RFC4180 it is     the basis for most of the parsing.      In this mode you can specify a single character     to break the contents of the file line by line     into tokens. Then a BeanShell rule is called     for each of the lines in the file so transformations     on the data can be performed as the data is being     read from the file.       RegularExpression Grouping - Using Java's regexp library      In this mode must specify a regular expressions using     regular expression groups the connector will break     up the contents of the file into tokens.
* Attributes:
  - static java.util.Map<java.lang.String,​java.util.Map<java.lang.String,​sailpoint.connector.DelimitedFileConnector.DataCache>> _dataCaches - Optional memory cache for data when getObject is called.
  - static java.lang.String CONFIG_COLUMN_LENGTH_STRICT -
  - static java.lang.String CONFIG_COLUMN_NAMES -
  - static java.lang.String CONFIG_COMMENT_CHARACTER -
  - static java.lang.String CONFIG_DELIMITED_PARSE_TYPE -
  - static java.lang.String CONFIG_DELIMITER -
  - static java.lang.String CONFIG_FILE_DESTINATION -
  - static java.lang.String CONFIG_FILE_ENCODING -
  - static java.lang.String CONFIG_FILENAME - Configuration attribute that specifies the file to use.
  - static java.lang.String CONFIG_FILTER -
  - static java.lang.String CONFIG_FILTER_EMPTY_RECORDS -
  - static java.lang.String CONFIG_HAS_HEADER -
  - static java.lang.String CONFIG_IGNORE_QUOTES -
  - static java.lang.String CONFIG_INDEX_COLUMN -
  - static java.lang.String CONFIG_IS_CASE_INSENSITIVE_MERGE -
  - static java.lang.String CONFIG_IS_SORTED -
  - static java.lang.String CONFIG_LINES_TO_SKIP -
  - static java.lang.String CONFIG_MERGE_COLUMNS -
  - static java.lang.String CONFIG_MERGE_ROWS -
  - static java.lang.String CONFIG_PARSE_TYPE -
  - static java.lang.String CONFIG_PARTITION_OBJECT_COUNT -
  - static java.lang.String CONFIG_POST_ITERATE_RULE -
  - static java.lang.String CONFIG_PRE_ITERATE_RULE -
  - static java.lang.String CONFIG_REGEX -
  - static java.lang.String CONFIG_REGEX_MULTILINED_MODE -
  - static java.lang.String CONFIG_REGEXP_PARSE_TYPE -
  - static java.lang.String CONFIG_SIMPLE_SEARCH_STRING -
  - static java.lang.String CONFIG_SPACE -
  - static java.lang.String CONFIG_USE_CACHE - Flag that indicates when getObject is called the iterated objects should be stored in memory to prevent trolling through the file for each object requested.
  - static java.lang.String CONNECTOR_TYPE - Constant denoting this connector's type.
  - boolean isAggregation -
  - static java.lang.String OPTION_CLEAR_CACHE -
* Methods:
  - ResourceObject buildResourceObjectFromMap​(Schema schema, java.util.Map<java.lang.String,​java.lang.Object> mergedObject) - Overide this method from the Abstract class so we can automatically add in the mergeColumns to the do not coerce list as default behavior.
  - static void clearDataCache() - Empty the cached file contents.
  - java.io.BufferedReader createBufferedReader​(java.io.BufferedInputStream bis) - Create a BufferedReader from the given BufferedInputStream.
  - static java.util.Map<java.lang.String,​java.lang.Object> defaultBuildMap​(java.util.List<java.lang.String> cols, java.util.List<java.lang.String> record) - Static method that takes an ordered list of columns names and a parsed record broken up into ordered tokens.
  - static java.util.Map<java.lang.String,​java.lang.Object> defaultBuildMap​(java.util.List<java.lang.String> cols, java.util.List<java.lang.String> record, boolean trimValues) - This method is the same as defaultBuildMap(List, List) but allows control over if the values should be trimmed with the last parameter.
  - Schema discoverSchema​(java.lang.String objectType, java.util.Map<java.lang.String,​java.lang.Object> options) - Discover the schema from the file or use the defined column names.
  - boolean filterEmptyRecords​(Schema schema) - Return whether empty records should be filtered for the given Schema.
  - java.util.List<AttributeDefinition> getBaseAttributes() - This list of attributes is relevant across all file based connectors.
  - java.util.List<java.lang.String> getColumnNames​(Schema schema) - Return the names of the columns for the given Schema from the config.
  - java.lang.String getCommentCharacter​(Schema schema) - Return the comment character for the given Schema from the config.
  - java.lang.String getConnectorType() - Returns a meaningful nice to display String to describe the connector.
  - java.util.List<AttributeDefinition> getDefaultAttributes() - Publish which attributes need to be configured and which can optionally be configured.
  - java.util.List<Schema> getDefaultSchemas() - This connector does not have a default schema, the data file will determine the schemas.
  - protected java.lang.Character getDelimiter​(Schema schema) - Return the Character used to delimit fields for the given Schema.
  - java.lang.String getFileDestination​(Schema schema) - Return the file destination for the given Schema from the config.
  - java.lang.String getFileName​(Schema schema) - Return the file name for the given Schema from the config.
  - protected CloseableIterator<ResourceObject> getIterator​(java.io.InputStream stream, Schema schema, java.util.Map<java.lang.String,​java.lang.Object> options) - Return a CloseableIterator that returns ResourceObjects read from the given InputStream for the given Schema.
  - java.util.List<Partition> getIteratorPartitions​(java.lang.String objectType, int suggestedPartitionCount, Filter filter, java.util.Map<java.lang.String,​java.lang.Object> ops) - Called during aggregation of accounts and groups to slice the data in a way that different machines and/or different threads can aggregate data.
  - protected java.util.List<AttributeDefinition> getMergeAttributess() - Return attributes that are necessary for the merge functionality.
  - ResourceObject getObject​(java.lang.String objectType, java.lang.String identity, java.util.Map<java.lang.String,​java.lang.Object> options) - Communicate with the application and get the object which should be identified by the objectType and identity.
  - protected java.util.List<AttributeDefinition> getPartitionConfigs() - Return the AttributeDefinitions used to configure partitioning.
  - java.util.List<Application.Feature> getSupportedFeatures() - Every connector needs to register which sailpoint.object.Application.Feature are supported.
  - boolean isGroupSchema​(Schema schema) - Prior to version 6.4, delimited file connectors only supported the object type 'group'.
  - CloseableIterator<ResourceObject> iterateObjects​(java.lang.String objectType, Filter filter, java.util.Map<java.lang.String,​java.lang.Object> options) - Returns an iterator over the ResourceObjects in the file.
  - CloseableIterator<ResourceObject> iterateObjects​(Partition partition) - Iterate over a subset (defined by the Partition) of the objects.
  - protected java.util.List<java.lang.String> readColumnsFromHeader​(sailpoint.tools.RFC4180LineParser parser, java.io.BufferedReader buffer) -
  - protected java.io.InputStream runPreIterateRule​(Schema schema) - Run a rule before we iterate, after we have the stream so customers can check things that were left behind by the postIterate rule.
  - void testConfiguration() - Connects to the file and attempts to iterate over the data stopping after the first line has been parsed and a non-null ResourceObject returned.
  - java.lang.String uncompressString​(java.lang.String compressedData) - This method will uncompress the file stream that is passed to each partition
  - Constructor: DelimitedFileConnector​(Application app) -

* Class Name: Connector
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: AbstractConnector, AbstractFileBasedConnector, DelimitedFileConnector, JDBCConnector
* Description: The Connector interface allows  IIQ to authenticate and read data from to enterprise applications.  It can be used used to communicate with applications such  as LDAP, JDBC Or SAP. There are several built in connectors,  but the interface can be used to create Connectors for home-grown  applications too.    Connectors will return ResourceObjects to represent application objects.  All ResourceObjects have a type that is either account or group.  The definition  of the object attributes will be defined by a Schema objects that holds  a list of AttributeDefinitions. The individual AttributeDefinition objects  define an attribute's type, name, description and value length.     The AbstractConnector class provides many of the necessary services  that span across all connectors. It is highly recommended that  all connectors extend AbstractConnector instead implementing this  interface directly. This will help avoid incompatibilities  when changes are made to the interface from release to release.     In some cases when a connector reads from a single source and defines  objects that span multiple Applications they will also participate in  generating Proxied Applications.     In 5.2 many of the methods that were used to describe default Applications  were deprecated and replaced with specified with Template applications  defined in the ConnectorRegistry Configuration object.
* Attributes:
  - static java.lang.String ATT_CHILD_OBJECTS - An attribute returned by a "hierarchical" connector that contains a list of ResourceObjects representing other objects associated with this object.
  - static java.lang.String ATT_CIQ_MULTIPLEX_IDENTITY - Deprecated. Use ATT_MULTIPLEX_IDENTITY
  - static java.lang.String ATT_CIQ_SOURCE_APPLICATION - Deprecated. Use ATT_SOURCE_APPLICATION
  - static java.lang.String ATT_IIQ_DISABLED - Special built-in attribute that indicates that if an account is disabled.
  - static java.lang.String ATT_IIQ_LOCKED - Special built-in attribute that indicates that if an account is locked.
  - static java.lang.String ATT_MULTIPLEX_IDENTITY - An optional attribute returned by a multiplexing connector to provide an alternate identifier to be used when correlating to a IdentityIQ Identity.
  - static java.lang.String ATT_PRIVILEGED - Deprecated. This can be used, but is no longer specially recognized and privileged needs to be modeled as an extended link attribute.
  - static java.lang.String ATT_SOURCE_APPLICATION - An attribute returned by a multiplexing connector to indicate which application this account is on.
  - static java.lang.String ATTR_DIRECT_PERMISSIONS - The name of the attribute used to define Permissions directly assigned to an object can be retrieved doing "typical" fetch of the object.
  - static java.lang.String ATTR_GROUPS - The name of the attribute used to define a list of group names assigned to a application object.
  - static java.lang.String ATTR_TARGET_PERMISSIONS - Deprecated.
  - static java.lang.String CONFIG_AGGREGATION_MODE - The name of the boolean configuration attribute that specifies whether to check if the delta aggregation flag should be consulted for a JDBC connector.
  - static java.lang.String CONFIG_AUTH_SEARCH_ATTRIBUTES - The name of the configuration option that specifies which attributes to use to use to search for accounts when authenticating.
  - static java.lang.String CONFIG_BUILD_MAP_RULE - The name of the configuration attribute that defines the rule to call to build a java Map object from the incoming data.
  - static java.lang.String CONFIG_GROUP_HIERARCHY_ATTRIBUTE - Deprecated. As of 6.4, this should live in the connector registry on the corresponding schema
  - static java.lang.String CONFIG_HOST - The name of a common configuration attribute used to define the host that should be connected when performing operations.
  - static java.lang.String CONFIG_JDBC_BUILD_MAP_RULE - The name of the configuration attribute that defines the rule that is called to build a java Map from the incoming data for a JDBC connector.
  - static java.lang.String CONFIG_JDBC_CREATE_PROVISION_RULE - The name of the configuration attribute that defines the rule to run when creating an account on a JDBC connector.
  - static java.lang.String CONFIG_JDBC_DELETE_PROVISION_RULE - The name of the configuration attribute that defines the rule to run when deleting an account on a JDBC connector.
  - static java.lang.String CONFIG_JDBC_DISABLE_PROVISION_RULE - The name of the configuration attribute that defines the rule to run when disabling an account on a JDBC connector.
  - static java.lang.String CONFIG_JDBC_ENABLE_PROVISION_RULE - The name of the configuration attribute that defines the rule to run when enabling an account on a JDBC connector.
  - static java.lang.String CONFIG_JDBC_MODIFY_PROVISION_RULE - The name of the configuration attribute that defines the rule to run when modifying an account on a JDBC connector.
  - static java.lang.String CONFIG_JDBC_PROVISION_RULE - The name of the configuration attribute that defines the rule to run when provisioning on a JDBC connector.
  - static java.lang.String CONFIG_JDBC_UNLOCK_PROVISION_RULE - The name of the configuration attribute that defines the rule to run when unlocking an account on a JDBC connector.
  - static java.lang.String CONFIG_MERGE_MAPS_RULE - The name of the configuration attribute that defines the rule that is called when merging to lines from a file that are part of the same object and is called after each call to the build map
  - static java.lang.String CONFIG_OBJECT_FILTERS - The name of the Configuration option used to configure the the objects that should be filtered when iterateObject is called.
  - static java.lang.String CONFIG_PARTITION_MODE - Configuration that tells the connector either that partitioning is enabled/disabled and possibly the mode if there are multiple modes supported.
  - static java.lang.String CONFIG_PASSWORD - The name of a common configuration attribute used to define the proxy user's password when authenticating.
  - static java.lang.String CONFIG_PEOPLESOFTHRMS_CREATE_PROVISION_RULE - The name of the configuration attribute that defines the rule to run when creating an account on a PeopleSoft HRMS connector.
  - static java.lang.String CONFIG_PEOPLESOFTHRMS_DELETE_PROVISION_RULE - The name of the configuration attribute that defines the rule to run when deleting an account on a PeopleSoft HRMS connector.
  - static java.lang.String CONFIG_PEOPLESOFTHRMS_DISABLE_PROVISION_RULE - The name of the configuration attribute that defines the rule to run when disabling an account on a PeopleSoft HRMS connector.
  - static java.lang.String CONFIG_PEOPLESOFTHRMS_ENABLE_PROVISION_RULE - The name of the configuration attribute that defines the rule to run when enabling an account on a PeopleSoft HRMS connector.
  - static java.lang.String CONFIG_PEOPLESOFTHRMS_MODIFY_PROVISION_RULE - The name of the configuration attribute that defines the rule to run when modifying an account on a PeopleSoft HRMS connector.
  - static java.lang.String CONFIG_PEOPLESOFTHRMS_PROVISION_RULE - The name of the configuration attribute that defines the rule to run when provisioning an account on a PeopleSoft HRMS connector.
  - static java.lang.String CONFIG_PEOPLESOFTHRMS_UNLOCK_PROVISION_RULE - The name of the configuration attribute that defines the rule to run when unlocking an account on a PeopleSoft HRMS connector.
  - static java.lang.String CONFIG_PERMISSION_SCOPE - The name of the Configuration option used to configure the the scope of permissions that a connector should return.
  - static java.lang.String CONFIG_PORT - The name of a common configuration attribute used to define the port to communicate on when connecting.
  - static java.lang.String CONFIG_PROVIDER - The name of security provider dependent on J2EE Application Server
  - static java.lang.String CONFIG_PROXY_GENERATOR_RULE - The name of the configuration attribute that defines the rule that is called to generate a proxy application for multiplexed applications.
  - static java.lang.String CONFIG_RWS_AFTER_OPERATION_RULE - The name of the configuration attribute that defines the rule to run After performing any operation on a Web Services connector.
  - static java.lang.String CONFIG_RWS_BEFORE_OPERATION_RULE - The name of the configuration attribute that defines the rule to run before performing any operation on a Web Services connector.
  - static java.lang.String CONFIG_SAPHR_CREATE_PROVISION_RULE - The name of the configuration attribute that defines the rule to run when creating an account on a SAPHR connector.
  - static java.lang.String CONFIG_SAPHR_DELETE_PROVISION_RULE - The name of the configuration attribute that defines the rule to run when deleting an account on a SAPHR connector.
  - static java.lang.String CONFIG_SAPHR_DISABLE_PROVISION_RULE - The name of the configuration attribute that defines the rule to run when disabling an account on a SAPHR connector.
  - static java.lang.String CONFIG_SAPHR_ENABLE_PROVISION_RULE - The name of the configuration attribute that defines the rule to run when enabling an account on a SAPHR connector.
  - static java.lang.String CONFIG_SAPHR_MODIFY_PROVISION_RULE - The name of the configuration attribute that defines the rule to run when modifying an account on a SAPHR connector.
  - static java.lang.String CONFIG_SAPHR_PROVISION_RULE - The name of the configuration attribute that defines the rule to run when provisioning an account on a SAPHR connector.
  - static java.lang.String CONFIG_SAPHR_UNLOCK_PROVISION_RULE - The name of the configuration attribute that defines the rule to run when unlocking an account on a SAPHR connector.
  - static java.lang.String CONFIG_SUCCESSFACTORS_PROVISION_RULE - The name of the configuration attribute that defines the rule to run when provisioning an account on a Successfactors connector.
  - static java.lang.String CONFIG_TRANSFORMATION_RULE - Configuration attribute that defines the rule called to build a ResourceObject object out Map objects.
  - static java.lang.String CONFIG_USER - The name of the common configuration attribute used to define the proxy user a connector can use to authenticate when doing its work.
  - static java.lang.String OP_AGGREGATION_TYPE - An option that is passed by the aggregator to destroy() to indicate the aggregation type - whether account or group
  - static java.lang.String OP_ALLOW_BRUTE_FORCE_SEARCH - An option that can be passed to iterateObjects() that specifies whether to perform a brute force filtering of objects when a filter is specified but the Connector does not support the SEARCH feature.
  - static java.lang.String OP_ATTRIBUTE_NAMES - The name of an option to connector methods to indicate which attributes should be included on returned application objects.
  - static java.lang.String OP_DELTA_AGGREGATION - An option that is passed by the aggregator to destroy() to indicate if the aggregation is a delta aggregation
  - static java.lang.String OP_INCLUDE_ACCOUNTS - An option that can be passed to getObject() to indicate that if this is a Compound Connector, it should return information about all the managed child accounts as well as the master account.
  - static java.lang.String OP_IS_PARTITIONED - An option that is passed by the aggregator to destroy() to indicate if the aggregation is a partitioned aggregation
  - static java.lang.String OP_IS_TERMINATE - An option that is passed by the aggregator to destroy() to indicate whether user has terminated the aggregation
  - static java.lang.String OP_PHASE_NAME - An option that is passed by the aggregator to destroy() to indicate the name of the phase of aggregation like phaseAggregation or phaseFinish
  - static java.lang.String OP_UNIQUENESS_CHECK - An option that can be passed to getObject() to give information for uniqueness check at Connector layer
  - static java.lang.String PROVISION_GLOBAL_RULE - Value for PROVISION_RULE_TYPE that specifies to run the global rule when provisioning on a JDBC connector.
  - static java.lang.String PROVISION_OPERATION_RULE - Value for PROVISION_RULE_TYPE that specifies to run an operation-specific rule when provisioning on a JDBC connector.
  - static java.lang.String PROVISION_RULE_TYPE - The name of the configuration attribute that specifies whether to run a global or operation rule when provisioning on a JDBC connector.
  - static java.lang.String SAPHR_CUSTOM_MANAGER_MODEL_RULE - The name of the configuration attribute that defines the rule to run when user want to create custom manager rule SAPHR connector.
  - static java.lang.String SAPHR_CUSTOM_MANAGER_RULE -
  - static java.lang.String TYPE_ACCOUNT - Type used when aggregating user accounts as Link objects.
  - static java.lang.String TYPE_GROUP - Type used when aggregating groups as ManagedAttribute objects.
* Methods:
  - ResourceObject authenticate​(java.lang.String username, java.lang.String password) - On a successful authentication, returns a ResourceObject representing the user account that was authenticated.
  - ResourceObject authenticate​(java.lang.String accountId, java.util.Map<java.lang.String,​java.lang.Object> options) - Overloaded method to have the options as additional input parameter.
  - ProvisioningResult checkStatus​(java.lang.String id) - New in 5.5 this method can be used by asynchronous provisioning implementations to check the status of a queued request.
  - void destroy​(java.util.Map<java.lang.String,​java.lang.Object> optionsMap) - Called by aggregator at the end of aggregation
  - java.util.Map<java.lang.String,​java.lang.Object> discoverApplicationAttributes​(java.util.Map<java.lang.String,​java.lang.Object> options) -
  - CloseableIterator<connector.common.DiscoveredApplication> discoverApplications() -
  - Schema discoverSchema​(java.lang.String objectType, java.util.Map<java.lang.String,​java.lang.Object> options) - Returns the discovered schema for the supplied objectType.
  - java.util.Map doHealthCheck​(java.util.Map<java.lang.String,​java.lang.Object> options) - Light Weight Test Connection API.Test the connection to the application,Returns nothing on success and throws an exception (as detailed as possible) when there is a problem
  - Application getApplication() - Returns the application associated with this object.
  - java.util.Iterator<java.util.Map<java.lang.String,​java.lang.Object>> getChangeLogExtract​(java.util.Map<java.lang.String,​java.lang.Object> requestParams) - This method will be called to fetch Change log extract from ERP Systems.
  - java.util.Map<java.lang.String,​java.lang.Object> getConfigOptions​(java.lang.String configOptionsKey) -
  - openconnector.ConnectorServices getConnectorServices() -
  - java.lang.String getConnectorType() - Deprecated. This now comes from the connector registry.
  - java.util.List<AttributeDefinition> getDefaultAttributes() - Deprecated. This now comes from the connector registry.
  - java.util.List<Schema> getDefaultSchemas() - Deprecated. This now comes from the connector registry.
  - java.util.Map<java.lang.String,​java.lang.Object> getDependencyData() - This method can be used to know the details (like version info), status of the dependent component on which the Connector is dependent.
  - java.util.List<java.util.Map<java.lang.String,​java.lang.Object>> getExtractPartitions​(java.util.Map<java.lang.String,​java.lang.Object> requestParams, java.lang.String extractType) - This method will be called to get extract Partition for ARM extract requests
  - java.lang.String getInstance() -
  - java.util.List<Partition> getIteratorPartitions​(java.lang.String objectType, int suggestedPartitionCount, Filter filter, java.util.Map<java.lang.String,​java.lang.Object> ops) - Return the list of partitions for a connector.
  - Application getLocalApplication() - Returns the application associated with this Connector depending upon whether its a cloud based application or not.
  - ResourceObject getObject​(java.lang.String objectType, java.lang.String identity, java.util.Map<java.lang.String,​java.lang.Object> options) - Communicate with the application and get the object which should be identified by the objectType and identity.
  - Application getProxiedApplication​(java.lang.String name, java.util.Map<java.lang.String,​java.lang.Object> options) - Create an Application object to represent a resource managed by a proxy connector.
  - java.util.Iterator<java.util.Map<java.lang.String,​java.lang.Object>> getSecurityExtract​(java.util.Map<java.lang.String,​java.lang.Object> requestParams) - This method will be called to fetch Security extract from ERP Systems.
  - connector.common.statisticscollector.StatisticsCollector getStatisticsCollector() - Retrive the Stored StatisticsCollector object by Connector proxy.
  - java.util.List<Application.Feature> getSupportedFeatures() - Deprecated. This now comes from the connector registry.
  - java.lang.String getSystemIdentity() -
  - Application getTargetApplication() -
  - java.lang.String getTargetInstance() -
  - java.util.Iterator<java.util.Map<java.lang.String,​java.lang.Object>> getUtilizationExtract​(java.util.Map<java.lang.String,​java.lang.Object> requestParams) - This method will be called to fetch Utilization extract from ERP Systems requestParams has required details to fetch Utilization extract data.
  - CloseableIterator<ResourceObject> iterateObjects​(java.lang.String objectType, Filter filter, java.util.Map<java.lang.String,​java.lang.Object> options) - Return an Iterator of ResourceObjects.
  - CloseableIterator<ResourceObject> iterateObjects​(Partition partition) - Return an iterator over the objects defined in the Partition object.
  - ProvisioningResult provision​(ProvisioningPlan plan) - Execute a provisioning plan.
  - void setApplication​(Application application) - Set the application associated with this object.
  - void setConnectorServices​(openconnector.ConnectorServices connServices) - Sets the ConnectorServices object.
  - void setInstance​(java.lang.String instance) - Set the instance for template applications.
  - void setStatisticsCollector​(connector.common.statisticscollector.StatisticsCollector statisticsCollector) - Set the StatisticsCollector object require for underlying connector to push the aggreagtion statistics.
  - void setSystemIdentity​(java.lang.String id) - Sets the target "meta" user id if this application is a multiplexer or bridge that requires operations be redirected through a meta user.
  - void setTargetApplication​(Application app) - Sets the target application if this application is a multiplexer or bridge.
  - void setTargetInstance​(java.lang.String inst) - Sets the target application instance if this application is a multiplexer or bridge.
  - boolean supportsPartitionedDeltaAggregation() - Gets if the connector supports partitioned delta aggregation
  - void testConfiguration() - Test the connection to the application.
  - void updateApplicationConfig() - Updates the application config if the connectorStateMap value is updated.

* Class Name: InvalidResponseException
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, sailpoint.connector.ConnectorException, java.lang.Throwable, sailpoint.connector.ConnectorException, java.lang.Exception, sailpoint.connector.ConnectorException, sailpoint.tools.AbstractLocalizableException, sailpoint.connector.ConnectorException, sailpoint.connector.InvalidResponseException
* Description: InvalidResponseException thrown when an invalid response is detected.  1)During aggregation or in the getObject when the connector is unable to  parse a data received from Managed System. If something fails, when  converting managed system response to ResourceObject. for e.g. a) Connector  receives a malformed response from the managed system which is not understood  by the connector.   2)When aggregating records from managed system if  connectors receives only some part of the record which is unacceptable, then  we can have this exception telling IdentityIQ about the record containing  partial information.   InvalidResponseException will be extended from ConnectorException.  This class will entertain the message String, Message object and throwable object.
* Attributes:
  - None
* Methods:
  - Constructor: InvalidResponseException() - InvalidResponseException constructor will be called by the connector components to throw an exception.
  - Constructor: InvalidResponseException​(java.lang.String message) - InvalidResponseException constructor will be called by passing the message.
  - Constructor: InvalidResponseException​(java.lang.String error, java.lang.String suggestion, java.lang.Throwable t) - Create a new InvalidResponseException from an error text, suggestion text and existing exception.
  - Constructor: InvalidResponseException​(java.lang.String message, java.lang.Throwable t) - InvalidResponseException constructor will be called by passing the throwable object and message string.
  - Constructor: InvalidResponseException​(java.lang.Throwable t) - InvalidResponseException constructor will be called by passing the throwable object.
  - Constructor: InvalidResponseException​(Message message) - InvalidResponseException constructor will be called by passing the Message object.
  - Constructor: InvalidResponseException​(Message message, java.lang.Throwable t) - InvalidResponseException constructor will be called by passing the throwable object and Message object.

* Class Name: JDBCConnector
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, sailpoint.connector.CollectorServices, sailpoint.connector.AbstractConnector, sailpoint.connector.JDBCConnector
* Description: A connector that can be used to read data from JDBC  enabled database engines.    This connector using configuration options to drive  the data that is fetched from the database.     For simple single table implementations the schema can be  used exclusively to configure the connector. The native  ObjectType in the schema defines the table name when  generating the sql.     For more complex situations the sql can manually be assigned  using the sql configuration parameter. CONFIG_SQL_STATEMENT  The select statement for the statement will drive the ResultSet that  is returned from the query. For each ResultSet returned by the sql  a buildMap rule is called to transform the ResultSet into a Map object.  The buildMap is where all of the per row transformations can take place  and there is a default static method buildMapFromResultSet(ResultSet)  that can be called from rules to transform the data into a Map.     Once each row has been transformed into a Map object it is then  transformed to a ResourceObject which is used to represent each   unique user or group in the data source.     The default methods use the Application's Schema to coerce the   sql datatype values into our simple Boolean, String, Long, Integer   and Date values. These behaviors can be overridden using the  Connector.CONFIG_TRANSFORMATION_RULE configuration  item.
* Attributes:
  - static java.lang.String ARG_CON_PROPERTIES -
  - static java.lang.String CONFIG_CONN_MAX_RETRY -
  - static java.lang.String CONFIG_CONN_RETRY_ENABLE -
  - static java.lang.String CONFIG_CONN_RETRY_EXCEPTION_LIST -
  - static java.lang.String CONFIG_CONN_WAIT_TIME_FOR_RETRY -
  - static java.lang.String CONFIG_CONVERT_LIST_TO_CSV -
  - static java.lang.String CONFIG_DBURL -
  - static java.lang.String CONFIG_DELTA_AGGREGATION -
  - static java.lang.String CONFIG_DELTA_TABLE -
  - static java.lang.String CONFIG_DIRECT_PERMISSIOB_SQL -
  - static java.lang.String CONFIG_DISABLE_ORDERING_CHECK -
  - static java.lang.String CONFIG_ENABLE_GROUP_HIERARCHY -
  - static java.lang.String CONFIG_EXCEPTION_SIMULATION_COUNT - An Application attribute that holds the simulated exception count.
  - static java.lang.String CONFIG_GET_DELTA_SQL_STATEMENT -
  - static java.lang.String CONFIG_GET_OBJECT_SQL_STATEMENT -
  - static java.lang.String CONFIG_INDEX_COLUMNS -
  - static java.lang.String CONFIG_IS_DIRECT_PERMISSIOB_ENABLED -
  - static java.lang.String CONFIG_MERGE_COLUMNS -
  - static java.lang.String CONFIG_MERGE_ROWS -
  - static java.lang.String CONFIG_PARTITION_NAMES - The application configuration that holds the list of partition names that should be used.
  - static java.lang.String CONFIG_PARTITION_SQL_STATEMENTS - The application configuration that holds the list of partitions that should be executed.
  - static java.lang.String CONFIG_PARTITION_STATEMENT - Configuration that is set on each Partition object that will configure the statement that should be executed for a particular partition.
  - static java.lang.String CONFIG_RESULT_SET_CONCURANCY -
  - static java.lang.String CONFIG_RESULT_SET_FETCH_SIZE - An optional setting that can be specified to override a JDBC connector's default row pre-fetch.
  - static java.lang.String CONFIG_RESULT_SET_TYPE -
  - static java.lang.String CONFIG_SORT_DESCENDING -
  - static java.lang.String CONFIG_SQL_STATEMENT -
  - static java.lang.String CONFIG_STATEMENT_FETCH_SIZE - An optional setting that can be specified to override a JDBC connector's default row pre-fetch.
  - static java.lang.String CONFIG_SUPPORT_UNSTRUCTURED_DATA -
  - static java.lang.String CONFIG_TEST_SQL_STATEMENT - This attribute is used to get SQL for test connection for account schema
  - static java.lang.String CONFIG_USE_EXEC_QUERY -
  - static java.lang.String CONNECTOR_SQLLOADER_TYPE -
  - static java.lang.String CONNECTOR_TYPE -
  - static java.lang.String POOL_PREFIX -
  - static java.lang.String SENSITIVE_ATTR_IDENTIFIER -
* Methods:
  - java.util.List<Permission> addDirectPermissions​(Schema schema, java.sql.Connection connection, ResourceObject object, java.lang.String sql, java.lang.String identity) -
  - protected ResourceObject assembleObject​(Schema schema, java.sql.ResultSet result, java.sql.Connection conn, java.util.Map<java.lang.String,​java.lang.Object> ruleState, java.lang.String last) - Assemble a resource object from the ResultSet.
  - protected java.util.Map<java.lang.String,​java.lang.Object> buildMap​(java.sql.ResultSet result, Schema schema, java.util.Map<java.lang.String,​java.lang.Object> ruleState, java.sql.Connection conn) - Build a map for each row.
  - static java.util.Map<java.lang.String,​java.lang.Object> buildMapFromResultSet​(java.sql.ResultSet result) - Given a ResultSet, for each of the column names put a new key/value pair into the map that represents the results set column value.
  - static java.util.Map<java.lang.String,​java.lang.Object> buildMapFromResultSet​(java.sql.ResultSet result, Schema schema) - Deprecated.
  - ResourceObject buildResourceObjectFromMap​(Schema schema, java.util.Map<java.lang.String,​java.lang.Object> mergedObject) - Override this method from the Abstract class so we can automatically add in the mergeColumns to the do not coerce list as default behavior.
  - protected void closeConnection​(java.sql.Connection connection) - Call close on the connection, this method performs null check and catches exceptions which are logged to the error log if thrown.
  - protected void closeResult​(java.sql.ResultSet resultset) - Call close() on the ResultSet, performs null check and logs exceptions thrown when trying to close.
  - protected void closeStatement​(java.sql.Statement statement) - Call close() on the statement, performs null check and logs exceptions thrown when trying to close.
  - Schema discoverSchema​(java.lang.String objectType, java.util.Map<java.lang.String,​java.lang.Object> options) - Discover the attributes that will be returned when we iterate over the accounts and groups.
  - protected java.sql.ResultSet executeStatement​(java.sql.PreparedStatement statement, boolean throwIfResultNull) - Execute the given PreparedStatement, returning the ResultSet.
  - protected static java.util.List<java.lang.String> getColumnNames​(java.sql.ResultSet result) - Use meta-data on the result to build up the column list.
  - protected java.sql.Connection getConnection​(Schema schema, java.util.Map<java.lang.String,​java.lang.Object> options) - Get a connection to the database, lean on the JdbcUtil class so we can add a pool if necessary.
  - java.lang.String getConnectorType() - Returns a meaningful nice to display String to describe the connector.
  - java.util.List<AttributeDefinition> getDefaultAttributes() - Returns a list of AttributeDefinitions for the configuration attributes.
  - protected java.lang.String getDefaultFetchSQL​(Schema schema, java.lang.String identity) - Return the SQL to execute to fetch an object for the given Schema with the given native identity, using Schema.getNativeObjectType() as the table name, the schema's attribute names in the select expression, and Schema.getIdentityAttribute() to filter the result to the specified identity.
  - java.util.List<Schema> getDefaultSchemas() - Returns a list of Schemas objects, each of which describes a separate objectType.
  - protected java.lang.String getDeleteSQL​(Schema schema, java.sql.ResultSet result, java.lang.String identity, java.lang.String action) - Return the SQL to delete items from the delta table with the given identity and action.
  - protected java.lang.String getDeltaFetchSQL​(Schema schema, java.lang.String identity) - Return either the CONFIG_GET_DELTA_SQL_STATEMENT or the delta SQL for the given identity.
  - protected java.lang.String getDeltaSQL​(Schema schema, Filter filter) - Return the SQL to fetch items from the delta table using the given Filter.
  - protected java.lang.String getFetchSQL​(Schema schema, java.lang.String identity) - Return either the CONFIG_GET_OBJECT_SQL_STATEMENT or the default fetch SQL.
  - protected java.util.List<java.lang.String> getIndexColumns​(Schema schema) -
  - protected java.lang.String getIterateSQL​(Schema schema, Filter filter) - Return the CONFIG_SQL_STATEMENT to iterate over objects with the given Schema, using the given Filter.
  - java.util.List<Partition> getIteratorPartitions​(java.lang.String objectType, int suggestedPartitionCount, Filter filter, java.util.Map<java.lang.String,​java.lang.Object> ops) - Default implementation returns null to indicate the connector does not have any partitions defined.
  - java.lang.String getMaskedSQL() -
  - protected java.util.List<java.lang.String> getMergeColumns​(Schema schema) -
  - ResourceObject getObject​(java.lang.String objectType, java.lang.String identity, java.util.Map<java.lang.String,​java.lang.Object> options) - Communicate with the application and get the object which should be identified by the objectType and identity.
  - protected JDBCConnector.JDBCObjectIterator getObjectIterator​(Schema schema, java.sql.Connection connection, java.sql.PreparedStatement statement, java.sql.ResultSet result) -
  - protected java.sql.PreparedStatement getStatement​(java.sql.Connection connection, java.lang.String sql) - Create a PreparedStatement to execute the given SQL.
  - java.util.List<Application.Feature> getSupportedFeatures() - Every connector needs to register which sailpoint.object.Application.Feature are supported.
  - protected boolean isRetriedOperation() -
  - CloseableIterator<ResourceObject> iterateObjects​(java.lang.String objectType, Filter filter, java.util.Map<java.lang.String,​java.lang.Object> options) - Return an Iterator of ResourceObjects.
  - CloseableIterator<ResourceObject> iterateObjects​(Partition partition) - Return an iterator over the objects defined in the Partition object.
  - static java.util.Map listToMap​(java.util.List<java.lang.String> ListOfValues) - This method to create map from list of string.
  - protected boolean mergeRows​(Schema schema) -
  - ProvisioningResult provision​(ProvisioningPlan plan) - New in 5.2.
  - ProvisioningResult ProvisionByRule​(ProvisioningPlan plan) - Perform provisioning operations using Rule
  - protected void resetIsRetriedOperation() -
  - CloseableIterator<ResourceObject> retryIterateObjects​(java.lang.String objectType, Filter filter, java.util.Map<java.lang.String,​java.lang.Object> options) - Method used to retry iterateObjects in case of any Excetion
  - void setMaskedSQL​(java.lang.String maskedSql) -
  - protected void setRetryErrorList​(java.util.List<java.lang.String> retryErrorList) -
  - protected boolean shouldRetryCPError​(java.lang.Exception e) - This method is used to sync credentials in application from credential provider vault in case of retryable error
  - void testConfiguration() - Execute the iterateSQL as a way to test both the authentication stuff AND the sql statement.
  - protected void updateConnectionMapWithProperties​(java.util.HashMap<java.lang.String,​java.lang.Object> connectionMap, java.util.List<java.lang.String> propertiesList) - This method will update ConnectionMap with the additional connection properties provided in schema for database connectors.
  - Constructor: JDBCConnector​(Application application) -

* Class Name: DelimitedFileConnector.PartitionIterator
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, sailpoint.connector.DelimitedFileConnector.PartitionIterator
* Description: Wrapper iterator implementation that knows how to read partitions  of a file. The partitionConfig will give the details of which  slice of the data should be read giving both the starting  point and where to stop.   When not in merge mode we can assume a single line per object.   Merging rows makes this more complicated since the data can span  multiple rows of data.  Further, because the buildMap rule  can influence how the merge works it has to be executed when  merging is enabled. The same is true with regexp, which can also  span multiple files.   For all others for the first pass during partitioning  AND when seeking to the correct place in the file it will just  read lines from the file until the correct position. Then process  them as usual.
* Attributes:
  - None
* Methods:
  - void close() - This method is where if necessary can disconnect and cleanup any connections etc.
  - boolean hasNext() - Returns true if there are more objects in the iterator.
  - ResourceObject next() - Returns the next element in the iterator.
  - Constructor: PartitionIterator​(CloseableIterator<ResourceObject> source, Partition partitionConfig) -

* Class Name: SchemaNotDefinedException
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, sailpoint.connector.ConnectorException, java.lang.Throwable, sailpoint.connector.ConnectorException, java.lang.Exception, sailpoint.connector.ConnectorException, sailpoint.tools.AbstractLocalizableException, sailpoint.connector.ConnectorException, sailpoint.connector.SchemaNotDefinedException
* Description: The base exception thrown by components.
* Attributes:
  - None
* Methods:
  - Constructor: SchemaNotDefinedException() - Construct a ExceptionWrapper with no message or nested throwable.
  - Constructor: SchemaNotDefinedException​(java.lang.String message) - Construct a new SchemaNotDefinedException with a detailed message.
  - Constructor: SchemaNotDefinedException​(java.lang.String error, java.lang.String suggestion, java.lang.Throwable t) - Create a new SchemaNotDefinedException from an error text, suggestion text and existing exception.
  - Constructor: SchemaNotDefinedException​(java.lang.String message, java.lang.Throwable t) - Create a new SchemaNotDefinedException from an existing exception.
  - Constructor: SchemaNotDefinedException​(java.lang.Throwable t) - Construct a new SchemaNotDefinedException wrapping an existing exception.

* Class Name: JDBCConnector.JDBCObjectIterator
* Package Name: sailpoint.connector
* Inherited Classes/Interfaces: java.lang.Object, ResourceObject, sailpoint.connector.JDBCConnector.JDBCObjectIterator
* Description:
* Attributes:
  - protected java.sql.Connection _connection -
  - protected int _exceptionSimulationCount -
  - protected ResourceObject _next -
  - protected java.sql.ResultSet _result -
  - protected Schema _schema -
  - protected java.sql.Statement _statement -
* Methods:
  - void close() - This method is where if necessary can disconnect and cleanup any connections etc.
  - protected ResourceObject getNext() -
  - protected ResourceObject getNextForJDBC() - Method used to retry getNext method
  - boolean hasNext() - Returns true if there are more objects in the iterator.
  - ResourceObject next() - Returns the next element in the iterator.
  - protected void printProgress() -
  - void setExceptionSimulationCount​(int i) -
  - Constructor: JDBCObjectIterator​(Schema schema, java.sql.Statement statement, java.sql.ResultSet result, java.sql.Connection con) -

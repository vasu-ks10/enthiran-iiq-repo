# SailPoint Integration API Documentation

## AbstractIntegration
**Package:** `sailpoint.integration`

### Description
A base implementation of IntegrationInterface that stubs out most
 methods methods to throw exceptions.  This should be extended rather
 than directly implementing IntegrationInterface to protect from
 changes to the interface.

### Inheritance & Interfaces
```java
public classAbstractIntegrationextends java.lang.Object
implementsIntegrationInterface
```

### Attributes
No attributes.

### Methods
- `RequestResult addRole ( RoleDefinition def)`: Create or update the definition of a role.
- `void configure (java.util.Map args)`: Must be called immediately after construction to provide
 a set of configuration parameters.
- `RequestResult deleteRole (java.lang.String roleName)`: Delete a role.
- `RequestResult getRequestStatus (java.lang.String requestID)`: Get the current status of the request with the given request
 ID.
- `java.util.List listRoles ()`: Return the current list of "manageable" roles.
- `java.lang.String ping ()`: Return some sort of status message.
- `RequestResult provision (java.lang.String identity, ProvisioningPlan plan)`: Make changes to an identity defined by a ProvisioningPlan.

---

## ApacheHttpClient
**Package:** `sailpoint.integration`

### Description
An implementation of HttpClient that delegates all calls to the Apache
 HTTP client.

### Inheritance & Interfaces
```java
public classApacheHttpClientextends java.lang.Object
implementsHttpClient
```

### Attributes
- `static java.lang.String ATTR_CONTENT_CHARSET`:
- `static java.lang.String AUTHORIZATION`:
- `static java.lang.String BASIC`:
- `static java.lang.String COOKIE`:
- `static java.lang.String HTTP_PROXYHOST`:
- `static java.lang.String HTTP_PROXYPORT`:
- `static java.lang.String HTTPS`:
- `static java.lang.String HTTPS_PROXYHOST`:
- `static java.lang.String HTTPS_PROXYPORT`:
- `static java.lang.String NO_PROXY_HOSTS`:
- `static java.util.List noProxyHostList`:
- `static java.lang.String SSL`:
- `static java.lang.String UTF8`:

### Methods
- `void addCookies (java.util.List cookies)`: Set the Cookies.
- `void addHeader (java.lang.String name,
         java.lang.String value)`: Adds a header entry
- `int delete (java.lang.String url)`: Perform an HTTP DELETE to the given URL.
- `int delete (java.lang.String url,
      java.util.Map headers)`: Perform HTTP DELETE with headers
- `int delete (java.lang.String url,
      java.util.Map headers,
      java.lang.String payload)`: Perform HTTP DELETE with headers and body
- `void disableCookies ()`: Disables cookies support.
- `int get (java.lang.String url)`: Perform an HTTP GET to the given URL.
- `int get (java.lang.String url,
   java.util.Map headers)`: Perform HTTP GET with headers
- `java.lang.String getBody ()`: Return the response body from the most recently executed request.
- `java.util.List getCookies ()`: Return the Cookies.
- `java.util.Map getHeaders ()`: Returns a Map containing header name-value pairs.
- `java.util.Map getResponseHeaders ()`: Returns the response headers of the last resquest execution.
- `int patch (java.lang.String url,
     java.lang.String data)`: Perform an HTTP PATCH to the given URL using the given data in the body.
- `int patch (java.lang.String url,
     java.lang.String payload,
     java.util.Map headers)`: Perform an HTTP PATCH to the given URL using the given data in the body.
- `int patch (java.lang.String url,
     java.util.Map headers,
     java.util.Map parameters)`: Perform URLEncoded HTTP PATCH operation.
- `int post (java.lang.String url,
    java.lang.String postData)`: Perform an HTTP POST to the given URL using the given data in the post
 body.
- `int post (java.lang.String url,
    java.lang.String postData,
    java.util.Map headers)`: Perform HTTP POST with headers
- `int post (java.lang.String url,
    java.util.Map parameters)`: Perform an HTTP POST to the given URL serializing the given parameters
 into the post body.
- `int post (java.lang.String url,
    java.util.Map headers,
    java.util.Map parameters)`: Perform URLEncoded HTTP POST operation.
- `int put (java.lang.String url,
   java.lang.String data)`: Perform an HTTP PUT to the given URL using the given data in the body.
- `int put (java.lang.String url,
   java.lang.String payload,
   java.util.Map headers)`: Perform an HTTP PUT to the given URL using the given data in the body.
- `int put (java.lang.String url,
   java.util.Map headers,
   java.util.Map parameters)`: Perform URLEncoded HTTP PUT operation.
- `void setHeaders (java.util.Map headers)`: Sets headers supplied in the argument
- `void setup (boolean useSSL,
     int port,
     java.lang.String username,
     java.lang.String password,
     java.lang.String timeoutInSeconds,
     java.util.Map options)`: Setup this client using the given configuration.
- `void setup (boolean useSSL,
     int port,
     java.lang.String username,
     java.lang.String password,
     java.lang.String timeoutInSeconds,
     java.util.Map options,
     java.lang.String sslProtocol)`: *Setup this client using the given configuration.**

---

## AuthenticationUtil.AuthType
**Package:** `sailpoint.integration`

### Description
No description available.

### Inheritance & Interfaces
```java
public static enumAuthenticationUtil.AuthTypeextends java.lang.Enum<AuthenticationUtil.AuthType>
```

### Attributes
No attributes.

### Methods
- `abstract java.lang.String getSeparator ()`:
- `abstract java.lang.String getToken ()`:
- `abstract boolean isSplitOnLast ()`:
- `static AuthenticationUtil.AuthType valueOf (java.lang.String name)`: Returns the enum constant of this type with the specified name.
- `static AuthenticationUtil.AuthType [] values ()`: Returns an array containing the constants of this enum type, in
the order they are declared.

---

## AuthenticationUtil.ValidationContext
**Package:** `sailpoint.integration`

### Description
This class is used by the JWT validation process. It will keep track of any errors and the user that is identified
 by the claim.

### Inheritance & Interfaces
```java
public static classAuthenticationUtil.ValidationContextextends java.lang.Object
```

### Attributes
No attributes.

### Methods
- `java.lang.String[] getErrors ()`:
- `Identity getUser ()`:
- `boolean hasErrors ()`:

---

## AuthenticationUtil
**Package:** `sailpoint.integration`

### Description
A utility to help perform authentication for REST requests.

### Inheritance & Interfaces
```java
public classAuthenticationUtilextends java.lang.Object
```

### Attributes
- `static java.lang.String BASIC`:
- `static java.lang.String BEARER`:
- `static java.lang.String PARAM_AUTHN_PASSWORD`: Argument that can be used to specify password for authentication.
- `static java.lang.String PARAM_AUTHN_USER`: Argument that can be used to specify username for authentication.

### Methods
- `static java.lang.String[] decodeHeader (java.lang.String authHeader)`: Process an authorization header that may or may not have an encoded header value.
- `static com.auth0.jwt.interfaces.DecodedJWT decodeToken (java.lang.String token)`: Decodes and possibly logs the JWT value.
- `static java.lang.String getBearerTokenValue (java.lang.String authHeader)`: Extract the Bearer token from the Authentication header (Authentication Bearer xxxxxx).
- `static java.lang.String[] getCredentials (java.lang.String authHeader,
              java.lang.String authnUserParam,
              java.lang.String authnPasswordParam)`: Return the credentials pulled from the request in a two-element String array with the first element
 being the username and the second element being the password.
- `static java.lang.String getSeparator (java.lang.String authType)`: Determine the header value separator.
- `static boolean isBasicAuth (java.lang.String authHeader)`: If the Authorization header doesn't start with "Basic", then this is not basic authorization.
- `static boolean isBearerAuth (java.lang.String authHeader)`: If the Authorization header doesn't start with "Bearer", then this is not bearer authorization.
- `static java.lang.String[] splitAuthHeader (java.lang.String authHeader)`: Split an authorization header into its two parts: where type could be 'Basic', 'Bearer',
 or other.
- `static java.lang.String[] splitAuthHeaderValue (java.lang.String authHeaderValue,
                    java.lang.String separator)`: Allow for us to infer search direction from auth type since
 BASIC doesn't allow a colon in the username and the period can appear
 in the username.
- `static java.lang.String[] splitAuthHeaderValue (java.lang.String authHeaderValue,
                    java.lang.String separator,
                    boolean splitOnLast)`: Splits an authorization header value by the separator.
- `static java.lang.String[] splitAuthHeaderValue (java.lang.String authHeaderValue, AuthenticationUtil.AuthType authType)`:
- `static AuthenticationUtil.ValidationContext validateJwt (com.auth0.jwt.interfaces.DecodedJWT jwt, SailPointContext ctx)`:
- `static AuthenticationUtil.ValidationContext validateJwt (com.auth0.jwt.interfaces.DecodedJWT jwt, SailPointContext ctx,
           boolean shortCircuit)`: Perform all validation on a decoded JWT.

---

## Authenticator
**Package:** `sailpoint.integration`

### Description
An interface used by the IntegrationServlet to provide pluggable
 authentication.

### Inheritance & Interfaces
```java
public interfaceAuthenticator
```

### Attributes
No attributes.

### Methods
- `boolean authenticate (java.lang.String user,
            java.lang.String password)`: Authenticate the given user and password and return true or false
 depending on whether the credentials are valid or not.

---

## Base64.InputStream
**Package:** `sailpoint.integration`

### Description
A Base64.InputStream will read data from another java.io.InputStream , given in the constructor,
 and encode/decode to/from Base64 notation on the fly.

### Inheritance & Interfaces
```java
public static classBase64.InputStreamextends java.io.FilterInputStream
```

### Attributes
No attributes.

### Methods
- `int read ()`: Reads enough of the input stream to convert
 to/from Base64 and returns the next byte.
- `int read (byte[] dest,
    int off,
    int len)`: Calls read() repeatedly until the end of stream
 is reached or len bytes are read.

---

## Base64.OutputStream
**Package:** `sailpoint.integration`

### Description
A Base64.OutputStream will write data to another java.io.OutputStream , given in the constructor,
 and encode/decode to/from Base64 notation on the fly.

### Inheritance & Interfaces
```java
public static classBase64.OutputStreamextends java.io.FilterOutputStream
```

### Attributes
No attributes.

### Methods
- `void close ()`: Flushes and closes (I think, in the superclass) the stream.
- `void flushBase64 ()`: Method added by PHIL.
- `void resumeEncoding ()`: Resumes encoding of the stream.
- `void suspendEncoding ()`: Suspends encoding of the stream.
- `void write (byte[] theBytes,
     int off,
     int len)`: Calls write(int) repeatedly until len bytes are written.
- `void write (int theByte)`: Writes the byte to the output stream after
 converting to/from Base64 notation.

---

## Base64
**Package:** `sailpoint.integration`

### Description
Encodes and decodes to and from Base64 notation.

### Inheritance & Interfaces
```java
public classBase64extends java.lang.Object
```

### Attributes
- `static int DECODE`: Specify decoding.
- `static int DONT_BREAK_LINES`: Don't break lines when encoding (violates strict Base64 specification)
- `static int ENCODE`: Specify encoding.
- `static int GZIP`: Specify that data should be gzip-compressed.
- `static int NO_OPTIONS`: No options specified.
- `static int ORDERED`: Encode using the special "ordered" dialect of Base64 described here: http://www.faqs.org/qa/rfcc-1940.html .
- `static int URL_SAFE`: Encode using Base64-like encoding that is URL- and Filename-safe as described
 in Section 4 of RFC3548: http://www.faqs.org/rfcs/rfc3548.html .

### Methods
- `static byte[] decode (byte[] source,
      int off,
      int len,
      int options)`: Very low-level access to decoding ASCII characters in
 the form of a byte array.
- `static byte[] decode (java.lang.String s)`: Decodes data from Base64 notation, automatically
 detecting gzip-compressed data and decompressing it.
- `static byte[] decode (java.lang.String s,
      int options)`: Decodes data from Base64 notation, automatically
 detecting gzip-compressed data and decompressing it.
- `static void decodeFileToFile (java.lang.String infile,
                java.lang.String outfile)`: Reads infile and decodes it to outfile .
- `static byte[] decodeFromFile (java.lang.String filename)`: Convenience method for reading a base64-encoded
 file and decoding it.
- `static boolean decodeToFile (java.lang.String dataToDecode,
            java.lang.String filename)`: Convenience method for decoding data to a file.
- `static java.lang.Object decodeToObject (java.lang.String encodedObject)`: Attempts to decode Base64 data and deserialize a Java
 Object within.
- `static java.lang.String encodeBytes (byte[] source)`: Encodes a byte array into Base64 notation.
- `static java.lang.String encodeBytes (byte[] source,
           int options)`: Encodes a byte array into Base64 notation.
- `static java.lang.String encodeBytes (byte[] source,
           int off,
           int len)`: Encodes a byte array into Base64 notation.
- `static java.lang.String encodeBytes (byte[] source,
           int off,
           int len,
           int options)`: Encodes a byte array into Base64 notation.
- `static void encodeFileToFile (java.lang.String infile,
                java.lang.String outfile)`: Reads infile and encodes it to outfile .
- `static java.lang.String encodeFromFile (java.lang.String filename)`: Convenience method for reading a binary file
 and base64-encoding it.
- `static java.lang.String encodeObject (java.io.Serializable serializableObject)`: Serializes an object and returns the Base64-encoded
 version of that serialized object.
- `static java.lang.String encodeObject (java.io.Serializable serializableObject,
            int options)`: Serializes an object and returns the Base64-encoded
 version of that serialized object.
- `static boolean encodeToFile (byte[] dataToEncode,
            java.lang.String filename)`: Convenience method for encoding data to a file.
- `static void main (java.lang.String[] args)`: Encodes or decodes two files from the command line.

---

## Cryptographer
**Package:** `sailpoint.integration`

### Description
No description available.

### Inheritance & Interfaces
```java
public classCryptographerextends java.lang.Object
```

### Attributes
- `static java.lang.String CIPHER_ALGORITHM`: Deprecated.
- `static java.lang.String KEY_ALGORITHM`: Deprecated.
- `static java.lang.String KEYID_ASCII`: Deprecated. Special key identifier used to indicate the value
 is not encrypted.

### Methods
- `java.lang.String decrypt (java.lang.String src)`: Deprecated.
- `java.lang.String encrypt (java.lang.String src)`: Deprecated.
- `boolean isEncrypted (java.lang.String src)`: Deprecated. Try to guess if a string looks encrypted.
- `static void main (java.lang.String[] args)`: Deprecated. The behavior of the main() method is important because
 this is one of the classes that can be launched
 from the "iiq" script via the Launcher class.
- `static void println (java.lang.Object o)`: Deprecated.

---

## HttpClient
**Package:** `sailpoint.integration`

### Description
An HttpClient issues HTTP requests.

### Inheritance & Interfaces
```java
public interfaceHttpClient
```

### Attributes
- `static java.lang.String OPT_CLOSE_IDLE_CONNECTIONS`: Optional that may be passed into setup that will specify the timeout in seconds
 to close idle connections
- `static java.lang.String OPT_MAX_HOST_CONNECTIONS`: Option that may be passed into setup that will allow configuration of the maximum
 number of connections per host
- `static java.lang.String OPT_MAX_TOTAL_CONNECTIONS`: Option that may be passed into setup that will allow configuration of the maximum
 number of total connections
- `static java.lang.String OPT_TRUST_ALL_CERTS`: Option that can be passed into setup that will causes all certificates to
 be trusted when using SSL.
- `static java.lang.String[] OPTS`: All of the options accepted by setup.

### Methods
- `void addCookies (java.util.List cookies)`: Set the Cookies.
- `void addHeader (java.lang.String name,
         java.lang.String value)`: Adds a header entry
- `int delete (java.lang.String url)`: Perform an HTTP DELETE to the given URL.
- `int delete (java.lang.String url,
      java.util.Map headers)`: Perform HTTP DELETE with headers
- `int delete (java.lang.String url,
      java.util.Map headers,
      java.lang.String payLoad)`: Perform HTTP DELETE with headers and body
- `int get (java.lang.String url)`: Perform an HTTP GET to the given URL.
- `int get (java.lang.String url,
   java.util.Map headers)`: Perform HTTP GET with headers
- `java.lang.String getBody ()`: Return the response body from the most recently executed request.
- `java.util.List getCookies ()`: Return the Cookies.
- `java.util.Map getHeaders ()`: Returns a Map containing header name-value pairs.
- `java.util.Map getResponseHeaders ()`: Returns the response headers of the last resquest execution.
- `int patch (java.lang.String url,
     java.lang.String patchData)`: Perform an HTTP PATCH to the given URL using the given data in the body.
- `int patch (java.lang.String url,
     java.lang.String patchData,
     java.util.Map headers)`: Perform an HTTP PATCH to the given URL using the given data in the body.
- `int patch (java.lang.String url,
     java.util.Map headers,
     java.util.Map parameters)`: Perform URLEncoded HTTP PATCH operation.
- `int post (java.lang.String url,
    java.lang.String postData)`: Perform an HTTP POST to the given URL using the given data in the post
 body.
- `int post (java.lang.String url,
    java.lang.String postData,
    java.util.Map headers)`: Perform HTTP POST with headers
- `int post (java.lang.String url,
    java.util.Map parameters)`: Perform an HTTP POST to the given URL serializing the given parameters
 into the post body.
- `int post (java.lang.String url,
    java.util.Map headers,
    java.util.Map parameters)`: Perform URLEncoded HTTP POST operation.
- `int put (java.lang.String url,
   java.lang.String postData)`: Perform an HTTP PUT to the given URL using the given data in the body.
- `int put (java.lang.String url,
   java.lang.String putData,
   java.util.Map headers)`: Perform an HTTP PUT to the given URL using the given data in the body.
- `int put (java.lang.String url,
   java.util.Map headers,
   java.util.Map parameters)`: Perform URLEncoded HTTP PUT operation.
- `void setHeaders (java.util.Map headers)`: Sets headers supplied in the argument
- `void setup (boolean useSSL,
     int port,
     java.lang.String username,
     java.lang.String password,
     java.lang.String timeoutInSeconds,
     java.util.Map options)`: Setup this client using the given configuration.
- `void setup (boolean useSSL,
     int port,
     java.lang.String username,
     java.lang.String password,
     java.lang.String timeoutInSeconds,
     java.util.Map options,
     java.lang.String sslProtocol)`: *Setup this client using the given configuration.**

---

## IIQClient.AuthorizationService.CheckAuthorizationResult
**Package:** `sailpoint.integration`

### Description
Encapsulates the result of checking authorization.

### Inheritance & Interfaces
```java
public static classIIQClient.AuthorizationService.CheckAuthorizationResultextendsRequestResult
```

### Attributes
No attributes.

### Methods
- `static IIQClient.AuthorizationService.CheckAuthorizationResult createResultFromMap (java.util.Map map)`: Create a result from the given map.
- `void fromMap (java.util.Map map)`: Initialize this result from the given map.
- `boolean isAuthorized ()`: Return whether the user is authorized for the requested right.
- `void setAuthorized (boolean authorized)`: Set whether the user is authorized for the requested right.
- `java.util.Map toMap ()`: Convert this result to a Map.

---

## IIQClient.AuthorizationService.Consts
**Package:** `sailpoint.integration`

### Description
Constants used by the authorization service.

### Inheritance & Interfaces
```java
public static classIIQClient.AuthorizationService.Constsextends java.lang.Object
```

### Attributes
- `static java.lang.String PARAM_RIGHT`: Query parameter that holds name of the right to check.
- `static java.lang.String RESOURCE_CHECK_AUTHORIZATION`: The path to the check authorization REST resource.

### Methods
No methods.

---

## IIQClient.AuthorizationService
**Package:** `sailpoint.integration`

### Description
Helper class IIQClient.checkAuthorization(String, String) .

### Inheritance & Interfaces
```java
public static classIIQClient.AuthorizationServiceextends java.lang.Object
```

### Attributes
No attributes.

### Methods
No methods.

---

## IIQClient.IdentityService.Consts.AttributeNames
**Package:** `sailpoint.integration`

### Description
JSON attributes in the POST request bodies to create and
 update an identity.

### Inheritance & Interfaces
```java
public static classIIQClient.IdentityService.Consts.AttributeNamesextends java.lang.Object
```

### Attributes
- `static java.lang.String EMAIL`: The identity's email.
- `static java.lang.String FIRST_NAME`: The identity's first name.
- `static java.lang.String LAST_NAME`: The identity's last name.
- `static java.lang.String MANAGER`: The name of the manager for the identity.
- `static java.lang.String PASSWORD`: The identity's password.
- `static java.lang.String USER_NAME`: The name of the Identity.

### Methods
No methods.

---

## IIQClient.IdentityService.Consts
**Package:** `sailpoint.integration`

### Description
Constants used for identity create and update.

### Inheritance & Interfaces
```java
public static classIIQClient.IdentityService.Constsextends java.lang.Object
```

### Attributes
No attributes.

### Methods
No methods.

---

## IIQClient.IdentityService.CreateOrUpdateResult
**Package:** `sailpoint.integration`

### Description
Encapsulates the result or creating or updating an identity.

### Inheritance & Interfaces
```java
public static classIIQClient.IdentityService.CreateOrUpdateResultextendsRequestResult
```

### Attributes
No attributes.

### Methods
- `static IIQClient.IdentityService.CreateOrUpdateResult createResultFromMap (java.util.Map map)`: Create a result from the given map.
- `void fromMap (java.util.Map map)`: Initialize this result from the given map.
- `boolean isPerformed ()`: Return whether the requested changes were performed.
- `void setPerformed (boolean created)`: Set whether the requested changes were performed.
- `java.util.Map toMap ()`: Convert this result to a Map.

---

## IIQClient.IdentityService
**Package:** `sailpoint.integration`

### Description
Helper class for identity create and update methods.

### Inheritance & Interfaces
```java
public static classIIQClient.IdentityServiceextends java.lang.Object
```

### Attributes
No attributes.

### Methods
No methods.

---

## IIQClient.PasswordService.CheckPasswordResult
**Package:** `sailpoint.integration`

### Description
Encapsulates results from IIQClient.checkPasswordPolicy(String, String)

### Inheritance & Interfaces
```java
public static classIIQClient.PasswordService.CheckPasswordResultextendsRequestResult
```

### Attributes
No attributes.

### Methods
- `static IIQClient.PasswordService.CheckPasswordResult createResultFromMap (java.util.Map map)`: Create a result from the given map.
- `void fromMap (java.util.Map map)`: Initialize this result from the given map.
- `boolean isValid ()`: Return whether the password was valid.
- `void setValid (boolean valid)`:
- `java.util.Map toMap ()`: Convert this result to a Map.

---

## IIQClient.PasswordService.Consts
**Package:** `sailpoint.integration`

### Description
Constants used for password policy checking.

### Inheritance & Interfaces
```java
public static classIIQClient.PasswordService.Constsextends java.lang.Object
```

### Attributes
- `static java.lang.String PARAM_ID`: The name of the request body parameter for the identity name.
- `static java.lang.String PARAM_PASSWORD`: The name of the request body parameter for the password.
- `static java.lang.String RESOURCE_CHECK_PASSWORD_POLICIES`: The path to the check password policies REST sub-resource.

### Methods
No methods.

---

## IIQClient.PasswordService
**Package:** `sailpoint.integration`

### Description
Helper class used by IIQClient.checkPasswordPolicy(String, String) .

### Inheritance & Interfaces
```java
public static classIIQClient.PasswordServiceextends java.lang.Object
```

### Attributes
No attributes.

### Methods
No methods.

---

## IIQClient
**Package:** `sailpoint.integration`

### Description
Class providing a convenient interface for SailPoint IIQ web services.

### Inheritance & Interfaces
```java
public classIIQClientextends java.lang.Object
```

### Attributes
- `static java.lang.String AGGREGATION_OPTIONS`: POST body parameter that contains options for aggregation.
- `static java.lang.String ARG_APPLICATION`: POST request body argument to specify the application for password
 intercept.
- `static java.lang.String ARG_ATTRIBUTE_NAME`: The name of the query parameter that specifies which configuration
 value to return in getConfiguration(String) .
- `static java.lang.String ARG_COMMENTS`: Deprecated. No longer supported.
- `static java.lang.String ARG_IDENTITY`: Query parameter to specify the name of the identity.
- `static java.lang.String ARG_PASSWORD`: POST request body argument to specify the password for password
 intercept.
- `static java.lang.String ARG_ROLE_MODE`: Query parameter that specifies the role mode.
- `static java.lang.String ARG_ROLE_REQUESTS`: Deprecated. No longer supported.
- `static java.lang.String ARG_ROLES`: Query parameter that specifies the roles to check for policy violations
 in checkRolePolicies(String, List) .
- `static java.lang.String ARG_WORKFLOW_INPUTS`: POST request body parameter that contains workflow launch arguments.
- `static java.lang.String DEFAULT_URL`: Default base URL to the IIQ server.
- `static java.lang.String PARAM_APPLICATION`: Query parameter with the name of the application to aggregate.
- `static java.lang.String PARAM_HOST`: POST request body parameter with the host requesting remote login.
- `static java.lang.String PARAM_RESOURCE_WORKFLOW_DEFINITION`: Path parameter with the name or ID of the workflow.
- `static java.lang.String RESOURCE_AGGREGATE`: The path to the aggregate identity REST sub-resource.
- `static java.lang.String RESOURCE_AUTHENTICATION`: The path to the authentication REST resource.
- `static java.lang.String RESOURCE_CHECK_ROLE_POLICIES`: The path to the check role policies REST sub-resource.
- `static java.lang.String RESOURCE_CONFIGURATION`: The path to the configuration REST resource.
- `static java.lang.String RESOURCE_GROUP_DEFINITION`: The path to the group definition REST sub-resource.
- `static java.lang.String RESOURCE_IDENTITIES`: The path to the identities REST resource.
- `static java.lang.String RESOURCE_MANAGED_IDENTITIES`: The path to the managed identities REST sub-resource.
- `static java.lang.String RESOURCE_PASSWORD_INTERCEPT`: The path to the password intercept REST resource.
- `static java.lang.String RESOURCE_PING`: The path to the ping REST resource.
- `static java.lang.String RESOURCE_POLICIES`: The path to the policies REST resource.
- `static java.lang.String RESOURCE_REQUESTS`: The path to the requests REST resource.
- `static java.lang.String RESOURCE_ROLES`: The path to the roles REST resource.
- `static java.lang.String RESOURCE_TASK_RESULTS`: The path to the task results REST resource.
- `static java.lang.String RESOURCE_WORKFLOWS`: The path to the workflows REST resource.
- `static java.lang.String RESULT_REMOTE_TOKEN_ID`: Deprecated. Unused
- `static java.lang.String SUB_RESOURCE_ASSIGNABLE_PERMITS`: The path to the assignable permits roles REST sub-resource.
- `static java.lang.String SUB_RESOURCE_REMOTE_LOGIN`: The path to the identity remote login REST sub-resource.
- `static java.lang.String SUB_RESOURCE_ROLE_REQUESTS`: Deprecated. No longer supported.
- `static java.lang.String SUB_RESOURCE_TASKRESULT_CANCELWORKFLOW`: The path to the cancel workflow task result REST sub-resource.
- `static java.lang.String SUB_RESOURCE_TASKRESULT_STATUS`: The path to the task result status REST sub-resource.
- `static java.lang.String SUB_RESOURCE_WORKFLOW_LAUNCH`: The path to the workflow launch REST sub-resource.

### Methods
- `RequestResult aggregateAccount (java.lang.String identity,
                java.lang.String appName,
                java.util.Map resourceObject,
                java.util.Map aggOptions)`: Aggregate the given resource object for the requested app onto the given
 identity.
- `java.lang.String authenticate ()`: Attempt to authenticate using the configured credentials.
- `RequestResult cancelWorkflow (java.lang.String taskId,
              java.lang.String comments)`: Cancel a workflow.
- `IIQClient.AuthorizationService.CheckAuthorizationResult checkAuthorization (java.lang.String identity,
                  java.lang.String right)`: Check whether the Identity with the given name is authorized for the
 requested right.
- `IIQClient.PasswordService.CheckPasswordResult checkPasswordPolicy (java.lang.String identity,
                   java.lang.String password)`: Check the password for the given identity.
- `java.util.List checkRolePolicies (java.lang.String identity,
                 java.util.List roles)`: Given a list of potential role assignments, check to see if assigning
 these roles would violate any SOD policies.
- `void configure ()`: Configure the IIQClient reading the properties from CONFIG_FILE.
- `void configure (java.lang.String baseURL,
         java.lang.String user,
         java.lang.String password)`: Configure the IIQClient reading the properties from CONFIG_FILE.
- `java.lang.String getBaseUrl ()`: Return the base URL being used for requests.
- `java.lang.String getConfiguration (java.lang.String configName)`: Return a system configuration value for the requested attribute.
- `java.lang.String getIdentityList (java.lang.String identity)`: Get the list of Identities for which the given Identity is authorized.
- `ListResult getLinks (java.lang.String identityName,
        boolean includeLinkState)`: Get the links associated with the named identity.
- `java.lang.String getRequestCommentsEnabled ()`: Deprecated. Unused
- `RequestResult getTaskResultStatus (java.lang.String taskId)`: Return details about the task result given
 the name or id of the task result.
- `java.lang.String getUsername ()`: Return the username being used for authentication.
- `IIQClient.IdentityService.CreateOrUpdateResult identityCreate (java.util.Map attributes)`: Create a new identity from the given attributes.
- `IIQClient.IdentityService.CreateOrUpdateResult identityCreateOrUpdate (java.lang.String identityName,
                      java.util.Map attributes)`: Create or update an identity from the given attributes.
- `static java.lang.String itoa (int i)`: Convert the given int to a string.
- `RequestResult launchWorkflow (java.lang.String workflowName,
              java.util.Map launchArgs)`: Service that can launch a workflow remotely using IIQ.
- `java.lang.String passwordIntercept (java.lang.String application,
                 java.lang.String identity,
                 java.lang.String password)`: Notify IIQ of a password intercept event.
- `java.lang.String ping ()`: Ping the IIQ REST endpoint and return a success string if the client
 could successfully connect and authenticate with the configured
 credentials.
- `static void println (java.lang.Object o)`: Print the given object to stdout.
- `java.lang.String remoteLogin (java.lang.String identityName)`: Create a RemoteLoginToken on the IIQ Server side.
- `java.lang.String rolesAssignablePermits (java.util.Map parameterMap,
                      java.lang.String identity)`: Return the roles that can be assigned to the given identity based on the
 role mode.
- `void setBaseUrl (java.lang.String s)`: Set the base URL to use for requests.
- `void setRequestCommentsEnabled (java.lang.String s)`: Deprecated. Unused
- `void setTrace (boolean b)`: Set whether to print trace information to stdout.
- `void setUsername (java.lang.String _username)`: Set the username to use for authentication.
- `java.lang.String showIdentity (java.lang.String identity)`: Return a JSON string that has a map with the roles and viewable
 attributes for the requested identity.
- `java.lang.String updateIdentityRoleReferences (java.lang.String identity,
                            java.lang.String roleJSON,
                            java.lang.String requestComments)`: Deprecated. No longer supported.
- `java.lang.String userRequestsIdentityRoles ()`: Deprecated. No longer supported.

---

## IntegrationInterface
**Package:** `sailpoint.integration`

### Description
Interface that defines the methods that may be supported by
 an integrated provisioning system.

 There are two default implementations.  RemoteIntegration uses
 a set of REST resources to communicate with the provisioning system.
 The remote servlet is expected to be implemented with the
 IIQIntegrationServlet framework or it may be completely custom.

 AbstractIntegration provides a skeleton implementation that
 appropriate error messages for all methods.  This is intended
 to be subclassed with real implementations of the supported methods.
 When using the IIQIntegrationServlet, it is registered as the
 handler class in the web.xml configuration for the servlet.

 NOTE: This is part of the standalone integration jar and must
 have NO dependencies to IIQ classes other than the ones in this package,
 and it must NOT use JDK 1.5 features.

 This is extended by sailpoint.object.IntegrationExecutor which
 adds a few additional methods that are allowed to have dependencies
 on the IIQ data model, such as the Identity and Bundle classes.
 Typically integrations will implement IntegrationExecutor
 or extend AbstractIntegrationExecutor and communicate directly
 with the target system through a proprietary protocol.  If the
 target system requires an "agent" then it may use the RemoteIntegration
 framework.

### Inheritance & Interfaces
```java
public interfaceIntegrationInterface
```

### Attributes
No attributes.

### Methods
- `RequestResult addRole ( RoleDefinition def)`: Create or update the definition of a role.
- `void configure (java.util.Map args)`: Must be called immediately after construction to provide
 a set of configuration parameters.
- `RequestResult deleteRole (java.lang.String roleName)`: Delete a role.
- `RequestResult getRequestStatus (java.lang.String requestID)`: Get the current status of the request with the given request
 ID.
- `java.util.List listRoles ()`: Return the current list of "manageable" roles.
- `java.lang.String ping ()`: Return some sort of status message.
- `RequestResult provision (java.lang.String identity, ProvisioningPlan plan)`: Make changes to an identity defined by a ProvisioningPlan.

---

## IntegrationServlet
**Package:** `sailpoint.integration`

### Description
An HttpServlet to convert a set of REST request into calls to
 an IntegrationInterface class.

 This is part of the integration framework provided to assist
 the writing of remote agents for provisioning systems.
 It parses a set of REST URIs and converts them into calls
 to a registered implementation IntegrationInterface.
 Authentication is delegated to a registered Authenticator.

 Example Servlet Configuration IIQ Integration Agent sailpoint.integration.IntegrationServlet handler sailpoint.integration.TestIntegration authenticator sailpoint.integration.TestAuthenticator IIQ Integration Agent /resources/iiq/* The handler class name would be changed to the subclass of
 IntegrationInterface that contains the custom code.
 The url-pattern would be adjusted according to the desires of the
 hosting app server administrator.

 REQUEST URIs

 GET /ping
   - return a status message or 500 on error

 GET /roles
   - return a list of "manageable" role names as a JSON array

 POST /role/ - post the JSON representation of a RoleDefinition
   - returns a map representation of a RequestResult object.
   - the is ignored since the RoleDefinition already has the name,
     it's just here for symmetry with the other role resources

 DELETE /role/ GET /role/ ?method='delete'
   - delete the role, return an array of error messages or a map
     representation of a RequestResult object.

 POST /provision/ - post the JSON representation of a ProvisioningPlan
   - returns a map representation of aRequestResult object.
   - must be the name of the aggregate user in the
      provisioning system

 GET /request/ - return a map representation of the RequestResult object which
     contains the status of the given request.

### Inheritance & Interfaces
```java
public classIntegrationServletextendsRestServlet
```

### Attributes
- `static java.lang.String RESOURCE_PING`: Path of the ping endpoint.
- `static java.lang.String RESOURCE_PROVISION`: Path of the provision endpoint.
- `static java.lang.String RESOURCE_REQUEST_STATUS`: Path of the request status endpoint.
- `static java.lang.String RESOURCE_ROLE`: Path of the role endpoint.
- `static java.lang.String RESOURCE_ROLES`: Path of the roles endpoint.

### Methods
- `void doDelete (javax.servlet.http.HttpServletRequest req,
        javax.servlet.http.HttpServletResponse res,
        java.util.List path)`: Subclass should overload this if it let's us do the URL parsing.
- `void doGet (javax.servlet.http.HttpServletRequest req,
     javax.servlet.http.HttpServletResponse res,
     java.util.List path)`: Subclass should overload this if it let's us do the URL parsing.
- `void doPost (javax.servlet.http.HttpServletRequest req,
      javax.servlet.http.HttpServletResponse res,
      java.util.List path)`: Subclass should overload this if it let's us do the URL parsing.
- `IntegrationInterface getHandler ()`: For subclasses after initialization.
- `void init (javax.servlet.ServletConfig config)`: Initialize this servlet and create the IntegrationInterface and
 Authenticator registered in the given config.
- `static java.lang.Object instantiate (java.lang.String name)`: Create an instance of a class given a class name.
- `protected boolean performAuthentication (java.lang.String username,
                     java.lang.String password)`: Delegate the authorization check to the registered authenticator.

---

## JsonUtil.JsonParseException
**Package:** `sailpoint.integration`

### Description
This internal exception is thrown when this class encounters a parse exception during
 processing.

### Inheritance & Interfaces
```java
public static classJsonUtil.JsonParseExceptionextends java.io.IOException
```

### Attributes
No attributes.

### Methods
No methods.

---

## JsonUtil
**Package:** `sailpoint.integration`

### Description
Utility class for rendering and parsing JSON.

 Dates are rendered as strings, but they do not parse back as dates.

### Inheritance & Interfaces
```java
public classJsonUtilextends java.lang.Object
```

### Attributes
- `static java.lang.String DATE_FORMAT`: Date format we render.
- `static boolean SortMapKeys`: A global flag controlling whether we sort map keys before
 rendering.

### Methods
- `static java.lang.Object parse (java.lang.String json)`: Public interface for parsing JSON that conforms to our restrictions.
- `static java.lang.String render (java.lang.Object o)`: Public interface to rendering something as a JSON string.
- `static void renderObject (java.lang.StringBuffer b,
            java.lang.Object targetClass)`:
- `static java.lang.String toStringOrJson (java.lang.Object object)`: Parses the object and returns a string value or an equivalent
 JSON representation.

---

## ListResult
**Package:** `sailpoint.integration`

### Description
Transfer object that is used to send back a list of results which may be
 sorted and paged.  As such, this returns the total count of objects that
 would be returned in the list without paging.

### Inheritance & Interfaces
```java
public classListResultextendsRequestResult
```

### Attributes
No attributes.

### Methods
- `void addObjects (java.util.List toAdd)`: Adds objects to the current result and increments the count.
- `void fromMap (java.util.Map map)`: Read this ListResult from a Map.
- `int getCount ()`: Return the total count of objects - disregarding pagination.
- `static ListResult getInstance ()`: Create an empty ListResult.
- `java.util.List getObjects ()`: Return the objects in this ListResult.
- `void mergeListResult ( ListResult mergeList)`: This function adds the object from mergeList to current ListResult and
 updates the count.
- `void setObjects (java.util.List objects)`: Set the objects in this ListResult.
- `java.util.Map toMap ()`: Convert this ListResult to a Map.

---

## ObjectResult
**Package:** `sailpoint.integration`

### Description
Simple RequestResult that returns a single object.

### Inheritance & Interfaces
```java
public classObjectResultextendsRequestResult
```

### Attributes
No attributes.

### Methods
- `void fromMap (java.util.Map map)`: Read this ObjectResult from a Map.
- `java.lang.Object getObject ()`: Return the object payload of this ObjectResult.
- `void setObject (java.lang.Object object)`: Set the object payload of this ObjectResult.
- `java.util.Map toMap ()`: Convert this ObjectResult to a Map.

---

## ProvisioningPlan.AccountRequest
**Package:** `sailpoint.integration`

### Description
A request to modify a single account.

### Inheritance & Interfaces
```java
public static classProvisioningPlan.AccountRequestextends java.lang.Object
```

### Attributes
No attributes.

### Methods
- `void add ( ProvisioningPlan.AttributeRequest att)`: Add the given AttributeRequest to this AccountRequest.
- `void add ( ProvisioningPlan.PermissionRequest perm)`: Add the given PermissionRequest to this AccountRequest.
- `void fromMap (java.util.Map map)`: Read this AccountRequest from the given Map.
- `java.lang.Object get (java.lang.String name)`: Set the requested argument for this AccountRequest.
- `java.lang.String getApplication ()`: Return the application for this request.
- `java.util.Map getArguments ()`: Return the arguments for this AccountRequest.
- `java.util.List getAttributeRequests ()`: Return the AttributeRequests for this AccountRequest.
- `java.lang.String getInstance ()`: Return the application instance for this request.
- `java.lang.String getNativeIdentity ()`: Return the native identity of the account for this request.
- `java.lang.String getOperation ()`: Return the operation for this request - one of the OP_* constants.
- `java.util.List getPermissionRequests ()`: Return the PermissionRequests for this AccountRequest.
- `RequestResult getResult ()`: Return the RequestResult from applying this request.
- `java.lang.String getTrackingId ()`: Return the tracking ID for this request.
- `void put (java.lang.String name,
   java.lang.Object value)`: Set the given argument on this AccountRequest.
- `void setApplication (java.lang.String s)`: Set the application for this request.
- `void setArguments (java.util.Map data)`: Set the arguments for this AccountRequest.
- `void setAttributeRequests (java.util.List reqs)`: Set the AttributeRequests for this AccountRequest.
- `void setInstance (java.lang.String instance)`: Set the application instance for this request.
- `void setNativeIdentity (java.lang.String id)`: Set the native identity of the account for this request.
- `void setOperation (java.lang.String op)`: Set the operation for this request - one of the OP_* constants.
- `void setPermissionRequests (java.util.List reqs)`: Set the PermissionRequests for this AccountRequest.
- `void setResult ( RequestResult _result)`: Set the RequestResult from applying this request.
- `void setTrackingId (java.lang.String id)`: Set the tracking ID for this request.
- `java.util.Map toMap ()`: Render the request in a generic Map/List model for JSON conversion.

---

## ProvisioningPlan.AttributeRequest
**Package:** `sailpoint.integration`

### Description
A request to add, remove, or set the value(s) of an attribute on an
 object or account.

### Inheritance & Interfaces
```java
public static classProvisioningPlan.AttributeRequestextends java.lang.Object
```

### Attributes
No attributes.

### Methods
- `void fromMap (java.util.Map map)`: Read this request from the given Map.
- `java.lang.Object get (java.lang.String name)`: Return the requested argument for this request.
- `java.util.Map getArguments ()`: Return the arguments for this request.
- `java.lang.String getName ()`: Return the name of the attribute to change.
- `java.lang.String getOperation ()`: Return the operation for this AttributeRequest - one of the OP_*
 constants.
- `RequestResult getResult ()`: Return the RequestResult from provisioning this attribute.
- `java.lang.String getTrackingId ()`: Return the tracking ID for this request.
- `java.lang.Object getValue ()`: Return the value to add, remove, or set - may be a List.
- `void put (java.lang.String name,
   java.lang.Object value)`: Set the given argument for this request.
- `void setArguments (java.util.Map data)`: Set the arguments for this request.
- `void setName (java.lang.String s)`: Set the name of the attribute to change.
- `void setOperation (java.lang.String op)`: Set the operation for this AttributeRequest - one of the OP_*
 constants.
- `void setResult ( RequestResult _result)`: Set the RequestResult from provisioning this attribute.
- `void setTrackingId (java.lang.String id)`: Set the tracking ID for this request.
- `void setValue (java.lang.Object o)`: Set the value to add, remove, or set - may be a List.
- `java.util.Map toMap ()`: Convert this request to a Map.

---

## ProvisioningPlan.ObjectRequest
**Package:** `sailpoint.integration`

### Description
A request for a non-account object (eg - a group).

### Inheritance & Interfaces
```java
public static classProvisioningPlan.ObjectRequestextends java.lang.Object
```

### Attributes
No attributes.

### Methods
- `void add ( ProvisioningPlan.AttributeRequest req)`: Add the given AttributeRequest to this request.
- `void fromMap (java.util.Map map)`: Read this ObjectRequest from a Map.
- `java.util.List getAttributeRequests ()`: Return the AttributeRequests for this request.
- `java.lang.String getOperation ()`: Return the operation for this request - one of the OP_* constants.
- `java.lang.String getTargetClass ()`: Return the database object class of the associated object.
- `java.lang.String getTargetId ()`: Return the unique database id of an associated object.
- `java.lang.String getTargetName ()`: Return the optional display name of an associated object.
- `void setAttributeRequests (java.util.List reqs)`: Set the AttributeRequests for this request.
- `void setOperation (java.lang.String op)`: Set the operation for this request - one of the OP_* constants.
- `void setTargetClass (java.lang.Class cls)`: Set the database object class of the associated object.
- `void setTargetClass (java.lang.String cls)`: Set the database object class of the associated object.
- `void setTargetId (java.lang.String id)`: Set the unique database id of an associated object.
- `void setTargetName (java.lang.String name)`: Set the optional display name of an associated object.
- `java.util.Map toMap ()`: Convert this ObjectRequest to a Map.

---

## ProvisioningPlan.PermissionRequest
**Package:** `sailpoint.integration`

### Description
A request to add, remove, or set permissions.

### Inheritance & Interfaces
```java
public static classProvisioningPlan.PermissionRequestextends java.lang.Object
```

### Attributes
No attributes.

### Methods
- `void fromMap (java.util.Map map)`: Read this request from a Map.
- `java.lang.Object get (java.lang.String name)`: Return the requested argument for this request.
- `java.util.Map getArguments ()`: Return the arguments for this request.
- `java.lang.String getOperation ()`: Return the operation for this request - one of the OP_* constants.
- `RequestResult getResult ()`: Return the RequestResult from provisioning this permission.
- `java.lang.String getRights ()`: Return the rights for the permission - may be a csv.
- `java.util.List getRightsList ()`: Return the rights as a List.
- `java.lang.String getTarget ()`: Return the permission target.
- `java.lang.String getTrackingId ()`: Return the tracking ID for this request.
- `void put (java.lang.String name,
   java.lang.Object value)`: Return the given argument for this request.
- `void setArguments (java.util.Map data)`: Set the arguments for this request.
- `void setOperation (java.lang.String op)`: Set the operation for this request - one of the OP_* constants.
- `void setResult ( RequestResult _result)`: Set the RequestResult from provisioning this permission.
- `void setRights (java.lang.String s)`: Set the rights for the permission - may be a csv.
- `void setRightsList (java.util.List list)`: Set the rights as a List.
- `void setTarget (java.lang.String s)`: Set the permission target.
- `void setTrackingId (java.lang.String id)`: Set the tracking ID for this request.
- `java.util.Map toMap ()`: Convert this request to a Map.

---

## ProvisioningPlan
**Package:** `sailpoint.integration`

### Description
Class used maintain a complex provisioning request involving
 several applications.

### Inheritance & Interfaces
```java
public classProvisioningPlanextends java.lang.Object
```

### Attributes
- `static java.lang.String APP_IDM`: The name of a special AccountRequest application that represents
 the aggregate identity managed by a provisioning system.
- `static java.lang.String ARG_IDENTITY_ATTRIBUTE`: Argument passed in an AccountRequest when the name of the
 account identity attribute is not fixed.
- `static java.lang.String ATT_ACCOUNT_APPLICATION`:
- `static java.lang.String ATT_ACCOUNT_ARGUMENTS`:
- `static java.lang.String ATT_ACCOUNT_ATTRIBUTES`:
- `static java.lang.String ATT_ACCOUNT_IDENTITY`:
- `static java.lang.String ATT_ACCOUNT_INSTANCE`:
- `static java.lang.String ATT_ACCOUNT_PERMISSIONS`:
- `static java.lang.String ATT_ATTRIBUTE_NAME`:
- `static java.lang.String ATT_ATTRIBUTE_VALUE`:
- `static java.lang.String ATT_CURRENT_PASSWORD`: Special attribute used in the arguments map of a password
 AttributeRequest that holds the users current password.
- `static java.lang.String ATT_IDM_ROLES`: The name of the attribute in the APP_IDM account that
 represents the assigned roles.
- `static java.lang.String ATT_OBJECT_ATTRIBUTES`:
- `static java.lang.String ATT_OBJECT_CLASS`:
- `static java.lang.String ATT_OBJECT_ID`:
- `static java.lang.String ATT_OBJECT_NAME`:
- `static java.lang.String ATT_OP`:
- `static java.lang.String ATT_PASSWORD`: Special attribute to allow setting an Identity or account's password.
- `static java.lang.String ATT_PERMISSION_RIGHTS`:
- `static java.lang.String ATT_PERMISSION_TARGET`:
- `static java.lang.String ATT_PLAN_ACCOUNTS`:
- `static java.lang.String ATT_PLAN_ARGUMENTS`:
- `static java.lang.String ATT_PLAN_IDENTITY`:
- `static java.lang.String ATT_PLAN_INTEGRATION_DATA`:
- `static java.lang.String ATT_PLAN_OBJECTS`:
- `static java.lang.String ATT_PRE_EXPIRE`: Special attribute used in the arguments map of a password
 AttributeRequest that indicates that the new password should be
 pre-expired (ie - the user has to change it after first login).
- `static java.lang.String ATT_REQUEST_ARGUMENTS`:
- `static java.lang.String ATT_REQUEST_RESULT`:
- `static java.lang.String OP_ACCOUNT_CREATE`:
- `static java.lang.String OP_ACCOUNT_DELETE`:
- `static java.lang.String OP_ACCOUNT_DISABLE`:
- `static java.lang.String OP_ACCOUNT_ENABLE`:
- `static java.lang.String OP_ACCOUNT_LOCK`:
- `static java.lang.String OP_ACCOUNT_MODIFY`:
- `static java.lang.String OP_ACCOUNT_UNLOCK`:
- `static java.lang.String OP_ADD`:
- `static java.lang.String OP_REMOVE`:
- `static java.lang.String OP_SET`:

### Methods
- `void add (java.util.Map map)`: Add the given map as arguments.
- `void add ( ProvisioningPlan.AccountRequest req)`: Add the given AccountRequest to this ProvisioningPlan.
- `void add ( ProvisioningPlan.ObjectRequest req)`: Add the given ObjectRequest to this ProvisioningPlan.
- `static java.util.List csvToList (java.lang.String src,
         boolean filterEmpty)`: Convert the given comma-separated string to a List.
- `void fromMap (java.util.Map map)`: Build a ProvisioningPlan from the generic Map/List model.
- `java.lang.Object get (java.lang.String name)`: Return the requested argument.
- `java.util.List getAccountRequests ()`: Return the AccountRequests.
- `java.util.Map getArguments ()`: Return the arguments for this ProvisioningPlan.
- `java.lang.String getIdentity ()`: Return the identity being provisioned.
- `java.util.Map getIntegrationData ()`: Deprecated. Use getArguments()
- `java.util.List getObjectRequests ()`: Return the ObjectRequests.
- `static java.lang.String listToCsv (java.util.List list,
         boolean filterEmpty)`: Convert the given list to a comma-separated string.
- `void put (java.lang.String name,
   java.lang.Object value)`: Add the given argument.
- `void setAccountRequests (java.util.List reqs)`: Set the AccountRequests.
- `void setArguments (java.util.Map data)`: Set the arguments for this ProvisioningPlan.
- `void setIdentity (java.lang.String s)`: Set the identity being provisioned.
- `void setIntegrationData (java.util.Map data)`: Deprecated. Use setArguments(Map)
- `void setObjectRequests (java.util.List reqs)`: Set the ObjectRequests.
- `java.util.Map toMap ()`: Render the ProvisioningPlan as a generic Map/List model.

---

## RemoteIntegration
**Package:** `sailpoint.integration`

### Description
Implementation of IntegrationInterface that uses REST resources
 to communicate with the provisioning system over HTTP.

### Inheritance & Interfaces
```java
public classRemoteIntegrationextends java.lang.Object
implementsIntegrationInterface
```

### Attributes
- `protected java.util.Map _intConfigArgs`: IntegrationConfig arguments.

### Methods
- `RequestResult addRole ( RoleDefinition def)`: Create or update the definition of a role.
- `void configure (java.util.Map args)`: Consume the IntegrationConfig.
- `RequestResult deleteRole (java.lang.String roleName)`: Delete a role.
- `RequestResult getRequestStatus (java.lang.String requestID)`: Get the current status of the request with the given request
 ID.
- `RestClient getRestClient ()`: Return the underlying RestClient.
- `java.util.List listRoles ()`: Return the current list of "manageable" roles.
- `java.lang.String ping ()`: Return a status message.
- `RequestResult provision (java.lang.String identity, ProvisioningPlan plan)`: Make changes to an identity defined by a ProvisioningPlan.

---

## RequestResult
**Package:** `sailpoint.integration`

### Description
A RequestResult holds information about a request on an integration system.
 Often requests to integrations are not executed immediately but instead
 launched in the background as a workflow.  This can return information about
 the status of a request, an ID of the request, and any errors or warnings
 that occurred during the request.  Note that request ID should be considered
 optional when returning a RequestResult from one of the IntegrationInterface
 methods since different integrations will use background requests and some
 won't.

### Inheritance & Interfaces
```java
public classRequestResultextends java.lang.Object
```

### Attributes
- `static java.lang.String STATUS_COMMITTED`: Status indicating the request was sent successfully and that
 the provisioning system was able to immediately commit the changes.
- `static java.lang.String STATUS_FAILURE`: Status indicating a failed request.
- `static java.lang.String STATUS_IN_PROCESS`: Status indicating a request that is currently being processed.
- `static java.lang.String STATUS_NOT_STARTED`: Status indicating a request that has not yet begun processing.
- `static java.lang.String STATUS_RETRY`: Status indicating a failed request that can be retried.
- `static java.lang.String STATUS_SUCCESS`: Status indicating a successful request.
- `static java.lang.String STATUS_WARNING`: Status indicating a request that completed with warnings.

### Methods
- `void addError (java.lang.String error)`: Add an error to this result.
- `void addError (java.lang.Throwable t)`: Add an exception to this result.
- `void addErrors (java.util.Map error)`: Add an error map to this result.
- `void addWarning (java.lang.String warning)`: Add a warning to this request.
- `void addWarnings (java.util.Map warning)`: Add a warnings to this request.
- `void assimilate ( RequestResult src)`: Assimilate one result into another.
- `void fromMap (java.util.Map map)`: Populate the attributes on this object from the given map.
- `java.util.Map getAttributes ()`: Return the generic Map of attributes
- `java.util.List getErrors ()`: Return the errors for this request.
- `java.util.Map getMetaData ()`: Additional metadata specific to the current
 request result's data payload.
- `java.lang.String getRequestID ()`: Return the ID of the request if available.
- `int getRetryWait ()`: Set the minimum number of seconds to wait until the next retry.
- `java.lang.String getStatus ()`: Return the status - one of the STATUS_* constants.
- `java.util.List getWarnings ()`: Return the warnings for this request.
- `boolean isComplete ()`: Return whether this request is complete.
- `boolean isFailure ()`: Return whether this request was completed with a failure.
- `boolean isRetry ()`: Return whether this request was completed due to a retryable failure.
- `boolean isSuccess ()`: Return whether this request was completed successful.
- `void setAttributes (java.util.Map attributes)`: Set the generic Map of attributes to set
- `void setErrors (java.util.List errors)`: Set the errors for this request.
- `void setMetaData (java.util.Map metaData)`:
- `void setRequestID (java.lang.String requestID)`: Set the ID of the request.
- `void setRetryWait (int i)`:
- `void setStatus (java.lang.String status)`: Set the status - one of the STATUS_* constants.
- `void setWarnings (java.util.List warnings)`: Set the warnings for this request.
- `java.util.Map toMap ()`: Convert this object to its map represenation.

---

## RestClient.ConnectionProblemException
**Package:** `sailpoint.integration`

### Description
Exception indicating a connection exception.

### Inheritance & Interfaces
```java
public static classRestClient.ConnectionProblemExceptionextends java.lang.Exception
```

### Attributes
No attributes.

### Methods
- `java.lang.String getError ()`: Return the error.
- `int getStatus ()`: Return the HTTP response status code.

---

## RestClient
**Package:** `sailpoint.integration`

### Description
Utility class for sending REST-style requests and parsing responses.
 Responses are assumed to be JSON strings of the basic data types
 supported by JsonUtil.

### Inheritance & Interfaces
```java
public classRestClientextends java.lang.Object
```

### Attributes
- `protected java.lang.String _baseUrl`: Base URL of the REST resources.
- `protected java.lang.StringBuffer _builder`: Buffer for building urls.
- `protected HttpClient _client`: HttpClient used to make the calls.
- `static java.lang.String ARG_PASSWORD`: Configuration argument that specifies the password.
- `static java.lang.String ARG_TIMEOUT`: Configuration argument that specifies the timeout in seconds.
- `static java.lang.String ARG_URL`: Configuration argument that specifies the URL.
- `static java.lang.String ARG_USERNAME`: Configuration argument that specifies the username.
- `static java.lang.String NATIVE_ID`: Configuration argument that specifies the native identifier for the identity

### Methods
- `void addHeader (java.lang.String name,
         java.lang.String value)`:
- `void configure (java.util.Map args)`: Configure connection parameters.
- `java.lang.Object delete (java.lang.String resource)`: Perform and HTTP DELETE on the requested resource.
- `java.lang.Object delete (java.lang.String resource,
      java.lang.String identity)`: Perform and HTTP DELETE on the requested resource.
- `java.lang.Object delete (java.lang.String resource,
      java.lang.String identity,
      java.util.Map _headers)`: Perform HTTP DELETE with headers.
- `java.lang.Object delete (java.lang.String resource,
      java.lang.String identity,
      java.util.Map _headers,
      java.lang.Object payLoad)`:
- `java.lang.Object get (java.lang.String resource)`: Send a REST request and return the JSON object that was
 in the response.
- `java.lang.Object get (java.lang.String resource,
   java.lang.String identity)`: Get a resource of the given type with the given name or ID.
- `java.lang.Object get (java.lang.String resource,
   java.lang.String identity,
   java.lang.String arg,
   java.lang.String value)`: Get a resource of the given type with the given name or ID.
- `java.lang.Object get (java.util.Map headers)`: GET with headers
- `java.lang.String getRaw (java.lang.String resource,
      java.lang.String identity,
      java.lang.String arg,
      java.lang.String value)`: GET without JSON assumptions.
- `java.lang.Object post (java.lang.Object payload,
    java.util.Map headers)`: Perform HTTP POST with headers.
- `java.lang.Object post (java.lang.String resource,
    java.lang.Object payload)`: Perform HTTP POST operation.
- `java.lang.Object post (java.lang.String resource,
    java.lang.String identity,
    java.lang.Object payload)`: Perform HTTP POST to the given resource.
- `java.lang.Object post (java.lang.String resource,
    java.lang.String identity,
    java.lang.String arg,
    java.lang.String value,
    java.lang.Object payload)`: Perform HTTP POST to the given resource with a query parameter.
- `java.lang.Object put (java.lang.String url,
   java.lang.String body)`: Perform HTTP PUT operation.
- `java.lang.Object put (java.lang.String url,
   java.lang.String body,
   java.util.Map headers)`: Perform HTTP PUT operation.

---

## RestServlet
**Package:** `sailpoint.integration`

### Description
An HttpServlet to handle REST requests.

### Inheritance & Interfaces
```java
public abstract classRestServletextends javax.servlet.http.HttpServlet
```

### Attributes
No attributes.

### Methods
- `static java.util.List delimToList (java.lang.String delim,
           java.lang.String src,
           boolean filterEmpty)`: Tokenize a delimited string.
- `void doDelete (javax.servlet.http.HttpServletRequest req,
        javax.servlet.http.HttpServletResponse res)`:
- `void doDelete (javax.servlet.http.HttpServletRequest req,
        javax.servlet.http.HttpServletResponse res,
        java.util.List path)`: Subclass should overload this if it let's us do the URL parsing.
- `void doGet (javax.servlet.http.HttpServletRequest req,
     javax.servlet.http.HttpServletResponse res)`:
- `void doGet (javax.servlet.http.HttpServletRequest req,
     javax.servlet.http.HttpServletResponse res,
     java.util.List path)`: Subclass should overload this if it let's us do the URL parsing.
- `void doPost (javax.servlet.http.HttpServletRequest req,
      javax.servlet.http.HttpServletResponse res)`:
- `void doPost (javax.servlet.http.HttpServletRequest req,
      javax.servlet.http.HttpServletResponse res,
      java.util.List path)`: Subclass should overload this if it let's us do the URL parsing.
- `void doPut (javax.servlet.http.HttpServletRequest req,
     javax.servlet.http.HttpServletResponse res)`:
- `void doPut (javax.servlet.http.HttpServletRequest req,
     javax.servlet.http.HttpServletResponse res,
     java.util.List path)`: Subclass should overload this if it let's us do the URL parsing.
- `protected java.lang.String[] getCredentials (javax.servlet.http.HttpServletRequest req)`: Return the credentials pulled from the request in a two-element String
 array with the first element being the username and the second element
 being the password.
- `java.util.List getListArgument (javax.servlet.http.HttpServletRequest req,
               java.lang.String name)`: Get a query argument and parse it as a string list.
- `java.lang.String getPath (java.util.List path,
       int index)`: Get a path element carefully to avoid exceptions,
 return null if invalid.
- `java.lang.String getPost (javax.servlet.http.HttpServletRequest req)`: Helper method called by doPost to get the post data as a string.
- `void init (javax.servlet.ServletConfig config)`:
- `java.util.List parseURL (javax.servlet.http.HttpServletRequest req)`: Convert a URL into a list of path elements.
- `protected abstract boolean performAuthentication (java.lang.String username,
                     java.lang.String password)`: Perform authentication for the given username and password.
- `void sendError (javax.servlet.http.HttpServletResponse response,
         java.lang.String msg)`: Send a 500 error.
- `void sendMethodNotAllowed (javax.servlet.http.HttpServletResponse response,
                    java.lang.String msg)`: Send a 405 error.
- `void sendResourceNotFound (javax.servlet.http.HttpServletResponse response,
                    java.lang.String msg)`: Send a 404 error.
- `static void sendResponse (javax.servlet.http.HttpServletResponse response,
            int status,
            java.lang.String msg)`: Send a response with the given status code and message.
- `static void sendResponse (javax.servlet.http.HttpServletResponse response,
            int status,
            java.lang.String msg,
            java.lang.String contentType)`: Send a response with the given status code, message and contentType.
- `static void sendResponse (javax.servlet.http.HttpServletResponse response,
            int status,
            java.lang.String msg,
            java.lang.String contentType,
            java.lang.String reason)`: Send a response with the given status code, message and contentType.
- `void sendResult (javax.servlet.http.HttpServletResponse response,
          java.lang.String msg)`: Send a 200 with the given message.
- `void sendSyntaxError (javax.servlet.http.HttpServletResponse response,
               java.lang.String msg)`: Send a 400 error.
- `void sendUnauthorized (javax.servlet.http.HttpServletResponse response,
                java.lang.String msg)`: Send a 401 error.
- `void service (javax.servlet.http.HttpServletRequest request,
       javax.servlet.http.HttpServletResponse response)`: Many browsers and HTTP clients do not support PUT and DELETE
 methods so simulate these with a request parameter.
- `protected boolean shouldAuthenticate (javax.servlet.http.HttpServletRequest req)`: Subclasses can override this method to disable authentication checks for
 certain requests.

---

## RoleDefinition
**Package:** `sailpoint.integration`

### Description
Class used to convey a role definition through the web-services interface
 to a provisioning system when we're doing role synchronization.

### Inheritance & Interfaces
```java
public classRoleDefinitionextends java.lang.Object
```

### Attributes
- `static java.lang.String ATT_ATTRIBUTES`:
- `static java.lang.String ATT_NAME`:
- `static java.lang.String ATT_REQUIRED_ROLES`: Resesrved name of an extended attribute that holds the
 list of required role names in the "dual" integration model.
- `static java.lang.String ATT_RESOURCES`:

### Methods
- `void add ( RoleResource res)`: Add a RoleResource to this role.
- `void fromMap (java.util.Map src)`:
- `java.lang.Object get (java.lang.String name)`: Return the request attribute for this role.
- `java.util.Map getAttributes ()`:
- `java.lang.String getName ()`:
- `RoleResource getResource (java.lang.String name)`: Return the RoleResource with the given name, if available.
- `java.util.List getResources ()`:
- `java.lang.String getString (java.lang.String name)`: Return the requested attribute as a string.
- `void put (java.lang.String name,
   java.lang.Object value)`: Set the given attribute for this role.
- `void setAttributes (java.util.Map atts)`: Set the attributes for this role.
- `void setName (java.lang.String s)`: Set the name of the role.
- `void setResources (java.util.List resources)`: Set the list of RoleResources.
- `java.util.Map toMap ()`:

---

## RoleEntitlement
**Package:** `sailpoint.integration`

### Description
Class used to convey a role definition through the web-services interface
 to a provisioning system when we're doing role synchronization.

 An entitlement is assumed to be a name/value pair where
 name is typically a multi-valued group or role membership
 attribute such as "memberOf".  Since this is usually used
 with multi-valued attribute the representation for the value
 will be an array.  If this is actually a single valued attribute
 convenience methods are provided to get and set the value
 from the first element of the array.

### Inheritance & Interfaces
```java
public classRoleEntitlementextends java.lang.Object
```

### Attributes
- `static java.lang.String ATT_NAME`:
- `static java.lang.String ATT_VALUES`:
- `static java.lang.String TYPE_PERMISSION`:

### Methods
- `void add (java.lang.String value)`: Add the given value to this entitlement.
- `void fromMap (java.util.Map src)`:
- `java.lang.String getName ()`:
- `java.lang.String getType ()`:
- `java.lang.String getValue ()`: Return a single value of this entitlement.
- `java.util.List getValues ()`:
- `boolean isPermission ()`:
- `void setName (java.lang.String s)`: Set the attribute name.
- `void setPermission (boolean b)`: Set whether this entitlement is a permission.
- `void setType (java.lang.String s)`: Set the attribute type - TYPE_PERMISSION if this is a permission.
- `void setValue (java.lang.String val)`: Set the value of this entitlement.
- `void setValues (java.util.List vals)`: Set the values for this attribute.
- `java.util.Map toMap ()`:

---

## RoleResource
**Package:** `sailpoint.integration`

### Description
Class used to convey a role definition through the web-services interface
 to a provisioning system when we're doing role synchronization.

### Inheritance & Interfaces
```java
public classRoleResourceextends java.lang.Object
```

### Attributes
- `static java.lang.String ATT_ENTITLEMENTS`:
- `static java.lang.String ATT_INSTANCE`:
- `static java.lang.String ATT_NAME`:

### Methods
- `void add ( RoleEntitlement ent)`: Add the given RoleEntitlement to this resource.
- `void fromMap (java.util.Map src)`:
- `RoleEntitlement get (java.lang.String name)`: Return the requested RoleEntitlement from this resource.
- `java.util.List getEntitlements ()`:
- `java.lang.String getInstance ()`:
- `java.lang.String getName ()`:
- `void setEntitlements (java.util.List ents)`: Set the RoleEntitlements on this resource.
- `void setInstance (java.lang.String s)`: Set the name of the resource instance.
- `void setName (java.lang.String s)`: Set the name of the resource.
- `java.util.Map toMap ()`:

---

## SailPointHttpClient.Cookie
**Package:** `sailpoint.integration`

### Description
Helper class containing information about cookies.

### Inheritance & Interfaces
```java
public static classSailPointHttpClient.Cookieextends java.lang.Object
```

### Attributes
No attributes.

### Methods
- `void dump ()`:
- `java.lang.String getDomain ()`:
- `java.lang.String getExpires ()`:
- `java.lang.String getName ()`:
- `java.lang.String getPath ()`:
- `java.lang.String getValue ()`:
- `boolean isSecure ()`:
- `void setDomain (java.lang.String s)`:
- `void setExpires (java.lang.String s)`:
- `void setName (java.lang.String s)`:
- `void setPath (java.lang.String s)`:
- `void setSecure (boolean b)`:
- `void setValue (java.lang.String s)`:

---

## SailPointHttpClient
**Package:** `sailpoint.integration`

### Description
A custom implementation of HttpClient.  By default we use the ApacheHttpClient .

### Inheritance & Interfaces
```java
public classSailPointHttpClientextends java.lang.Object
implementsHttpClient
```

### Attributes
- `int _MAX_WAIT`: The maximum amount of time we'll wait for an HTTP response
 in milliseconds.

### Methods
- `void addCookies (java.util.List cookies)`: Set the Cookies.
- `void addHeader (java.lang.String name,
         java.lang.String value)`: Adds a header entry
- `static int atoi (java.lang.String a)`: Utility method brought over from tools/Util.
- `void clearAuthentication ()`:
- `void clearCookies ()`: Clear all cookies.
- `void clearCookies (java.lang.String domain)`: Clear all cookies for a domain.
- `void clearSessionCookies ()`: Clear all session cookies.
- `void clearSessionCookies (java.lang.String domain)`: Clear all session cookies for a domain.
- `int delete (java.lang.String path)`: Do a delete.
- `int delete (java.lang.String url,
      java.util.Map headers)`: Perform HTTP DELETE with headers
- `int delete (java.lang.String url,
      java.util.Map headers,
      java.lang.String payLoad)`: Perform HTTP DELETE with headers and body
- `static java.util.List delimToList (java.lang.String delim,
           java.lang.String src,
           boolean filterEmpty)`: Utility method brought over from tools/Util.
- `void dumpCookies ()`: Debug method to dump all cookies.
- `void dumpHeaders ()`: Dump all headers.
- `java.lang.String encryptCredentials (java.lang.String name,
                  java.lang.String pass)`:
- `int get (java.lang.String path)`: Do a get.
- `int get (java.lang.String path,
   java.util.Map header)`: Do a get.Returns the status code.
- `java.lang.String getBody ()`: Return the last response body as a string.
- `byte[] getBodyBytes ()`: Return the last response body.
- `java.lang.String getCookie (java.lang.String domain,
         java.lang.String name)`: Obtain a cookie value
- `SailPointHttpClient.Cookie getCookieObject (java.lang.String domain,
               java.lang.String name)`: Obtain a cookie object.
- `java.util.List getCookies ()`: Return the Cookies.
- `java.util.Map getCookies (java.lang.String domain)`: Get all the cookies in a domain.
- `java.lang.String getDomain (java.lang.String host)`: Given a fully qualified hostname, extract the domain name.
- `java.lang.Object getHeader (java.lang.String name)`: Return a response header.
- `java.util.Map getHeaders ()`: Returns a Map containing header name-value pairs.
- `java.util.Map getResponseHeaders ()`: Returns the response headers of the last resquest execution.
- `java.lang.String getSingleHeader (java.lang.String name)`: Return a response header, expected to have a single value.
- `int getStatus ()`: Return the last response status code.
- `static java.lang.String itoa (int i)`: Utility method brought over from tools/Util.
- `int patch (java.lang.String path,
     java.lang.String data)`: Do a patch.
- `int patch (java.lang.String path,
     java.lang.String data,
     java.util.Map header)`: Perform an HTTP PATCH to the given URL using the given data in the body.
- `int patch (java.lang.String url,
     java.util.Map headers,
     java.util.Map parameters)`: Perform URLEncoded HTTP PATCH operation.
- `int post (java.lang.String path,
    java.lang.String data)`: Do a post.
- `int post (java.lang.String path,
    java.lang.String data,
    java.util.Map header)`: Perform HTTP POST with headers
- `int post (java.lang.String path,
    java.util.Map data)`: Perform an HTTP POST to the given URL serializing the given parameters
 into the post body.
- `int post (java.lang.String url,
    java.util.Map headers,
    java.util.Map parameters)`: Perform URLEncoded HTTP POST operation.
- `static void println (java.lang.String msg)`:
- `int put (java.lang.String path,
   java.lang.String data)`: Do a put.
- `int put (java.lang.String path,
   java.lang.String data,
   java.util.Map header)`: Perform an HTTP PUT to the given URL using the given data in the body.
- `int put (java.lang.String url,
   java.util.Map headers,
   java.util.Map parameters)`: Perform URLEncoded HTTP PUT operation.
- `void reset ()`: Called by tests when they want to simulate the effect
 of killing the browser and starting a new one.
- `void setAuthentication (java.lang.String name,
                 java.lang.String password)`:
- `void setCookie (java.lang.String domain,
         java.lang.String name,
         java.lang.String value)`: Set the value of a cookie.
- `void setCookie ( SailPointHttpClient.Cookie c)`: Add a cookie object.
- `void setFollowRedirects (boolean b)`: Control whether we automatically follow redirects.
- `void setHeaders (java.util.Map headers)`: Sets headers supplied in the argument
- `void setMaxWait (int milliseconds)`:
- `void setSimulateIE (boolean b)`:
- `void setTrace (boolean b)`:
- `void setup (boolean useSSL,
     int port,
     java.lang.String username,
     java.lang.String password,
     java.lang.String timeoutInSeconds,
     java.util.Map options)`: Setup the client.
- `void setup (boolean useSSL,
     int port,
     java.lang.String username,
     java.lang.String password,
     java.lang.String timeoutInSeconds,
     java.util.Map options,
     java.lang.String sslProtocol)`: As existing setup method throws an UnsupportedOperationException if
 useSSL is true.So this method will not provide support for custom
 sslProtocol configuration.

---

## TraceExecutor
**Package:** `sailpoint.integration`

### Description
Implementation of IntegrationExecutor interface used for system testing.
 This prints information to stdout and keeps role and provisioning information
 in memory.

### Inheritance & Interfaces
```java
public classTraceExecutorextends sailpoint.integration.AbstractIntegrationExecutor
```

### Attributes
- `static java.lang.String ARG_SIMULATE_ERROR`: Special argument passed in ProvisioningPlan's integration data
 map to simulate errors for testing.

### Methods
- `RequestResult addRole ( RoleDefinition def)`: Create or update the definition of a role.
- `void configure (java.util.Map args)`: Configure this integration - this is a no-op.
- `RequestResult deleteRole (java.lang.String name)`: Delete a role.
- `void finishRoleDefinition ( Bundle src, RoleDefinition dest)`: Print a message to stdout saying that the role is finished.
- `static java.util.List< ProvisioningPlan > getProvisions ()`: Return the ProvisioningPlans that have been added through provision(String, ProvisioningPlan) .
- `static java.util.List< RoleDefinition > getRoles ()`: Return the RoleDefinitions that have been added through addRole(RoleDefinition) .
- `java.lang.String jsonify (java.util.Map map)`: Convert the given Map to a JSON string.
- `java.lang.String jsonify ( ProvisioningPlan plan)`: Convert the given ProvisioningPlan to a JSON string.
- `java.lang.String jsonify ( RoleDefinition def)`: Convert the given RoleDefinition to a JSON string.
- `java.util.List listRoles ()`: Return the current list of "manageable" roles.
- `java.lang.String ping ()`: Print a message and return a successful ping response.
- `static void println (java.lang.Object o)`: Print the given object to stdout.
- `RequestResult provision (java.lang.String identity, ProvisioningPlan plan)`: Make changes to an identity defined by a ProvisioningPlan.
- `ProvisioningResult provision ( ProvisioningPlan plan)`: Override to handle non-identity plans (i.e.
- `static void reset ()`: Clear the RoleDefinitions and ProvisioningPlans that are stored in memory.

---

## Util
**Package:** `sailpoint.integration`

### Description
Various utilities copied over from the sailpoint.tools package.

### Inheritance & Interfaces
```java
public classUtilextends java.lang.Object
```

### Attributes
No attributes.

### Methods
- `static java.util.List asList (java.lang.Object o)`: Return a List with the given object.
- `static boolean atob (java.lang.String a)`: Convert a string to a boolean.
- `static float atof (java.lang.String a)`: Convert a string to a float.
- `static int atoi (java.lang.String a)`: Convert a String value into a primitive integer value.
- `static int atoi (java.lang.String a,
    int def)`: Convert a String value into a primitive integer value.
- `static long atol (java.lang.String a)`: Convert a string to a long.
- `static java.lang.String compressWhiteSpace (java.lang.String str)`: This method strips leading and trailing whitespace and guarantees that there is
 at most one space between characters in the output.
- `static java.lang.String deleteWhitespace (java.lang.String src)`: Deletes any whitespace from the string
- `static boolean getBoolean (java.util.Map map,
          java.lang.String name)`: Return a map value as a boolean.
- `static java.lang.String getHostName ()`: Return the host name of this JVM.
- `static java.lang.String getString (java.lang.String s)`: Return the given String or null (if the given String is null or
 zero-length).
- `static java.lang.String getString (java.util.Map map,
         java.lang.String name)`: Return a map value as a string.
- `static boolean isEmpty (java.util.Collection collection)`: Return whether the given Collection is empty.
- `static boolean isEmpty (java.util.Map map)`: Return whether the given Map is empty.
- `static boolean isExpired (java.util.Date date)`:
- `static boolean isNotNullOrEmpty (java.lang.String str)`: Negative of isNullOrEmpty
 Its simply there for easier to read code.
- `static boolean isNullOrEmpty (java.lang.String str)`: Check String for null or Empty.
- `static java.lang.String limit (java.lang.String src,
     int max)`: Utility to limit a string to the maximum allowed in the event.
- `static int nullSafeCompareTo (java.lang.String o1,
                 java.lang.String o2)`: Compare two objects that may be null.
- `static boolean nullSafeEq (java.lang.Object o1,
          java.lang.Object o2)`: This method performs a null-safe equality comparison between the two
 given objects.
- `static boolean nullSafeEq (java.lang.Object o1,
          java.lang.Object o2,
          boolean nullsEq)`: This method performs a null-safe equality comparison between the two
 given objects.
- `static java.lang.String otoa (java.lang.Object o)`: Convert an object to a String.
- `static boolean otob (java.lang.Object o)`: Convert an object to a boolean.
- `static java.lang.String preparePayloadJson (java.lang.Object payload)`: Parses the payload object and returns an equivalent JSON
 representation.
- `static int rand (int low,
    int high)`: Generate a random number between a low a high value inclusive.
- `static int size (java.util.Collection c)`: Return the size of the given collection.
- `static void sleep (int millis)`: Pause for reflection, catching the usual silly exception.
- `static java.lang.String trimWhitespace (java.lang.String src)`: Trims trailing whitespace from a string.
- `static java.lang.String uuid ()`: Generate a unique identifier.

---

## ValidationContext
**Package:** `sailpoint.integration`

### Description
This class is used by the JWT validation process. It will keep track of any errors and the user that is identified
 by the claim.

### Inheritance & Interfaces
```java
public classValidationContextextends java.lang.Object
```

### Attributes
No attributes.

### Methods
- `java.lang.String[] getErrors ()`:
- `Identity getUser ()`:
- `boolean hasErrors ()`:

---

## XmlUtil.SailPointEntityResolver
**Package:** `sailpoint.integration`

### Description
Custom entity resolver that handles different locations.

### Inheritance & Interfaces
```java
public static classXmlUtil.SailPointEntityResolverextends java.lang.Object
implements org.xml.sax.EntityResolver
```

### Attributes
No attributes.

### Methods
- `org.xml.sax.InputSource resolveEntity (java.lang.String pubid,
             java.lang.String sysid)`: Attempt to resolve an entity reference to a resource stream.

---

## XmlUtil.SailPointErrorHandler
**Package:** `sailpoint.integration`

### Description
Custom error handler that just throws exceptions.

### Inheritance & Interfaces
```java
public static classXmlUtil.SailPointErrorHandlerextends java.lang.Object
implements org.xml.sax.ErrorHandler
```

### Attributes
No attributes.

### Methods
- `void error (org.xml.sax.SAXParseException e)`:
- `void fatalError (org.xml.sax.SAXParseException e)`:
- `void warning (org.xml.sax.SAXParseException e)`:

---

## XmlUtil
**Package:** `sailpoint.integration`

### Description
Utilities for creating and parsing XML.

### Inheritance & Interfaces
```java
public classXmlUtilextends java.lang.Object
```

### Attributes
- `static char DOUBLE_QUOTE`:
- `static char SINGLE_QUOTE`:

### Methods
- `static void addAttribute (java.lang.StringBuilder b,
            java.lang.String name,
            java.lang.String value)`: Adds an attribute name and value to a string buffer.
- `static void addContent (java.lang.StringBuilder b,
          java.lang.Object o)`: Replaces special characters in a string with XML character entities.
- `static void escapeAttribute (java.io.Writer f,
               java.lang.String s)`: Variant for Writers.
- `static java.lang.String escapeAttribute (java.lang.String s)`: Escape the given attribute.
- `static void escapeAttribute (java.lang.StringBuilder b,
               java.lang.String s)`: Escape the given attribute and store it in the given StringBuffer.
- `static void escapeContent (java.io.Writer f,
             java.lang.String s)`: Escape the given element content and stream it to a Writer.
- `static java.lang.String escapeContent (java.lang.String s)`: Escape the given element content.
- `static void escapeContent (java.lang.StringBuilder b,
             java.lang.String s)`: Differs from escapeAttribute in that we don't escape quotes.
- `static org.w3c.dom.Text findText (org.w3c.dom.Node node,
        boolean ignoreEmpty)`: Search for the first Text node beneath a node.
- `static java.lang.String getAttribute (org.w3c.dom.Element e,
            java.lang.String name)`: Get an attribute, collapsing empty strings to null.
- `static org.w3c.dom.Element getChildElement (org.w3c.dom.Node node)`: Dig out the first child element under a node.
- `static org.w3c.dom.Element getChildElement (org.w3c.dom.Node node,
               java.lang.String elementName)`: Dig out the child element with the given name under a node.
- `static java.lang.String getContent (org.w3c.dom.Element e)`: Return the content of an element as a string.
- `static org.w3c.dom.Element getNextElement (org.w3c.dom.Node node)`: Get the next right sibling that is an element.
- `static boolean isXmlChar (char ch)`: Return whether the given character is an XML char.
- `static org.w3c.dom.Element parseOld (java.lang.String xml,
        java.lang.String dtd,
        boolean validating)`: Parse an XML string and return the document element.
- `static void serialize (java.lang.StringBuilder b,
         org.w3c.dom.Node node)`: Serialize the given Node into the given StringBuilder.
- `static java.lang.String stripInvalidXml (java.lang.String s)`:
- `static java.lang.String unescapeAttribute (java.lang.String s)`: Unescape an XML attribute - this is the inverse of escapeAttribute().

---

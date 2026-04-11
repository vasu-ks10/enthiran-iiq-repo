# sailpoint.tools API Reference

## Interface CloseableIterator<E>
**Package:** `sailpoint.tools`

### Description
Similar to the Iterator interface, but  with an additional close() method that can clean  up resources when the iteration is complete. This also  does not have a remove() method.

### Declaration
```java
public interface CloseableIterator<E>
```

### Attributes
No attributes.

### Methods
- `void close()`
- `boolean hasNext()`
- `E next()`

---

## Class EmailException
**Package:** `sailpoint.tools`

### Description
An exception for errors sending emails.

### Declaration
```java
public class EmailException extends GeneralException
```

### Attributes
No attributes.

### Methods
- `java.lang.String getLocalizedMessage()`
- `java.lang.String getLocalizedMessage​(java.util.Locale locale,                    java.util.TimeZone timezone)`
- `java.lang.String getMessage()`
- `java.lang.String getRecipient()`

---

## Class GeneralException
**Package:** `sailpoint.tools`

### Description
The base exception thrown by most IdentityIQ classes.

### Declaration
```java
public class GeneralException extends sailpoint.tools.AbstractLocalizableException
```

### Attributes
No attributes.

### Methods
- `void breakpoint()`
- `void checkBreakpoint()`
- `static void enableBreakpoint​(boolean b)`

---

## Interface JdbcUtil.ClobHandler
**Package:** `sailpoint.tools`

### Description
Simple interface so the Oracle dependencies can be wrapped in a   class that can be called by name.

### Declaration
```java
public static interface JdbcUtil.ClobHandler
```

### Attributes
No attributes.

### Methods
- `void free​(java.lang.Object lob)`
- `java.lang.Object setClobParameter​(java.sql.PreparedStatement ps,                 int pos,                 java.lang.String value)`

---

## Enum JdbcUtil.ConnectorType
**Package:** `sailpoint.tools`

### Description
No description available.

### Declaration
```java
public static enum JdbcUtil.ConnectorType extends java.lang.Enum<JdbcUtil.ConnectorType>
```

### Attributes
No attributes.

### Methods
- `static JdbcUtil.ConnectorType valueOf​(java.lang.String name)`
- `static JdbcUtil.ConnectorType[] values()`

---

## Class JdbcUtil
**Package:** `sailpoint.tools`

### Description
Various JDBC utilities.

### Declaration
```java
public class JdbcUtil extends java.lang.Object
```

### Attributes
- `static java.lang.String ARG_ARG1`
- `static java.lang.String ARG_ARG2`
- `static java.lang.String ARG_ARG3`
- `static java.lang.String ARG_CON_PROPERTIES`
- `static java.lang.String ARG_DATABASE`
- `static java.lang.String ARG_DRIVER_CLASS`
- `static java.lang.String ARG_DRIVER_PREFIX`
- `static java.lang.String ARG_HOST`
- `static java.lang.String ARG_PASSWORD`
- `static java.lang.String ARG_POOL_DISABLE`
- `static java.lang.String ARG_POOL_DISABLE_AUTO_COMMIT`
- `static java.lang.String ARG_POOL_EVICT_IDLE`
- `static java.lang.String ARG_POOL_EVICT_RUNS`
- `static java.lang.String ARG_POOL_MAX_ACTIVE`
- `static java.lang.String ARG_POOL_MAX_IDLE`
- `static java.lang.String ARG_POOL_MAX_TOTAL`
- `static java.lang.String ARG_POOL_MAX_WAIT`
- `static java.lang.String ARG_PORT`
- `static java.lang.String ARG_SQL`
- `static java.lang.String ARG_TYPE`
- `static java.lang.String ARG_URL`
- `static java.lang.String ARG_USER`
- `static java.lang.String DB2_EXT`
- `static java.lang.String DB2_PRODUCT_NAME`
- `static java.lang.String MS_SQL_PRODUCT_NAME`
- `static java.lang.String MSSQL_EXT`
- `static java.lang.String MYSQL_EXT`
- `static java.lang.String MYSQL_PRODUCT_NAME`
- `static java.lang.String ORACLE_CLOB_HANDLER`
- `static java.lang.String ORACLE_DRIVER`
- `static java.lang.String ORACLE_EXT`
- `static java.lang.String ORACLE_PREFIX`
- `static java.lang.String ORACLE_PRODUCT_NAME`
- `static java.lang.String ORACLE_URL`
- `static java.lang.String POSTGRESQL_EXT`
- `static java.lang.String POSTGRESQL_PRODUCT_NAME`
- `static java.lang.String TYPE_ORACLE`

### Methods
- `static void clearDataSource​(java.lang.String user,                java.lang.String url)`
- `static void clearDataSources()`
- `static void closeConnection​(java.sql.Connection con)`
- `static void closeResult​(java.sql.ResultSet res)`
- `static void closeStatement​(java.sql.Statement stmt)`
- `static void dumpArguments​(java.lang.String method,              java.util.Map map)`
- `static java.lang.String escapeSpecialCharactor​(java.lang.String name,                       JdbcUtil.ConnectorType type)`
- `static java.lang.String formatUrl​(java.lang.String template,          java.lang.String host,          java.lang.String port,          java.lang.String database)`
- `static java.lang.String getClobValue​(java.sql.Clob clob)`
- `static java.lang.String getClobValue​(java.sql.ResultSet rs,             java.lang.String name)`
- `static int getColumnLength​(java.sql.Connection connection,                java.lang.String tableName,                java.lang.String columnName)`
- `static java.sql.Connection getConnection​(java.lang.String driverClass,              java.lang.String driverPrefix,              java.lang.String url,              java.lang.String user,              java.lang.String password)`
- `static java.sql.Connection getConnection​(java.lang.String driverClass,              java.lang.String driverPrefix,              java.lang.String url,              java.lang.String user,              java.lang.String password,              java.util.Properties additionalProperties)`
- `static java.sql.Connection getConnection​(java.util.Map args)`
- `static javax.sql.DataSource getDataSourceObject​(java.lang.String factoryClass,                    java.lang.String path)`
- `static javax.sql.DataSource getDataSourceObject​(java.lang.String factoryClass,                    java.lang.String path,                    java.lang.String providerUrl)`
- `static javax.sql.DataSource getDataSourceObject​(java.lang.String factoryClass,                    java.lang.String path,                    java.util.Properties props)`
- `static java.lang.String getScriptExtensionForDatabase​(java.sql.Connection connection)`
- `static boolean isDriverRegistered​(java.lang.String driverClass)`
- `static boolean isMySQL​(java.sql.Connection connection)`
- `static boolean isOracle​(java.sql.Connection connection)`
- `static boolean isOracle​(java.sql.PreparedStatement ps)`
- `static void populateUnwantedSymbolList()`
- `static java.sql.Clob queryClob​(java.sql.Connection c,          java.lang.String q,          java.lang.String arg)`
- `static java.lang.String queryClobString​(java.sql.Connection c,                java.lang.String q,                java.lang.String arg)`
- `static java.util.Date queryDate​(java.sql.Connection c,          java.lang.String q,          java.lang.String arg)`
- `static int queryInt​(java.sql.Connection c,         java.lang.String q,         java.lang.String arg)`
- `static java.util.List queryList​(java.sql.Connection c,          java.lang.String q,          java.lang.String arg)`
- `static java.util.List queryList​(java.util.Map args)`
- `static java.lang.String queryString​(java.sql.Connection c,            java.lang.String q,            java.lang.String arg)`
- `static java.lang.String queryString​(java.util.Map args)`
- `static java.util.List queryTable​(java.sql.Connection c,           java.lang.String q,           java.lang.String arg,           int cols)`
- `static java.util.List queryTableString​(java.sql.Connection c,                 java.lang.String q,                 java.lang.String arg,                 int cols)`
- `static void registerDriver​(java.lang.String driverClass,               java.lang.String prefix)`
- `static java.sql.PreparedStatement setClobParameter​(java.sql.PreparedStatement ps,                 int pos,                 java.lang.String value)`
- `static java.lang.Object setOracleCLOBParameter​(java.sql.PreparedStatement st,                       int index,                       java.lang.String val)`
- `static void sql​(java.sql.Connection c,    java.lang.String stmt,    java.lang.String... arg)`
- `static void sql​(java.util.Map args)`
- `static void sqlStream​(java.sql.Connection c,          java.lang.String stmt,          java.io.InputStream arg,          int len)`
- `static int update​(java.sql.Connection c,       java.lang.String stmt,       java.lang.String arg)`
- `static int update​(java.sql.PreparedStatement s)`
- `static int updateLong​(java.sql.Connection c,           java.lang.String stmt,           java.lang.String arg)`
- `static java.lang.String useQuoteForScripts​(java.lang.String val,                   java.lang.String quoteForCaseInsensitveDatabase,                   java.lang.String quoteForCaseSensitiveDatabase,                   boolean caseSensitive)`

---

## Enum JsonHelper.JsonOptions
**Package:** `sailpoint.tools`

### Description
No description available.

### Declaration
```java
public static enum JsonHelper.JsonOptions extends java.lang.Enum<JsonHelper.JsonOptions>
```

### Attributes
No attributes.

### Methods
- `static JsonHelper.JsonOptions valueOf​(java.lang.String name)`
- `static JsonHelper.JsonOptions[] values()`

---

## Class JsonHelper
**Package:** `sailpoint.tools`

### Description
A utility class that helps to format various JSON responses.

### Declaration
```java
public class JsonHelper extends java.lang.Object
```

### Attributes
- `static JsonHelper.JsonOptions[] ALL_OPTIONS`
- `static JsonHelper.JsonOptions[] CLEANSE`
- `static JsonHelper.JsonOptions[] PRETTY_NONULLS`

### Methods
- `static java.lang.String buildObjectString​(com.fasterxml.jackson.databind.JsonNode node)`
- `static java.lang.String buildObjectString​(com.fasterxml.jackson.databind.node.ArrayNode aNode)`
- `static java.lang.String buildObjectString​(com.fasterxml.jackson.databind.node.ObjectNode oNode)`
- `static java.lang.String cleanseJson​(java.lang.String json,            boolean prettyPrint)`
- `static java.lang.String computeDiff​(java.lang.String earlierJson,            java.lang.String laterJson)`
- `static java.lang.String computeDiff​(java.lang.String earlierJson,            java.lang.String laterJson,            boolean pretty)`
- `static java.lang.String emptyList()`
- `static java.lang.String emptyListResult​(java.lang.String countProp,                java.lang.String objectsProp)`
- `static java.lang.String emptyObject()`
- `static java.lang.String failure()`
- `static java.lang.String failure​(java.lang.String errorMsg)`
- `static java.lang.String failure​(java.lang.String errorMsg,        java.lang.String error)`
- `static java.util.List<com.fasterxml.jackson.databind.JsonNode> findJsonArrayItems​(com.fasterxml.jackson.databind.JsonNode rootJsonNode,                   java.lang.String propPath,                   java.lang.String propName,                   java.lang.String expectedPropValue)`
- `static com.fasterxml.jackson.databind.JsonNode findJsonNode​(com.fasterxml.jackson.databind.JsonNode rootJsonNode,             java.lang.String propPath)`
- `static java.util.Map<java.lang.String,​java.lang.String> findJsonProperties​(java.lang.String jsonStr,                   java.util.Map<java.lang.String,​java.lang.String> propPathMap)`
- `static java.lang.String findJsonProperty​(com.fasterxml.jackson.databind.JsonNode rootJsonNode,                 java.lang.String propPath)`
- `static java.lang.String findJsonProperty​(java.lang.String jsonStr,                 java.lang.String propPath)`
- `static java.lang.Boolean findJsonPropertyAsBoolean​(com.fasterxml.jackson.databind.JsonNode rootJsonNode,                          java.lang.String propPath)`
- `static boolean findJsonPropertyAsBoolean​(com.fasterxml.jackson.databind.JsonNode rootJsonNode,                          java.lang.String propPath,                          boolean defaultValue)`
- `static java.lang.Boolean findJsonPropertyAsBoolean​(java.lang.String rootJson,                          java.lang.String propPath)`
- `static java.lang.Boolean findJsonPropertyAsBoolean​(java.lang.String rootJson,                          java.lang.String propPath,                          boolean defaultValue)`
- `static java.util.Date findJsonPropertyAsDate​(com.fasterxml.jackson.databind.JsonNode rootJsonNode,                       java.lang.String propPath)`
- `static java.util.Date findJsonPropertyAsDate​(java.lang.String rootJson,                       java.lang.String propPath)`
- `static java.lang.Double findJsonPropertyAsDouble​(com.fasterxml.jackson.databind.JsonNode rootJsonNode,                         java.lang.String propPath)`
- `static java.lang.Double findJsonPropertyAsDouble​(java.lang.String rootJson,                         java.lang.String propPath)`
- `static java.lang.Integer findJsonPropertyAsInteger​(com.fasterxml.jackson.databind.JsonNode rootJsonNode,                          java.lang.String propPath)`
- `static java.lang.Integer findJsonPropertyAsInteger​(java.lang.String rootJson,                          java.lang.String propPath)`
- `static java.lang.Long findJsonPropertyAsLong​(com.fasterxml.jackson.databind.JsonNode rootJsonNode,                       java.lang.String propPath)`
- `static java.lang.Long findJsonPropertyAsLong​(java.lang.String rootJson,                       java.lang.String propPath)`
- `static java.lang.String findJsonPropertyAsString​(com.fasterxml.jackson.databind.JsonNode rootJsonNode,                         java.lang.String propPath)`
- `static java.lang.String findJsonPropertyAsString​(java.lang.String rootJson,                         java.lang.String propPath)`
- `static <T> T fromJson​(java.lang.Class<T> objectType,         java.lang.String json)`
- `static java.util.Map<java.lang.String,​java.util.Map> fromXmlFileToJson​(java.lang.String filePath)`
- `static java.util.Map<java.lang.String,​java.util.Map> fromXmlStringToJson​(java.lang.String xmlString)`
- `static com.fasterxml.jackson.databind.JsonNode getJsonNode​(java.lang.String jsonStr)`
- `static com.fasterxml.jackson.databind.ObjectMapper getObjectMapper​(JsonHelper.JsonOptions... options)`
- `static com.fasterxml.jackson.databind.ObjectMapper getObjectMapperNoEscapes​(JsonHelper.JsonOptions... options)`
- `static com.fasterxml.jackson.databind.ObjectMapper getObjectMapperWebSafe​(JsonHelper.JsonOptions... options)`
- `static com.fasterxml.jackson.databind.ObjectMapper getXmlMapper()`
- `static boolean isJsonArray​(java.lang.Object obj)`
- `static boolean isJsonArray​(java.lang.String jsonStr)`
- `static boolean isJsonNodesEqual​(com.fasterxml.jackson.databind.JsonNode node1,                 com.fasterxml.jackson.databind.JsonNode node2)`
- `static boolean isJsonNodesEqual​(java.lang.String jsonStr1,                 java.lang.String jsonStr2)`
- `static boolean isJsonObject​(java.lang.Object obj)`
- `static boolean isJsonObject​(java.lang.String jsonStr)`
- `static boolean isScalar​(com.fasterxml.jackson.databind.JsonNode node)`
- `static boolean isValid​(java.lang.String jsonStr)`
- `static java.lang.String keyValuesToJson​(JsonHelper.JsonOptions[] options,                java.lang.Object... keyValues)`
- `static java.lang.String keyValuesToJsonNoEscapes​(JsonHelper.JsonOptions[] options,                         java.lang.Object... keyValues)`
- `static <T> java.util.List<T> listFromJson​(java.lang.Class<T> objectType,             java.lang.String json)`
- `static <S,​T>java.util.List<java.util.Map<S,​T>> listOfMapsFromJson​(java.lang.Class<S> keyType,                   java.lang.Class<T> valueType,                   java.lang.String json)`
- `static java.lang.String makePretty​(java.lang.String json)`
- `static java.lang.String makePrettyNoEscapes​(java.lang.String json)`
- `static java.lang.String makeUnpretty​(java.lang.String json,             JsonHelper.JsonOptions... options)`
- `static <S,​T>java.util.Map<S,​T> mapFromJson​(java.lang.Class<S> keyType,            java.lang.Class<T> valueType,            java.lang.String json)`
- `static java.lang.String patchDocReplay​(java.lang.String jsonStr,               java.lang.String... patchDocs)`
- `static java.lang.String success()`
- `static java.lang.String success​(java.lang.Object... keyValues)`
- `static java.lang.String success​(java.util.Map<java.lang.String,​java.lang.Object> attrs)`
- `static java.lang.String toJson​(java.lang.Object o,       JsonHelper.JsonOptions... options)`
- `static java.lang.String toJsonNoEscapes​(java.lang.Object o,                JsonHelper.JsonOptions... options)`
- `static java.lang.String toJsonWebSafe​(java.lang.Object o,              JsonHelper.JsonOptions... options)`
- `static java.lang.String updateJsonProperty​(java.lang.String jsonString,                   sailpoint.tools.Pair<java.lang.String,​java.lang.Object>... pathValuePairs)`

---

## Enum Message.Type
**Package:** `sailpoint.tools`

### Description
Type or severity of the message.

### Declaration
```java
public static enum Message.Type extends java.lang.Enum<Message.Type>
```

### Attributes
No attributes.

### Methods
- `static Message.Type valueOf​(java.lang.String name)`
- `static Message.Type[] values()`

---

## Class Message
**Package:** `sailpoint.tools`

### Description
A class containing all the elements needed to generate localized message text,  including the key of the message and any parameters which should be injected  into the message string.

### Declaration
```java
public class Message extends AbstractXmlObject implements sailpoint.tools.Localizable, java.io.Serializable, openconnector.OpenMessagePart
```

### Attributes
No attributes.

### Methods
- `boolean equals​(java.lang.Object other)`
- `static Message error​(java.lang.String key,      java.lang.Object... args)`
- `protected java.lang.String getBundleMessage​(java.lang.String key,                 java.util.Locale locale)`
- `java.lang.String getKey()`
- `java.lang.String getLocalizedMessage()`
- `java.lang.String getLocalizedMessage​(java.util.Locale locale,                    java.util.TimeZone timezone)`
- `java.lang.String getLocalizedMessage​(java.util.Locale locale,                    java.util.TimeZone timezone,                    boolean escapeParams)`
- `java.lang.Integer getMaxLength()`
- `java.lang.String getMessage()`
- `java.util.List<java.lang.Object> getParameters()`
- `Message.Type getType()`
- `static Message info​(java.lang.String key,     java.lang.Object... args)`
- `boolean isError()`
- `boolean isPlainText()`
- `boolean isType​(Message.Type theType)`
- `boolean isWarning()`
- `static Message localize​(java.lang.String key)`
- `static Message localize​(java.lang.String key,         java.lang.Object[] arguments)`
- `void setKey​(java.lang.String key)`
- `void setMaxLength​(java.lang.Integer maxLength)`
- `void setParameters​(java.util.List<java.lang.Object> parameters)`
- `void setType​(Message.Type type)`
- `java.lang.String toString()`
- `static Message warn​(java.lang.String key,     java.lang.Object... args)`

---

## Interface Util.IConverter<T1,​T2>
**Package:** `sailpoint.tools`

### Description
No description available.

### Declaration
```java
public static interface Util.IConverter<T1,​T2>
```

### Attributes
No attributes.

### Methods
- `T2 convert​(T1 t1)`

---

## Interface Util.IMatcher<T>
**Package:** `sailpoint.tools`

### Description
No description available.

### Declaration
```java
public static interface Util.IMatcher<T>
```

### Attributes
No attributes.

### Methods
- `boolean isMatch​(T val)`

---

## Interface Util.ListElementWrapper<T>
**Package:** `sailpoint.tools`

### Description
A ListElementWrapper is responsible for wrapping (or transforming) each  element of a List when the element is retrieved from the list.

### Declaration
```java
public static interface Util.ListElementWrapper<T>
```

### Attributes
No attributes.

### Methods
- `T wrap​(T element)`

---

## Interface Util.ListFilter<T>
**Package:** `sailpoint.tools`

### Description
Interface that is used with filter(List, ListFilter) to specify  which elements should not be included in the filtered list.

### Declaration
```java
public static interface Util.ListFilter<T>
```

### Attributes
No attributes.

### Methods
- `boolean removeFromList​(T o)`

---

## Class Util.ParseException
**Package:** `sailpoint.tools`

### Description
A runtime exception that is thrown when decoding fails.

### Declaration
```java
public static class Util.ParseException extends java.lang.RuntimeException
```

### Attributes
No attributes.

### Methods
No methods.

---

## Class Util
**Package:** `sailpoint.tools`

### Description
Various utilities.

### Declaration
```java
public class Util extends java.lang.Object
```

### Attributes
- `static java.lang.String APPLICATION_HOME`
- `static long MILLI_IN_DAY`
- `static long MILLI_IN_HOUR`
- `static long MILLI_IN_MINUTE`
- `static long MILLI_IN_MONTH`
- `static long MILLI_IN_SECOND`
- `static long MILLI_IN_WEEK`
- `static long MILLI_IN_YEAR`
- `static long MILLIS_PER_DAY`

### Methods
- `static boolean areUrlsEqual​(java.lang.String source,             java.lang.String destination)`
- `static <T> java.util.List<T> arrayToList​(T[] array)`
- `static java.util.List asList​(java.lang.Object o)`
- `static boolean atob​(java.lang.String a)`
- `static float atof​(java.lang.String a)`
- `static int atoi​(java.lang.String a)`
- `static int atoi​(java.lang.String a,     int def)`
- `static long atol​(java.lang.String a)`
- `static java.util.Date baselineDate​(java.util.Date src)`
- `static java.util.Date baselineDate​(java.util.Date src,             java.util.TimeZone timeZone)`
- `static java.lang.String bytesToString​(byte[] bytes)`
- `static java.lang.String capitalize​(java.lang.String str)`
- `static java.lang.String capitalizeAndNormalize​(java.lang.String str)`
- `static <T> T caseInsensitiveKeyValue​(java.util.Map<java.lang.String,​T> map,                        java.lang.String key)`
- `static java.lang.String compressWhiteSpace​(java.lang.String str)`
- `static java.lang.String computeDifference​(java.util.Date start,                  java.util.Date end)`
- `static long computeDifferenceMilli​(java.util.Date start,                       java.util.Date end)`
- `static boolean containsAny​(java.util.Collection c1,            java.util.Collection c2)`
- `static <T extends java.lang.Comparable<? super T>>boolean containsComparable​(java.util.List<T> list,                   T toFind,                   boolean sorted)`
- `static <T1,​T2>java.util.List<T2> convert​(java.util.List<T1> list1,        Util.IConverter<T1,​T2> converter)`
- `static java.lang.Integer[] convertDecimalToBinary​(java.lang.String value)`
- `static java.lang.Object convertValue​(java.lang.Class clazz,             java.lang.String property,             java.lang.Object valueObject)`
- `static void copyFile​(java.lang.String src,         java.lang.String dest)`
- `static int countChars​(java.lang.String sourceString,           char lookFor)`
- `static java.lang.Object createObjectByClassName​(java.lang.String name)`
- `static java.lang.String[] csvToArray​(java.lang.String src)`
- `static java.util.List<java.lang.String> csvToList​(java.lang.String src)`
- `static java.util.List<java.lang.String> csvToList​(java.lang.String src,          boolean filterEmpty)`
- `static java.util.Set<java.lang.String> csvToSet​(java.lang.String src,         boolean filterEmpty)`
- `static java.util.Date dateBetween​(java.util.Date startDate,            java.util.Date endDate)`
- `static java.lang.String dateToString​(java.util.Date src)`
- `static java.lang.String dateToString​(java.util.Date src,             java.lang.Integer dateFormat,             java.lang.Integer timeFormat)`
- `static java.lang.String dateToString​(java.util.Date src,             java.lang.Integer dateFormat,             java.lang.Integer timeFormat,             java.util.TimeZone timeZone,             java.util.Locale locale)`
- `static java.lang.String dateToString​(java.util.Date src,             java.lang.String format)`
- `static java.lang.String dateToString​(java.util.Date src,             java.lang.String format,             java.util.TimeZone tz)`
- `static java.lang.String decodeJavaIdentifier​(java.lang.String s)`
- `static java.lang.String deleteWhitespace​(java.lang.String src)`
- `static java.util.List<java.lang.String> delimToList​(java.lang.String delim,            java.lang.String src,            boolean filterEmpty)`
- `static void disableSQLTrace()`
- `static boolean doesUrlStartWith​(java.lang.String urlToCheck,                 java.lang.String urlPrefix)`
- `static long dottedQuadToLong​(java.lang.String ipaddr)`
- `static void dumpProperties()`
- `static void dumpProperties​(java.io.PrintWriter out)`
- `static java.lang.String durationToString​(int duration)`
- `static void enableSQLTrace()`
- `static java.lang.String encodeJavaIdentifier​(java.lang.String s)`
- `static boolean equalizeObjects​(java.lang.Object obj1,                java.lang.Object obj2)`
- `static java.lang.String escapeHTML​(java.lang.String html,           boolean allowUnescapedFormatting)`
- `static java.lang.String escapeHTMLNewlines​(java.lang.String src)`
- `static java.lang.String escapeJsonCharacter​(java.lang.String value)`
- `static java.lang.String escapeNewlines​(java.lang.String src)`
- `static java.lang.String escapeNewlines​(java.lang.String src,               java.lang.String nRepl,               java.lang.String rRepl)`
- `static java.lang.String expandVariables​(java.lang.String src,                java.util.Map<java.lang.String,​java.lang.Object> variables)`
- `static <T> java.util.List<T> filter​(java.util.List<T> list,       Util.ListFilter<T> filter)`
- `static <T> java.util.List<T> filterNulls​(java.util.List<T> src)`
- `static <T> T find​(java.util.List<T> values,     Util.IMatcher<T> matcher)`
- `static <T> T find​(java.util.List<T> list,     T t,     java.util.Comparator<T> comparator)`
- `static <T extends java.lang.Comparable<? super T>>T findComparable​(java.util.List<T> list,               T toFind,               boolean sorted)`
- `static java.lang.String findFile​(java.lang.String name)`
- `static java.lang.String findFile​(java.lang.String property,         java.lang.String name)`
- `static java.lang.String findFile​(java.lang.String property,         java.lang.String name,         boolean searchClasspath)`
- `static java.lang.String findOutputFile​(java.lang.String name)`
- `static void flushIterator​(java.util.Iterator i)`
- `static java.lang.String ftoa​(float i)`
- `static java.lang.Object get​(java.util.Map map,    java.lang.String name)`
- `static java.lang.String getApplicationHome()`
- `static java.util.Date getBeginningOfDay​(java.util.Date day)`
- `static boolean getBoolean​(java.util.Map map,           java.lang.String name)`
- `static java.lang.String getClasspathDirectory​(int idx)`
- `static java.util.Date getDate​(java.lang.Object o)`
- `static java.util.Date getDate​(java.util.Map map,        java.lang.String name)`
- `static java.text.DateFormat getDateFormatForLocale​(java.lang.Integer dateFormat,                       java.lang.Integer timeFormat,                       java.util.Locale locale)`
- `static int getDaysDifference​(java.util.Date d1,                  java.util.Date d2)`
- `static java.lang.String getDetectedCharset​(byte[] input,                   java.lang.String defaultCharset)`
- `static java.util.Date getEndOfDay​(java.util.Date day)`
- `static java.lang.String getFullname​(java.lang.String first,            java.lang.String last)`
- `static java.lang.String getHostName()`
- `static java.util.ResourceBundle getIIQHelpMessages​(java.util.Locale locale)`
- `static java.util.ResourceBundle getIIQMessages​(java.util.Locale locale)`
- `static int getInt​(java.util.Map map,       java.lang.String name)`
- `static java.lang.String getJsonSafeKey​(java.lang.String key)`
- `static java.lang.String getKeyFromJsonSafeKey​(java.lang.String jsonSafeKey)`
- `static java.util.List getList​(java.lang.Object value)`
- `static java.util.function.Function<Message,​java.lang.String> getLocalizedMessage​(java.util.Locale locale,                    java.util.TimeZone timezone)`
- `static long getLongDifference​(java.util.Date d1,                  java.util.Date d2)`
- `static java.lang.String getMachineUser()`
- `static java.lang.String getMemoryStats()`
- `static java.lang.String getMessage​(java.util.ResourceBundle bundle,           java.lang.String keyName)`
- `static java.lang.String getMessage​(java.util.ResourceBundle bundle,           java.lang.String keyName,           boolean returnKey)`
- `static int getPercentage​(int x,              int y)`
- `static java.lang.Class getPropertyType​(java.lang.Class objectClass,                java.lang.String propertyName)`
- `static java.util.ResourceBundle getResourceBundle​(java.lang.String bundleBaseName,                  java.util.Locale locale)`
- `static java.lang.String getResourcePath​(java.lang.String name)`
- `static java.lang.Class getSailPointObjectClass​(java.lang.String name)`
- `static java.lang.String getString​(java.lang.String s)`
- `static java.lang.String getString​(java.util.Map map,          java.lang.String name)`
- `static java.util.List<java.lang.String> getStringList​(java.util.Map m,              java.lang.String name)`
- `static java.util.HashMap hashtableToMap​(java.util.Hashtable hash)`
- `static java.lang.String htmlify​(java.lang.String src)`
- `static java.util.Date incrementDateByDays​(java.util.Date date,                    long duration)`
- `static java.util.Date incrementDateByMinutes​(java.util.Date date,                       int minutes)`
- `static java.util.Date incrementDateBySeconds​(java.util.Date date,                       int seconds)`
- `static <T> java.util.List<T> intersection​(java.util.List<T> xs,             java.util.List<T> ys)`
- `static boolean isAlreadyExistsException​(java.lang.Throwable t)`
- `static boolean isAnyNullOrEmpty​(java.lang.String... vals)`
- `static boolean isDateAfter​(java.util.Date testDate,            java.util.Date startDate)`
- `static boolean isDateAfterToday​(java.util.Date date)`
- `static boolean isDateBetween​(java.util.Date testDate,              java.util.Date startDate,              java.util.Date endDate)`
- `static boolean isEmpty​(java.lang.Object[] args)`
- `static boolean isEmpty​(java.lang.String csv)`
- `static boolean isEmpty​(java.util.Collection collection)`
- `static boolean isEmpty​(java.util.Iterator i)`
- `static boolean isEmpty​(java.util.Map map)`
- `static boolean isEscapedForExcelVulnerability​(java.lang.String value)`
- `static boolean isFirstElement​(java.lang.Object o,               java.lang.Iterable i)`
- `static boolean isInt​(java.lang.String str)`
- `static boolean isLastElement​(java.lang.Object o,              java.lang.Iterable i)`
- `static boolean isNothing​(java.lang.String str)`
- `static boolean isNotNullOrEmpty​(java.lang.String str)`
- `static boolean isNullOrEmpty​(java.lang.String str)`
- `static boolean isNullOrEmptyString​(java.lang.Object value)`
- `static boolean isNumeric​(java.lang.String str)`
- `static boolean isObjectId​(java.lang.String objectIdString)`
- `static boolean isRemoteAddressInConfiguredIpsOrCidrs​(java.util.List ips,                                      java.lang.String remoteAddr)`
- `static boolean isWindows()`
- `static <T> java.lang.Iterable<T> iterate​(java.lang.Iterable<T> iterable)`
- `static <T> java.util.List<T> iteratorToList​(java.util.Iterator<T> iterator)`
- `static java.util.List<java.util.Map<java.lang.String,​java.lang.Object>> iteratorToMaps​(java.util.Iterator<java.lang.Object[]> iterator,               java.lang.String... keys)`
- `static java.lang.String itoa​(int i)`
- `static java.lang.String join​(java.util.Collection c,     java.lang.String delimiter)`
- `static java.lang.String leftPadZeros​(int toValue,             int padding)`
- `static java.lang.String listToCsv​(java.util.List list)`
- `static java.lang.String listToCsv​(java.util.List list,          boolean filterEmpty)`
- `static java.lang.String listToPipeDelimited​(java.util.List list)`
- `static java.lang.String listToQuotedCsv​(java.util.List list,                java.lang.Character quoteChar,                boolean filterEmpty)`
- `static java.lang.String listToQuotedCsv​(java.util.List list,                java.lang.Character quoteChar,                boolean filterEmpty,                boolean conditionallyQuote)`
- `static java.lang.String listToQuotedCsv​(java.util.List list,                java.lang.Character quoteChar,                boolean filterEmpty,                boolean conditionallyQuote,                boolean conditionallyAddSpace)`
- `static java.lang.String listToRfc4180Csv​(java.util.List<?> list)`
- `static java.lang.String longToDottedQuad​(long inaddr)`
- `static java.lang.String ltoa​(long i)`
- `static void main​(java.lang.String[] args)`
- `static java.util.List<java.util.Map<java.lang.String,​java.lang.Object>> makeJsonSafeKeys​(java.util.List<java.util.Map<java.lang.String,​java.lang.Object>> rows)`
- `static <T> java.util.List<T> mapKeys​(java.util.Map<T,​?> map)`
- `static java.lang.String mapToString​(java.util.Map map)`
- `static java.lang.String md5Hash30​(java.lang.String input)`
- `static java.lang.String memoryFormat​(long size)`
- `static long[] mergeAndSortArrays​(long[] array1,                   long[] array2)`
- `static java.lang.Object nullify​(java.lang.Object obj)`
- `static boolean nullsafeBoolean​(java.lang.Boolean val)`
- `static boolean nullSafeCaseInsensitiveEq​(java.lang.String o1,                          java.lang.String o2)`
- `static <T extends java.lang.Comparable>int nullSafeCompareTo​(T o1,                  T o2)`
- `static boolean nullSafeContains​(java.lang.String csv,                 java.lang.Object o)`
- `static boolean nullSafeContains​(java.util.List list,                 java.lang.Object o)`
- `static boolean nullSafeEq​(java.lang.Object o1,           java.lang.Object o2)`
- `static boolean nullSafeEq​(java.lang.Object o1,           java.lang.Object o2,           boolean nullsEq)`
- `static boolean nullSafeEq​(java.lang.Object o1,           java.lang.Object o2,           boolean nullsEq,           boolean emptyStringToNull)`
- `static int nullSafeHashCode​(java.lang.Object o)`
- `static long nullsafeLong​(java.lang.Long val)`
- `static java.lang.String nullSafeLowerCase​(java.lang.String str)`
- `static int nullSafeSize​(java.util.List list)`
- `static <T> boolean orderInsensitiveEquals​(java.util.List<T> l1,                       java.util.List<T> l2)`
- `static java.lang.String otoa​(java.lang.Object o)`
- `static boolean otob​(java.lang.Object o)`
- `static int otoi​(java.lang.Object o)`
- `static java.util.List<java.lang.String> otol​(java.lang.Object o)`
- `static java.util.List<java.lang.String> otol​(java.lang.Object o,     boolean forceSplitOnComma)`
- `static long otolo​(java.lang.Object o)`
- `static java.util.Map<java.lang.String,​java.lang.Object> otom​(java.lang.Object o)`
- `static java.lang.String otos​(java.lang.Object o)`
- `static java.lang.String padID​(java.lang.String strId)`
- `static <T> java.util.List<java.util.List<T>> partition​(java.util.Collection<T> members,          int maxSize)`
- `static int rand​(int low,     int high)`
- `static byte[] readBinaryFile​(java.io.File f)`
- `static byte[] readBinaryFile​(java.lang.String name)`
- `static byte[] readBinaryInputStream​(java.io.InputStream inputStream)`
- `static java.lang.String readFile​(java.io.File f)`
- `static java.lang.String readFile​(java.lang.String name)`
- `static java.lang.String readInputStream​(java.io.InputStream inputStream)`
- `static java.lang.String readResource​(java.lang.String resource)`
- `static java.lang.Object readSerializedObject​(byte[] bytes)`
- `static <T> void removeDuplicates​(java.util.List<T> list)`
- `static java.lang.String replaceCharacter​(java.lang.String toReplace,                 java.lang.String replaceWith,                 java.lang.String str)`
- `static <T> java.lang.Iterable<T> safeIterable​(java.lang.Iterable<T> iterable)`
- `static java.lang.String safeMessageFormat​(java.lang.String format,                  java.lang.Object... args)`
- `static <T> java.util.stream.Stream<T> safeStream​(java.util.Collection<T> collection)`
- `static java.util.Map scrubPasswords​(java.util.Map sensitiveMap,               java.util.List<java.lang.String> secretAttributes)`
- `static byte[] serializableObjectToBytes​(java.lang.Object toWrite)`
- `static void setJavaLibraryPath()`
- `static void setSailpointWebDir​(java.lang.String slptWebDir)`
- `static void setSecureCookies​(boolean secure)`
- `static java.lang.String setToCsv​(java.util.Set<?> set)`
- `static java.lang.String[] shiftArray​(java.lang.String[] input)`
- `static int size​(java.lang.String s)`
- `static int size​(java.util.Collection c)`
- `static void sleep​(int millis)`
- `static boolean smellsLikeMessageKey​(java.lang.String key)`
- `static java.lang.String splitCamelCase​(java.lang.String str)`
- `static java.lang.String stackToString​(java.lang.Throwable th)`
- `static java.util.Date stringToDate​(java.lang.String src)`
- `static java.util.List stringToList​(java.lang.String value)`
- `static java.util.Map stringToMap​(java.lang.String value)`
- `static java.util.Date stringToTime​(java.lang.String src)`
- `static java.lang.String stripLeadingChar​(java.lang.String s,                 char c)`
- `static java.lang.String stripLeadingTrailingChar​(java.lang.String s,                         char c)`
- `static java.lang.String strstr​(java.lang.String inString,       java.lang.String delimeter)`
- `static java.lang.String toCamelCase​(java.lang.String str)`
- `static java.lang.String toCamelCase​(java.lang.String str,            char delimiter)`
- `static java.lang.String trimnull​(java.lang.String str)`
- `static java.lang.String trimWhitespace​(java.lang.String src)`
- `static java.lang.String trimWhiteSpaceAndSlash​(java.lang.String str)`
- `static java.lang.String truncate​(java.lang.String s,         int maxLength)`
- `static java.lang.String truncatedJoin​(java.util.Collection c,              java.lang.String delimiter,              int maxChars)`
- `static java.lang.String truncateFront​(java.lang.String s,              int maxLength)`
- `static java.lang.String uniqueString​(int length)`
- `static java.lang.String unxml​(java.lang.String src)`
- `static boolean useSecureCookies()`
- `static java.lang.String uuid()`
- `static void waitForCondition​(sailpoint.tools.AwaitFunction awaitFunction,                 long timeoutInMillis)`
- `static void waitForCondition​(sailpoint.tools.AwaitFunction awaitFunction,                 long timeoutInMillis,                 java.lang.String timeoutMessage)`
- `static <T> java.util.List<T> wrappedList​(java.util.List<T> list,            Util.ListElementWrapper<T> wrapper)`
- `static void writeFile​(java.lang.String name,          byte[] contents)`
- `static void writeFile​(java.lang.String name,          java.lang.String contents)`
- `static void writeTestFile​(java.lang.String name,              byte[] contents)`
- `static void writeTestFile​(java.lang.String name,              java.lang.String contents)`

---

## Class AttributeDefinition
**Package:** `sailpoint.tools.ldap`

### Description
An AttributeDefinition represents an attribute definition defined in an LDAP  schema.      RFC: http://www.ietf.org/rfc/rfc2252.txt

### Declaration
```java
public class AttributeDefinition extends java.lang.Object
```

### Attributes
No attributes.

### Methods
- `boolean equals​(java.lang.Object o)`
- `java.lang.String getDescription()`
- `java.lang.String getName()`
- `java.lang.String getSyntax()`
- `int hashCode()`
- `boolean isMulti()`

---

## Class LDAPUtil
**Package:** `sailpoint.tools.ldap`

### Description
Utility class to help with LDAP access.

### Declaration
```java
public class LDAPUtil extends java.lang.Object
```

### Attributes
No attributes.

### Methods
- `static java.lang.Object escapeLDAPSearchStringValue​(java.lang.Object val)`
- `static java.util.List<java.lang.String> getAllAttributeValues​(javax.naming.directory.Attribute attr)`
- `static java.lang.String getAttributeValue​(javax.naming.directory.DirContext ctx,                  java.lang.String dn,                  java.lang.String attr)`
- `static javax.naming.directory.Attributes getRootDSE​(javax.naming.directory.DirContext ctx)`
- `static Schema getSchema​(javax.naming.directory.DirContext ctx)`
- `static java.lang.String getSchemaDN​(javax.naming.directory.DirContext ctx)`
- `static java.lang.String getSingleValue​(javax.naming.directory.Attributes attrs,               java.lang.String attrName)`

---

## Enum ObjectClass.Type
**Package:** `sailpoint.tools.ldap`

### Description
Enumeration of the types of object classes.

### Declaration
```java
public static enum ObjectClass.Type extends java.lang.Enum<ObjectClass.Type>
```

### Attributes
No attributes.

### Methods
- `static ObjectClass.Type valueOf​(java.lang.String name)`
- `static ObjectClass.Type[] values()`

---

## Class ObjectClass
**Package:** `sailpoint.tools.ldap`

### Description
An ObjectClass represents an object class defined in an LDAP schema. Note  that the attributes returned do not include attributes from parent object  classes (for example - SUP).      RFC: http://www.ietf.org/rfc/rfc2252.txt

### Declaration
```java
public class ObjectClass extends java.lang.Object
```

### Attributes
No attributes.

### Methods
- `boolean equals​(java.lang.Object o)`
- `java.util.List<java.lang.String> getAllAttributeNames()`
- `java.util.List<AttributeDefinition> getAllAttributes()`
- `java.util.List<java.lang.String> getMay()`
- `java.util.List<AttributeDefinition> getMayAttributes()`
- `java.util.List<java.lang.String> getMust()`
- `java.util.List<AttributeDefinition> getMustAttributes()`
- `java.lang.String getName()`
- `java.util.List<java.lang.String> getSupers()`
- `ObjectClass.Type getType()`
- `int hashCode()`
- `java.lang.String toString()`

---

## Class Schema
**Package:** `sailpoint.tools.ldap`

### Description
A Schema represents the object classes and attribute definitions returned  from an LDAP schema. Usually created by LDAPUtil.getSchema(DirConext).

### Declaration
```java
public class Schema extends java.lang.Object
```

### Attributes
No attributes.

### Methods
- `AttributeDefinition getAttributeDefinition​(java.lang.String attrName)`
- `ObjectClass getObjectClass​(java.lang.String objectClassName)`

---

## Class AbstractXmlObject
**Package:** `sailpoint.tools.xml`

### Description
Base class for objects that want to provide an XML  serialization but do not need to be first-class persistent   SailPointObjects.

### Declaration
```java
public abstract class AbstractXmlObject extends java.lang.Object implements sailpoint.tools.xml.PersistentXmlObject, java.io.Serializable
```

### Attributes
No attributes.

### Methods
- `java.lang.Object deepCopy​(sailpoint.tools.xml.XMLReferenceResolver res)`
- `java.lang.String getOriginalXml()`
- `static java.lang.Object parseXml​(sailpoint.tools.xml.XMLReferenceResolver resolver,         java.lang.String xml)`
- `static java.lang.Object parseXml​(sailpoint.tools.xml.XMLReferenceResolver resolver,         java.lang.String xml,         boolean validate)`
- `static java.lang.Object parseXml​(sailpoint.tools.xml.XMLReferenceResolver resolver,         org.w3c.dom.Element e)`
- `void setOriginalXml​(java.lang.String xml)`
- `java.lang.String toXml()`
- `java.lang.String toXml​(boolean includeHeader)`
- `void toXml​(sailpoint.tools.xml.XMLBuilder b)`
- `void writeXml​(java.lang.String filename)`

---

## Class XMLObjectFactory
**Package:** `sailpoint.tools.xml`

### Description
Primary control class for XML serialization and deserialization.  To obtain the singleton factory call the getInstance method.

### Declaration
```java
public class XMLObjectFactory extends java.lang.Object
```

### Attributes
- `static java.lang.String DTD`

### Methods
- `java.lang.Object clone​(java.lang.Object object,      sailpoint.tools.xml.XMLReferenceResolver resolver)`
- `java.lang.Object cloneWithoutId​(java.lang.Object object,               sailpoint.tools.xml.XMLReferenceResolver resolver)`
- `static java.util.List<java.lang.Class<?>> getAnnotatedClasses()`
- `java.lang.String getDTD()`
- `static XMLObjectFactory getInstance()`
- `java.lang.Object parseElement​(sailpoint.tools.xml.XMLReferenceResolver resolver,             org.w3c.dom.Element element)`
- `java.lang.Object parseXml​(sailpoint.tools.xml.XMLReferenceResolver resolver,         java.lang.String xml,         boolean validating)`
- `java.lang.String toXml​(java.lang.Object object)`
- `java.lang.String toXml​(java.lang.Object object,      boolean includeHeader)`
- `void toXml​(java.lang.Object object,      sailpoint.tools.xml.XMLBuilder builder)`
- `java.lang.String toXmlNoIndent​(java.lang.Object object)`

---

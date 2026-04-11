# Connector Common Classes Details

## JsonUtil.JsonParser

**Package:** `connector.common`

**Description:** Returns boolean value if the provided key is present in the supplied JSON source

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `connector.common.JsonUtil.JsonParser`

**Attributes:** N/A

**Methods:**
- `boolean containsKey (java.lang.String source, java.lang.String key)`
- `java.lang.Object get (java.lang.String source, java.lang.String key)`
- `java.util.Map<java.lang.String,​java.lang.Object> get (java.lang.String source, java.util.Collection<java.lang.String> keys)`
- `java.lang.Boolean getAsBoolean (java.lang.String source, java.lang.String key)`
- `java.util.List<java.lang.Object> getAsList (java.lang.String source, java.lang.String key)`
- `java.lang.Number getAsNumber (java.lang.String source, java.lang.String key)`
- `java.lang.String getAsString (java.lang.String source, java.lang.String key)`
- `boolean isEmpty (java.lang.String source, java.lang.String key)`
- `int length (java.lang.String source)`
- `java.lang.Object parseJson (java.lang.String source)`
- `java.lang.Object parseJson (java.lang.String source, java.lang.Class<?> targetClass)`
- `java.lang.String put (java.lang.String target, java.lang.String key, java.lang.Object value)`
- `java.lang.String remove (java.lang.String target, java.lang.String key)`
- `java.lang.String toJson (java.lang.Object source)`
- `java.util.List<java.lang.Object> toList (java.lang.String jsonArraySource)`
- `java.util.Map<java.lang.String,​java.lang.Object> toMap (java.lang.String source)`

---

## JsonUtil.JsonParserBuilder

**Package:** `connector.common`

**Description:** Builder for creating a JsonParser instance.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `connector.common.JsonUtil.JsonParserBuilder`

**Attributes:** N/A

**Methods:**
- `JsonUtil.JsonParser create ()`
- `staticJsonUtil.JsonParserBuilder custom ()`
- `staticJsonUtil.JsonParser defaultJsonParser ()`
- `JsonUtil.JsonParserBuilder disableHtmlEscaping ()`
- `JsonUtil.JsonParserBuilder serializeNulls ()`
- `JsonUtil.JsonParserBuilder setDateFormat (java.lang.String dateFormat)`

---

## JsonUtil

**Package:** `connector.common`

**Description:** Utility class for rendering and parsing JSON. Developers can makes use of methods from JsonParserBuilder for creating an instance of the utility class depending upon the necessary customizations. For default JSON parsing: JsonUtil.JsonParserBuilder.defaultJsonParser() - Returns an instance of default Json utility which ignores null values and disables HTML escaping For customized JSON parsing: JsonUtil.JsonParserBuilder.custom() - Returns a builder instance for creating customized JsonUtil object JsonUtil.JsonParserBuilder.serializeNulls() - Enables including null values in json representation JsonUtil.JsonParserBuilder.disableHtmlEscaping() - Disables HTML escaping in the resulting json representation JsonUtil.JsonParserBuilder.create() - Prepares the JsonUtil instance with the customizations Dates are rendered as strings, but they do not parse back as dates.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `connector.common.JsonUtil`

**Attributes:** N/A

**Methods:**
- `static boolean containsKey (java.lang.String source, java.lang.String key)`
- `static java.lang.Object get (java.lang.String source, java.lang.String key)`
- `static java.util.Map<java.lang.String,​java.lang.Object> get (java.lang.String source, java.util.Collection<java.lang.String> keys)`
- `static java.lang.Boolean getAsBoolean (java.lang.String source, java.lang.String key)`
- `static java.util.List<java.lang.Object> getAsList (java.lang.String source, java.lang.String key)`
- `static java.lang.Number getAsNumber (java.lang.String source, java.lang.String key)`
- `static java.lang.String getAsString (java.lang.String source, java.lang.String key)`
- `static boolean isEmpty (java.lang.String source, java.lang.String key)`
- `static int length (java.lang.String source)`
- `static java.lang.Object parse (java.lang.String json)`
- `static java.lang.Object parseJson (java.lang.String source)`
- `static java.lang.Object parseJson (java.lang.String source, java.lang.Class<?> targetClass)`
- `static java.lang.String put (java.lang.String target, java.lang.String key, java.lang.Object value)`
- `static java.lang.String remove (java.lang.String target, java.lang.String key)`
- `static java.lang.String render (java.lang.Object o)`
- `static java.lang.String toJson (java.lang.Object source)`
- `static java.util.List<java.lang.Object> toList (java.lang.String jsonArraySource)`
- `static java.util.Map<java.lang.String,​java.lang.Object> toMap (java.lang.String source)`
- `static java.lang.String toStringOrJson (java.lang.Object object)`

---

## LoggingUtil

**Package:** `connector.common`

**Description:** Logs a message at DEBUG level, if enabled for className .

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `connector.common.LoggingUtil`

**Attributes:** N/A

**Methods:**
- `static void debug (java.lang.Class<?> className, java.lang.String message, java.lang.Object[] args)`
- `void debug (java.lang.String message, org.apache.logging.log4j.util.Supplier<?>... args)`
- `void debug (org.apache.logging.log4j.util.Supplier<?> message)`
- `static void entering (java.lang.Class<?> className, java.lang.String method, java.lang.Object[] args)`
- `static void error (java.lang.Class<?> className, java.lang.String message, java.lang.Object[] args)`
- `static void error (java.lang.Class<?> className, java.lang.String message, java.lang.Object[] args, java.lang.Throwable t)`
- `void error (org.apache.logging.log4j.util.Supplier<?> message)`
- `void error (org.apache.logging.log4j.util.Supplier<?> message, java.lang.Throwable t)`
- `static void exiting (java.lang.Class<?> className, java.lang.String method, java.lang.Object[] args, java.lang.Object returnValue)`
- `static void info (java.lang.Class<?> className, java.lang.String message, java.lang.Object[] args)`
- `void info (java.lang.String message, org.apache.logging.log4j.util.Supplier<?>... args)`
- `void info (org.apache.logging.log4j.util.Supplier<?> message)`
- `static void trace (java.lang.Class<?> className, java.lang.String message, java.lang.Object[] args)`
- `void trace (java.lang.String message, org.apache.logging.log4j.util.Supplier<?>... args)`
- `void trace (org.apache.logging.log4j.util.Supplier<?> message)`
- `static void warn (java.lang.Class<?> className, java.lang.String message, java.lang.Object[] args)`
- `void warn (java.lang.String message, org.apache.logging.log4j.util.Supplier<?>... args)`
- `void warn (org.apache.logging.log4j.util.Supplier<?> message)`

---

## SecurityUtil

**Package:** `connector.common`

**Description:** The SecurityUtil class contains methods for performing common basic security related operations.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `connector.common.SecurityUtil`

**Attributes:** N/A

**Methods:**
- `static java.security.PrivateKey decryptPrivateKey (java.lang.String privateKey, java.lang.String privateKeyPassword)`

---

## XmlUtil.SailPointEntityResolver

**Package:** `connector.common`

**Description:** Custom entity resolver that handles different locations.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `connector.common.XmlUtil.SailPointEntityResolver`
- `org.xml.sax.EntityResolver`

**Attributes:** N/A

**Methods:**
- `org.xml.sax.InputSource resolveEntity (java.lang.String pubid, java.lang.String sysid)`

---

## XmlUtil.SailPointErrorHandler

**Package:** `connector.common`

**Description:** Custom error handler that just throws exceptions.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `connector.common.XmlUtil.SailPointErrorHandler`
- `org.xml.sax.ErrorHandler`

**Attributes:** N/A

**Methods:**
- `void error (org.xml.sax.SAXParseException e)`
- `void fatalError (org.xml.sax.SAXParseException e)`
- `void warning (org.xml.sax.SAXParseException e)`

---

## XmlUtil

**Package:** `connector.common`

**Description:** Utilities for creating and parsing XML.

**Inherited Classes/Interfaces:**
- `java.lang.Object`
- `connector.common.XmlUtil`

**Attributes:**
- `static char DOUBLE_QUOTE`
- `static char SINGLE_QUOTE`

**Methods:**
- `static void addAttribute (java.lang.StringBuilder b, java.lang.String name, java.lang.String value)`
- `static void addContent (java.lang.StringBuilder b, java.lang.Object o)`
- `static java.lang.String DocumentToString (org.w3c.dom.Document doc)`
- `static void escapeAttribute (java.io.Writer f, java.lang.String s)`
- `static java.lang.String escapeAttribute (java.lang.String s)`
- `static void escapeAttribute (java.lang.StringBuilder b, java.lang.String s)`
- `static void escapeContent (java.io.Writer f, java.lang.String s)`
- `static java.lang.String escapeContent (java.lang.String s)`
- `static void escapeContent (java.lang.StringBuilder b, java.lang.String s)`
- `static java.lang.Object evaluateXpath (org.w3c.dom.Node xmlDocument, java.lang.String xpath, java.util.Map<java.lang.String,java.lang.String> namespaceMappings, javax.xml.namespace.QName qname)`
- `static java.lang.Object evaluateXpath (org.w3c.dom.Node xmlDocument, java.lang.String xpath, java.util.Map<java.lang.String,java.lang.String> namespaceMappings, javax.xml.namespace.QName qname, boolean isOptionalNameSpacePrefix)`
- `static java.util.Map<java.lang.String,​java.lang.String> extractNamespaces (java.lang.String xmlContent)`
- `static java.util.List<java.lang.String> extractNodes (java.lang.String rawResponse, java.lang.String rootPath, java.util.Map<java.lang.String,java.lang.String> namespaceMappings)`
- `static org.w3c.dom.Text findText (org.w3c.dom.Node node, boolean ignoreEmpty)`
- `static java.lang.String getAttribute (org.w3c.dom.Element e, java.lang.String name)`
- `static org.w3c.dom.Element getChildElement (org.w3c.dom.Node node)`
- `static org.w3c.dom.Element getChildElement (org.w3c.dom.Node node, java.lang.String elementName)`
- `static java.lang.String getContent (org.w3c.dom.Element e)`
- `static org.w3c.dom.Document getDocument (java.lang.String xml)`
- `static org.w3c.dom.Document getDocument (java.lang.String xml, boolean isNamespaceAware)`
- `static org.w3c.dom.Element getNextElement (org.w3c.dom.Node node)`
- `static javax.xml.xpath.XPath getXpath (java.util.Map<java.lang.String,java.lang.String> namespaceMappings)`
- `static javax.xml.xpath.XPath getXpath (java.util.Map<java.lang.String,java.lang.String> namespaceMappings, boolean isOptionalNameSpacePrefix)`
- `static javax.xml.xpath.XPathExpression getXpathExpression (java.lang.String xpathExpr, java.util.Map<java.lang.String,java.lang.String> namespaceMappings)`
- `static javax.xml.xpath.XPathExpression getXpathExpression (java.lang.String xpathExpr, java.util.Map<java.lang.String,java.lang.String> namespaceMappings, boolean isOptionalNameSpacePrefix)`
- `static boolean isXmlChar (char ch)`
- `static org.w3c.dom.Element parseOld (java.lang.String xml, java.lang.String dtd, boolean validating)`
- `static void println (java.lang.Object o)`
- `static void serialize (java.lang.StringBuilder b, org.w3c.dom.Node node)`
- `static java.lang.String unescapeAttribute (java.lang.String s)`

---

* Class Name: `PluginBaseHelper`
* Package Name: `sailpoint.plugin`
* Description: Helper methods that provide functionality that all base plugin classes will provide such as getting the value of a plugin setting or a connection to the plugin database.
* Attributes:
  * *No attributes.*
* Inheritance: `public class PluginBaseHelper extends java.lang.Object`
* Methods:
  * `static java.sql.Connection` `getConnection()`
  * `static boolean` `getSettingBool​(java.lang.String pluginName, java.lang.String settingName)`
  * `static int` `getSettingInt​(java.lang.String pluginName, java.lang.String settingName)`
  * `static long` `getSettingLong​(java.lang.String pluginName, java.lang.String settingName)`
  * `static java.util.List<SailPointObject>` `getSettingMultiObject​(SailPointContext context, java.lang.String pluginName, java.lang.String settingName)`
  * `static java.util.List<java.lang.String>` `getSettingMultiString​(java.lang.String pluginName, java.lang.String settingName)`
  * `static SailPointObject` `getSettingObject​(SailPointContext context, java.lang.String pluginName, java.lang.String settingName)`
  * `static java.lang.String` `getSettingSecret​(SailPointContext context, java.lang.String pluginName, java.lang.String settingName)`
  * `static java.lang.String` `getSettingString​(java.lang.String pluginName, java.lang.String settingName)`
  * `static boolean` `isCached​(java.lang.String pluginName)`
  * `static java.sql.PreparedStatement` `prepareStatement​(java.sql.Connection connection, java.lang.String sql, java.lang.Object... params)`

* Class Name: `PluginContext`
* Package Name: `sailpoint.plugin`
* Description: Interface for plugin developers to access a connection to the plugin database and retrieve plugin setting values.
* Attributes:
  * *No attributes.*
* Inheritance: `public interface PluginContext`
* Methods:
  * `java.sql.Connection` `getConnection()`
  * `java.lang.String` `getPluginName()`
  * `default boolean` `getSettingBool​(java.lang.String settingName)`
  * `default int` `getSettingInt​(java.lang.String settingName)`
  * `default long` `getSettingLong​(java.lang.String settingName)`
  * `default java.util.List<SailPointObject>` `getSettingMultiObject​(SailPointContext context, java.lang.String settingName)`
  * `default java.util.List<java.lang.String>` `getSettingMultiString​(java.lang.String settingName)`
  * `default SailPointObject` `getSettingObject​(SailPointContext context, java.lang.String settingName)`
  * `default java.lang.String` `getSettingSecret​(SailPointContext context, java.lang.String settingName)`
  * `default java.lang.String` `getSettingString​(java.lang.String settingName)`

* Class Name: `PluginsUtil`
* Package Name: `sailpoint.plugin`
* Description: Utility methods for working with plugins.
* Attributes:
  * *No attributes.*
* Inheritance: `public class PluginsUtil extends java.lang.Object`
* Methods:
  * `static void` `audit​(java.lang.String auditEvent, Plugin plugin, SailPointContext context)`
  * `static sailpoint.tools.Pair<java.lang.String,​java.lang.String>` `getNameAndFileFromUrl​(java.lang.String path, java.lang.String prefix)`
  * `static java.lang.String` `getPluginFileIncludeUrl​(java.lang.String pluginName, java.lang.String file)`
  * `static java.lang.String` `getPluginFileUrl​(java.lang.String pluginName, java.lang.String file)`
  * `static <T> T` `instantiate​(java.lang.String pluginName, java.lang.String className)`
  * `static <T> T` `instantiate​(java.lang.String pluginName, java.lang.String className, java.lang.Object[] params, java.lang.Class<?>[] paramTypes)`
  * `static <T> T` `instantiate​(java.lang.String pluginName, java.lang.String className, Plugin.ClassExportType classExportType)`
  * `static <T> T` `instantiate​(java.lang.String pluginName, java.lang.String className, Plugin.ClassExportType classExportType, java.lang.Object[] params, java.lang.Class<?>[] paramTypes)`
  * `static <T> T` `instantiate​(java.lang.String pluginName, java.lang.String className, Plugin.ClassExportType classExportType, sailpoint.plugin.PluginsCache pluginsCache)`
  * `static <T> T` `instantiateWithException​(java.lang.String pluginName, java.lang.String className, Plugin.ClassExportType classExportType, java.lang.Object[] params, java.lang.Class<?>[] paramTypes)`
  * `static boolean` `isAuthorizedForContent​(java.lang.String requiredRight, java.lang.String regex, sailpoint.plugin.PageContentRequest contentRequest)`
  * `static boolean` `isEqualOrDowngrade​(Plugin prev, Plugin next)`
  * `static boolean` `isMinUpgradableVersionMet​(Plugin prev, Plugin next)`
  * `static boolean` `isPluginValidForSystemVersion​(Plugin plugin, java.lang.String systemVersion)`
  * `static boolean` `isRestrictedPackage​(java.lang.String packageName)`
  * `static boolean` `isVersionGreaterThanOrEqual​(java.lang.String first, java.lang.String second)`
  * `static boolean` `isVersionLessThanOrEqual​(java.lang.String first, java.lang.String second)`

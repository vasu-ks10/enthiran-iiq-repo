## Class: AbstractTaskExecutor

**Package:** `Package sailpoint.task`

**Description:**
An implementation of TaskExecutor that provides a set of
 common utilities for executor classes.

**Inheritance:**
- java.lang.Object

**Attributes:**
- `static java.lang.String ARG_FILTER`
- `static java.lang.String ARG_LOCK_MODE`
- `static java.lang.String ARG_LOCK_TIMEOUT`
- `static java.lang.String ARG_PROFILE`
- `static java.lang.String ARG_RESTARTABLE`
- `static java.lang.String ARG_TRACE`
- `static int DEFAULT_LOCK_TIMEOUT`
- `static java.lang.String RET_TOTAL`

**Methods:**
- `sailpoint.task.Monitor getMonitor()`
- `protected int getSuggestedPartitionCount​(SailPointContext context, boolean includeInactive, java.lang.String requestDefinitionName)`
- `protected int getSuggestedPartitionCount​(SailPointContext context, boolean includeInactive, java.lang.String requestDefinitionName, java.util.List<Server> o_servers)`
- `void launchPartitions​(SailPointContext context, TaskResult result, java.util.List<Request> requests)`
- `void processCommand​(Request cmd)`
- `void saveRequest​(SailPointContext context, TaskResult result, Request request)`
- `void setMonitor​(sailpoint.task.Monitor monitor)`
- `void updateProgress​(SailPointContext ctx, TaskResult result, java.lang.String progressString)`
- `void updateProgress​(SailPointContext ctx, TaskResult result, java.lang.String progressString, int percentComplete)`

---

## Class: BasePluginTaskExecutor

**Package:** `Package sailpoint.task`

**Description:**
Base class that a plugin task executor implementation should
 inherit from if it needs to leverage common functionality that
 plugin task executors may need such as getting a connection to
 the plugins datasource or reading a plugin configuration value.

**Inheritance:**
- java.lang.Object
- sailpoint.task.AbstractTaskExecutor

**Attributes:**
None

**Methods:**
- `java.sql.Connection getConnection()`
- `abstract java.lang.String getPluginName()`
- `protected java.sql.PreparedStatement prepareStatement​(java.sql.Connection connection, java.lang.String sql, java.lang.Object... params)`

---

# Class Details: sailpoint.rest.plugin.BasePluginResource

## Package Name
`sailpoint.rest.plugin`

## Class Name
`BasePluginResource`

## Description
The base class for all plugin REST resources. This class provides easy access to plugin settings and plugin database interaction. Any plugin developer who wishes to ship REST resources should extend this class.

## Inherited Classes and Interfaces
**Inherits from:**
* `java.lang.Object`
* `sailpoint.rest.BaseResource`
* `sailpoint.rest.BaseListResource`

**Implements Interfaces:**
* `sailpoint.plugin.PluginContext`
* `sailpoint.web.UserContext`

## Attributes (Fields)
*None declared directly.*

**Inherited from `sailpoint.rest.BaseListResource`:**
`CALCULATED_COLUMN_PREFIX`, `colKey`, `exclude`, `excludedIds`, `filters`, `groupBy`, `limit`, `PARAM_COL_KEY`, `PARAM_DIR`, `PARAM_EXCLUDED_IDS`, `PARAM_GROUP_BY`, `PARAM_LIMIT`, `PARAM_QUERY`, `PARAM_SELECT_ALL`, `PARAM_SELECTED`, `PARAM_SORT`, `PARAM_START`, `query`, `selectAll`, `selectedIds`, `sortBy`, `sortDirection`, `STANDARD_PARAMS`, `start`

**Inherited from `sailpoint.rest.BaseResource`:**
`authnPassword`, `authnUsername`, `headers`, `request`, `uriInfo`

## Method Signatures
* `protected void authorize(sailpoint.authorization.Authorizer... authorizers) throws GeneralException`
* `public java.sql.Connection getConnection() throws GeneralException`
* `public abstract java.lang.String getPluginName()`
* `protected java.sql.PreparedStatement prepareStatement(java.sql.Connection connection, java.lang.String sql, java.lang.Object... params) throws java.sql.SQLException`

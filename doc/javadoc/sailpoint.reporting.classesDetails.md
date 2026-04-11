# Sailpoint Reporting Datasource Classes Details

## JavaDataSource

**Package Name:** `sailpoint.reporting.datasource`

**Description:**
This class allows a java datasource implement to be used with the  GridReportExecutor.

**Attributes:**
- None

**Inherits/Implements:**
`net.sf.jasperreports.engine.JRDataSource, LiveReportDataSource, sailpoint.reporting.datasource.TopLevelDataSource`

**Methods:**
- `void initialize(SailPointContext context,           LiveReport report,           Attributes<java.lang.String,java.lang.Object> arguments,           java.lang.String groupBy,           java.util.List<Sort> sort)`
- `void setLimit(int startRow,         int pageSize)`

---

## LiveReportDataSource

**Package Name:** `sailpoint.reporting.datasource`

**Description:**
Extension of the TopLevelDataSource interface that allows  us to execute the datasource outside of Jasper and  allows us to get an idea of the size of the data source's  dataset.

**Attributes:**
- None

**Inherits/Implements:**
`net.sf.jasperreports.engine.JRDataSource, sailpoint.reporting.datasource.TopLevelDataSource`

**Methods:**
- `java.lang.String getBaseHql()`
- `QueryOptions getBaseQueryOptions()`
- `java.lang.Object getFieldValue(java.lang.String field)`
- `int getSizeEstimate()`

---

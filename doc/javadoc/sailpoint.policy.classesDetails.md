# SailPoint Policy Classes Details

## Class AbstractPolicyExecutor

**Package:** sailpoint.policy

**Description:** An implementation of PolicyExecutor that provides utility methods common to most executors.

**Inherited Classes/Interfaces:**
java.lang.Object -> sailpoint.policy.AbstractPolicyExecutor

**Attributes:**
- static java.lang.String ARG_CONSTRAINT
- static java.lang.String ARG_IDENTITY
- static java.lang.String ARG_POLICY
- static java.lang.String ARG_STATE
- static java.lang.String ARG_VIOLATION

**Methods:**
- PolicyViolation formatViolation(SailPointContext context, Identity identity, Policy policy, BaseConstraint constraint, PolicyViolation violation)
- protected boolean isSimulating()
- void makeAlertable(PolicyViolation policyViolation)
- void setSimulating(boolean val)

---

## Class BasePluginPolicyExecutor

**Package:** sailpoint.policy

**Description:** Base class that a plugin policy executor implementation should inherit from if it requires common functionality that plugin policy executors may need such as getting a connection to the plugins datasource or reading of plugin configuration values.

**Inherited Classes/Interfaces:**
java.lang.Object -> sailpoint.policy.AbstractPolicyExecutor -> sailpoint.policy.BasePluginPolicyExecutor

**Attributes:**
None

**Methods:**
- java.sql.Connection getConnection()
- abstract java.lang.String getPluginName()
- protected java.sql.PreparedStatement prepareStatement(java.sql.Connection connection, java.lang.String sql, java.lang.Object... params)

---

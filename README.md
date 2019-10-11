# Log Analytics Security Audit Queries
Security Audit queries in Log Analytics

This repo tracks and documents queries in Log Analytics for key security events in Active Directory and Domain Controllers.

It is modeled after events that are outlined by this documentation - <a href="https://docs.microsoft.com/en-us/azure/active-directory-domain-services/security-audit-events">Enable Security Audits for Azure AD Domain Services.</a>

Additional resources: <a href="https://blogs.msdn.microsoft.com/wei_out_there_with_system_center/2016/08/05/leveraging-oms-log-search-to-report-on-user-logon-and-object-access-events/">Leveraging OMS Log Search to report on user logon and object access events.</a>

The basis of the queries will be based on EventIDs identified by the different security-related events. For example:

SecurityEvent
| where EventID==528 or EventID==540 or EventID==4624
| project TimeGenerated, Activity, Computer, IpAddress, AuthenticationPackageName, LogonProcessName, LogonTypeName, TargetAccount

## Future work

<a href="https://docs.microsoft.com/en-us/azure/azure-monitor/platform/powerbi">Importing Log Analytics data into PowerBI</a>

##Screenshot of query displaying Logon/Logoff events from monitored VMs

<img src="https://github.com/juliansoh/LogAnalyticsSecurityAuditQueries/blob/master/Screenshots/LogAnalyticsQueryShowingLogonLogoffEvents.jpg">

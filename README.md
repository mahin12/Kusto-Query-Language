# Kusto-Query-Language



This KQL query retrieves successful user logon events from the `SecurityEvent` table, specifically for console logons (LogonType 2). It filters for EventID 4624 and selects the timestamp, user account, computer name, logon type, and IP address.

Here's the breakdown:

- `SecurityEvent`: Table containing security events.
- `EventID == 4624`: Successful logon events.
- `AccountType == "User"`: Filters to user accounts.
- `LogonType == 2`: Console logons.
- `project`: Selects specified columns: `TimeGenerated`, `Account`, `Computer`, `LogonType`, `IpAddress`.


SecurityEvent
| where EventID == 4624
| where AccountType == "User" and LogonType == 2
| project TimeGenerated, Account, Computer, LogonType, IpAddress

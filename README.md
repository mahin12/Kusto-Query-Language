# Kusto-Query-Language



This KQL query retrieves successful user logon events from the `SecurityEvent` table, specifically for console logons (LogonType 2). It filters for EventID 4624 and selects the timestamp, user account, computer name, logon type, and IP address.

Here's the breakdown:

- `SecurityEvent`: Table containing security events.
- `EventID == 4624`: Successful logon events.
- `AccountType == "User"`: Filters to user accounts.
- `LogonType == 2`: Console logons.
- `project`: Selects specified columns: `TimeGenerated`, `Account`, `Computer`, `LogonType`, `IpAddress`.




# The query should generate results:

![Screenshot 2024-05-31 at 12 58 17 PM](https://github.com/mahin12/Kusto-Query-Language/assets/27288616/9f4065f2-348d-4617-8289-fcb495afa681)


`SecurityEvent`: This specifies that the query is targeting security-related events.
`| where EventID == 4624`: This filters the events to only include those with an Event ID of 4624, which corresponds to a successful account logon event1.
`| where AccountType == "User" and LogonType == 2`: This further filters the results to only include logon events by user accounts (as opposed to system accounts) and where the logon type is 2, which indicates an interactive logon. This means the user has logged on directly at the machine, such as at the console or via Remote Desktop2.
`| project TimeGenerated, Account, Computer, LogonType, IpAddress`: This part of the query specifies which fields to display in the results. It projects the time the event was generated, the account name, the computer name, the logon type, and the IP address from which the logon occurred.


So, this query is used to extract details about all interactive logon events by user accounts, showing when they occurred, who logged on, to which computer, the logon type, and the originating IP address. This can be useful for security auditing and monitoring purposes.

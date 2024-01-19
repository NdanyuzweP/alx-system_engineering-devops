### 0x19. Postmortem
Duration:
Start Time: January 19, 2024, 10:30 AM (UTC)
End Time: January 19, 2024, 2:45 PM (UTC)
Impact:
Service Affected: User Authentication and Authorization
User Experience: Users were unable to log in or access secured features.
User Affected: Approximately 30% of the total user base.
Timeline:

Detection Time:
January 19, 2024, 10:30 AM (UTC)
Detection Method:
Automated monitoring alerted the DevOps team about an unusual spike in authentication errors.
Actions Taken:
Investigated backend services handling user authentication.
Assumed initial root cause: Database connectivity issues.
Misleading Paths:
Initially focused on the database layer, checking for performance bottlenecks and connectivity problems.
Temporary mitigation implemented to bypass the database, allowing user logins but compromising security.
Escalation:
Incident escalated to the DevOps and Database teams for further investigation.
Resolution:
Identified an authentication service misconfiguration causing excessive database queries.
Implemented a quick fix to correct the misconfiguration, restoring normal service.
Root Cause and Resolution:

Root Cause:
The authentication service was making redundant database queries due to misconfiguration, causing database overload.
Resolution:
Updated authentication service configuration to optimize database queries.
Performed database cleanup to address the temporary data overload.
Conducted thorough testing to ensure the issue was fully resolved.
Corrective and Preventative Measures:

Improvements/Fixes:
Implement stricter code review processes for configuration changes.
Enhance automated monitoring for abnormal query patterns.
Conduct regular audits of critical services' configurations.
Tasks:
Immediate:
Remove the temporary mitigation that bypassed the database for logins.
Communicate with affected users, providing an explanation and assurance.
Short Term:
Conduct a comprehensive review of all critical services for potential misconfigurations.
Enhance the incident response plan to include quicker communication strategies.
Long Term:
Schedule regular training sessions to keep the team updated on best practices in service configurations.
Explore redundancy options to ensure continued service availability during similar incidents.

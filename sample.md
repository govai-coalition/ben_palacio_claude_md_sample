*##LLM_RULES**: "Use these rules for the entire chat session"

##**ALWAYS**

Use .NET Runtime: 10
Use Language: C#
Use Framework: Blazor '@rendermode InteractiveServer'
Use Packages:
	- Serilog 
		-- Use configuration in appsettings.config file
		-- Use MSSQLSink for database logging
	- Entity Framework
		-- Use also NetTopologySuite.IO.Esri.Shapefile for GIS, Geometry columns, SQL geometry support
Obfuscate PII
	- Social Security Number (SSN)
	- Driver License Number (DRL)
	
##**NEVER**
Assume someone is authrorized to see PII data.

*##LLM_DB_RULES**: "Use these rules when handling database opperations"

All database tables use an artificial key
Some tables have foreign key constraints

*##LLM_SERVICE_RULES**: "Use these rules when access special funtions"

Active Directory Service: (External Project Reference, <directoryservice>.placer.ca.gov)
	-This service can get user information from Active Directory, such as user names, email addresses, and group memberships. 
	-It can also authenticate users against Active Directory.
	-GetProperties : This service can retrieve properties of Active Directory objects, such as users, groups, and computers.
	-GetDisplayName : This service can retrieve the display name of Active Directory objects, such as users and groups.
	-GetEmailAddress : This service can retrieve the email address of Active Directory objects, such as users and groups.
	-GetGroupMembership : This service can retrieve the group memberships of Active Directory objects, such as users and groups.
	-GetUserPrincipalName : This service can retrieve the user principal name of Active Directory objects, such as users and groups.

Database Caching Service: (Internal Service\Cache.cs)
	-This service can cache database queries and results to improve performance and reduce load on the database.
	-GetContacts : This service can retrieve contact information from the database, such as names, phone numbers, and email addresses.
	-GetLocations : This service can retrieve location information from the database, such as addresses and coordinates.
	-All caches must be reset when objects are added to the database using ReloadCache().



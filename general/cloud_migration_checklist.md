## Database Migration Checklist

1. How Large is your Database?
2. How many schemas and tables do you have?
3. How many tables do you have over 200 gigabytes or 200 million rows in
size?
4. What do the transaction boundaries look like?
5. Are there engine-specific data types that won’t be migrated by your
migration tool?
6. Do you have LOBs in your tables, and how large are they?
7. Do all your tables with LOBs have primary keys?
8. How busy is your source database?
9. What kind of users, roles, and permissions do you have on the source
database?
10. When was the last time you compacted your database?
11. How can your database be accessed (firewalls, tunnels, VPNs)?
12. Do you know what VPC you want to use in AWS?
13. Do you know what VPC security group you can use?
14. Do you have enough bandwidth to move all your data?
15. Can you afford downtime? How much?
16. Do you need the source database to stay alive after the migration? For
how long?
17. Do you know why you preferred one target database engine over
another?
18. What are your high availability (HA) requirements?
19. Does all the data need to move?
20. Does it need to move to the same place?
21. Do you understand the benefits offered by Amazon RDS?
22. Do you understand any Amazon RDS limitations which might affect
you?
23. What happens to your application after the migration?
24. What is your contingency plan if things go wrong?


# Business/Mission Drivers (8)

Migrating this system to a cloud is driven by the opportunity to …

(or &quot;Migrating this system to the cloud presents opportunities to …&quot;)

|   | Strongly Agree | Agree | Neutral | Disagree | Strongly disagree |
| --- | --- | --- | --- | --- | --- |
| Improve the end-user experience |   |   |   |   |   |
| Avoid cost |   |   |   |   |   |
| Improve value to other applications |   |   |   |   |   |
| Reduce complexity |   |   |   |   |   |
| Improve compliance |   |   |   |   |   |
| Improve functionality |   |   |   |   |   |
| Demonstrate cloud feasibility |   |   |   |   |   |
| Reduce security risk |   |   |   |   |   |

Are there other mission/business drivers that should impact prioritizing this relative to other applications that need to be cloud-ready?

# Mission alignment (3)

Before we apply the SaaS-&gt; PaaS-&gt;IaaS-&gt;Datacenter decision flow, we should first determine if this is something we can wholly outsource, or cease doing entirely.

|   | Strongly Agree | Agree | Neutral | Disagree | Strongly disagree |
| --- | --- | --- | --- | --- | --- |
| We can meet the business drivers by **no longer providing** this functionality or service |   |   |   |   |   |
| We can meet the business drivers by having **some other entity manage** this functionality or service |   |   |   |   |   |
| This a core mission need or a sector differentiator |   |   |   |   |   |

# Generic application considerations (17)

What&#39;s needed for the system to run? Documents like system requirements, installation guide, runbooks, architectural diagrams and so on would be helpful to provide as well.

| Question / Consideration | Response |
| --- | --- |
| Application language or language version |  [Text to balance column width] Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod |
| Current application operating system and version |   |
| Compatible application operating systems and platforms (32/64bit) |   |
| App servers in use (e.g. Liberty, Tomcat, etc)?  Any app server side code? |   |
| Any proprietary server product dependencies? |   |
| Does the **app** require any products to be installed on the server besides .NET/Java IIS/appServer? |   |
| Data stores (DS): Databases, Caching, Messaging Queues, Object stores
Any shared data stores? |   |
| Custom data access techniques (view, triggers, stored procedures) / business logic? |   |
| External integrations: Network calls to via, REST, SOAP, sockets, etc / connections/ authentication means |
| Non-HTTP inbound networking protocols like RMI-IIOP, etc |   |
| Use of Distributed 2-phase-commit/XA Transactions |   |
| Persistent Remote/Local File System Access like NFS or SMB/CIFS or over a SAN? |   |
| Batch/ETL (transaction-based processing) and periodic processes? Are these internal or external? |   |
| Do application admins have a side channel (e.g. a different port or service)? |   |
| Stateless or stateful? How is HTTP session state handled? |   |
| Any non-commodity hardware requirements? |   |
| Requirements for local accounts and UIDs? |   |

**Other notes about the application:**

# COTS considerations (7)

| Question / Consideration | Response |
| --- | --- |
| What versions are installed, how current are they, and when are they EOL&#39;d? | [Text to balance column width] Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod |
| How is the application delivered? Or updates to it (e.g. MSI, WAR) |   |
| Release cycle for patches and upgrades? |   |
| What&#39;s the licensing model? |   |
| How is customization of the application managed? | |
| How is customization versioned-controlled? |   |
| What&#39;s the support model with the vendor? |   |

**Other COTS considerations**

# Locally-developed applications (12)

| Question / Consideration | Response |
| --- | --- |
| Back end application frameworks and APIs in place (e.g. Django, Spring, J2EE, JNDI, …) | [Text to balance column width] Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod |
| Front end client technologies: JSP, JS, Angular, React, ... |   |
| How is code built (ant, maven, …) and packaged (ear, pkg, AMI, …) |   |
| 3rd-party libraries packaged with deployment |   |
| What version control system? |   |
| Continuous integration? |   |
| Test frameworks for unit, integration, load |   |
| % test coverage |   |
| Mock data availability |   |
| How many lines of code?
| How old is the code base? |   |
| Release frequency |   |

**Other notes on application development:**

# Change processes (11)
Gated, multiteam, high-friction infrequently-used change processes indicate a business environment that will add time, expense and risk to rehosting, replatforming or refactoring (if those processes are left unchanged).

| **Question** | **Brief answer** |
| --- | --- |
| What&#39;s the time to enact a minor functional change (e.g change a button color) |  [Text to balance column width] Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod  |
| How many teams/persons are involved in deciding, approving, making and delivering that change? |   |
| What&#39;s the change failure rate? Is that rate OK? |   |
| What&#39;s the time to enact a minor non-functional requirement change (e.g. patch the OS) |    |
| How many teams/persons are involved in deciding, approving, making and delivering that change |   |
| What&#39;s the change failure rate? Is that rate OK? |   |
| How frequently are changes pushed to production? |   |
| What application environments are there (e.g. local, dev, stage, prod)? |   |
| Which teams manage each env? |   |
| How are differences between envs minimized? |   |
| Where are teams located? How do they communicate and plan? |    |

**Other notes on change processes:**

# Business and Operations considerations (14)
| Question / Consideration | Response |
| --- | --- |
| Number of application users? |  [Text to balance column width] Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod  |
How many concurrent or in one day? |   |
| How do you handle user/admin authentication and authorization? |   |
| Is peak demand met? How is the application scaled? |   |
| What are current SLA expectations? How often are downtimes and how are they managed? |   |
| How are configuration changes managed? Is there configuration mgmt (DSC, Chef, Puppet) in place? |   |
| What shared services is it operationally dependent on (that is, it won&#39;t work at all without them?) |   |
|  What&#39;s in place for high-availability? |   |
| How much data do you store? How much of that can be cold storage? | |
|  Backup system and RPO/RTO |   |
| External program personnel (e.g., OCIO ADMINs) that may manage or administer the system/application? |   |
| How are data/configs sync&#39; for continuity of operations? |   |
| Are parts of the system or application already virtualized (e.g., Vmware)? - potentially cloud-ready | |
| Dependency on external systems? |   |
| How much data is being passed to-and-from the system, if known. |   |

**Other notes on business and operations:**

# Security and compliance considerations (7)
Having the System Security Plan (SSP), Interconnection Security Agreements (ISAs), and POAM (Plan of Action and Milestones) available would be useful.


| Question / Consideration | Response |
| --- | --- |
| FISMA impact levels |  [Text to balance column width] Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod  |
| Current ATO status (none, 3yr, provisional) |   |
| How many POAMs are you carrying? |   |
| Main FISMA information types |   |
| How are interconnections secured and managed? (VPN, shared-secret, PKI,...) |   |
| What security tools/agents are in place? How are they licensed? |   |
| Security key management (Windows, or Database pswd mngt) e.g. how would you change database access passwords? |   |

## AWS Whitepapers
https://media.amazonwebservices.com/CloudMigration-main.pdf
https://media.amazonwebservices.com/CloudMigration-scenario-wep-app.pdf
https://www.slideshare.net/AmazonWebServices/aws-migration-planning-roadmap

![image](https://user-images.githubusercontent.com/40743779/188272400-1a5dbcd6-b823-4388-b374-2ec7e14380ec.png)
![image](https://user-images.githubusercontent.com/40743779/188272411-2b4ad464-1cb4-4ff1-ba45-b6d6b1cd9dd0.png)


READ:
https://www.ancoris.com/blog/12-items-cloud-migration-checklist
https://cloud.google.com/resources/cloud-migration-checklist
https://phoenixnap.com/blog/cloud-migration-checklist
https://peoplactive.com/cloud-migration-checklist/
https://medium.datadriveninvestor.com/step-by-step-cloud-migration-checklist-4735b9456802
https://www.techtarget.com/searchcloudcomputing/opinion/What-to-include-on-your-cloud-migrations-checklist

https://aws.amazon.com/blogs/enterprise-strategy/6-strategies-for-migrating-applications-to-the-cloud/
https://docs.aws.amazon.com/prescriptive-guidance/latest/migration-portfolio-discovery/planning.html
https://d1.awsstatic.com/whitepapers/cloud-migration-main.pdf
https://www.youtube.com/watch?v=tB0sAR3aCb4
https://nodeployfriday.com/posts/aws-wordpress-reference-architecture/


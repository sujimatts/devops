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

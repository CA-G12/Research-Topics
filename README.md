# Modify schema of production sql database
Suppose that you haven’t done the schema of your database perfectly and you need to make some changes on it, or you want to add a new feature the needs some operations to be done on the database by altering tables: add column, delete column, rename column, ….etc any change that affects the structure. To update a database in a production environment, you need to do ‘Database migration’ . 

- Migrations help transition database schemas from their current state to a new desired state, whether that involves adding tables and columns, removing elements, splitting fields, or changing types and constraints. We do that using the db-migrate npm package this will automatically create a migration folder where you can write your migration scripts.

- But you have to be aware of the downtime that could happen. This means that the web application might crach for a period of time. Why? This happens for two reasons: 
 
1. Backward incompatibility: a deployment process isn't instant, and at some point, the database is already upgraded, but older application instances are still running in production. If the newer database version is incompatible with the previous application version, it may cause errors and crashes in production until older application instances are fully replaced with newer ones.
2. Heavy DB operations that may slow down the application or make it unresponsive during the DB upgrade.

- How to solve the downtime problem?
By splitting the feature deployment into multiple phases and deploy them one by one, waiting for each phase to deploy completely before moving to the next one. For example when dding a column, a very aggressive lock on the table would occur, which blocks read and write. If you add a column with a default, PostgreSQL will rewrite the whole table to fill in the default for every row, which can take hours on large tables. In the meantime, all queries will block, so your database will be unavailable. The downtime caused by adding a column could be handled by splitting the feature deployment into multiple phases and deploying them one by one, waiting for each phase to deploy completely before moving to the next one. Ex :-
the database migration script only adds a new nullable field and therefore doesn't cause any issues with new records inserted by the previous app version. Then the updated application version is deployed, and the new field becomes populated for all new records.
`NEW COLUMN ADDED WITH ATTRIBUTES NULLABLE →  NEW FEATURE IS ADDED TO APPLICATION  →ATTRIBUTES CHANGED TO NOT-NULL` 


- Resourses: 
[Migiration and downtime](https://teamplify.com/blog/zero-downtime-DB-migrations/).

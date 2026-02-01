## Integrity and Trade-Off Reflection

In the relational design, data integrity is enforced automatically by the database. Primary keys and foreign keys ensure that advising notes and support visits always belong to a valid student. If a student record is deleted or updated, the database can prevent orphaned records or invalid references. This makes relational databases very reliable for official academic records where accuracy and consistency matter most.

In the MongoDB document design, integrity is more flexible but also more fragile. Because advising notes and support visits are embedded inside a student document, there are no built-in foreign key constraints. This means mistakes such as missing fields, inconsistent field names, or incomplete data are possible if the application is not careful. However, embedding related data makes it much easier and faster to view a student’s full support history in one place, which is valuable for advisors.

To protect integrity in MongoDB, responsibility shifts to the application and design practices. Schema validation rules can be used to require certain fields, and developers can follow clear naming conventions to keep documents consistent. Periodic cleanup scripts and application-level checks help prevent bad data over time. This reflects Week 3 concepts such as flexible schemas and the trade-off between strong consistency in relational systems and greater flexibility in document databases.


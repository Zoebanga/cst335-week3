# CST 335 – Week 3: Relational vs MongoDB Modeling

## Scenario Overview
This project models a simple Student Success Hub used by advisors to view student profiles, advising notes, and support visit history. The goal is to compare a traditional relational design with a MongoDB document-based design and understand the trade-offs between structure, flexibility, and data integrity.

---

## Relational Design Summary
The relational design uses separate tables for Students, AdvisingNotes, and SupportVisits. Each advising note and support visit references a student using a foreign key. This design emphasizes strong data integrity and consistency, making it well suited for official academic records and long-term accuracy.

---

## MongoDB Document Design Summary
The MongoDB design uses a `students` collection where advising notes and support visits are embedded directly inside each student document. This allows advisors to quickly retrieve a full student support history with a single query. The design favors flexibility and ease of access over strict enforcement of relationships.

---

## Comparison
The relational model is strongest when correctness and historical accuracy are critical, such as maintaining official records. MongoDB is strongest when flexibility and performance are important, especially when data structures evolve over time. In this scenario, MongoDB simplifies advisor workflows, while relational databases provide stronger guarantees of integrity.

---

## Running the MongoDB Commands
1. Start MongoDB Community Server.
2. Open MongoDB Compass and connect to `mongodb://localhost:27017`.
3. Create the `student_success` database and `students` collection.
4. Open the MongoDB shell inside Compass.
5. Run the commands in `week3_mongo_commands.txt`.
6. Run the queries in `week3_mongo_queries.txt`.

---

## AI Assistance
AI assistance: I used a chat-based AI tool to help clarify MongoDB concepts, troubleshoot setup issues, and refine explanations of integrity and consistency trade-offs.

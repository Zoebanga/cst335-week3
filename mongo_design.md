# MongoDB Document Design - Student Success Hub

## Collections
- students

## Modeling Approach
I will store one document per student in the `students` collection. Each student document will
embed two arrays: `advisingNotes` and `supportVisits`. This matches the main user story:
an advisor opens a student profile and immediately sees notes and support history together.

## Why Embed (Instead of Separate Collections)
1. **Simple reads for advisors:** a single query can return the student profile plus their notes and visits.
2. **Flexible structure:** notes and visits may change over time (new categories or new service types),
   and MongoDB allows us to evolve fields without redesigning tables.
3. **Trade-off:** MongoDB does not automatically enforce foreign keys or required fields the way a relational
   database does, so we must protect integrity using consistent field names and validation rules.

## Sample Student Document
```js
{
  _id: "S1001",
  name: "Afi Felegnan",
  email: "afi.felegnan@university.edu",
  program: "IT",
  advisingNotes: [
    {
      date: ISODate("2025-10-01T00:00:00Z"),
      advisor: "Dr. Smith",
      category: "academic plan",
      text: "Reviewed degree plan and mapped next term courses."
    },
    {
      date: ISODate("2025-10-20T00:00:00Z"),
      advisor: "Dr. Smith",
      category: "well-being",
      text: "Discussed balancing coursework and stress management resources."
    }
  ],
  supportVisits: [
    {
      date: ISODate("2025-10-05T00:00:00Z"),
      service: "Tutoring",
      description: "SQL joins and filters."
    },
    {
      date: ISODate("2025-10-12T00:00:00Z"),
      service: "Workshop",
      description: "Time management workshop."
    }
  ]
}

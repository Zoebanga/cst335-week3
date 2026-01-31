# Relational Desihn - Student Success Hub

## Tables

### Student
- studentID (Primary Key)
- name
- email
-program

### AdvisingNote
- noteID (Primary Key)
- studentID (Foreign Key)
- advisorName
- category
- note_text
- note_date

### SupportVisit
- visitID (Primary Key)
- studentID (Foreign Key)
- service_type
- visit_date
- description

## Relationships
- Advisingnote.studentID ---> Student.studentID
- SupportVisit.studentID ---> Student.studentID

Each student can have many advising notes and many support visits


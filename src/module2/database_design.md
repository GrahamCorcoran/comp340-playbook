# Database Design

> Database Design is about modeling how the actual data required by your system will be stored and retrieved.

Previously, with [domain modeling](./domain_modeling.md), we were thinking about the real-world concepts that our system needed to understand to be implemented. With the database model, we need to start thinking about how these concepts get mapped and stored, and how they relate to each other.

We usually design databases before we start coding specifically so that we can challenge our assumptions about how the pieces will fit together. When thinking at the domain modeling level, it's easy to hand-wave away problems by saying that you'll get to that later. When designing a database, it's much more concrete as you have to connect the various tables together in a way that makes sense, but it can still be changed very easily before anything is concretely implemented.

## Domain Model -> Database Model

When transitioning from a *Domain Model* to a *Database Model*, we will:

- Map Entities to Tables
- Map Attributes to Columns
- Represent Relationships

Representing Relationships is where the main differences between Domain Modeling and Database Modeling show up. In Domain Modeling, we're less concerned with how the relationships themselves *work*, whereas in Database Modeling, we need to represent those relationships via columns or tables as appropriate. A one-to-many relationship might be defined by a foreign key column, while a many-to-many relationship would involve a linking table to connect both sides.

## The Stages of Database Design

When designing a database, it helps to think in layers. We start broad, defining what data needs to exist, and then gradually move toward how it will be implemented. We will describe database design in three stages:

- **Conceptual Design:** focuses on identifying entities and how they relate to one another. This stage answers, "What information do we need to store?"

- **Logical Design:** focuses on organizing that information into a structured form using tables, attributes, and relationships. Here we define things like primary and foreign keys, data types, and constraints.

- **Physical Design:** focuses on performance and implementation details. This is where indexing, storage strategies, and optimization for a specific database engine come in.

By working through these stages in order, we can ensure that our database reflects both the needs of the system and the realities of how it will run in practice. Each stage helps validate the previous one before we commit to code or production.

## Entities, Attributes, and Relationships

A database is made up of three key building blocks: entities, attributes, and relationships.

Entities represent the things we need to keep track of - like Students, Courses, or Instructors. In a relational database, each entity typically becomes a table.

Attributes are the details we want to record about each entity - like a student's name or a course's title. These become columns within the table.

Relationships describe how entities are connected - for example, a Student enrolls in a Course.

Relationships give structure and meaning to the data. Without them, our database would just be a collection of unrelated lists. Representing these connections accurately is one of the most important parts of the design process.

When modeling entities and relationships, think carefully about cardinality (one-to-one, one-to-many, many-to-many) and optionality (whether a relationship must exist). These details determine how your tables and constraints will be defined later.

## Designing with Relationships in Mind

Relationships are what make a database relational. Understanding how to represent them correctly is key to building systems that reflect the real world accurately.

In a one-to-one relationship, each record in one table corresponds to exactly one record in another. For example, a User might have exactly one Profile.
In a one-to-many relationship, one record relates to several others - a Course can have many Enrollments.
In a many-to-many relationship, records on both sides can be connected to many others - a Student can enroll in many Courses, and each Course can have many Students. These relationships require a linking (junction) table to connect them.

To maintain consistency, we use foreign keys - columns that reference primary keys in other tables. Foreign keys enforce referential integrity, ensuring that relationships remain valid even as data changes. Many database systems also let you specify what should happen when a related record is deleted or updated (for example, cascading the change or preventing it).

## Practical Schema Design Considerations

Once you've mapped out your tables and relationships, it's time to make design decisions that affect usability, performance, and maintainability. Some best practices include:

- **Naming conventions:** Use consistent, clear names (e.g., student_id instead of just id when it's a foreign key).

- **Choosing data types:** Pick data types that match how the data will be used - use integers for IDs, dates for timestamps, and strings of reasonable length for text fields.

- **Using constraints wisely:** Apply NOT NULL, UNIQUE, and CHECK constraints to enforce data rules directly in the database.

- **Indexing:** Add indexes to columns that are frequently searched or joined on, but avoid adding too many as they can slow down inserts and updates.

- **Audit fields:** Include created_at, updated_at, and sometimes created_by or updated_by columns for traceability.

- **Avoiding common pitfalls:** Be cautious with NULL values, overly generic column names, or fields that combine multiple pieces of information.

Good schema design is about finding balance - between strictness and flexibility, normalization and performance, simplicity and completeness. A well-designed schema will make your system easier to work with and evolve over time.

```admonish example "In-Class Exercise - Building a Library's Inventory System"
In class, we will expand on our model of a Library's inventory system using [dbdiagram.io](https://dbdiagram.io/d).
```
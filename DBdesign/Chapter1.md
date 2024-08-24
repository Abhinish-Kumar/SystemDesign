## 1st watch an interview of Database Schema design.




### Lets do Schema Design 

## What do you mean by Database Schem design?

In MongoDB, the concept of database schema design differs somewhat from traditional relational databases due to its NoSQL nature. MongoDB is a document-oriented database, meaning that data is stored in flexible, JSON-like documents within collections rather than rigidly structured tables. However, schema design is still crucial for performance, scalability, and data consistency. Here’s what database schema design involves in MongoDB:

### Key Concepts in MongoDB Schema Design

1. **Collections:-**  Analogous to tables in relational databases, collections are containers for documents. However, unlike tables, collections don’t enforce a schema, allowing for flexible data structures within the same collection.
2. **Documents:-** Documents are the basic units of data in MongoDB, stored in BSON (Binary JSON) format. A document is a key-value pair structure, similar to a JSON object. Each document can contain different sets of fields and data types.
3. **Embedded Documents:-** Documents in MongoDB can contain nested, or embedded, documents. This allows for storing related data within a single document, reducing the need for multiple queries or joins (which are typical in relational databases).
4. **References (Links Between Documents):-**
- Manual References: Store the ObjectID (unique identifier) of one document inside another document to create a relationship between them.
- DBRefs: A more standardized way to reference documents across collections, though it's less commonly used due to its complexity compared to manual references.

5. **Schema Design Patterns:-**
- Embedding: Store related data together in a single document. This is useful when data is typically accessed together. It can improve read performance since all related data is in one place.
- Referencing: Store relationships between documents using references. This is useful when related data is large or frequently updated separately, preventing duplication.
- Bucket Pattern: Group data that shares a common attribute into buckets (e.g., storing time-series data).
- Subset Pattern: Store only frequently accessed data in a document and reference less frequently accessed data, optimizing read performance.
- Polymorphic Pattern: Use when documents in a collection share some, but not all, fields (e.g., storing different types of products in a single collection).

6. Indexes
7. Data Modeling Considerations:
8. Aggregation:

# Example Scenarios

## One-to-One Relationship :- 
accessed by parent only.

```json

{
  "_id": 1,
  "name": "John Doe",
  "contactInfo": {
    "email": "john.doe@example.com",
    "phone": "123-456-7890"
  }
}

```

## One-to-Many Relationship:- 
One has data of many items 

```json

{
  "_id": 1,
  "name": "John Doe",
  "orders": [
    { "order_id": 101, "total": 29.99 },
    { "order_id": 102, "total": 49.99 }
  ]
}

```

## Many-to-Many Relationship

```json

// users collection
{
  "_id": 1,
  "name": "John Doe",
  "purchasedProductIds": [10, 20, 30]
}

// products collection
{
  "_id": 10,
  "name": "Product 1",
  "price": 19.99
}

```






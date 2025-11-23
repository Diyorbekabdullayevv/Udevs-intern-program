Part 2: One-to-Many Relationships (1-1.5 hours)

Activity 2.1: Understanding One-to-Many (15 min)
    
Concept: One author can write many blog posts, but each blog post has only one author.

Read about relationships in Ucode docs, then document in relationships-notes.md:

-   What is a One-to-Many relationship?
-   Real-world examples (3-5)
-   How is this stored in the database?

Answers:

-   Screenshot in the screenshots folder

--------------------------------------------------------------------------------------------------------------------------------------------------

Activity 2.2: Create Authors Table (20 min)

-   Create new table: authors
-   Add fields:
    
    *   Field Name	  Type	           Required
    
    *   id	          Auto-increment   Yes
    *   first_name	  String	       Yes
    *   last_name	  String	       Yes
    *   email	      Email	           Yes (Unique)
    *   bio           Text	           No
    *   active	      Boolean	       No

-   Save the table
-   Add 3-5 author records


Answers:

-   Screenshot in the screenshots folder    

--------------------------------------------------------------------------------------------------------------------------------------------------

Activity 2.3: Create the Relationship (25 min)

-   Go back to blog_posts table
-   Add a new field: author_id
    
    -   Type: Many-to-One (or Foreign Key)
    -   Related Table: authors
    -   Display Field: Choose which author field to show

-   Save the configuration
-   Screenshot: screenshots/author_relationship.png

Answers:

-   Screenshot in the screenshots folder

--------------------------------------------------------------------------------------------------------------------------------------------------

Activity 2.4: Test the Relationship (15 min)

-   Create 3 new blog posts
-   Assign each to a different author
-   View an author record - can you see their posts?
-   Edit a blog post - how do you select the author?
-   Document behavior in relationships-notes.md

Answers:

-   Documented in the relationships-notes.md file
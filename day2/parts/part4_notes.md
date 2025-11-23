Part 4: Complete Data Model Design (1 hour)

Activity 4.1: Add Categories Table (15 min)

Extend your blog with categories (different from tags):

-   Create categories table
-   Add fields: id, name, description, slug
-   Add relationship to blog_posts (One-to-Many)
-   Add 4-5 categories:

    -   Web Development
    -   Mobile Development
    -   Data Science
    -   DevOps
    -   Design

Answers:

-   Screenshot in the screenshots folder    

--------------------------------------------------------------------------------------------------------------------------------------------------

Activity 4.2: Add Comments Table (20 min)
Add ability for users to comment on posts:

-   Create comments table
-   Fields:
    
    *   Field Name	   Type	            Required
    
    *   id      	   Auto-increment	Yes
    *   blog_post_id   Many-to-One	    Yes
    *   author_name	   String	        Yes
    *   author_email   Email	        Yes
    *   content        Text             Yes
    *   created_at	   DateTime	        Yes
    *   approved	   Boolean	        No

-   Add relationship to blog_posts
-   Create 3-5 test comments

Answers:

-   Screenshot in the screenshots folder    

--------------------------------------------------------------------------------------------------------------------------------------------------

Activity 4.3: Data Model Diagram (25 min)
Create a complete diagram showing all tables and relationships:

authors (1) ----< (M) blog_posts (M) >----< (M) tags
                       |
                       | (1)
                       |
                       v (M)
                     comments
                       
                 blog_posts (M) >---- (1) categories

Tasks:

-   Draw this diagram (digital or hand-drawn, then photographed)
-   Label each relationship type (One-to-Many, Many-to-Many)
-   Save as: diagrams/blog-data-model.png
-   In data-model.md, explain each table's purpose

Answers:

-   Documented in the data-model.md file   
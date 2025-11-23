Part 3: Many-to-Many Relationships (1.5 hours)

Activity 3.1: Understanding Many-to-Many (15 min)

Concept: A blog post can have many tags, and a tag can belong to many blog posts.

Document in relationships-notes.md:

-   What is a Many-to-Many relationship?
-   Real-world examples (3-5)
-   Why do we need a junction table?

Answers:

-   Documented in the relationships-notes.md file 

--------------------------------------------------------------------------------------------------------------------------------------------------

Activity 3.2: Create Tags Table (15 min)

-   Create new table: tags
-   Add fields:

    *   Field Name	Type	        Required
     
    *   id	        Auto-increment	Yes
    *   name	    String	        Yes (Unique)
    *   slug	    String	        Yes (Unique)
    *   color	    String	        No

-   Add 8-10 tag records:
    
    -   Technology
    -   Tutorial
    -   News
    -   Review
    -   Opinion
    -   Guide
    -   Tips
    -   Best Practices

Answers:

-   Screenshot in the screenshots folder    

--------------------------------------------------------------------------------------------------------------------------------------------------

Activity 3.3: Create Junction Table (30 min)

Method 1: Manual Junction Table

-   Create table: blog_posts_tags
-   Add fields:

    *   Field Name	   Type	            Required
    *   id	           Auto-increment	Yes
    *   blog_post_id   Many-to-One	    Yes
    *   tag_id	       Many-to-One	    Yes

Method 2: Many-to-Many Field (if Ucode supports)

-   Add field to blog_posts: tags
-   Type: Many-to-Many
-   Related Table: tags

Choose the method available in your Ucode version.
Screenshot: screenshots/many_to_many_setup.png

Answers:

-   Screenshot in the screenshots folder

--------------------------------------------------------------------------------------------------------------------------------------------------

Activity 3.4: Test Many-to-Many (30 min)

-   Go to a blog post
-   Add 2-3 tags to it
-   Go to another blog post
-   Add some of the same tags + different ones
-   View a tag - can you see all posts with that tag?

Document in relationships-notes.md:

-   How do you add multiple tags to a post?
-   How do you view all posts for a tag?
-   What happens if you delete a tag?

Answers:

-   Documented in the relationships-notes.md file
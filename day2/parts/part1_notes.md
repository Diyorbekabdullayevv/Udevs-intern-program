Part 1: Creating Tables (1 hour)

Activity 1.1: Create Your First Table (20 min)

Scenario: You're building a blog system. Start with a blog_posts table.

-   Navigate to Tables section
-   Click "Create New Table"
-   Configure the table:
    
    -   Table Name: blog_posts
    -   Icon: (choose an appropriate icon)

-   Add these fields:

    *   Field Name    Type            Required    Notes
       
    *   id            Auto-increment  Yes         Primary key
    *   title         String/Text     Yes         Max 255 chars
    *   content       Long Text       Yes         Full blog content
    *   published     Boolean         No          Default: false
    *   publish_date  Date            No          When published
    *   views         Integer         No          Default: 0

-   Save the table
-   Screenshot: screenshots/blog_posts_table.png

Answers:

-   Screenshot in the screenshots folder

--------------------------------------------------------------------------------------------------------------------------------------------------

Activity 1.2: Understand Field Types (20 min)

Create a practice table called field_types_demo with one of each type:

*   Field Name	     Field Type	    Purpose

*   text_field	     String	        Short text
*   long_text_field	 Text	        Long content
*   number_field	 Integer	    Whole numbers
*   decimal_field	 Decimal/Float  Prices, measurements
*   boolean_field	 Boolean	    Yes/No, True/False
*   date_field	     Date	        Calendar date
*   datetime_field	 DateTime	    Date + Time
*   email_field	     Email	        Email validation
*   url_field	     URL	        Website links
*   json_field	     JSON	        Structured data

Document in field-types.md:

-   What validation does each type provide?
-   When would you use each type?

Answers:

-   Documented in the field-types.md file

--------------------------------------------------------------------------------------------------------------------------------------------------

Activity 1.3: Field Configuration Options (20 min)

For the blog_posts table, explore these options:

-   Required vs Optional: Make title required
-   Default Values: Set views default to 0
-   Unique Constraint: Should titles be unique?
-   Hidden Fields: Can fields be hidden? 
-   Read-only: Can fields be read-only? 

Document all options in field-config.md

Answers:

-   Documented in the field-config.md file

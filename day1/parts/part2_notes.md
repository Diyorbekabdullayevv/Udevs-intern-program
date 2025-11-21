Part 2: Understanding Your Database (1-1.5 hours)

Activity 2.1: Database Introspection Demo (30 min)
Your mentor will demonstrate:

-   How Ucode connects to a database
-   How tables are automatically detected
-   How field types are mapped
-   Your Task: In notes.md, draw a simple diagram showing: [Your Database] ←→ [Ucode Layer] ←→ [Admin Panel / API]

Explain each component in 1-2 sentences.

Answers:

-   Ucode connects to database via API that is created and managed by the Udevs team. We can easily create and manage tables using the user frinedly UI Ucode and the actual tables are created in the database through the API

--------------------------------------------------------------------------------------------------------------------------------------------------

Activity 2.2: Explore Existing Tables (30 min)
Navigate to the Tables section

-   Pick the products table (or assigned table)
-   Document in table-analysis.md:

    -   Table name
    -   Number of fields
    -   Field types (text, number, boolean, date, etc.)
    -   Required vs optional fields
    -   Any relationships to other tables

Answers: 

-   Given in "table-analysis.md" file

--------------------------------------------------------------------------------------------------------------------------------------------------

Activity 2.3: View Sample Data (30 min)
Click into the products table

-   View existing items (records)
-   Click on one item to see its detail view
-   Screenshot: screenshots/product-detail.png
-   Answer in notes.md: How is data organized? What information can you see?

Answers: 

-   The data is organized in a very understandable way for the user with user-frinedly UI. Field names are defined clearly and field types can be detected just by clicking the button attached to every field. Below that items(rows) are placed in LIFO order. At the end of each row there is a delete button for deleting purposes 
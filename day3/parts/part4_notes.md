Part 4: Field-Level Permissions (1 hour)

Activity 4.1: Understanding Field Permissions (15 min)

Concept: Sometimes users can see a record but not all fields.

Examples:

-   Editors see draft posts but not author email addresses
-   Viewers see published posts but not view counts
-   Moderators see comment content but not IP addresses

Document in field-permissions.md: 3 scenarios where field-level permissions are useful

Answers: 

-   Documented in the field-permissions.md file!

--------------------------------------------------------------------------------------------------------------------------------------------------

Activity 4.2: Configure Field Permissions for Blog Editor (20 min)

For the blog_posts table, Blog Editor role:

-   Can see: all fields
-   Can edit: title, content, tags, category
-   Cannot edit: id, views, published_date
-   Cannot see: (nothing hidden)

Configure these field permissions and document the process.

Answers: 

-   Documented in the field-permissions.md file!

--------------------------------------------------------------------------------------------------------------------------------------------------

Activity 4.3: Configure Field Permissions for Blog Viewer (15 min)

For the blog_posts table, Blog Viewer role:

-   Can see: id, title, content, published_date, category, tags, author
-   Cannot see: views, internal notes (if you added this field)
-   Cannot edit: any fields (read-only)

Screenshot: screenshots/viewer-field-permissions.png

Answers: 

-   Screenshot in the screenshots folder!

--------------------------------------------------------------------------------------------------------------------------------------------------

Activity 4.4: Test Field Permissions (10 min)

Document in field-permissions.md:

-   What happens when a user tries to edit a forbidden field?
-   Can hidden fields be accessed via the API?
-   How do you hide sensitive data?

Answers: 

-   Documented in the field-permissions.md file!
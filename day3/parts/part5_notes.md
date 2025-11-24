Part 5: Creating and Testing Users (1-1.5 hours)

Activity 5.1: Create Test Users (30 min)

Create 4 test users:

User 1: Editor

-   Email: editor@blogtest.com
-   Password: TestPassword123!
-   First Name: Emma
-   Last Name: Editor
-   Role: Blog Editor
-   Status: Active

User 2: Viewer

-   Email: viewer@blogtest.com
-   Password: TestPassword123!
-   First Name: Victor
-   Last Name: Viewer
-   Role: Blog Viewer
-   Status: Active

User 3: Admin

-   Email: admin@blogtest.com
-   Password: TestPassword123!
-   First Name: Alice
-   Last Name: Admin
-   Role: Blog Admin
-   Status: Active

User 4: Moderator

-   Email:  
-   Password: TestPassword123!
-   First Name: Mike
-   Last Name: Moderator
-   Role: Comment Moderator
-   Status: Active

Screenshot: screenshots/test-users.pngl

Answers: 

-   Screenshot in the screenshots folder!

--------------------------------------------------------------------------------------------------------------------------------------------------

Activity 5.2: Test Permission Scenarios (45 min)
For each user, test and document in permission-tests.md:

Test with Blog Editor (editor@blogtest.com):

✓ Can they create a new blog post?
✓ Can they edit an existing blog post?
✗ Can they delete a blog post?
✗ Can they create a new author?
✓ Can they add tags to a post?
Test with Blog Viewer (viewer@blogtest.com):

✗ Can they create a blog post?
✓ Can they view blog posts?
✗ Can they edit comments?
✗ Can they see the users section?
Test with Comment Moderator (moderator@blogtest.com):

✗ Can they edit blog posts?
✓ Can they view comments?
✓ Can they delete comments?
✓ Can they approve/reject comments?
Test with Blog Admin (admin@blogtest.com):

✓ Can they do everything?
Document each test:

What you tested
Expected result
Actual result
Screenshot if relevant

Answers: 

-   Documented in the permission-tests.md file!

--------------------------------------------------------------------------------------------------------------------------------------------------

Activity 5.3: Document Permission Matrix (15 min)
Create a complete permissions matrix in permission-matrix.md:

| Action | Blog Admin | Blog Editor | Comment Moderator | Blog Viewer |
|--------|-----------|-------------|-------------------|-------------|
| Create Post | ✓ | ✓ | ✗ | ✗ |
| Edit Post | ✓ | ✓ | ✗ | ✗ |
| Delete Post | ✓ | ✗ | ✗ | ✗ |
| View Posts | ✓ | ✓ | ✓ | ✓ |
| ... (complete this) |

Answers: 

-   Completed document in the permission-matrix.md file!

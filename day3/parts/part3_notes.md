Part 3: Configuring Table Permissions (1 hour)

Activity 3.1: Configure Blog Editor Permissions (20 min)

-   Select the "Blog Editor" role
-   Go to Permissions or Table Permissions section
-   Configure permissions for each table:

        Table	    Create	Read   Update	    Delete
       
        blog_posts	   ✓	 ✓	    ✓	         ✗
        authors	       ✗	 ✓	    ✓(own only)	 ✗
        categories	   ✗	 ✓   	✗	         ✗
        tags	       ✓	 ✓	    ✓	         ✗
        comments	   ✓	 ✓	    ✓	         ✓ 

-   Save configuration
-   Screenshot: screenshots/blog-editor-permissions.png

Answers: 

-   Screenshot in the screenshots folder!

--------------------------------------------------------------------------------------------------------------------------------------------------

Activity 3.2: Configure Blog Viewer Permissions (15 min)

        Table	    Create	  Read	  Update	Delete
        blog_posts	  ✗	       ✓	   ✗	     ✗
        authors	      ✗	       ✓       ✗	     ✗
        categories	  ✗  	   ✓       ✗         ✗
        tags	      ✗	       ✓	   ✗	     ✗  
        comments	  ✗	       ✓	   ✗         ✗

-   Apply and save.

Answers: 

-   Screenshot in the screenshots folder!

--------------------------------------------------------------------------------------------------------------------------------------------------

Activity 3.3: Configure Blog Admin Permissions (10 min)

Grant Full Access to all blog-related tables.

Answers: 

-   Screenshot in the screenshots folder!

--------------------------------------------------------------------------------------------------------------------------------------------------

Activity 3.4: Configure Comment Moderator Permissions (15 min)

        Table	   Create	Read   Update	Delete
        
        blog_posts	 ✗	     ✓	    ✗	     ✗  
        comments	 ✗	     ✓	    ✓	     ✓
        authors	     ✗     	 ✓	    ✗	     ✗

-   Apply and save.

Answers: 

-   Screenshot in the screenshots folder!
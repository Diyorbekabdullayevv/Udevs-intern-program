Part 1: Understanding Ucode API

Activity 1.1: API Architecture 

Answer these questions:

-   What is a REST API?
-   What are the main HTTP methods and what do they do?
-   Why do APIs use JSON?
-   What's the difference between PUT and PATCH?

Answers:

-   REST API is a connection system between clients and the server! 
-   Main HTTP methods are GET, POST, PUT, PATCH and DELETE. They define the type of action that clients can make. With GET method clients can read data and with POST method clients can insert information to a certain application and create items! 
-   Because JSON is the most popular and most efficient data format. It is lighweight, easy to understand and many other tools support JSON(ex.: encoding/json package in Go)
-   With PUT method we can only update all the columns in the entire row and with PATCH we can update the columns we want, not all, not necesseraly!
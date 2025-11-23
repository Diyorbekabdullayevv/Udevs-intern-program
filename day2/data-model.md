Blog posts table is the central table that holds all the tables togather

blog_posts ---> authors || Many2one relationship : many posts belong to one author, but many author can not have the same post
blog_posts ---> tags || Many2Many relationship : many post can have many tags and many tags can belong to many posts too
categories ---> posts || One@Many : one category can have many posts but one post can not belong to many categories
comments ---> posts || One2Many : one post can have many posts but many posts can not have one comments

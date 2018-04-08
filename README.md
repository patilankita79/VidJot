# VidJot
An application developed using NodeJS, Express and MongoDB<br>
### Description
An application for content creators, YouTubers to register and jot down ideas for their upcoming videos. Video ideas are private and therefore only logged in users can see their own ideas
<br>
### Technology Stack
- Express
- Mongoose
- Local MongoDB for local enviornment
- mlab 
- Passport for authetication
- Bcyrpt for password encryption
- Express-session
- Handlebars
- Bootstrap 4

<hr>

## Approach

1. **Create Package.json file** 
   
      ```
       npm init
      ```
   
      - Install Express and create a server
   
        ```
         npm install express --save
        ```
  
      - Creating basic routes such as, /,  /about, etc.
        
  
      - Adding express middlewares
         - More information -> https://expressjs.com/en/guide/using-middleware.html
    
      - Adding Express-Handlerbars which is a templating engine
         - More information -> https://github.com/ericf/express-handlebars

        ```
         npm install express-handlebars --save
        ```
        
         By default, Express uses views directory to render views and hence views directory needs to be created and inside the views   directory, templates can be stored. We can pass dynamic data into views
   
         ```
           const exphbs  = require('express-handlebars');
           const path = require('path');

           // Handlebars Middleware
           app.engine('handlebars', exphbs({
              defaultLayout: 'main',
              layoutsDir: path.resolve(__dirname, 'views/layouts')
          }));
         app.set('views',path.resolve(__dirname,'./views'));
         app.set('view engine', 'handlebars');
         ```
   
   - Creating partials with handlebars
      - partial is created for navigation bar
 
 2. **Database**
   
   - Install mongoose
     ```
      npm install mongoose --save
     ```
   
 3. **Creating Models**
   
      - Creating a model named Idea. This model will consist of **title** which is of type String, **details** which is of type String, **Date** which is of type Date
      
      - Adding routes for models
         - /ideas
         - /ideas/add
       
       - Install body-parser (With body parser we can access whatever we have submitted i.e. we get access to form values)
         ```
            npm install body-parser --save
          ```
   4. **Handling the Idea form submission**
      - Saving the title and details of an idea to MongoDB
      - Performing CRUD operations on an Idea 
      
         ```
          npm install method-override --save
         ```
         
       - Implementing flash messages -> to give flash message when user adds or deletes an idea
         https://github.com/jaredhanson/connect-flash
         ```
            npm install connect-flash --save
         ```
         
        
         https://github.com/expressjs/session

         ```
            npm install express-session --save
         ```
<hr>

## Problems encountered

1. No such file or directory (When I was using Handlebars)
   - Solution: https://github.com/ericf/express-handlebars/issues/195
   
<hr>

## References: <br>

- https://cloudfour.com/thinks/the-hidden-power-of-handlebars-partials/

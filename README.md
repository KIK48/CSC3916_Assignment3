
[<img src="https://run.pstmn.io/button.svg" alt="Run In Postman" style="width: 128px; height: 32px;">](https://app.getpostman.com/run-collection/51944629-12b9f6f6-43c4-4acd-87d9-ac0cd2b443cc?action=collection%2Ffork&source=rip_markdown&collection-url=entityId%3D51944629-12b9f6f6-43c4-4acd-87d9-ac0cd2b443cc%26entityType%3Dcollection%26workspaceId%3Da3ef2224-269b-4db5-aa56-7388bd526502#?env%5Bperezalvarez_HW3%5D=W3sia2V5IjoidXJsIiwidmFsdWUiOiIiLCJlbmFibGVkIjp0cnVlLCJ0eXBlIjoiZGVmYXVsdCIsInNlc3Npb25WYWx1ZSI6Imh0dHBzOi8vY3NjMzkxNi1hc3NpZ25tZW50My1keWVwLm9ucmVuZGVyLmNvbSIsImNvbXBsZXRlU2Vzc2lvblZhbHVlIjoiaHR0cHM6Ly9jc2MzOTE2LWFzc2lnbm1lbnQzLWR5ZXAub25yZW5kZXIuY29tIiwic2Vzc2lvbkluZGV4IjowfSx7ImtleSI6InRva2VuIiwidmFsdWUiOiIiLCJlbmFibGVkIjp0cnVlLCJ0eXBlIjoiZGVmYXVsdCIsInNlc3Npb25WYWx1ZSI6IkpXVC4uLiIsImNvbXBsZXRlU2Vzc2lvblZhbHVlIjoiSldUIGV5SmhiR2NpT2lKSVV6STFOaUlzSW5SNWNDSTZJa3BYVkNKOS5leUpwWkNJNklqWTVZV1kyTXpVNVlqa3lOREZsTTJObU9EVmlZalU1TXlJc0luVnpaWEp1WVcxbElqb2ljM1IxWkdWdWRERkFaMjFoYVd3dVkyOXRJaXdpYVdGMElqb3hOemN6TWpBNU5EQXlMQ0psZUhBaU9qRTNOek15TVRNd01ESjkuaDhyUC1ZbVJ3Rnk3YUdadHJQSVQyRVA1aDllSVNFWEt6bUEzWUZUTERYVSIsInNlc3Npb25JbmRleCI6MX1d)

# Assignment Three
## Purpose
The purpose of this assignment is to get comfortable working with a NoSQL database (MongoDB). 

For this assignment you will create a Users collection to store users for your signup and signin methods.  You will pass Username, Name and Password as part of signup.  To get a token you will call SingIn with username and password only.  The token should include the Name and UserName (not password)

You will also create Movies collection to store information about movies.  All endpoints will be protected with the JWT token received by a signin call. 

## Requirements
Create a collection in MongoDB to hold information about movies
- Each entry should contain the following
    - title (string, required, index)
    - releaseDate
    - genre (Action, Adventure, Comedy, Drama, Fantasy, Horror, Mystery, Thriller, Western, Science Fiction)
    - Array of three actors that were in the film
        - actorName
        - characterName
    - The movie collection should have at least five movies
- Create a NodeJS Web API to interact with your database
    - Follow best practices (e.g. /movies collection)
    - Your API should support all CRUD operations (through HTTP POST, PUT, DELETE, GET)
    - Ensure incoming entities contain the necessary information.  For example if the movie does not contain actors, the entity should not be created and an error should be returned 
- All endpoints should be protected with a JWT token (implement signup, and signin)
    - For this assignment you must implement a User database in Mongo
        - name
        - username 
        - password (should be hashed)
    - If username exists the endpoint should return an error that the user already exists
    - JWT secret needs to be stored in an environment variable
- Update the Pre-React CSC3916_REACT placeholder project to support /signup and /signin methods.  The React Single Page App should use your Assignment 3 API to support those two operations.

## Submissions
- All source code should be stored on github (remember .gitignore for node_modules)
- API needs to be deployed to heroku or render
- React Website that allows user to signup and singin (we did this in class)
- PostMan test collection that 
    - Signs Up a user (create a random user name and random password in your pre-test)
    - SignIn a User – parse token and store in postman environment variable
    - A separate call for each endpoint (save a movie, update a movie, delete a movie and get a movie)
    - Test error conditions (user already exists)
        - SignUp (user already exist)
        - Save Movie (missing information like actors (must be at least three), title, year or Genre)

- Create a readme.md at the root of your github repository with the embedded (markdown) to your test collection
    - Within the collection click the (…), share collection -> Embed
    - Static Button
    - Click update link
    - Include your environment settings
    - Copy to clipboard 
- Submit the Url to canvas with the REPO CSC_3916
- Note: All tests should be testing against your Heroku or Render endpoint

| Route | GET | POST | PUT | DELETE |
| --- | --- | --- | --- | --- |
| movies | Return all movies| save a single movie | FAIL | FAIL |
| movies/:movieparameter | Return a specific movie based on the :movieparameter | FAIL | Update the specific movie based on the :movieparameter in your case it’s the title | Delete the specific movie based on the :movieparamters your case it’s the title |*

* If Query String (Later Homework) reviews=true aggregate in reviews |

## Rubic
- -5 for missing REACT site (-2 if you are not able to signup or signin on the react site) that is all we implemented
- -1 for MovieSchema missing any of the attributes (array of actors, genre, year released or title)
- -2 for missing routes for /movies (POST/PUT/DELETE/GET)
- -1 for missing authentication on routes
- -2 for not deployed on Heroku/Render
- -1 missing Test error conditions
- -1 missing PostMan tests (signup, signin, separate call for each route)

## Resources
- https://www.mongodb.com/cloud/atlas
- Create a Free Subscription *Amazon
- https://render.com/docs/deploy-create-react-app **important: Environment Variable for https://github.com/AliceNN-ucdenver/CSC3916_REACT env.REACT_APP_API_URL, this weekend I will look at changes (I believe only 1 change in the actions)

[<img src="https://run.pstmn.io/button.svg" alt="Run In Postman" style="width: 128px; height: 32px;">](https://app.getpostman.com/run-collection/51944629-12b9f6f6-43c4-4acd-87d9-ac0cd2b443cc?action=collection%2Ffork&source=rip_markdown&collection-url=entityId%3D51944629-12b9f6f6-43c4-4acd-87d9-ac0cd2b443cc%26entityType%3Dcollection%26workspaceId%3Da3ef2224-269b-4db5-aa56-7388bd526502#?env%5Bperezalvarez_HW3%5D=W3sia2V5IjoidXJsIiwidmFsdWUiOiIiLCJlbmFibGVkIjp0cnVlLCJ0eXBlIjoiZGVmYXVsdCIsInNlc3Npb25WYWx1ZSI6Imh0dHBzOi8vY3NjMzkxNi1hc3NpZ25tZW50My1keWVwLm9ucmVuZGVyLmNvbSIsImNvbXBsZXRlU2Vzc2lvblZhbHVlIjoiaHR0cHM6Ly9jc2MzOTE2LWFzc2lnbm1lbnQzLWR5ZXAub25yZW5kZXIuY29tIiwic2Vzc2lvbkluZGV4IjowfSx7ImtleSI6InRva2VuIiwidmFsdWUiOiIiLCJlbmFibGVkIjp0cnVlLCJ0eXBlIjoiZGVmYXVsdCIsInNlc3Npb25WYWx1ZSI6IkpXVC4uLiIsImNvbXBsZXRlU2Vzc2lvblZhbHVlIjoiSldUIGV5SmhiR2NpT2lKSVV6STFOaUlzSW5SNWNDSTZJa3BYVkNKOS5leUpwWkNJNklqWTVZV1kyTXpVNVlqa3lOREZsTTJObU9EVmlZalU1TXlJc0luVnpaWEp1WVcxbElqb2ljM1IxWkdWdWRERkFaMjFoYVd3dVkyOXRJaXdpYVdGMElqb3hOemN6TWpBNU5EQXlMQ0psZUhBaU9qRTNOek15TVRNd01ESjkuaDhyUC1ZbVJ3Rnk3YUdadHJQSVQyRVA1aDllSVNFWEt6bUEzWUZUTERYVSIsInNlc3Npb25JbmRleCI6MX1d)
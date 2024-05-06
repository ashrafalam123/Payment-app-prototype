# Working model of a Banking website using MERN stack

## Backend

# Database

**MongoDB :** Linked my mongoDB account locally to store 2 datas 
- User : The personal information of the user
- Account : The account balance corresponding to the particular user

  Then these 2 databases were joined with the criteria on user id that is created in the mongoDB database

# Routing

**Express :** Used the express library to create router and send neccessary requests to corresponding routes. There were 2 routes created -- one that handles the _user_ requests and another 
that handles the _account_ requests. This was done in order to reduce the load on each router and additionally if any subsequent versions are created then the previous version will still run
provided we add an additional router

# MiddleWares

To ensure that access is given to only existing users and no false users enter the page, middlewares were used to provide authorization.

# Session

Since the model is sensitive to Mutex locks, i.e. there is a possibility that one part of code gets executed and one doesn't and the consequence of this operation is huge, it can prove to 
be costly to either the user or the bank. To resolve this the operation is made atomic. If interrupted due to any reason the system is reset to initial stage.

## Frontend

The Frontend has 4 pages and currently doesn't have any home page to redirect to other pages.
- Signup : New users can create an account an they are given an initial random amount between 0 - 100000
- Signin : Existing users can log in to their account and use the features
- Dashboard : Once signed in the user is redirected to the dashboard where he can also search for other users using the **Search Bar** and send money to them
- SendMoney : This page is used for the transactions and is passed the token for authorisation

There is also logic applied to store the token after signing in, in the local storage of the system, which can ideally also be removed by adding this function on the sign out button.
```
  localStorage.removeItem("token")
```

There are many more functionalities which can be added to make this better but this was an initial attempt to recreate a transaction app.

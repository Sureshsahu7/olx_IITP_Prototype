# olx_IITP_Prototype

🔳 **BHEJO APP** 🔳 

 This Website is basic prototype based on idea of OLX application.
 Created an IIT Patna version of OLX.com, that is, an E-commerce website where students can sell or buy used items, to other students.
 
 
## View live App

Hosted at **https://concerned-gray-reindeer.cyclic.app/**
 
## User Permissions

### Student

A student can

* register himself on the app
* provide various details like facebook profile, email, phone number, room no. for contact
* view and edit his profile
* edit privacy settings (whether to include his contact number and room no. of hostel)
* change his password
* search for various products and contact the concerned student for buying it
* upload details of a product to be sold online (to be verified by admin)
* turn on bidding for a product, he/she sells
* view bidding history of a product, he/she sells and turn bidding off, if he wants to fix the price.
* edit the products he has uploaded
* mark some of his products as *favorites*
* delete a product when it is sold
* bid some amount for a product he likes (But this is just to get listed in the owner's view and there is nothing like verification of account details, so it may also happen that a person can bid an amount that is less than the highest bid done. This is to ensure that all get a fair chance of bidding and no fake bids can rise issues.)
* edit his bid
* view bid history of a product he owns

### Admin

An admin can

* view and edit his profile
* approve a product (if admin flags as appropriate then only,
all users will be able to see that product online. This is to ensure that no fake or obscene images are uploaded as well as no vulgar language is used )
* mark some of his products as *favorites*

When a user logs in and views the detail of a product, the number of views of that product increases by 1. In this way, the top 3 products with the maximum number of views are displayed on the home page.

## Built with 

### The MERN Stack

* [![MongoDb][mongo.com]][mongo-url]
* [![Express][express.com]][express-url]
* [![ReactJs][react.com]][react-url]
* [![NodeJs][nodejs.com]][nodejs-url]

### Other

* [![Heroku][h.com]][h-url]
* [![Bootstrap][Bootstrap.com]][Bootstrap-url]
* [![Redux][r.com]][r-url]
* [![Javascript][Js.com]][Js-url]

## SETUP

### Setting up server and database

1. Initialise a package.json file by entering the following command in terminal, after getting into the project directory :

```(bash)
npm init
```

2. Install npm packages required for backend side :

```(bash)
npm i express body-parser mongoose concurrently
npm i -D nodemon
```

3. Create a file server.js to make use of the express packages 

4. Modify the package.json by adding the following scripts to it :

```(JSON)
  "start": "node server.js",
  "server": "nodemon server.js",
```

5. Create an account on MongoDB cloud Atlas, thereafter, creating a database on it and get your MongoURI exported from a file keys.js in a folder config

6. Modify server.js to get connected to the database, using the MongoURI and also add the following lines at the end of server.js :

```(JavaScript)
const port = process.env.PORT || 5000;
app.listen(port, ()=> console.log(`Server started running on port ${port}`));
```

7. Type the following command to get your server running on your localhost and ensure hot-reloading, when the server-side code is modified :

```(bash)
npm run server
```

8. Make Schemas for various collections to be stored in database and export them from a folder models and the REST APIs for various routes in the folder routes. Change the server.js accordingly to make the use of these REST APIs. Ensure that the APIs are working correctly, by making requests using POSTMAN

### Setting up the React client

1. Create a folder 'client' in the project directory. Ensure that you have create-react-app CLI installed. Enter the following commands in terminal :

```(bash)
cd client
create-react-app .
cd ..
```

2. Firstly, delete the .git folder in client. Secondly, in the package.json of the server, add the following scripts :

```(JSON)
"client-install": "npm install --prefix client",
"client": "npm start --prefix client",
"dev": "concurrently \"npm run server\" \"npm run client\" ",
```

3. Remove all the additional default setup from client folder like logo, index.css, etc. Then, configure the client to make use of *bootstrap* and *reactstrap* to make the app responsive by using following commands in terminal :

```(bash)
cd client
npm i bootstrap reactstrap react-popper font-awesome bootstrap-social
```

Add the following line to index.js :

```(JavaScript)
import 'bootstrap/dist/css/bootstrap.min.css
```

4. Install Redux for maintaining the state :

```(Terminal)
npm i redux react-redux redux-thunk
```

5. Create a redux store, the various actions and reducers required in a folder named redux. Make corresponding changes in the React components to map the actions and state to props

## Deployment

Install Heroku CLI and make sure you have intialised a git repository in the project directory. Enter the following commands in the terminal :

```(bash)
heroku login
heroku create
git add .
git commit -am "Deployed to Heroku"
git push heroku master
```

Open your heroku account and click on **Open App** option in the dashboard.


<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/github_username/repo_name.svg?style=for-the-badge
[contributors-url]: https://github.com/github_username/repo_name/graphs/contributors

[Bootstrap.com]: https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white
[Bootstrap-url]: https://getbootstrap.com
[mongo.com]: https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white
[mongo-url]: https://mongodb.com
[express.com]: https://img.shields.io/badge/Express.js-404D59?style=for-the-badge
[express-url]: https://express.com
[react.com]: https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB
[react-url]: https://react.com
[nodejs.com]: https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white
[nodejs-url]: https://nodejs.com
[css.com]:https://img.shields.io/badge/CSS-239120?&style=for-the-badge&logo=css3&logoColor=white
[css-url]: https://css.com
[html.com]: https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white
[html-url]:	https://html.com
[Js.com]: https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black
[Js-url]: https://javascript.com
[python.com]: https://img.shields.io/badge/Python-14354C?style=for-the-badge&logo=python&logoColor=white
[python-url]: https://python.com
[flask.com]: https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white
[flask-url]: https://flask.com
[h.com]: 	https://img.shields.io/badge/Heroku-430098?style=for-the-badge&logo=heroku&logoColor=white
[h-url]: https://heroku.com
[r.com]: 	https://img.shields.io/badge/Redux-593D88?style=for-the-badge&logo=redux&logoColor=white
[r-url]: https://heroku.com
	

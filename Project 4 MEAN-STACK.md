# MEAN-STACK
## What is Mean Stack
**MEAN stands for:** 
* MongoDB 
* Express.js 
* AngularJS 
* Node.js. 

**MEAN is an end-to-end JavaScript stack largely used for cloud-ready applications. MEAN is a full-stack development toolkit which is also refer to as a collection of JavaScript technologies used to develop web applications from the client to the server and from server to database, everything is based on JavaScript. It is also free and open-source stack which offers a quick and organized method for creating rapid prototypes for web-based applications.**


## MEAN STACK is comprised of four different technologies:
* **M**ongoDB (Document database): Stores and retrieve data.
* **E**xpress JS (Back-end application framework): Makes requests to Database and return a response
* **A**ngularJS (Front-end application framework): Handles Client and Server Requests
* **N**ode.js (JavaScript runtime environment): Accept requests and display results to end user


![image](https://user-images.githubusercontent.com/85270361/129397413-e9948fc7-f02c-4ff2-a527-bab8e9072f41.png)


**There are variations to the MEAN stack such as MERN (replacing Angular.js with React.js) and MEVN (using Vue.js). The MEAN stack is one of the most popular technology concepts for building web applications.**

# How Does the MEAN Stack Work?

## MEAN Stack Architecture
The MEAN architecture is designed to make building web applications in JavaScript and handling JSON incredibly easy.

![image](https://user-images.githubusercontent.com/85270361/129397323-0d4d8820-0aa0-4476-ab59-fc96e700df2e.png)


# MEAN Stack Components

## MongoDB

**MongoDB** is an open source, NoSQL database designed for cloud applications. It uses object-oriented organization instead of a relational model. It stores data in the key-value pair, using binary data type like JSON. MongoDB is an ideal choice for a database system where we need to manage large sized tables with millions of data. Moreover, including a field to MongoDB is easier as it does not require updating the entire table. With MongoDB we can develop an entire application with just one application which is JavaScript.


## Express

**Express** is a mature, flexible, lightweight server framework. It is designed for building single, multi-page, and hybrid web applications. This lightweight framework uses the Pug engine to provide support for templates. Express is a web application framework for Node.js. It handles all the interactions between the frontend and the database, ensuring a smooth transfer of data to the end user.


## Angular

**Angular** JS is an open-source JavaScript framework and it is maintained by Google. The goal of this framework is to introduce MVC(Model View Controller) architecture in the browser-based application that makes the development and testing process easier. The framework helps us create a smarter web app that supports personalization.
AngularJS allows us to use HTML as a template language. Therefore, we can extend HTML's syntax to express the components of our application. Angular features like dependency injection and data binding eliminate plenty of code that we need to write.


## Node.js

**Node.js** is an open source JavaScript framework that uses asynchronous events to process multiple connections simultaneously. It allows developers to create web servers and build web applications on it. It's a server-side Javascript execution environment and also an ideal framework for a cloud-based application, as it can effortlessly scale requests on demand.
Node.js uses a non-blocking and event-driven I/O model. This makes it lightweight and efficient, perfect for data-intensive real-time applications that run across distributed devices. We’re likely to find Node.js behind most well-known web presences.


![image](https://user-images.githubusercontent.com/85270361/129399038-47e15f55-ba45-4b6c-9e1d-252416e48476.png)


# MEAN STACK USE CASES

**While the MEAN stack isn’t perfect for every application, there are many uses where it excels. It’s a strong choice for developing cloud native applications because of its scalability and its ability to manage concurrent users. The AngularJS frontend framework also makes it ideal for developing single-page applications that serve all information and functionality on a single page. Here are a few examples for using MEAN:**

* Calendars
* Expense tracking
* News aggregation sites
* Mapping and location finding


![image](https://user-images.githubusercontent.com/85270361/129399664-96bdd361-8839-4893-a685-9a68b32be97d.png)


# In this Project we are going to deploy a web based application on our Linux server using MEAN STACK with the following steps.

# Step 0 – Preparing prerequisites

In order to complete this project you will need an AWS account and a virtual server with Ubuntu Server OS.

If you do not have an AWS account – go back to Project 1 Step 0 to sign in to AWS free tier account ans create a new EC2 Instance of t2.nano family with Ubuntu Server 20.04 LTS (HVM) image.


# Step1: Install NodeJs

## Task
In this assignment you are going to implement a simple Book Register web form using MEAN stack.

## We will install nodejs on our server

Node.js is a JavaScript runtime built on Chrome’s V8 JavaScript engine. Node.js is used in this tutorial to set up the Express routes and AngularJS controllers.

**Update ubuntu**

```
sudo apt update
```

**Upgrade ubuntu**

```
sudo apt upgrade
```

**Install NodeJS**

```
sudo apt install -y nodejs
```

# Step 2: Install MongoDB

**MongoDB stores data in flexible, JSON-like documents. Fields in a database can vary from document to document and data structure can be changed over time. For our example application, we are adding book records to MongoDB that contain book name, isbn number, author, and number of pages.**

* **Run these commands:**

```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 0C49F3730359A14518585931BC711F9BA15703C6
```

**OUTPUT:

<img width="516" alt="mean 1" src="https://user-images.githubusercontent.com/85270361/129403387-44891a56-7aca-4b46-b631-f8e187abbb8e.PNG">


```
echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.4.list
```

**OUTPUT:

<img width="510" alt="mean 2" src="https://user-images.githubusercontent.com/85270361/129403566-bfb6399d-ef96-45c9-8c17-e9bb81c56e7f.PNG">


## Install MongoDB

```
sudo apt install -y mongodb
```

**Start The server**

```
sudo service mongodb start
```

**Verify that the service is up and running**

```
sudo systemctl status mongodb
```

**OUTPUT:

<img width="509" alt="mean 3" src="https://user-images.githubusercontent.com/85270361/129404256-7ccfe8c9-da18-4450-a687-4f97c92c7fff.PNG">


Install [npm](https://www.npmjs.com) – Node package manager.

```
sudo apt install -y npm
```

## Install ‘body-parser package

We need ‘body-parser’ package to help us process JSON files passed in requests to the server.

```
sudo npm install body-parser
```

**OUTPUT:**

<img width="522" alt="mean 4" src="https://user-images.githubusercontent.com/85270361/129405770-b37c76ce-328c-4fc7-83cd-eab867c4a799.PNG">


**Create a folder named ‘Books’**

```
mkdir Books && cd Books
```

**In the Books directory, Initialize npm project**

```
npm init
```

**OUTOUT:**

<img width="436" alt="mean 5" src="https://user-images.githubusercontent.com/85270361/129406606-ba6c7afe-52d6-4b68-8a13-fb2012d07286.PNG">


**Add a file to it named server.js**

```
touch server.js
```

```
vi server.js
```

**Copy and paste the web server code below into the server.js file.**

```
var express = require('express');
var bodyParser = require('body-parser');
var app = express();
app.use(express.static(__dirname + '/public'));
app.use(bodyParser.json());
require('./apps/routes')(app);
app.set('port', 3300);
app.listen(app.get('port'), function() {
    console.log('Server up: http://localhost:' + app.get('port'));
});
```

**OUTPUT:**

<img width="494" alt="mean vi 5" src="https://user-images.githubusercontent.com/85270361/129407042-255a2e61-97e7-448e-9d3e-7f59e3a3f3e1.PNG">



# Step 3: Install Express and set up routes to the server

**Express is a minimal and flexible Node.js web application framework that provides features for web and mobile applications. We will use Express in to pass book information to and from our MongoDB database.**

**We also will use Mongoose package which provides a straight-forward, schema-based solution to model your application data. We will use Mongoose to establish a schema for the database to store data of our book register.**


```
sudo npm install express mongoose
```

**OUTPUT:**

<img width="511" alt="mean 6 monagoos" src="https://user-images.githubusercontent.com/85270361/129410973-36827a0b-14b2-462f-b7a5-b151a84ceab9.PNG">


**In ‘Books’ folder, create a folder named apps**

```
mkdir apps && cd apps
```

**Create a file named routes.js**


```
touch routes.js
```

```
vi routes.js
```

**Copy and paste the code below into routes.js**


```
var Book = require('./models/book');
module.exports = function(app) {
  app.get('/book', function(req, res) {
    Book.find({}, function(err, result) {
      if ( err ) throw err;
      res.json(result);
    });
  }); 
  app.post('/book', function(req, res) {
    var book = new Book( {
      name:req.body.name,
      isbn:req.body.isbn,
      author:req.body.author,
      pages:req.body.pages
    });
    book.save(function(err, result) {
      if ( err ) throw err;
      res.json( {
        message:"Successfully added book",
        book:result
      });
    });
  });
  app.delete("/book/:isbn", function(req, res) {
    Book.findOneAndRemove(req.query, function(err, result) {
      if ( err ) throw err;
      res.json( {
        message: "Successfully deleted the book",
        book: result
      });
    });
  });
  var path = require('path');
  app.get('*', function(req, res) {
    res.sendfile(path.join(__dirname + '/public', 'index.html'));
  });
};
```


**OUTPUT:**

<img width="519" alt="mean 7" src="https://user-images.githubusercontent.com/85270361/129411341-d8b40718-358c-4494-b086-b01cab7cc353.PNG">



**In the ‘apps’ folder, create a folder named models**

```
mkdir models && cd models
```

**Create a file named book.js**

```
touch book.js
```

```
vi book.js
```

**OUTPUT:**

<img width="501" alt="mean 8" src="https://user-images.githubusercontent.com/85270361/129412076-df1b9937-bef3-4fbd-a052-498c98919c30.PNG">


**Copy and paste the code below into ‘book.js’**


```
var mongoose = require('mongoose');
var dbHost = 'mongodb://localhost:27017/test';
mongoose.connect(dbHost);
mongoose.connection;
mongoose.set('debug', true);
var bookSchema = mongoose.Schema( {
  name: String,
  isbn: {type: String, index: true},
  author: String,
  pages: Number
});
var Book = mongoose.model('Book', bookSchema);
module.exports = mongoose.model('Book', bookSchema);
```


<img width="505" alt="mean vi 8" src="https://user-images.githubusercontent.com/85270361/129412221-f988cb13-0bf8-475c-8fa8-af8a79b08087.PNG">


# Step 4: Access the routes with AngularJS

AngularJS provides a web framework for creating dynamic views in your web applications. In this tutorial, we use AngularJS to connect our web page with Express and perform actions on our book register.


**Change the directory back to ‘Books’**

```
cd ../..
```

**Create a folder named public**

```
mkdir public && cd public
```

**Add a file named script.js**

```
touch script.js
```

```
vi script.js
```

<img width="354" alt="mean 9" src="https://user-images.githubusercontent.com/85270361/129415019-14326dd1-406d-486e-8144-551884c44058.PNG">


**Copy and paste the Code below (controller configuration defined) into the script.js file.**


```
var Book = require('./models/book');
module.exports = function(app) {
  app.get('/book', function(req, res) {
    Book.find({}, function(err, result) {
      if ( err ) throw err;
      res.json(result);
    });
  }); 
  app.post('/book', function(req, res) {
    var book = new Book( {
      name:req.body.name,
      isbn:req.body.isbn,
      author:req.body.author,
      pages:req.body.pages
    });
    book.save(function(err, result) {
      if ( err ) throw err;
      res.json( {
        message:"Successfully added book",
        book:result
      });
    });
  });
  app.delete("/book/:isbn", function(req, res) {
    Book.findOneAndRemove(req.query, function(err, result) {
      if ( err ) throw err;
      res.json( {
        message: "Successfully deleted the book",
        book: result
      });
    });
  });
  var path = require('path');
  app.get('*', function(req, res) {
    res.sendfile(path.join(__dirname + '/public', 'index.html'));
  });
};
```

**OUTPUT:**

<img width="520" alt="mean9 vi" src="https://user-images.githubusercontent.com/85270361/129415306-8d15c470-b06a-4e3f-af00-d844e4dbf1eb.PNG">


**In public folder, create a file named index.html;**

```
touch index.html
```

```
vi index.html
```

**Copy and paste the code below into index.html file.**

```
<!doctype html>
<html ng-app="myApp" ng-controller="myCtrl">
  <head>
    <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.4/angular.min.js"></script>
    <script src="script.js"></script>
  </head>
  <body>
    <div>
      <table>
        <tr>
          <td>Name:</td>
          <td><input type="text" ng-model="Name"></td>
        </tr>
        <tr>
          <td>Isbn:</td>
          <td><input type="text" ng-model="Isbn"></td>
        </tr>
        <tr>
          <td>Author:</td>
          <td><input type="text" ng-model="Author"></td>
        </tr>
        <tr>
          <td>Pages:</td>
          <td><input type="number" ng-model="Pages"></td>
        </tr>
      </table>
      <button ng-click="add_book()">Add</button>
    </div>
    <hr>
    <div>
      <table>
        <tr>
          <th>Name</th>
          <th>Isbn</th>
          <th>Author</th>
          <th>Pages</th>

        </tr>
        <tr ng-repeat="book in books">
          <td>{{book.name}}</td>
          <td>{{book.isbn}}</td>
          <td>{{book.author}}</td>
          <td>{{book.pages}}</td>

          <td><input type="button" value="Delete" data-ng-click="del_book(book)"></td>
        </tr>
      </table>
    </div>
  </body>
</html>
```

**OUTPUT:**

<img width="519" alt="mean vi 10" src="https://user-images.githubusercontent.com/85270361/129416461-bb9c1c12-746d-4951-9140-bb57e76ed73b.PNG">


**Change the directory back up to Books**

```
cd ..
```

**Start the server by running this command:**

```
node server.js
```

**OUTPUT:**

<img width="515" alt="mean 11" src="https://user-images.githubusercontent.com/85270361/129416831-6b7bc9f9-d17a-485a-abce-d7c4566c117f.PNG">


## The server is now up and running, we can connect it via port 3300. You can launch a separate Putty or SSH console to test what curl command returns locally.

```
curl -s http://localhost:3300
```


It shall return an HTML page, it is hardly readable in the CLI, but we can also try and access it from the Internet.

For this – you need to open TCP port 3300 in your AWS Web Console for your EC2 Instance.

You are supposed to know how to do it, if you have forgotten – refer to Project 1 (Step 1 — Installing Apache and Updating the Firewall)

Your Security group shall look like this:


**OUTPUT:**

<img width="946" alt="mean 12" src="https://user-images.githubusercontent.com/85270361/129417156-93ccd71e-4376-42b0-9f7f-ae439aeea343.PNG">


Now you can access our Book Register web application from the Internet with a browser using Public IP address or Public DNS name.

Quick reminder how to get your server’s Public IP and public DNS name:

You can find it in your AWS web console in EC2 details

**Run curl -s http://169.254.169.254/latest/meta-data/public-ipv4 for Public IP address or curl -s http://169.254.169.254/latest/meta-data/public-hostname for Public DNS name.**

This is how your Web Book Register Application will look like in browser:


<img width="434" alt="mean 13" src="https://user-images.githubusercontent.com/85270361/129417274-b6fcb6d9-9e35-4545-b5bd-6efff6af84ea.PNG">

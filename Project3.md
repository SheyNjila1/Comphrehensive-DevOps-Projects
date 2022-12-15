# Mern.Project
MERN
# Mern-stack-project-

## MERN Stack

### MERN  stack is a web development framework. It consists of MongoDB, ExpressJS, ReactJS, and NodeJS as its working components. 

Each of these 4 powerful technologies provides an end-to-end framework for the developers to work in and each of these technologies play a big part in the development of web applications.

Here are the details of what each of these components is used for in developing a web application when using MERN stack:

* MongoDB: A document-oriented, No-SQL database used to store the application data.

* NodeJS: The JavaScript runtime environment. It is used to run JavaScript on a machine rather than in a browser.

* ExpressJS: A framework layered on top of NodeJS, used to build the backend of a site using NodeJS functions and structures. Since NodeJS was not developed to make websites but rather run JavaScript on a machine, ExpressJS was developed.

* ReactJS: A library created by Facebook. It is used to build UI components that create the user interface of the single page web application.

### Understanding the Parts of the MERN Stack

## MongoDB

 * MongoDB is a cross-platform document-based database known as a nonrelational document-orientated database, or NoSQL. MongoDB stores data in flexible documents using a query language based on JavaScript Object Notation (JSON). The size, number and content of document fields vary, so the data structure can be altered later on. MongoDB is easy to scale and quite flexible, making it popular among many web developers.

## Express

 * Express is a back end framework for Node.js web applications. We can use Express to make writing server code much simpler, as opposed to the traditional alternative of manually writing full web server code on Node.js, since it lets us avoid having to repeat the same code like we would using the Node.js HTTP module.
Express’s framework was designed to enable simple, easy construction of APIs and efficient web applications. It is loaded with plugin features and is renowned for its speed. Its minimalistic structure makes it simple for developers to pick up and start using right away.

## React

 * In React, views are declarative, meaning developers do not have to manage the effects of changes in data or the view’s state. (A view’s state is the object that determines the behavior of individual components.) Instead, React lets developers use a full-featured programming language to design conditional or repetitive DOM elements rather than relying on templates that automatically create repetitive DOM (Document Object Model) or HTML elements. React lets the same code run on the browser and server simultaneously, which is what enables React to anchor the MERN stack and makes it essential to the operation.

## Node.js

 * Node.js is a cross-platform JavaScript runtime environment that is built on Chrome’s V8 JavaScript engine and is intended to allow developers to build scalable network applications and execute JavaScript code outside of browsers. Node.js works by using its own module system that is based on CommonJS, meaning it does not need an enclosing HTML page to put together more than one JavaScript file.

How does the MERN stack work?

The MERN architecture allows us to easily construct a 3-tier architecture (frontend, backend, database) entirely using JavaScript and JSON.

![image](https://user-images.githubusercontent.com/85270361/126515365-ab55e9d4-46b1-4f20-9497-ee96919170ca.png)

### In this project, you are tasked to implement a web solution based on MERN stack in AWS Cloud.

![image](https://user-images.githubusercontent.com/85270361/128374397-ff946c38-0028-4d55-9e2d-9ee1b3f552e1.png)

# Step 0 

In order to complete this project you will need an AWS account and a virtual server with Ubuntu Server OS.

Hint #1: When you create your EC2 Instances, you can add Tag “Name” to it with a value that corresponds to a current project you are working on - it will be reflected in the name of the EC2 Instance. Like this:

<img width="795" alt="WEB STACK SERVER EC2" src="https://user-images.githubusercontent.com/85270361/128376007-55bd4a1f-b091-43f7-b668-37ef76e003f2.PNG">

**Download and launch MobaxTerm, create a new SSH session with , ‘ubuntu’ as username and your private key (.pem file) like this:**

<img width="672" alt="mobaxterm" src="https://user-images.githubusercontent.com/85270361/128376445-90753d5b-054d-45a5-9584-e084f6dcae0f.PNG">

# Task

![image](https://user-images.githubusercontent.com/85270361/128377080-e679d2d5-0809-4ff1-83a3-8f2ba46b0423.png)


**In this project, we are required to implement a web solution based on MERN stack on a Linux server. We will be deploying an application that is used to create ‘Todo’ lists by implementing the steps below:

# Step 1 - Prepare the backend Linux server

* Update and upgrade ubuntu
```
$ sudo apt update
$ sudo apt upgrade
```

# Step 2 - First, we will need to locate and install nodejs on the server.

**Lets get the location of Node.js software from Ubuntu repositories.**

```
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
```

# Install Node.js on the server
Install Node.js with the command below

```
sudo apt-get install -y nodejs
```

<img width="679" alt="node js istall" src="https://user-images.githubusercontent.com/85270361/128379431-10776b88-b447-48ba-8ee8-a65b96eeb16c.PNG">


**Note:** The command above will install both nodejs and npm. NPM is a package manager. Similar to what apt does on Ubuntu, NPM is used to install node modules or softwares, and manages dependency conflicts intelligently.


 * Verify the node installation with both commands below
 
 
 ```
 $ node -v
 
 $ npm -v 
 ```
 
## We'll see something like this


 <img width="259" alt="npm" src="https://user-images.githubusercontent.com/85270361/128380552-223a2371-4a31-4d73-95c5-5ea940d8e753.PNG">
 
 
 # Step 3 - Application Code Set
 
 
 **Create a new directory for your To-Do project:
 
 
 ```
 $ mkdir Todo
 ```
 
 
 **Verify that the Todo directory is created


```
lS
```


## We'll see something like this


<img width="248" alt="todo" src="https://user-images.githubusercontent.com/85270361/128382016-7a0042cf-4d20-41ea-803a-95edd0f465d5.PNG">


**Now change your current directory to the newly created one:


```
$ cd Todo
```

<img width="225" alt="todo 2" src="https://user-images.githubusercontent.com/85270361/128382330-3d567819-4397-4601-9cd9-01f0e7cd64ac.PNG">

**Next, we will use the command npm init to initialise our project, so that a new file named package.json will be created. This file will normally contain information about our app and the dependencies that it needs to run. Follow the prompts after running the command. We can hit enter to accept default values, then we accept to write out the package.json file by typing yes.

 
 ```
 $ npm init
 ```
 
 ## We'll see something like this
 
 <img width="591" alt="script" src="https://user-images.githubusercontent.com/85270361/128383188-16930224-35b9-49ea-abcf-9dbf7c85ab3f.PNG">
 
 **Run the command ls to confirm that you have package.json file created.
 
 
# Step 4 - Install ExpressJS

## Express is a back end framework for Node.js web applications. it lets us avoid having to repeat the same code like we would using the Node.js HTTP module and It also helps to define routes of our application based on HTTP methods and URLs.

* **Inside the todo list folder,We will install Express using npm :**

```
$ npm install express
```

**Now create a file index.js with the command below**

```
$ touch index.js
```

**Run ls to confirm that your index.js file is successfully created**

```
$ ls
```


**Inside the todo list folder, We will Install the dotenv module**

```
$ npm install dotenv
```

# We'll see something like this

<img width="565" alt="npm npm" src="https://user-images.githubusercontent.com/85270361/128384584-484d80e2-4ed4-4a44-97a5-a5cc38503557.PNG">

**We need to open the index.js file with the command below**

```
$ vi index.js
```

**Type the code below into it and save. Do not get overwhelmed by the code you see. For now, simply paste the code into the file.


```
const express = require('express');
require('dotenv').config();

const app = express();

const port = process.env.PORT || 5000;

app.use((req, res, next) => {
res.header("Access-Control-Allow-Origin", "\*");
res.header("Access-Control-Allow-Headers", "Origin, X-Requested-With, Content-Type, Accept");
next();
});

app.use((req, res, next) => {
res.send('Welcome to Express');
});

app.listen(port, () => {
console.log(`Server running on port ${port}`)
});
```


**We'll see something like this


We use :w to save in vi and use :q! to exit vi.


NOTE we have specified to use port 5000 in the code. This will be required later when we go on the browser.


To test if our server works. We open our terminal in the same Todo directory as our index.js file and type

```
$ node index.js
```


**If every thing goes well, We should see our Server running on port 5000 in our terminal.**


<img width="501" alt="5000" src="https://user-images.githubusercontent.com/85270361/129028488-15024284-fc7b-4c70-8cdd-260e6ca34b35.PNG">


Now we need to open this port in EC2 Security Groups. Refer to Project 1 Step 1 – Installing the Nginx Web Server. There we created an inbound rule to open TCP port 80, you need to do the same for port 5000, like this:


<img width="923" alt="SG" src="https://user-images.githubusercontent.com/85270361/128386834-a67dc980-071f-4c1d-becb-bb9d894070e4.PNG">


```
http://<PublicIP-or-PublicDNS>:5000
```
  
Quick reminder how to get your server’s Public IP and public DNS name:
  
```
curl -s http://169.254.169.254/latest/meta-data/public-ipv4
curl -s http://169.254.169.254/latest/meta-data/public-hostname
```

<img width="332" alt="express" src="https://user-images.githubusercontent.com/85270361/128387572-2eab5ba7-d818-4158-b66c-8e09708ba2f6.PNG">

  
## Step 5 - Routes

**For each task, we need to create routes that will define various endpoints that the todo app will depend on.**

So let’s create a folder routes
 
 ```
 $ mkdir routes
 ```
 
Change directory into the routes folder.
 
```
$ cd routes
```

Now, create a file api.js with the command below
 
```
$ touch api.js
```

 
Open the file with the command below

 
```
vi api.js
```


 
<img width="480" alt="routes" src="https://user-images.githubusercontent.com/85270361/128389172-c78d9076-06f6-41fb-a287-ae7d91e0f052.PNG">


* Input below code in it.



```
const express = require ('express');
const router = express.Router();

router.get('/todos', (req, res, next) => {

});

router.post('/todos', (req, res, next) => {

});

router.delete('/todos/:id', (req, res, next) => {

})

module.exports = router;
```

## Step 6 - Models

Since the app is going to make use of Mongodb which is a NoSql database, we need to create a model which will be used to define the database schema. This is important so that we will be able to define the fields stored in each Mongodb document.
 
 
In essence the Schema is a blueprint of how the database will be constructed, including other data fields that may not be required to be stored in the database. These are known as virtual properties. To create a Schema and a model, install mongoose which is a node package that makes working with mongodb easier.
 
Change directory back Todo folder with cd .. and install Mongoose

```
$ npm install mongoose
```

<img width="544" alt="mongoose" src="https://user-images.githubusercontent.com/85270361/128391224-c63ab2a0-4cc0-47b6-aee9-8235a2a77cbb.PNG">

Create a new folder with mkdir models command
 
```
$ mkdir models
```
 
Change directory into the newly created ‘models’ folder with
 
```
$ cd models
```
 
Inside the models folder, create a file and name it
 
```
$ touch todo.js
```
 
<img width="435" alt="mkdir" src="https://user-images.githubusercontent.com/85270361/128392550-4aaa89e5-e3b6-4e41-9a17-345f2fa5f1c8.PNG">
 
All three commands above can be defined in one line to be executed consequently with help of && operator, like this:
 
```
mkdir models && cd models && touch todo.js
```

Open the file created with vi todo.js then paste the code below in the file:
 
 
```
const mongoose = require('mongoose');
const Schema = mongoose.Schema;

//create schema for todo
const TodoSchema = new Schema({
action: {
type: String,
required: [true, 'The todo text field is required']
}
})

//create model for todo
const Todo = mongoose.model('todo', TodoSchema);

module.exports = Todo;
```
 
 
<img width="602" alt="mon" src="https://user-images.githubusercontent.com/85270361/128393532-6e260643-1f67-43e2-83e4-6b879d40fd40.PNG">


Now we need to update our routes from the file api.js in Routes directory to make use of the new model.


In Routes directory, open api.js with vi api.js, delete the code inside with :%d and paste the code below into it then save and exit


```
const express = require ('express');
const router = express.Router();
const Todo = require('../models/todo');

router.get('/todos', (req, res, next) => {

//this will return all the data, exposing only the id and action field to the client
Todo.find({}, 'action')
.then(data => res.json(data))
.catch(next)
});

router.post('/todos', (req, res, next) => {
if(req.body.action){
Todo.create(req.body)
.then(data => res.json(data))
.catch(next)
}else {
res.json({
error: "The input field is empty"
})
}
});

router.delete('/todos/:id', (req, res, next) => {
Todo.findOneAndDelete({"_id": req.params.id})
.then(data => res.json(data))
.catch(next)
})

module.exports = router;
```


<img width="671" alt="step 6" src="https://user-images.githubusercontent.com/85270361/128394178-956aeb17-59a7-4b24-93f9-de7b30a34d00.PNG">


# Step 7- MongoDB Database
 
We need a database where we will store our data. For this we will make use of mLab. mLab provides MongoDB database as a service solution (DBaaS), so to make life easy, you will need to sign up for a shared clusters free account, which is ideal for our use case

https://www.mongodb.com/atlas-signup-from-mlab 
Follow the sign up process, select AWS as the cloud provider, and choose a region near you.


Create a mongodb database and connection inside mLab and then obtain the connection string through the connect TAB. Also, update the password and database name and removed the <>.


mongodb+srv://annafamefuna:<password>@cluster0.5bbee.mongodb.net/myFirstDatabase?retryWrites=true&w=majority
 
 
Create a file in your TODO directory with and name it .env. Add the connection string to access the database in it, just as below
 
 
In order to allow the node.js to connect to the database in Mongodb, the index.js was updated so as to reflect the use of dotenv.
 
 
```
touch .env
vi .env
```

  
Create a mongodb database and connection inside mLab and then obtain the connection string through the connect TAB. Also, update the password and database name and removed the <>.
 
 
Now we need to update the index.js to reflect the use of .env so that Node.js can connect to the database.

Simply delete existing content in the file, and update it with the entire code below.

To do that using vim, follow below steps

Open the file with vim index.js
 
Press esc
 
Type :
 
Type %d
 
Hit ‘Enter’
 
The entire content will be deleted, then,

Press i to enter the insert mode in vim
 
Now, paste the entire code below in the file.
 
  
```
const express = require('express');
const bodyParser = require('body-parser');
const mongoose = require('mongoose');
const routes = require('./routes/api');
const path = require('path');
require('dotenv').config();

const app = express();

const port = process.env.PORT || 5000;

//connect to the database
mongoose.connect(process.env.DB, { useNewUrlParser: true, useUnifiedTopology: true })
.then(() => console.log(`Database connected successfully`))
.catch(err => console.log(err));

//since mongoose promise is depreciated, we overide it with node's promise
mongoose.Promise = global.Promise;

app.use((req, res, next) => {
res.header("Access-Control-Allow-Origin", "\*");
res.header("Access-Control-Allow-Headers", "Origin, X-Requested-With, Content-Type, Accept");
next();
});

app.use(bodyParser.json());

app.use('/api', routes);

app.use((err, req, res, next) => {
console.log(err);
next();
});

app.listen(port, () => {
console.log(`Server running on port ${port}`)
});
```
 
Using environment variables to store information is considered more secure and best practice to separate configuration and secret data from the application, instead of writing connection strings directly inside the index.js application file.

Start your server using the command:
 
```
node index.js
```
 
<img width="501" alt="5000" src="https://user-images.githubusercontent.com/85270361/129056020-214941a7-97f3-4d79-9125-2392b61196ca.PNG">

 
<img width="792" alt="cannot get" src="https://user-images.githubusercontent.com/85270361/129056074-f0032d8d-ffaf-40cd-ac6a-ab17553e838a.PNG">

 
# Step 8 -Testing Backend Code without Frontend using RESTful API
 
So far we have written our TODO application, and configured backend database, but we do not have a frontend UI yet. We need ReactJS code to achieve that. But during development, we will need a way to test our code using RESTFUL API. Therefore, we will need to make use of some api development clients to test our code.
 
In this project, we will use Postman to test for our API.
 
Install Postman in Ubuntu
 

```
$ sudo snap install postman
```
 
<img width="523" alt="postman" src="https://user-images.githubusercontent.com/85270361/128419657-fa341f34-85ea-4010-a539-66a82b7f25f7.PNG">
 
Now we open our Postman, We will create a ‘POST’ and ‘GET’ request in postman to the API http://localhost:5000/api/todos
 
POST Request
 
 
<img width="769" alt="post 1" src="https://user-images.githubusercontent.com/85270361/129056253-22700291-afad-444f-bb65-66a968c70d10.PNG">

 
# GET Request
 
 
<img width="674" alt="get 1" src="https://user-images.githubusercontent.com/85270361/129056357-4cac3517-02fe-4131-97c3-2d47fed98a2b.PNG">

 
 
# Step 9 - Creating the Frontend
 
**we are done with the functionality we want from our api, it is time to create an interface for the client to interact with the api. To start out with the frontend of the todo app, we will use the create-react-app command to scaffold our app.
 
 
* In our Todo directory, We will run:
 
```
$ npx create-react-app client
```
 
This will create a new folder in our Todo directory called client, where we will add all the react code.
 
 
<img width="675" alt="install npx" src="https://user-images.githubusercontent.com/85270361/129057201-197614d4-d387-4c4e-aea7-9cb05b763d14.PNG">

 
 
##Step 10 - Running the React App
 
**Before testing the react app, there are a number of dependencies that need to be installed.
 
We need to Install concurrently: It is used to run more than one command simultaneously from the same terminal window.
 

```
$ npm install concurrently --save-dev
```
 
<img width="515" alt="npm concurrently" src="https://user-images.githubusercontent.com/85270361/129056821-01af0741-d626-4d7e-bcd8-5b5440471d35.PNG">


 
 
* We need to Install nodemon: It is used to run and monitor the server. If there is any change in the server code, nodemon will restart it automatically and load the new changes.
 
```
$ npm install nodemon --save-dev
```
 
<img width="472" alt="npm step 8 b" src="https://user-images.githubusercontent.com/85270361/128703906-9d6b9396-3fb1-436e-a5a0-36f1b408d570.PNG">
 
 
* In the Todo folder, open the package.json file. Change the highlighted part of the below screenshot and replace with the code below.

 
```
"scripts": {
"start": "node index.js",
"start-watch": "nodemon index.js",
"dev": "concurrently \"npm run start-watch\" \"cd client && npm start\""
},
```
 
# Step 11 - Configure Proxy in package.json
 
* Enter into the client folder from Todo directory

```
$ cd client
```
 
* Open the package.json file
 
```
$ vi package.json
```
 
* Add the key value pair in the package.json file "proxy": "http://localhost:5000".
 
<img width="476" alt="step 11" src="https://user-images.githubusercontent.com/85270361/129058009-b4eaadd2-6294-4935-adae-cc0eb073652d.PNG">
 
 
The whole purpose of adding the proxy configuration in number 3 above is to make it possible to access the application directly from the browser by simply calling the server url like http://localhost:5000 rather than always including the entire path like http://localhost:5000/api/todos
 

 
 
# Now, we will ensure that we are inside the Todo directory, and simply do:
 
 
```
$  npm run dev
```

<img width="433" alt="npm step 8 c" src="https://user-images.githubusercontent.com/85270361/128741447-c1bea91c-6e3e-42df-b76e-541be8aeb5c8.PNG">
 
 
**Your app should open and start running on localhost:3000
 
<img width="488" alt="src" src="https://user-images.githubusercontent.com/85270361/128741793-7e95cd22-9188-4844-b4a1-fa5aed82c2d1.PNG">


Important note: In order to be able to access the application from the Internet you have to open TCP port 3000 on EC2 by adding a new Security Group rule. You already know how to do it.

 
# Step 12 - Creating our React Components 
 
Creating your React Components
One of the advantages of react is that it makes use of components, which are reusable and also makes code modular. For our Todo app, there will be two stateful components and one stateless component. From your Todo directory run
 
 
```
cd client
```
 
**Move to the src directory**
 
```
cd src
```
 
**Inside your src folder create another folder called components**
 
 
```
mkdir components
```

**Move into the components directory with 

 ```
 cd components
 ```
 
Inside ‘components’ directory create three files Input.js, ListTodo.js and Todo.js.
 
**touch Input.js ListTodo.js Todo.js**
 

Open Input.js file

```
vi Input.js
```
 
**Copy and paste the following**

```
import React, { Component } from 'react';
import axios from 'axios';

class Input extends Component {

state = {
action: ""
}

addTodo = () => {
const task = {action: this.state.action}

    if(task.action && task.action.length > 0){
      axios.post('/api/todos', task)
        .then(res => {
          if(res.data){
            this.props.getTodos();
            this.setState({action: ""})
          }
        })
        .catch(err => console.log(err))
    }else {
      console.log('input field required')
    }

}

handleChange = (e) => {
this.setState({
action: e.target.value
})
}

render() {
let { action } = this.state;
return (
<div>
<input type="text" onChange={this.handleChange} value={action} />
<button onClick={this.addTodo}>add todo</button>
</div>
)
}
}

export default Input
```

 
Axios is a promise based HTTP client for the browser and node.js, you need to cd into your client from your terminal and run yarn add axios or npm install axios.
 
 
* Move to the src folder
 
```
$ cd ..
```
 
* Move to clients folder
 
```
$ cd ..
```
 
 
**Install Axios in the clients folder**
 
```
$ npm install axios
```
 

* Go to components directory
 
```
$ cd src/components
```
 
 
* After that open your ListTodo.js
 
```
$ vi ListTodo.js
```

* In the ListTodo.js copy and paste the following code
 
```
import React from 'react';

const ListTodo = ({ todos, deleteTodo }) => {

return (
<ul>
{
todos &&
todos.length > 0 ?
(
todos.map(todo => {
return (
<li key={todo._id} onClick={() => deleteTodo(todo._id)}>{todo.action}</li>
)
})
)
:
(
<li>No todo(s) left</li>
)
}
</ul>
)
}

export default ListTodo
```
 
* **Then in your Todo.js file you write the following code**
 
```
import React, {Component} from 'react';
import axios from 'axios';

import Input from './Input';
import ListTodo from './ListTodo';

class Todo extends Component {

state = {
todos: []
}

componentDidMount(){
this.getTodos();
}

getTodos = () => {
axios.get('/api/todos')
.then(res => {
if(res.data){
this.setState({
todos: res.data
})
}
})
.catch(err => console.log(err))
}

deleteTodo = (id) => {

    axios.delete(`/api/todos/${id}`)
      .then(res => {
        if(res.data){
          this.getTodos()
        }
      })
      .catch(err => console.log(err))

}

render() {
let { todos } = this.state;

    return(
      <div>
        <h1>My Todo(s)</h1>
        <Input getTodos={this.getTodos}/>
        <ListTodo todos={todos} deleteTodo={this.deleteTodo}/>
      </div>
    )

}
}

export default Todo;
```
 


**We need to make little adjustment to our react code. Delete the logo and adjust our App.js to look like this.**

* Move to the src folder

 
```
cd ..
```
 
 
* **Make sure that you are in the src folder and run**

 
```
vi App.js
```
 
 
**Copy and paste the code below into it**
 
 
``` 
import React from 'react';

import Todo from './components/Todo';
import './App.css';

const App = () => {
return (
<div className="App">
<Todo />
</div>
);
}

export default App;
```
 
 
**After pasting, exit the editor.**

* In the src directory open the App.css 
 
 
```
vi App.css
```
 
 
**Then paste the following code into App.css:**
 
 
```
.App {
text-align: center;
font-size: calc(10px + 2vmin);
width: 60%;
margin-left: auto;
margin-right: auto;
}

input {
height: 40px;
width: 50%;
border: none;
border-bottom: 2px #101113 solid;
background: none;
font-size: 1.5rem;
color: #787a80;
}

input:focus {
outline: none;
}

button {
width: 25%;
height: 45px;
border: none;
margin-left: 10px;
font-size: 25px;
background: #101113;
border-radius: 5px;
color: #787a80;
cursor: pointer;
}

button:focus {
outline: none;
}

ul {
list-style: none;
text-align: left;
padding: 15px;
background: #171a1f;
border-radius: 5px;
}

li {
padding: 15px;
font-size: 1.5rem;
margin-bottom: 15px;
background: #282c34;
border-radius: 5px;
overflow-wrap: break-word;
cursor: pointer;
}

@media only screen and (min-width: 300px) {
.App {
width: 80%;
}

input {
width: 100%
}

button {
width: 100%;
margin-top: 15px;
margin-left: 0;
}
}

@media only screen and (min-width: 640px) {
.App {
width: 60%;
}

input {
width: 50%;
}

button {
width: 30%;
margin-left: 10px;
margin-top: 0;
}
}
```
 
 
 
## Exit
 

* In the src directory open the index.css

 
```
vim index.css
```
 
 
**Copy and paste the code below:**
 
 
```
body {
margin: 0;
padding: 0;
font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen",
"Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue",
sans-serif;
-webkit-font-smoothing: antialiased;
-moz-osx-font-smoothing: grayscale;
box-sizing: border-box;
background-color: #282c34;
color: #787a80;
}

code {
font-family: source-code-pro, Menlo, Monaco, Consolas, "Courier New",
monospace;
}
```
 
 
**Go to the Todo directory**

 
```
cd ../..
```
 

When you are in the Todo directory run:


```
npm run dev
```
 
 
Assuming no errors when saving all these files, our To-Do app should be ready and fully functional with the functionality discussed earlier: creating a task, deleting a task and viewing all your tasks.
 
 
 
![image](https://user-images.githubusercontent.com/85270361/129060343-05d73c7c-8718-4725-8fc7-5e5353c09328.png)

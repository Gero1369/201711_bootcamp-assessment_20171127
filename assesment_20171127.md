## Final Assessment

### Question 1

#### What are the features and key characteristics of Node? (Choose three that apply)

[ ] Virtual DOM
[X] High performance for I/O operations
[ ] High performance for CPU operations
[X] Non-blocking I/O
[X] Built-in core modules for networking

### Question 2

#### What Node can be used for? (Choose two that apply)

[X] Front-end apps
[X] Web apps with server-side rendering
[ ] Programs which control drones
[ ] None of the above
[ ] All of the above 

### Question 3

#### What type of servers Node developers can build? 

( ) Static HTTP servers
( ) GraphQL API servers
( ) RESTful API servers
( ) Networking (non-HTTP) clients and servers
(X) All of the above 
( ) None of the above

### Question 4

#### What would be a valid Node object? (Choose three that apply)

[X] `process`
[X] `React`
[ ] `global`
[ ] `module`
[X] `document`

### Question 5


```
/var
  /www
    /api
      server.js
```

#### Given the structure above, what would be the value of `__dirname` in the `server.js` file?

( ) `/var`
( ) `/var/www`
(X) `/var/www/api`
( ) `/var/www//api`
( ) `/var/www/api/server.js`

### Question 6

```
/var
  /www
    /webapp
      /routes
        transactions.js
      app.js
```

#### Given the structure of an Express app above, what is the correct statement for importing transaction routein `app.js`, in Node v8. (Choose three of the following choices)?<<

[X] `const transactions = require('./routes/transactions.js`)
[X] `const {transactions} = require('./routes/transactions.js`)
[X] `require('./routes/transactions`)
[ ] `const transactions = require('./routes/transaction.js`)
[ ] `const transactions = require('./routes/transaction`)


[explanation]
import statement will not work out-of-the-box in Node v8
[explanation]

### Question 7

```js
app.get('/transactions/:transactionId', TODO)
```

#### Given the object above and the the `transactions.getTransaction(id, callback)` method, how do you use thiroute in a `app.get()`?<<

( ) `app.get('/transactions/:transactionId', transactions.getTransaction(id))`
( ) `app.get('/transactions/:id', (req, res, next)=>{transactions.getTransaction(req.params.transactionId, next)})`
( ) `app.get('/transactions/:id', (req, res)=>{transactions.getTransaction(req.params.transactionId, next)})`
(X) `app.get('/transactions/:transactionId', (req, res, next)=>{transactions.getTransaction(req.params.transactionId, next)})`
( ) `app.get('/transactions/:id', (req, res, next)=>{getTransaction(req.params.transactionId, next)})`

[explanation]
The request handler must have (req, res, next) signatures for the callback argument and id parameter must be consistently named.
[explanation]

### Question 8


```js
app.get('/transactions/:transactionId', TODO)
```

#### Given the object above and the the `transactions.getTransaction(req, res)` method, how do you use this routin a `app.get()`?<<

( ) `app.get('/transactions/:transactionId', transactions.getTransaction(id))`
(X) `app.get('/transactions/:transactionId', transactions.getTransaction)`
( ) `app.get('/transactions/:transactionId', (req, res, next)=>{transactions.getTransaction(req.params.id, next)})`
( ) `app.get('/transactions/:id', (req, res, next)=>{transactions.getTransaction(req.params.transactionId, next)})`
( ) `app.get('/transactions/:id', (req, res, next)=>{getTransaction(req.params.transactionId, next)})`

[explanation]
`getTransaction()` is a request handler itself so we can just pass it to app.get() - no need for an extra function.
[explanation]

### Question 9

#### What is the default folder name for Express templates which is also the folder create by Express Generator?

( ) `templates`
( ) `tpl`
(X) `views`
( ) `view`
( ) `jade`

[explanation]
views is the default folder for templates. 
[explanation]

### Question 10

#### What is the name of a useful npm module which will allow to work with incoming payload from clients in ouExpress server?<<

( ) `bodyparser`
( ) `body_parser`
(X) `body-parser`
( ) `incoming-payload`
( ) `express-validator`

[explanation]
Please refer to Module 2, Lesson 4
[explanation]

### Question 11

#### There are many types of NoSQL databases. To what type MongoDB belongs?

( ) Key-value stores
(x) Document stores 
( ) Columnar stores
( ) Graphs stores
( ) Relational

### Question 12

#### What would be the correct MongoDB REPL/shell command to delete document(s)?

(X) `> db.messages.remove({name:"John"});`
( ) `> db.messages.unmount({name:"John"});`
( ) `> db.messages.removeByName({name:"John"});`
( ) `> db.messages.delete({name:"John"});`
( ) `> db.messages.deleteeById({_id:ObjectId('56b2ac41065598d78bd5366f')});`

### Question 13


```js
const mongodb = require('mongodb')
//TODO
MongoClient.connect('mongodb://localhost:27017/edx-course-db', (err, db) => {
  if (err) return process.exit(1)
  console.log('Kudos. Connected successfully to server')
  db.close()
})
```

#### What code is missing in the script above?

( ) `const MongoClient = mongodb`
( ) `const MongoClient = mongodb.client`
( ) `const MongoClient = mongodb.connect`
( ) `const MongoClient = {connect: mongodb.connect}`
(X) `const {MongoClient} = mongodb`

[explanation]
We need to define MongoClient, and `const {MongoClient} = mongodb` is the same as `const MongoClient = mongodb.MongoClient`.
[explanation]

### Question 14

```js
collection.find({tags: /javascript/}).toArray(fn)
```

#### What would be the right definition of `fn`?

( ) `const fn = {}`
( ) `const fn = (documents) => {}`
(X) `const fn = (error, documents) -> {}`
( ) `function fn(error, documents) {}`
( ) `const fn = (documents, error) => {}`

### Question 15

```js
collection.findOne({_id: '56b2ac41065598d78bd5366f'}, fn)
```

#### What is wrong with this statement?

( ) No error handler
( ) More than one documents
( ) No `toArray()`
(X) 56b2ac41065598d78bd5366f is not ObjectId
( ) All of the above

[explanation]
This is the proper query since the previous query will not return any documents (most likely):

`collection.findOne({_id: ObjectId('56b2ac41065598d78bd5366f')}, fn)`
[explanation]

### Question 16

#### What things Node supports (out-of-the-box)? (Choose two that apply)

[X] Support for ES6, ES7 and ES8 in v8+
[ ] Support for JSX
[ ] Cross-browser support
[X] Cross-platform support
[ ] Database support

[explanation]
Typically, cross-platform means OS: Windows, Linux, macOS.
[explanation]

# React Questions

1. You can set state in a component method (not a constructor) with this syntax: this.setState(a), this.state = a or this.a = a.

this.setState(a)

1. If you want to update the render process, it's normal practice to change properties in components like this this.props.a=100. True or false?

false

1. States are mutable and properties are immutable. True or false?

true

1. Stateless components can be implemented as function. True of false?

true

1. How do you define the first state variables when element is created? setState(), initialState(), this.state =... in constructor, or setInitialState()?

this.state =... in constructor

1. React provides robust validation, which eliminates the necessity to check input on the server side. True or false?

false

1. In addition to setting the properties with defaultProps, you can set them in constructor using this.prop.NAME = VALUE. True or false?

false

1. The children property can be an array or a node. True or false?

true

1. A higher-order component pattern is implemented via a function. True or false?

true

1. The main differences between minified development and unminified production versions of the React library file is that minified has warnings and unminified has optimized code. True or false?

true
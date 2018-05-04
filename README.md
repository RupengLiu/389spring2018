# Online Book Store<br />
Name: Rupeng Liu<br />
Date: May 3 2018<br />
Project Topic: Online Book Store <br />
## URL: https://p5-reddit-clone-okrltmncfm.now.sh/ <br />
### 1. Data Format and Storage
Data point fields:<br />
Schema: Book <br />
-```Field 1```: Title Type: Text <br />
-```Field 2```: Year Type: Number <br />
-```Field 3```: Author Type: Text <br />
-```Field 4```: Words Type: Number <br />
-```Field 5```: Purchases Type: [purchaseschema] <br />
Schema:
```
var bookSchema = new mongoose.Schema({
    title: {
        type: String,
        required: true
    },
    year: {
        type: Number,
        min: 0,
        max: 2018,
        required: true
    },
    author: {
        type: String,
        required: true
    },
    words: {
        type: Number,
    },
    purchases: [purchaseSchema]
});
```
Schema: Purchase <br />
-```Field 1```: Price Type: Number <br />
-```Field 2```: Store Type: Number <br />
-```Field 3```: Purchasedate Type: Date <br />
-```Field 4```: Comment Type: Text <br />
-```Field 5```: Publisher Type: Text <br />

Schema:
```
var purchaseSchema = new mongoose.Schema({
    price: {
        type: Number,
        required: true
    },
    comment: {
        type: String,
    },
    publisher: {
        type: String,
    },
    purchasedate: {
        type: String,
    },
    store: {
        type: String,
        required: true
    }

});
```
### 2. Add New Data <br />
HTML form route: ```/addBook ``` <br />
HTML form route: (purchase) ```/book/:id/purchase ``` <br />
POST endpoint route: ```/api/addBook``` <br />
Example Node.js POST request to endpoint: <br />
```
var request = require("request");

var options = { 
    method: 'POST',
    url: 'http://localhost:3000/api/addBook',
    headers: { 
        'content-type': 'application/x-www-form-urlencoded' 
    },
    form: { 
        title: Road,
        year: 2014,
        author: Mike,
        words: 2428347,
        purchases: []
    } 
};

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

### 3. View Data
GET endpoint route: ```/api/getbooks```

### 4. Search Data
Search Field: ```Title``` <br />
Endpoint route: ```/getbook/:title```

### 5. Navigation Pages
Navigation Filters <br/ >

1. Thick Book -> ```/thickbook```
2. Allen's Book -> ```/Allen```
3. New Book -> ```/newbook```
4. Old Book -> ```/oldbook```
5. Popular Book -> ```/popbook```









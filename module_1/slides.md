# Compound Data Structures
## First Step @ Launch Academy

---

# Learning Outcomes

At the end of this program, you will be able to:

- Define a compound data structure
- Demonstrate valid use cases for an array of JSON objects
- Leverage Twitter API Data to answer a series of data oriented questions

---

# Overview of the Evening Together

1. Introductions and Logistics
2. **Facilitation**: API's and Compound Data Structures
  * Review JSON objects
  * API's in the wild
  * A Framework for Integrating API's
3. **Exercise**: Display a weather forecast
4. **Break**: Launch Academy and the Launcher Experience
5. **Facilitation**: Analyzing Compound Data Structures
  * Strategies for analyzing the nature of a given compound data structure
  * Address common gotchas in working with compound data structures
  * Common patterns for analysis
6. **Exercise**: Twitter Data analysis
7. Demos and Refactoring

---

# Module 1
## Compound Data Structures in the Real World

---

# First: Sign up for openweathermap

* https://openweathermap.org
* Go to the API tab

---

# *Recap*: Data Structures
## Arrays

![Shoe Cubby](https://images-na.ssl-images-amazon.com/images/I/61ibNWhYQ7L._SX355_.jpg)

---

# *Recap*: Data Structures
## Arrays

* Ordered "slots" for data
* Starts at index **0**
* *Mental Concept*: A line at the bank

---

# *Recap*: Data Structures
## Arrays


```javascript
var bankQueue = ['Sally', 'Sam', 'Jon']

// who's first in line?
console.log(bankQueue[0])

// who's last in line?
console.log(bankQueue[bankQueue.length - 1])

// get to the back of the line!
var newPatron = 'Dan'
bankQueue.push(newPatron)
console.log(bankQueue)

// forget this, I'm out of here
bankQueue.pop()
console.log(bankQueue)
```

---

# *Recap*: Data Structures
## JSON Literal

* Used to "name" data
* Order not as important
* Uses strings to access values

---

# *Recap*: Data Structures
## JSON Literal

```javascript
var person = {
  "firstName": "Jon",
  "lastName": "Snow",
  "occupation": "King in the North"
}

//what's their first name?
console.log(person["firstName"])
console.log(person.firstName)
```

---
# Other Data Structures

* Linked Lists
* Trees
* Graphs

---

# What is a Compound Data Structure?

```javascript
[
  {
    "coordinates": null,
    "truncated": false,
    "created_at": "Tue Aug 28 21:16:23 +0000 2012",
    "favorited": false,
    "id_str": "240558470661799936",
    "in_reply_to_user_id_str": null,
    "entities": {
      "urls": [

      ],
      "hashtags": [

      ],
      "user_mentions": [

      ]
    }
  }
]
```

---

# The Real World Use Case
## Application Programming Interface (API)

* Not a type of beer
* The Developer's web

---

# API's...

* Provide programmatic access to web data
* Allows third party access to manipulate data on the web

---

# API Delivery Methods

* CSV
* XML
* JSON

---

## CURL and Terminal
### GitHub User Info

```bash
curl -i https://api.github.com/users/launchacademy
```

---

## CURL and Terminal
### Digital Ocean Status API

```bash
curl -i https://s2k7tnzlhrpw.statuspage.io/api/v1/summary.json
```

---

## API's and Authentication

Some API's require api keys

```bash
curl -i http://api.openweathermap.org/data/2.5/weather?zip=02111,us&appid=<your key>
```

---

## Integrating Web API's: A Framework

- What are the business requirements?
- What data will you have as input?
- What data will the API be able to provide?
- What are the services available?
    - ProgrammableWeb as a great place to start
- Read the docs
- Evaluate:
  - How easy is it to integrate?
  - How popular is the service?
  - What support is available?
  - What are the licensing terms?
  - Understand applicable costs and rate limits

---

# Using jQuery and AJAX with API's

```javascript
var url = 'http://api.openweathermap.org/data/2.5/weather?zip=02111,us&appid=<your api key>'
  $.ajax({
    dataType: "json",
    url: url,
    success: function(data){
      console.log(data)
    }
  });
```

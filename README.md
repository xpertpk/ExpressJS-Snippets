# ExpressJs Snippets

## Snippets info
This is simple code snippet extension for express / node js projects. 
Below is the List of few Triggers that will generate boilerplate Codes.

## Supported languages (file extensions)

- JavaScript (.js)

## Basic Methods
<!-- Tables -->
| Prefix          | Method                            |
| --------------- | --------------------------------- |
| `!express`      | Create Express server             |
| `!route.get` 	  | Create GET Route Method           |
| `!route.post`   | Create POST Route Method          |
| `!route.put`    | Create PUT Route Method           |
| `!route.delete` | Create DELETE Route Method        | 
| `!route.all`    | Create ALL Route Methods          |
| `!mongo.local`  | Connect to Local Mongo DB         |
| `!mongo.cloud`  | Connect to Mongo DB Cloud Storage |


## ExpressJs Snippets

### `!express`

```javascript
const express = require('express');
const bodyParser = require('body-parser');
const app = express();

// parse application/x-www-form-urlencoded
app.use(bodyParser.urlencoded({ extended: false }))

// parse application/json
app.use(bodyParser.json())

app.post('/', (req, res) => {
    const data = req.body;
    res.send(`Hello ${data.name}!`);
});

app.listen(3000, () => {
    console.log('Server running on port 3000');
});
```

### `!route.get`

```javascript
app.get('/API_URL', async (req, res) => {
    try {
        const id = req.params.id;
        // code that could throw an error, such as an asynchronous function
        const user = await fetchUser(id);
        res.send(`User: ${user}`);
    } catch (error) {
        res.status(500).send({ error: error.message });
    }
});
```

### `route.post`

```javascript
app.post('/API_URL', async (req, res) => {
    try {
        const id = req.params.id;
        // code that could throw an error, such as an asynchronous function
        const user = await fetchUser(id);
        res.send(`User: ${user}`);
    } catch (error) {
        res.status(500).send({ error: error.message });
    }
});
```

### `!route.put`

```javascript
router.put('/API_URL/:id', async(req, res) => {
    try {
        const apps = await Apps.findByIdAndUpdate(req.params.id, {
            key:value
        },{new: true})
        res.send(apps)
    } catch (error) {
        res.status(500).send(error.message)
    }
});
```

### `!route.delete`

```javascript
router.delete('/API_URL/:id', async(req, res) => {
    try {
        const apps = await Apps.findByIdAndDelete(req.params.id)
        res.send(apps)
    } catch (error) {
        res.status(500).send(error.message)
    }
});
```

### `!route.all`

```javascript
const { Router } = require('express');
const router = Router();
const Apps = require('../model/Apps')

router.get('/', async(req, res) => {
    try {
        const appss = await Apps.find()
        res.send(appss)
    } catch (error) {
        res.status(500).send(error.message)
    }
})

router.post('/', async(req, res) => {
    try {
        let apps = new Apps({
            key:value
        })
        apps = await apps.save()
        res.send(apps)
    } catch (error) {
        res.status(500).send(error.message)
    }
})

router.get('/:id', async(req, res) => {
    try {
        const apps = await Apps.findById(req.params.id)
        res.send(apps)
    } catch (error) {
        res.status(500).send(error.message)
    }
})

router.put('/:id', async(req, res) => {
    try {
        const apps = await Apps.findByIdAndUpdate(req.params.id, {
            key:value
        },{new: true})
        res.send(apps)
    } catch (error) {
        res.status(500).send(error.message)
    }
})

router.delete('/:id', async(req, res) => {
    try {
        const apps = await Apps.findByIdAndDelete(req.params.id)
        res.send(apps)
    } catch (error) {
        res.status(500).send(error.message)
    }
})

module.exports = router
```

### `!mongo.local`

```javascript
const mongoose = require('mongoose');

// Connect MongoDB at default port = 27017
mongoose.connect('mongodb://localhost:27017/DB Name', {
useNewUrlParser: true,
useCreateIndex: true,
}, (err) => {
    if (!err) {
        console.log('MongoDB Connection Succeeded.')
    } else {
        console.log('Error in DB connection: ' + err)
    }
});
```

### `!mongo.cloud`

```javascript
const mongoose = require('mongoose');

mongoose.connect(process.env.MONGO_DB_URL, {
    useNewUrlParser: true,
    useUnifiedTopology: true,
}).then(response=>{
    console.log('MongoDB Connection Succeeded.')
}).catch(error=>{
    console.log('Error in DB connection: ' + error)
});
```

## Release Notes

This is the release notes.

### 1.0.4

Snippets code added to Readme file.

### 1.0.3

MongoDB and all-routers snippets added.

### 1.0.2

Multiple routes snippets added.

### 1.0.1

Express snippet added to this extension.

### 1.0.0

ExpressJS snippets extension added.

## Publisher

###### Mern Stack Developer - Shahbaz Mughal
@xpertpk

My Passion and Love:

**Hostings House & Mumara**.

![App Logo](https://hmco.pk/icon.png)
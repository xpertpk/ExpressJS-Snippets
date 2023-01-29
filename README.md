# ExpressJs Snippets

## Snippets info
ExpressJS snippets are code snippets that can be used to quickly write and insert common ExpressJS code patterns into your application. Some benefits of using ExpressJS snippets include:

- Increased productivity: ExpressJS snippets can help you write code faster and more efficiently, allowing you to focus on the logic of your application rather than the syntax of the ExpressJS framework.

- Consistency: Using ExpressJS snippets can help ensure that your code is consistent and follows best practices, making it easier to maintain and understand.

- Reduced errors: ExpressJS snippets can help reduce the number of errors in your code, as they are pre-written and tested code patterns.

- Learning aid: ExpressJS snippets can be a useful tool for learning the framework, as they can help you understand how different parts of ExpressJS work and how they can be used in your application.

- Community support: Many popular code editors like Visual Studio Code, have a large community of developers who contribute and share their own ExpressJS snippets, so you can find the snippet that best suits your needs.

- Customization: You can also customize and modify the snippets to fit your specific requirements and development style.

- Overall, ExpressJS snippets can be a valuable tool for developers working with the ExpressJS framework, helping them write code faster, more

### `ExpressJS Snippets`
![ExpressJS Snippets](https://raw.githubusercontent.com/xpertpk/express-snippets/main/express.gif)

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
| `!upload.image` | Upload and store image to server  |


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

### `!upload.image`

```javascript
const express = require('express');
const multer = require('multer');
const app = express();
const storage = multer.diskStorage({
    destination: (req, file, cb) => {
        cb(null, 'uploads/');
    },
    filename: (req, file, cb) => {
        cb(null, file.originalname);
    }
});
const upload = multer({ storage });

app.post('/upload', upload.single('image'), (req, res) => {
    if (!req.file) {
        return res.status(400).send('No file uploaded.');
    }
    res.send(`File uploaded: ${req.file.originalname}`);
});

app.listen(3000, () => {
    console.log('Server running on port 3000');
});
```

## Release Notes

ExpressJs snippets release notes.

### 1.0.7

ExpressJS Snippet help gif uploaded

### 1.0.6

ExpressJS Snippet Code finished

### 1.0.5

ExpressJS route that handles image upload and saving using the `multer` middleware.

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

![App Logo](https://raw.githubusercontent.com/xpertpk/express-snippets/main/icon.png)

```javascript
Install Extension for all type of expressjs project snippets here:
https://marketplace.visualstudio.com/items?itemName=Xpertpk.express-snippets
```

```javascript
Read more information about expressjs snippets:
https://meshahbazmughal.medium.com/expressjs-snippets-the-vscode-extension-fab92e853430
```

**Enjoy!**

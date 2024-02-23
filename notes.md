### Creating your own middleware

```JS
app.use((req, res, next) => {
  req.requestTime = new Date().toISOString();
  next();
});
```

- We can modify req object like req.requestTime = new Date();

### Mounting the router

- Basically meanas to mount a route to a route

```JS
// 3) ROUTES

const userRouter = require('./routes/userRoutes');
const tourRouter = require('./routes/tourRoutes');


//This is where we mount our routers, which are stored above
app.use('/api/v1/tours', tourRouter);
app.use('/api/v1/users', userRouter);
```

- app.use('/api/v1/tours', tourRouter); for this route we are applying tourRouter middleware

### Route Handlers becomes controllers in Model View Controller Software Architecture

- nodemon install --global
- nodemon install --save-dev

### Task :

- Create a checkBody middleware
- Check if the body contains the name and the price property
- if not then send 400 (Bad Request)
- Add it to the post handler Stack

```JS

exports.checkBody =  (req, res, next, val)=> {

    if(!req.body || !req.price){
        return res.status(400).json({
            status:"error",
        })
    }
    next();
}

```

The error you’re seeing is because the command you’re trying to run is specific to Unix-based systems, and it’s not compatible with Windows command prompt.

In Windows, you can use the cross-env package to set environment variables. Here’s how you can do it:

First, install the cross-env package by running the following command in your terminal:

```**bash**
npm install --save-dev cross-env
```

Then, modify your start:prod script in your package.json file to use cross-env like this:
JSON

```bash
"start:prod": "cross-env NODE_ENV=production nodemon server.js"
```

AI-generated code. Review and use carefully. More info on FAQ.
Now, you should be able to run your start:prod script on Windows without any issues. The cross-env package ensures that you can use the same command to set environment variables across different platforms. It’s a handy tool for maintaining cross-platform Node.js projects.

Remember to run npm install after modifying your package.json file to install the new package.

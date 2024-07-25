## Core Node.js Questions:

- What is the event loop in Node.js, and how does it work?
  The event loop is a key component of Node.js's asynchronous architecture. It continuously checks the call stack and the event queue. When the call stack is empty, it processes the next event from the event queue. This allows Node.js to perform non-blocking I/O operations by offloading tasks to the operating system.

- Explain the difference between setImmediate and process.nextTick.
  setImmediate schedules a callback to be executed on the next iteration of the event loop, after I/O events. process.nextTick schedules a callback to be executed before the next iteration of the event loop, essentially giving it higher priority.

- How does Node.js handle asynchronous operations?
  Node.js handles asynchronous operations using callbacks, Promises, and async/await syntax. It uses the event loop to manage these operations without blocking the main thread, allowing it to perform other tasks while waiting for asynchronous operations to complete.
- What are streams in Node.js? How do you use them?
  Streams are objects that allow reading and writing data in a continuous flow. They are used for handling large amounts of data efficiently. There are four types of streams: readable, writable, duplex (both readable and writable), and transform (modifies data as it is read or written).

```
const fs = require('fs');
const readableStream = fs.createReadStream('input.txt');
const writableStream = fs.createWriteStream('output.txt');
readableStream.pipe(writableStream);
```

- Explain the concept of middleware in Express.js.
  Middleware functions are functions that have access to the request and response objects and can modify them. They can perform tasks such as logging, authentication, parsing request bodies, and handling errors. Middleware functions can be stacked together to handle requests in a sequential manner.

## Express.js Questions:

How do you create a RESTful API using Express.js?
By defining routes that correspond to the CRUD operations (Create, Read, Update, Delete) and using HTTP methods (GET, POST, PUT, DELETE). Each route handler interacts with the database and sends appropriate responses.

```
const express = require('express');
const app = express();
app.use(express.json());

app.get('/api/items', (req, res) => res.send('GET all items'));
app.post('/api/items', (req, res) => res.send('POST new item'));
app.put('/api/items/:id', (req, res) => res.send(`PUT item ${req.params.id}`));
app.delete('/api/items/:id', (req, res) => res.send(`DELETE item ${req.params.id}`));

app.listen(3000, () => console.log('Server running on port 3000'));

```

- What are the different types of middleware in Express.js?
  Application-level middleware: bound to an instance of the app using app.use().
  Router-level middleware: bound to an instance of express.Router().
  Error-handling middleware: takes four arguments (err, req, res, next) and handles errors.
  Built-in middleware: such as express.json() and express.static().
  Third-party middleware: such as body-parser and cors.

- How do you handle errors in Express.js?
  By defining error-handling middleware. This middleware has four arguments (err, req, res, next) and should be placed after all other middleware and routes.

  ```
  app.use((err, req, res, next) => {
    console.error(err.stack);
    res.status(500).send('Something went wrong!');
  });

  ```

- How do you handle file uploads in Express.js?
  By using middleware such as multer. multer handles multipart/form-data, which is used for file uploads.

```
const multer = require('multer');
const upload = multer({ dest: 'uploads/' });

app.post('/upload', upload.single('file'), (req, res) => {
    res.send('File uploaded!');
});

```

- Explain the role of app.use() in Express.js.
  app.use() is used to mount middleware functions to the application. It can be used to apply middleware to all routes or to specific routes by passing a path as the first argument.

## Advanced Node.js Questions:

- What are child processes in Node.js, and how do you use them?
  Child processes allow you to execute other programs or scripts from within a Node.js application. You can use the child_process module to create and manage these processes.

```
const { exec } = require('child_process');
exec('ls -la', (err, stdout, stderr) => {
    if (err) {
        console.error(`Error: ${err}`);
        return;
    }
    console.log(`Output: ${stdout}`);
});

```

- How do you implement authentication and authorization in a Node.js application?
  By using libraries like jsonwebtoken for JWT-based authentication and middleware to protect routes.

```
const jwt = require('jsonwebtoken');
const secretKey = 'your_secret_key';

app.post('/login', (req, res) => {
    const { username, password } = req.body;
    // Validate credentials
    const token = jwt.sign({ username }, secretKey, { expiresIn: '1h' });
    res.json({ token });
});

const authenticate = (req, res, next) => {
    const token = req.header('Authorization').replace('Bearer ', '');
    try {
        const decoded = jwt.verify(token, secretKey);
        req.user = decoded;
        next();
    } catch (err) {
        res.status(401).send('Unauthorized');
    }
};

app.get('/protected', authenticate, (req, res) => {
    res.send('Protected resource');
});

```

- What are WebSockets, and how do you use them in Node.js?
  WebSockets provide full-duplex communication channels over a single TCP connection. You can use the ws library to implement WebSocket functionality in a Node.js application.

- Explain the concept of clustering in Node.js.
  Clustering allows you to create multiple instances of a Node.js application to take advantage of multi-core systems. The cluster module helps to create a master process that forks worker processes, each running an instance of the application.

- How do you optimize a Node.js application for performance?
  Optimizing a Node.js application for performance involves a combination of best practices, tools, and techniques to ensure efficient resource utilization, faster response times, and overall better performance. Here are some key strategies:

Asynchronous and Non-Blocking Operations:
Use Async/Await or Promises: Ensure that your code makes use of async/await or Promises to handle asynchronous operations, avoiding blocking the event loop.

Clustering:
Use the Cluster Module: Node.js runs on a single thread by default. Utilize the cluster module to create multiple worker processes that can take advantage of multi-core systems.
javascript

Caching:
Implement Caching Strategies: Use caching for frequently accessed data to reduce database or API calls. Common caching mechanisms include in-memory caching (e.g., with Redis) and HTTP caching headers.

Optimize Database Queries:
Use Indexes: Ensure your database queries are optimized with appropriate indexes.
Limit Data Returned: Fetch only the necessary data and use projections in MongoDB to limit the fields returned.

Use Load Balancing:
Employ a Reverse Proxy: Use a reverse proxy server (e.g., Nginx) to distribute incoming traffic across multiple instances of your application.

Minimize and Optimize Dependencies:
Review Dependencies: Regularly review and remove unused dependencies. Minimize the number of dependencies to reduce overhead.
Optimize Bundles: Use tools like Webpack or Parcel to bundle and minify JavaScript files.

Monitor and Profile:
Use Monitoring Tools: Implement monitoring tools like New Relic, Datadog, or Prometheus to track application performance and identify bottlenecks.
Profile with Node.js Tools: Use built-in profiling tools or libraries like clinic.js to analyze performance and identify hotspots.

Optimize Memory Usage:
Avoid Memory Leaks: Regularly test for memory leaks using tools like memwatch-next or heapdump.
Manage Memory Efficiently: Use streams and avoid loading large amounts of data into memory all at once.

Efficient Error Handling:
Handle Errors Gracefully: Implement proper error handling to avoid crashes and ensure that errors are logged and managed without impacting performance.

Use Efficient Algorithms and Data Structures:
Optimize Algorithms: Use efficient algorithms and data structures to reduce computation time and memory usage.

Enable Compression:
Gzip Compression: Use gzip compression to reduce the size of HTTP responses. This can be done using middleware like compression in Express.

##Testing and Debugging Questions:

- How do you test Node.js applications?
- What are some common testing frameworks for Node.js?
- How do you debug a Node.js application?
- Explain the role of the assert module in Node.js.
- How do you use tools like Mocha, Chai, and Jest for testing Node.js applications?

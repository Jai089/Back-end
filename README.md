const express = require('express');
const app = express();
const port = 3000;

// Middleware for parsing JSON requests
app.use(express.json());

// Example route handler for handling user requests
app.get('/', (req, res) => {
  res.send('Welcome to the back end of the website!');
});

// Example route handler for handling user requests to retrieve data
app.get('/api/data', (req, res) => {
  // Logic to retrieve data from the website's storage
  const data = { message: 'Data retrieved successfully' };
  res.json(data);
});

// Example route handler for handling user requests to store data
app.post('/api/data', (req, res) => {
  // Logic to store data in the website's storage
  const newData = req.body;
  // Assuming data storage is successful
  res.json({ message: 'Data stored successfully', data: newData });
});

// Middleware for handling errors
app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(500).send('Internal Server Error');
});

// Start the server
app.listen(port, () => {
  console.log(`Server is running on http://localhost:${port}`);
});


// Start the server
app.listen(port, () => {
  console.log(`Server is running on http://localhost:${port}`);
});


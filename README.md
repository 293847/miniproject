TASK 1: Landing Page
Develop a simple, clean landing page using HTML and CSS.
HTML (index.html):
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Landing Page</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#services">Services</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>
    <main>
        <section id="home">
            <h1>Welcome to Our Website</h1>
            <p>Your journey to success starts here.</p>
            <button>Learn More</button>
        </section>
    </main>
    <footer>
        <p>&copy; 2024 Company Name. All rights reserved.</p>
    </footer>
</body>
</html>
CSS (styles.css):
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

header {
    background: #333;
    color: #fff;
    padding: 1rem;
}

nav ul {
    list-style: none;
    display: flex;
    justify-content: space-around;
    padding: 0;
}

nav a {
    color: #fff;
    text-decoration: none;
}

main {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 80vh;
    background: #f4f4f4;
    text-align: center;
}

footer {
    background: #333;
    color: #fff;
    text-align: center;
    padding: 1rem 0;
    position: absolute;
    bottom: 0;
    width: 100%;
}
TASK 2: Simple Website with DropDowns
Develop a website with dropdown navigation and multiple pages.

HTML (index.html):
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Website</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <nav>
            <ul>
                <li><a href="index.html">Home</a></li>
                <li class="dropdown">
                    <a href="javascript:void(0)" class="dropbtn">Services</a>
                    <div class="dropdown-content">
                        <a href="service1.html">Service 1</a>
                        <a href="service2.html">Service 2</a>
                        <a href="service3.html">Service 3</a>
                    </div>
                </li>
                <li><a href="about.html">About</a></li>
                <li><a href="contact.html">Contact</a></li>
            </ul>
        </nav>
    </header>
    <main>
        <h1>Welcome to Our Simple Website</h1>
        <p>Navigate using the menu above.</p>
    </main>
    <footer>
        <p>&copy; 2024 Company Name. All rights reserved.</p>
    </footer>
</body>
</html>
CSS (styles.css):
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

header {
    background: #333;
    color: #fff;
    padding: 1rem;
}

nav ul {
    list-style: none;
    display: flex;
    justify-content: space-around;
    padding: 0;
}

nav a {
    color: #fff;
    text-decoration: none;
    padding: 1rem;
}

.dropdown {
    position: relative;
    display: inline-block;
}

.dropdown-content {
    display: none;
    position: absolute;
    background-color: #f9f9f9;
    min-width: 160px;
    box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
    z-index: 1;
}

.dropdown-content a {
    color: black;
    padding: 12px 16px;
    text-decoration: none;
    display: block;
}

.dropdown-content a:hover {background-color: #f1f1f1;}

.dropdown:hover .dropdown-content {display: block;}
.dropdown:hover .dropbtn {background-color: #3e8e41;}

TASK 3: Login Signup Page using PHP
Build a login and signup page using HTML, CSS, PHP, and MySQL.

HTML (login.html):

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="form-container">
        <form action="login.php" method="post">
            <h2>Login</h2>
            <label for="username">Username:</label>
            <input type="text" id="username" name="username" required>
            <label for="password">Password:</label>
            <input type="password" id="password" name="password" required>
            <button type="submit">Login</button>
            <p>Don't have an account? <a href="signup.html">Sign Up</a></p>
        </form>
    </div>
</body>
</html>

HTML (signup.html):

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sign Up</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="form-container">
        <form action="signup.php" method="post">
            <h2>Sign Up</h2>
            <label for="username">Username:</label>
            <input type="text" id="username" name="username" required>
            <label for="password">Password:</label>
            <input type="password" id="password" name="password" required>
            <button type="submit">Sign Up</button>
            <p>Already have an account? <a href="login.html">Login</a></p>
        </form>
    </div>
</body>
</html>

CSS (styles.css):
body {
    font-family: Arial, sans-serif;
    background: #f4f4f4;
    margin: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

.form-container {
    background: #fff;
    padding: 2rem;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

form {
    display: flex;
    flex-direction: column;
}

label, input, button {
    margin-bottom: 1rem;
}

PHP (login.php):

<?php
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "mydatabase";

$conn = new mysqli($servername, $username, $password, $dbname);

if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}

$username = $_POST['username'];
$password = $_POST['password'];

$sql = "SELECT * FROM users WHERE username='$username' AND password='$password'";
$result = $conn->query($sql);

if ($result->num_rows > 0) {
    echo "Login successful!";
} else {
    echo "Invalid username or password!";
}

$conn->close();
?>

PHP (signup.php):
<?php
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "mydatabase";

$conn = new mysqli($servername, $username, $password, $dbname);

if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}

$username = $_POST['username'];
$password = $_POST['password'];

$sql = "INSERT INTO users (username, password) VALUES ('$username', '$password')";

if ($conn->query($sql) === TRUE) {
    echo "Signup successful!";
} else {
    echo "Error: " . $sql . "<br>" . $conn->error;
}

$conn->close();
?>

TASK 4: Calculator using JavaScript
Develop a basic calculator using HTML, CSS, and JavaScript.

HTML (index.html):

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="calculator">
        <input type="text" id="display" disabled>
        <div class="buttons">
            <button onclick="appendNumber('1')">1</button>
            <button onclick="appendNumber('2')">2</button>
            <button onclick="appendNumber('3')">3</button>
            <button onclick="appendNumber('+')">+</button>
            <button onclick="appendNumber('4')">4</button>
            <button onclick="appendNumber('5')">5</button>
            <button onclick="appendNumber('6')">6</button>
            <button onclick="appendNumber('-')">-</button>
            <button onclick="appendNumber('7')">7</button>
            <button onclick="appendNumber('8')">8</button>
            <button onclick="appendNumber('9')">9</button>
            <button onclick="appendNumber('*')">*</button>
            <button onclick="appendNumber('0')">0</button>
            <button onclick="clearDisplay()">C</button>
            <button onclick="calculate()">=</button>
            <button onclick="appendNumber('/')">/</button>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>

CSS (styles.css):

body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background: #f4f4f4;
    font-family: Arial, sans-serif;
}

.calculator {
    background: #fff;
    padding: 1rem;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

#display {
    width: 100%;
    padding: 1rem;
    font-size: 1.5rem;
    text-align: right;
    margin-bottom: 1rem;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 0.5rem;
}

button {
    padding: 1rem;
    font-size: 1.5rem;
    background: #f0f0f0;
    border: none;
    cursor: pointer;
}

button:hover {
    background: #ddd;
}

JavaScript (script.js):

let display = document.getElementById('display');

function appendNumber(number) {
    display.value += number;
}

function clearDisplay() {
    display.value = '';
}

function calculate() {
    display.value = eval(display.value);
}

TASK 5: FrontEnd Development using ReactJS
Develop a landing page using ReactJS.

React Components:

App.js:

import React from 'react';
import './App.css';

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <nav>
          <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#services">Services</a></li>
            <li><a href="#contact">Contact</a></li>
          </ul>
        </nav>
      </header>
      <main>
        <section id="home">
          <h1>Welcome to Our Website</h1>
          <p>Your journey to success starts here.</p>
          <button>Learn More</button>
        </section>
      </main>
      <footer>
        <p>&copy; 2024 Company Name. All rights reserved.</p>
      </footer>
    </div>
  );
}

export default App;

App.css:

body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.App {
    text-align: center;
}

.App-header {
    background: #333;
    color: #fff;
    padding: 1rem;
}

nav ul {
    list-style: none;
    display: flex;
    justify-content: space-around;
    padding: 0;
}

nav a {
    color: #fff;
    text-decoration: none;
}

main {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 80vh;
    background: #f4f4f4;
    text-align: center;
}

footer {
    background: #333;
    color: #fff;
    text-align: center;
    padding: 1rem 0;
    position: absolute;
    bottom: 0;
    width: 100%;
}

TASK 6: To-Do List using MERN Stack
Develop a To-Do List application with the ability to add, update, and delete tasks using the MERN stack.

Frontend (React):

App.js:

import React, { useState, useEffect } from 'react';
import axios from 'axios';
import './App.css';

function App() {
  const [tasks, setTasks] = useState([]);
  const [task, setTask] = useState('');
  const [editId, setEditId] = useState(null);

  useEffect(() => {
    fetchTasks();
  }, []);

  const fetchTasks = async () => {
    const response = await axios.get('/api/tasks');
    setTasks(response.data);
  };

  const addTask = async () => {
    if (editId) {
      await axios.put(`/api/tasks/${editId}`, { task });
    } else {
      await axios.post('/api/tasks', { task });
    }
    setTask('');
    setEditId(null);
    fetchTasks();
  };

  const editTask = (id, task) => {
    setTask(task);
    setEditId(id);
  };

  const deleteTask = async (id) => {
    await axios.delete(`/api/tasks/${id}`);
    fetchTasks();
  };

  return (
    <div className="App">
      <h1>To-Do List</h1>
      <input
        type="text"
        value={task}
        onChange={(e) => setTask(e.target.value)}
      />
      <button onClick={addTask}>{editId ? 'Update' : 'Add'}</button>
      <ul>
        {tasks.map((task) => (
          <li key={task._id}>
            {task.task}
            <button onClick={() => editTask(task._id, task.task)}>Edit</button>
            <button onClick={() => deleteTask(task._id)}>Delete</button>
          </li>
        ))}
      </ul>
    </div>
  );
}

export default App;

Backend (Node.js/Express):

server.js:

const express = require('express');
const mongoose = require('mongoose');
const cors = require('cors');
const Task = require('./models/Task');

const app = express();
const PORT = 5000;

mongoose.connect('mongodb://localhost:27017/todolist', { useNewUrlParser: true, useUnifiedTopology: true });

app.use(cors());
app.use(express.json());

app.get('/api/tasks', async (req, res) => {
  const tasks = await Task.find();
  res.json(tasks);
});

app.post('/api/tasks', async (req, res) => {
  const newTask = new Task(req.body);
  await newTask.save();
  res.json(newTask);
});

app.put('/api/tasks/:id', async (req, res) => {
  const updatedTask = await Task.findByIdAndUpdate(req.params.id, req.body, { new: true });
  res.json(updatedTask);
});

app.delete('/api/tasks/:id', async (req, res) => {
  await Task.findByIdAndDelete(req.params.id);
  res.json({ message: 'Task deleted' });
});

app.listen(PORT, () => {
  console.log(`Server running on port ${PORT}`);
});

Task Model (models/Task.js):
const mongoose = require('mongoose');

const taskSchema = new mongoose.Schema({
  task: {
    type: String,
    required: true
  }
});

module.exports = mongoose.model('Task', taskSchema);


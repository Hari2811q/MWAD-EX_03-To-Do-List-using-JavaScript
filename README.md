# MWAD-EX_03-To-Do-List-using-JavaScript
## Date:29.10.25

## AIM
To create a To-do Application with all features using JavaScript.

## ALGORITHM
### STEP 1
Build the HTML structure (index.html).

### STEP 2
Style the App (style.css).

### STEP 3
Plan the features the To-Do App should have.

### STEP 4
Create a To-do application using Javascript.

### STEP 5
Add functionalities.

### STEP 6
Test the App.

### STEP 7
Open the HTML file in a browser to check layout and functionality.

### STEP 8
Fix styling issues and refine content placement.

### STEP 9
Deploy the website.

### STEP 10
Upload to GitHub Pages for free hosting.

## PROGRAM
## HTML
```
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To do list</title>
    <link rel="stylesheet" href="ds1.css">
</head>

<body>
    <h1> MY TO-DO LIST</h1>
    <div class="tasks-container">
        <div class="task-box">
            <h2>Task Header</h2>
            <p>Task description</p>
            <button class="delete-btn">Delete</button>
        </div>
    </div>
    
    <div class="add-task-form">
        <input type="text" placeholder="Enter the task header">
        <input type="text" placeholder="Enter the task description">
        <button class="add-task-btn">Add</button>
    </div>
    <button class="add-btn">+</button>
    <script src="ds1.js"></script>
</body>
</html>
```

## CSS
```
    margin: 0;
    padding: 0;
    font-family: 'Times New Roman', Times, serif;
    background-color: rgb(154, 74, 174);
    display: flex;
    flex-direction: column;
    align-items: center;
    min-height: 100vh;
}
h1{
    text-align: center;
    color: rgb(36, 17, 41);
}
.tasks-container{
    width: 90%;
    max-width: 650px;
    margin: 25px;
}
.task-box{
    box-shadow: 0 4px 6px rgba(151, 58, 58, 0.1);
    padding: 18px;
    background-color: rgb(91, 15, 135);
    border-radius: 10px;
    position: relative;
}
.task-box h2{
    margin: 0 0 5px;
    color: rgb(191, 166, 204);
}
.task-box p{
    margin: 0 0 10px;
    color: #bda1d1;
}
.delete-btn{
    position: absolute;
    top: 40px;
    right: 15px;
    padding: 5px 10px;
    border-radius: 8px;
    border: 1px solid;
    background-color: rgb(158, 16, 234);
}
.add-task-form{
    display: none;
    flex-direction: column;
    border: 2px solid;
    border-radius: 10px;
    padding: 18px;
    width: 90%;
    max-width: 650px;
    margin-top: 20px;
}
.add-task-form input{
    width: 90%;
    display: block;
    padding: 9px;
    border: 1px solid;
    border-radius: 8px;
    font-size: 18px;
    font-weight: 700;
    margin-bottom: 10px;
}
.add-task-btn{
    background-color: #4B0082;
    color: white;
    border: none;
    border-radius: 8px;
    width: 100%;
    height: 30px;
    cursor: pointer;
}
.add-btn{
    position: fixed;
    bottom: 20px;
    left: 20px;
    background-color: #4B0082;
    color: white;
    width: 60px;
    height: 60px;
    font-size: 35px;
    border-radius: 50%;
    border: none;
}
```
## JAVASCRIPT
```
const addBtn = document.querySelector('.add-btn');
const addTaskForm = document.querySelector('.add-task-form');
const addTaskBtn = document.querySelector('.add-task-btn');
const tasksContainer = document.querySelector('.tasks-container');
const inputs = addTaskForm.querySelectorAll('input');

addBtn.addEventListener('click', () => {
    if (addTaskForm.style.display === 'block') {
        addTaskForm.style.display = 'none';
    } else {
        addTaskForm.style.display = 'block';
    }
});

addTaskBtn.addEventListener('click', () => {
    const header = inputs[0].value.trim();
    const desc = inputs[1].value.trim();

    if (header && desc) {
        const newTask = document.createElement('div');
        newTask.classList.add('task-box');
        newTask.innerHTML = `
            <h2>${header}</h2>
            <p>${desc}</p>
            <button class="delete-btn">Delete</button>
        `;
        tasksContainer.appendChild(newTask);

        inputs[0].value = '';
        inputs[1].value = '';
    } else {
        alert("Please enter both task header and description.");
    }
});

tasksContainer.addEventListener('click', (event) => {
    if (event.target.classList.contains('delete-btn')) {
        event.target.parentElement.remove();
    }
});

```
## OUTPUT
<img width="1919" height="1199" alt="image" src="https://github.com/user-attachments/assets/a2060724-490a-41a3-85d9-6eeb231ea667" />


## RESULT
The program for creating To-do list using JavaScript is executed successfully.

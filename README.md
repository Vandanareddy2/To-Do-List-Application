# To-Do-List-Application
A simple To-Do List app built with HTML, CSS, and JavaScript to practice DOM manipulation. Demonstrates adding, editing, and removing tasks dynamically using methods like createElement(), appendChild(), and removeChild() for an interactive, real-time task manager.

# To-Do List Application  
A simple JavaScript DOM manipulation project that allows users to add, edit, and remove tasks dynamically. This project was built using HTML, CSS, and JavaScript with separate index.html and function.js files.  

Features: Add a new task with a single click or by pressing Enter, each task appears with Edit and Delete buttons, edit a task using a prompt box to update the text, delete a task instantly from the list, input box clears automatically after adding a task, simple and clean UI.  

Technologies Used: HTML5 for page structure, CSS3 for styling the to-do list container and layout, JavaScript (ES6) for DOM manipulation and task handling.  

File Structure:  
To-Do-List-Application/  
│── index.html (Main HTML page)  
│── function.js (JavaScript logic for Add/Edit/Delete tasks)  
│── README.md (Project documentation)  

How It Works: First we select elements using document.getElementById("taskInput") for the input field and document.getElementById("todoList") for the ul. Then we create new elements using document.createElement("li") for a task row, document.createElement("span") for the task text, and document.createElement("button") for Edit/Delete buttons. Event handlers are added: Edit button uses onclick = () => editTask(span) and Delete button uses onclick = () => removeTask(li). Next, we append elements: text and buttons go inside li, and li is appended to ul. Finally, we clear the input field using input.value = "" to reset it for the next entry.  

Demo Flow: Type a task and click Add Task, the task appears with Edit/Delete buttons. Click Edit to update the text, click Delete to remove the task.  

Example Code Snippet:  
```javascript
function addTask() {
    const input = document.getElementById("taskInput");
    const taskText = input.value.trim();
    if (taskText !== "") {
        const ul = document.getElementById("todoList");
        const li = document.createElement("li");
        const span = document.createElement("span");
        span.textContent = taskText;
        const editButton = document.createElement("button");
        editButton.textContent = "Edit";
        editButton.onclick = () => editTask(span);
        const removeButton = document.createElement("button");
        removeButton.textContent = "Delete";
        removeButton.onclick = () => removeTask(li);
        li.appendChild(span);
        li.appendChild(editButton);
        li.appendChild(removeButton);
        ul.appendChild(li);
        input.value = "";
    } else {
        alert("Please enter a valid task.");
    }
}

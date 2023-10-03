<!DOCTYPE html>
<html>
<head>
    <title>To-Do List</title>
</head>
<body>
    <h1>To-Do List</h1>
    <ul id="todo-list">
        <!-- To-do items will be dynamically added here -->
    </ul>
    <input type="text" id="new-task" placeholder="Add a new task">
    <button id="add-task">Add Task</button>

    <script>
        // JavaScript code for the to-do list
        const todoList = document.getElementById('todo-list');
        const newTaskInput = document.getElementById('new-task');
        const addTaskButton = document.getElementById('add-task');

        // Function to add a new task to the list
        function addTask() {
            const taskText = newTaskInput.value;
            if (taskText.trim() !== '') {
                const listItem = document.createElement('li');
                listItem.textContent = taskText;
                todoList.appendChild(listItem);
                newTaskInput.value = '';
            }
        }

        // Event listener for adding a task
        addTaskButton.addEventListener('click', addTask);

        // Event listener for pressing Enter to add a task
        newTaskInput.addEventListener('keypress', function (e) {
            if (e.key === 'Enter') {
                addTask();
            }
        });
    </script>
</body>
</html>

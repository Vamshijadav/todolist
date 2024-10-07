document.getElementById('addTaskBtn').addEventListener('click', function() {
    const taskInput = document.getElementById('taskInput');
    const taskText = taskInput.value.trim();

    if (taskText) {
        const taskList = document.getElementById('taskList');

        // Create a new list item
        const listItem = document.createElement('li');

        // Create a span for the task text
        const taskSpan = document.createElement('span');
        taskSpan.textContent = taskText;
        listItem.appendChild(taskSpan);

        // Add complete functionality
        taskSpan.addEventListener('click', function() {
            taskSpan.classList.toggle('completed');
        });

        // Create a remove button
        const removeBtn = document.createElement('button');
        removeBtn.textContent = 'Remove';
        removeBtn.classList.add('remove-btn');
        removeBtn.addEventListener('click', function() {
            taskList.removeChild(listItem);
        });

        // Append the remove button to the list item
        listItem.appendChild(removeBtn);

        // Append the list item to the task list
        taskList.appendChild(listItem);

        // Clear the input
        taskInput.value = '';
    }
});

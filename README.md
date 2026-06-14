<!DOCTYPE html>
<html>
<head>
    <title>Group Project Manager</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 700px;
            margin: 20px auto;
        }

        input, button {
            padding: 8px;
            margin: 5px;
        }

        li {
            margin: 8px 0;
        }

        .done {
            text-decoration: line-through;
            color: gray;
        }
    </style>
</head>
<body>

<h1>Group Project Manager</h1>

<h2>Add Team Member</h2>
<input type="text" id="memberInput" placeholder="Enter member name">
<button onclick="addMember()">Add Member</button>

<ul id="memberList"></ul>

<h2>Add Task</h2>
<input type="text" id="taskInput" placeholder="Enter task">
<button onclick="addTask()">Add Task</button>

<ul id="taskList"></ul>

<script>
function addMember() {
    let input = document.getElementById("memberInput");
    let name = input.value;

    if (name === "") return;

    let li = document.createElement("li");
    li.textContent = name;

    document.getElementById("memberList").appendChild(li);
    input.value = "";
}

function addTask() {
    let input = document.getElementById("taskInput");
    let task = input.value;

    if (task === "") return;

    let li = document.createElement("li");

    let checkbox = document.createElement("input");
    checkbox.type = "checkbox";

    checkbox.onchange = function() {
        if (checkbox.checked) {
            li.classList.add("done");
        } else {
            li.classList.remove("done");
        }
    };

    li.appendChild(checkbox);
    li.appendChild(document.createTextNode(" " + task));

    document.getElementById("taskList").appendChild(li);
    input.value = "";
}
</script>

</body>
</html>

# Revesed-Bucket-List
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Reversed Bucket List</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f9;
        }

        .container {
            max-width: 600px;
            margin: 20px auto;
            padding: 20px;
            background: white;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        h1 {
            text-align: center;
            color: #333;
        }

        form {
            display: flex;
            margin-bottom: 20px;
        }

        input[type="text"] {
            flex: 1;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
        }

        button {
            padding: 10px;
            border: none;
            background-color: #4CAF50;
            color: white;
            border-radius: 4px;
            cursor: pointer;
            margin-left: 10px;
        }

        button:hover {
            background-color: #45a049;
        }

        ul {
            list-style-type: none;
            padding: 0;
        }

        li {
            background: #f9f9f9;
            margin: 5px 0;
            padding: 10px;
            border-radius: 4px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border: 1px solid #ddd;
        }

        .delete {
            background: #ff4d4d;
            color: white;
            border: none;
            padding: 5px 10px;
            border-radius: 4px;
            cursor: pointer;
        }

        .delete:hover {
            background: #ff1a1a;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Reversed Bucket List</h1>
        <form id="bucketForm">
            <input type="text" id="achievementInput" placeholder="Add an achievement...">
            <button type="submit">Add</button>
        </form>
        <ul id="bucketList"></ul>
    </div>

    <script>
        const form = document.getElementById('bucketForm');
        const achievementInput = document.getElementById('achievementInput');
        const bucketList = document.getElementById('bucketList');

        form.addEventListener('submit', function(event) {
            event.preventDefault();

            const achievement = achievementInput.value.trim();

            if (achievement !== '') {
                addAchievement(achievement);
                achievementInput.value = '';
            }
        });

        function addAchievement(achievement) {
            const li = document.createElement('li');
            li.textContent = achievement;

            const deleteButton = document.createElement('button');
            deleteButton.textContent = 'Delete';
            deleteButton.classList.add('delete');
            deleteButton.addEventListener('click', function() {
                bucketList.removeChild(li);
            });

            li.appendChild(deleteButton);
            bucketList.appendChild(li);
        }
    </script>
</body>
</html>

# feb-2025-avasjcript-events-and-basic-interactivity
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript Events and Interactivity</title>
    <style>
        /* Simple styling for buttons and modal */
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
        }

        button {
            padding: 10px 20px;
            margin: 10px;
            background-color: #4CAF50;
            color: white;
            border: none;
            cursor: pointer;
        }

        button:hover {
            background-color: #45a049;
        }

        /* Modal styling */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            width: 300px;
            text-align: center;
        }

        input[type="password"] {
            padding: 8px;
            width: 100%;
        }
    </style>
</head>
<body>

    <h1>Interactive Web Page with JavaScript</h1>

    <!-- Change text content -->
    <h2>Change Text Example</h2>
    <p id="text-content">This is the original text.</p>
    <button id="change-text-btn">Change Text</button>

    <!-- Toggle password visibility -->
    <h2>Toggle Password Visibility</h2>
    <input type="password" id="password-field" placeholder="Enter password">
    <button id="toggle-password-btn">Show/Hide Password</button>

    <!-- Form validation -->
    <h2>Form Validation</h2>
    <form id="myForm">
        <input type="text" id="username" placeholder="Enter your name" required>
        <button type="submit">Submit</button>
    </form>

    <!-- Modal -->
    <h2>Modal Example</h2>
    <button id="open-modal-btn">Open Modal</button>

    <div class="modal" id="myModal">
        <div class="modal-content">
            <span id="close-modal-btn" style="cursor:pointer;">&times;</span>
            <h3>This is a Modal!</h3>
            <p>Click the close button to close.</p>
        </div>
    </div>

    <script>
        // 1. Change Text dynamically
        document.getElementById('change-text-btn').addEventListener('click', function() {
            document.getElementById('text-content').textContent = "The text has been changed dynamically!";
        });

        // 2. Toggle password visibility
        document.getElementById('toggle-password-btn').addEventListener('click', function() {
            const passwordField = document.getElementById('password-field');
            if (passwordField.type === "password") {
                passwordField.type = "text";
            } else {
                passwordField.type = "password";
            }
        });

        // 3. Form validation (prevent form submission if the field is empty)
        document.getElementById('myForm').addEventListener('submit', function(event) {
            const username = document.getElementById('username').value;
            if (username === "") {
                alert("Please enter your name!");
                event.preventDefault(); // Prevent form submission
            }
        });

        // 4. Modal functionality (open and close modal)
        const modal = document.getElementById('myModal');
        const openModalButton = document.getElementById('open-modal-btn');
        const closeModalButton = document.getElementById('close-modal-btn');

        openModalButton.addEventListener('click', function() {
            modal.style.display = 'flex'; // Show the modal
        });

        closeModalButton.addEventListener('click', function() {
            modal.style.display = 'none'; // Close the modal
        });
    </script>

</body>
</html>

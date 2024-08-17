<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fake Discord Messages</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: 'Whitney', Arial, sans-serif;
            background-color: #36393f;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .container {
            width: 100%;
            max-width: 900px;
            background-color: #2f3136;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
            display: flex;
            flex-direction: column;
            height: 80vh;
        }
        .header {
            background-color: #202225;
            color: #ffffff;
            padding: 15px;
            border-bottom: 1px solid #3f444d;
            display: flex;
            align-items: center;
            position: relative;
        }
        .header img {
            border-radius: 50%;
            width: 40px;
            height: 40px;
            margin-right: 10px;
        }
        .header h1 {
            margin: 0;
            font-size: 18px;
            font-weight: bold;
        }
        .messages {
            flex: 1;
            padding: 20px;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
        }
        .message {
            padding: 10px;
            border-radius: 8px;
            margin-bottom: 10px;
            max-width: 80%;
            word-wrap: break-word;
            line-height: 1.4;
            position: relative;
            display: flex;
            align-items: flex-start;
        }
        .from-user {
            background-color: #7289da;
            color: #ffffff;
            align-self: flex-end;
        }
        .from-bot {
            background-color: #ffffff;
            color: #000000;
            align-self: flex-start;
        }
        .message .avatar {
            width: 32px;
            height: 32px;
            border-radius: 50%;
            margin-right: 8px;
        }
        .message .content {
            display: flex;
            flex-direction: column;
        }
        .message .username {
            font-weight: bold;
            color: #ffffff;
            margin-bottom: 5px;
        }
        .input-area {
            border-top: 1px solid #3f444d;
            padding: 10px;
            background-color: #202225;
            display: flex;
            flex-direction: column;
        }
        .input-area input[type="text"] {
            border: 1px solid #7289da;
            border-radius: 20px;
            padding: 10px;
            margin-bottom: 10px;
            background-color: #2f3136;
            color: #ffffff;
        }
        .input-area button {
            background-color: #7289da;
            color: #ffffff;
            border: none;
            padding: 10px;
            border-radius: 20px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        .input-area button:hover {
            background-color: #5b6eae;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <img src="https://cdn.discordapp.com/icons/yourserverid/youricon.png" alt="Server Icon">
            <h1>Fake Discord Chat</h1>
        </div>
        <div class="messages" id="messages">
            <!-- Messages will be appended here -->
        </div>
        <div class="input-area">
            <input type="text" id="user-id-input" placeholder="Enter user ID...">
            <input type="text" id="user-name-input" placeholder="Enter user name...">
            <input type="text" id="user-message-input" placeholder="Enter user message...">
            <input type="text" id="my-name-input" placeholder="Enter your name...">
            <input type="text" id="my-message-input" placeholder="Enter your message...">
            <button id="load-button">Send Messages</button>
        </div>
    </div>

    <script>
        const messagesDiv = document.getElementById('messages');
        const userIdInput = document.getElementById('user-id-input');
        const userNameInput = document.getElementById('user-name-input');
        const userMessageInput = document.getElementById('user-message-input');
        const myNameInput = document.getElementById('my-name-input');
        const myMessageInput = document.getElementById('my-message-input');
        const loadButton = document.getElementById('load-button');

        // Mock user data
        const userDatabase = {
            '123456': { name: 'User One', avatar: 'https://cdn.discordapp.com/avatars/123456/userone.png' },
            '789101': { name: 'User Two', avatar: 'https://cdn.discordapp.com/avatars/789101/usertwo.png' }
        };

        loadButton.addEventListener('click', () => {
            const userId = userIdInput.value.trim();
            const userName = userNameInput.value.trim();
            const userMessage = userMessageInput.value.trim();
            const myName = myNameInput.value.trim();
            const myMessage = myMessageInput.value.trim();

            if (userId && userMessage && myMessage) {
                let user = userDatabase[userId];
                if (!user) {
                    user = { name: userName, avatar: 'https://cdn.discordapp.com/embed/avatars/0.png' };
                }
                appendMessage(userMessage, 'from-user', user.name, user.avatar);
                appendMessage(myMessage, 'from-bot', myName);
            } else {
                appendMessage('Invalid input or user not found.', 'from-bot');
            }
        });

        function appendMessage(text, className, username = 'Bot', avatar = 'https://cdn.discordapp.com/embed/avatars/0.png') {
            const message = document.createElement('div');
            message.className = `message ${className}`;
            message.innerHTML = `
                <img src="${avatar}" alt="${username}" class="avatar">
                <div class="content">
                    <div class="username">${username}</div>
                    <div>${text}</div>
                </div>
            `;
            messagesDiv.appendChild(message);
            messagesDiv.scrollTop = messagesDiv.scrollHeight;
        }
    </script>
</body>
</html>

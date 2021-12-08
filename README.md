# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.\
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

# Chat Engine

Chat Engine is a free serverless chat API.

Try our free plan at chatengine.io

## Installation
Using npm: npm install react-chat-engine --save
Using Yarn: yarn add react-chat-engine
Quick Start
Add serverless chat to your React app in 3 minutes.

Register then create a project and user at chatengine.io

Collect the public key, username and user password

Install yarn add react-chat-engine

Import the ChatEngine component and pass in publicKey, userName, and userSecret props

Voila! You're done

### EXAMPLE: Your implementation should look like the following
```
import React from 'react'

import { ChatEngine } from 'react-chat-engine'

export function App() {
  return (
    <ChatEngine
      publicKey={'b75e5bd5-cd84-404c-b820-06feff8c98c0'}
      userName={'john_smith'}
      userSecret={'secret_1234'}
    />
  )
}
```

## Features
* Authenticate users
* Subscribe (connect) to incoming chats and messages
* Create chats and messages
* Add and remove people from chats
* Edit and delete chat and message data

## Props
* `publicKey` (UUID REQUIRED) - Public API key for your chatengine.io project
* `userName` (String REQUIRED) - Username of a person in this project
* `userSecret` (String REQUIRED) - Set a secret for this person and use it to authenticate.
* `onConnect` (Function) - Callback when the connection/authentication is complete
* `onFailAuth` (Function) - Callback when the connection/authentication fails
* `onGetChats` (Function) Callback when the person fetches their chats array
* `onNewChat` (Function) - Callback when the person creates a new chat
* `onEditChat` (Function) - Callback when the person edits a chat title
* `onDeleteChat` (Function) - Callback when the person deletes one of their chats (must the chat's admin)
* `onAddPerson` (Function) - Callback when a person is added to a chat
* `onRemovePerson` (Function) - Callback when a person is removed/deleted from a chat
* `onGetMessages` (Function) - Callback when the person gets a chat's messages
* `onNewMessage` (Function) - Callback when a person posts a new message in one of the chats
* `onEditMessage` (Function) - Callback when a person edits a new message in one of the chats
* `onDeleteMessage` (Function) - Callback when a person deletes a new message in one of the chats
* `hideUI` (Boolean) - Hides all UI components for a custom implementation (Warning: Advanced)

## Functions
```
import { functionName } from 'react-chat-engine'

...

functionName(conn, args)
```

* `getChats` (conn) => void - Get a person's array of chats
* `newChat` (conn, title) => void - Create a new chat with this person as admin
* `editChat` (conn, chatId, chatObj) => void - Edit the title of an existing chat
* `deleteChat` (conn, chatId) => void - If you're admin, delete this existing chat
* `addPerson` (props, chatId, userName) => void - Add an existing person (in the project) to an existing chat
* `removePerson` (props, chatId, userName) => void - If you're admin, remove this user from an existing chat
* `getMessages` (props, chatId) => void - Get the messages for an existing chat
* `sendMessage` (props, chatId, messageObj) => void - Send a new message object into this chat
* `editMessage` (props, chatId, messageId, messageObj) => void - Edit an exiting message object in this chat
* `deleteMessage` (props, chatId, messageId) => void - Delete an exiting message object from this chat

## Objects
### Chat Object
* `id` (int) - Unique primary key to identify this chat
* `admin` (String) - Unique username of the person who created this chat
* `title` (String) - Optional title of this chat
* `created` (Datetime) - Date-time of chat creation
* `people` (Array) - Array of people added to this chat
```
{
    "id": 1,
    "admin": "john_smith",
    "title": "Canada Day Party!",
    "created": "2020-09-05T20:28:22.352373Z",
    "people": [
        {
            "person": "john_smith"
        }
    ]
}
```

## Chat / Person Association
* `person` (String) - Unique username of a person involved in this chat
```
{ person: "john_smith" }
```

## Message Object
* `id` (int) - Unique primary key to identify this message
* `sender` (String) - Unique username of the person who sent this message
* `text` (String) - Contents of the message sent
* `created` (Datetime) - Date-time of message creation
```
{
    "id": 1,
    "sender": "john_smith",
    "text": "Hey let's party!",
    "created": "2020-09-07T13:20:26.936400Z"
}
```
## Keywords
 none

## Project Demo

https://react-community-chatapp.netlify.app/


## Demo Credentials
### 1.) User 1
username: user1 \
password: 123123 

### 2.) User 2
username: user2 \
password: 123123

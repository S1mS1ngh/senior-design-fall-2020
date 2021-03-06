# Testing Plan
Our testing plan is to step through all the steps that a user of the application would take. First dealing with the
signup process, then testing what happens when the login is successful or unsuccessful. We will then test the front
end of the app to make sure that everything is displayed correctly, like the chat and forum posts, and the options that
come with them, like replying to chat/forums and pinning forums to save for later, as well as deleting posts. Next is to 
test adding and removing chat channels, as well as adding and removing users from those channels. Along with all this,
we will be testing the backend of the application to make sure everything necessary is being saved in their respective databases.

# Test Case Table
|   | Normal/Abnormal | Blackbox/White Box | Functional/Performance | Unit/Integration|
|---|---------------- |------------------- | ---------------------- |-----------------|
|1  | Normal          | Blackbox           | Functional             | Integration     |
|2  | Normal          | Blackbox           | Functional             | Integration     |
|3  | Normal          | Blackbox           | Functional             | Integration     |
|4  | Normal          | Blackbox           | Functional             | Integration     |
|5  | Normal          | Blackbox           | Functional             | Integration     |
|6  | Normal          | Whitebox           | Functional             | Unit            |
|7  | Normal          | Whitebox           | Functional             | Integration     |
|8  | Normal          | Blackbox           | Functional             | Integration     |
|9  | Normal          | Both               | Functional             | Integration     |
|10 | Normal          | Blackbox           | Functional             | Integration     |
|11 | Normal          | Whitebox           | Functional             | Unit            |
|12 | Normal          | Whitebox           | Functional             | Unit            |
|13 | Normal          | Blackbox           | Functional             | Unit            |
|14 | Normal          | Blackbox           | Functional             | Unit            |

## Test Case Descriptions
All tests will be number with the following characteristics:
1. test case identifier (a number or unique name)
2. purpose of test
3. description of test
4. inputs used for test
5. expected outputs/results
6. normal/abnormal/boundary case indication
7. blackbox/whitebox test indication
8. functional/performance test indication
9. unit/integration test indication

### 1. Login Test Pass
1. Login Pass Test
2. To test if login functionality works when inputs are correct
3. The test will go through the front end and backend components to verify user is a registered user and correctly 
inputs login details and not login without correct credentials
4. (Login Button) Correct Username, Password
5. Go to homepage
6. No action or incorrect page
7. Black box
8. Functional
9. Integration

### 2. Login Fail Test
1. Login Fail Test
2. To test if login functionality works when inputs are incorrect
3. The test will go through the front end and backend components to verify user is a registered user and correctly 
inputs login details and not login without correct credentials
4. (Login Button) Incorrect Username, Password
5. View incorrect password text
6. No action or incorrect page or no text viewed
7. Black box
8. Functional
9. Integration

### 3. Signup Test
1. Signup Test
2. To test if signup functionality works
3. The test will go through the front end and backend components to verify the registration process works for all fields
and stores proper information
4. (Signup Button) Name, other personal information
5. Prompt successful sign up message
6. No action, does not sign up correctly or does not store correct information
7. Black box
8. Functional
9. Integration

### 4. Forum Post Addition Test
1. Forum Post Addition Test
2. To test if forum post is properly created
3. The test will check if the forum post box is properly viewed on the page and stored in the database
4. (Add post Button) Post title, Post content
5. Show post on homepage or forum page
6. No action, does not show correctly or does not store correct data
7. Black box
8. Functional
9. Integration

### 5. Forum Post Delete Test
1. Forum Post Deletion Test
2. To test if forum post is properly deleted
3. The test will check if the forum post box is properly removed from the page and removed from the database
4. (Delete post Button)
5. Remove post from homepage or forum page
6. No action, does not delete correctly or does not correctly remove data
7. Black box
8. Functional
9. Integration

### 6. Forum Post List Test
1. Forum Post List Test
2. To test if forum posts are properly viewed on a list
3. The test will check to see if the page properly loads the posts from the database and views them on the page
4. None
5. List correctly displayed from database
6. No list displayed or not properly displayed
7. White box
8. Functional
9. Unit

### 7. Forum DataBase Save Test
1. Forum Save Test
2. To test if forum post is properly saved in the database
3. The test will create a forum post and verify that the database saves the created post
4. Create post button, Input message on forum, Post Forum button, forum database
5. Forum is saved in the database
6. Normal
7. White box
8. Functional
9. Integration

### 8. Forum Post Reply Test
1. Forum Post Reply Test
2. To test if forum post is able to be replied to
3. The test will check if the forum post is able to have other users create comments on the post.
4. (Add Reply button) Type in reply, (Submit Reply button), reply shows on forum post and is saved in the database with the forum.
5. Show reply on forum post and save reply in database
6. Normal
7. Black and white box
8. Functional
9. Integration

### 9. Chat Backend Send Channel Message Test
1. Send Channel Message Test
2. To test chat feature API endpoint that allows users to send message into current chat channel
3. The test will use test client to send JSON message with authorization token to the endpoints of the chat backend
4. Auth Token, User chat name, message, timestamp
5. Return original message to sender and emit message event to all other connected clients
6. No message displayed
7. Whitebox
8. Functional
9. Unit

### 10. Chat Backend Send Private Message Test
1. Send Private Message Test
2. To test private chat feature API endpoint that allows users to send private message to other users
3. The test will use test client to send JSON message with authorization token to the endpoints of the chat backend and then server will forward the message to other user.
4. Auth Token, User chat name, message, timestamp
5. Return original message and emit send message event to targeted client
6. Notifying user that message error
7. Whitebox
8. Functional
9. Unit

### 11. Chat Backend Create New Channel Test
1. Create New Channel Test
2. To test chat feature of creating a new channel using backend API endpoints
3. The test will use test client to send a JSON request to server for establishing a new chatroom through SocketIO
4. Auth Token, User Account information (ID, Name, etc)
5. Return to the client a room ID for the connection and display chat channel on the frontend
6. Return JSON error message that is interpreted on the frontend as server error
7. Blackbox
8. Functional
9. Unit

### 12. Chat Backend Add New User to Channel Test
1.  Add New User to Channel Test
2. To test chat feature of adding a new user to the channel using backend API endpoints
3. The test will use a test client to send a JSON request to the server containing ID of user that current user wants to invite to the channel
4. Auth Token, User Account information, Targeted user ID
5. Send a request from the server to another user to join in the channel, if accepted, establish a new SocketIO connection to the user and display on the frontend
6. Return JSON error message that is interpreted on the frontend as server error
7. Blackbox
8. Functional
9. Unit

### 13. Chat Front End Send Message
1. Chat Send Message
2. To test if a message can be sent
3. Will test if the sent message will be posted in the Chat
4. Type message, (Send Message Button)
5. The message box will be emptied and the message will appear in the Chat
6. Normal
7. Blackbox
8. Functional
9. Unit

### 14. Chat Front End Receive Message
1. Chat Receive Message
2. To test if a message can be received
3. Will test if the received message will be posted in the chat
4. Type message, (Send Message Button)
5. The message will be received by the recipient
6. Normal
7. Blackbox
8. Functional
9. Unit

## Test Framework
![Test Framework](Resources/img/fastapi_docs.png "Test Framework")

Beside running unit test in front end and back end, you can also test out back end functionality by using FastAPI generated docs. All requests made here are functional using a test database instead of production one.
***

# Chatbot Using Google Dialogflow

Welcome to the Chatbot repository! This project is a conversational chatbot application that leverages **Google Dialogflow** for natural language understanding, along with a backend implemented in Node.js and MongoDB for session and issue management.

***

## Overview

This chatbot allows users to report internet-related issues via conversational interaction. It identifies users by their account numbers, retrieves user information from a MongoDB database, and generates trouble tickets for problems reported by users.

***

## Features

- User Identification by Account Number
- Issue Reporting with Dynamic Trouble Ticket Generation
- Integration with MongoDB for Persistent Storage
- Rich Responses using Dialogflow's Payload for Enhanced User Experience
- Designed to handle multiple intents with custom payloads
- Easily extensible to incorporate more intents and functionalities

***

## How It Works

1. **User Identification**: The bot asks the user to enter an account number. It verifies this number against the MongoDB user database.
2. **User Greeting**: If the account number is valid, the bot greets the user by name.
3. **Issue Reporting**: The user can then report an internet issue selected from a predefined list (e.g., Internet Down, Slow Internet, Buffering problem, No connectivity).
4. **Ticket Generation**: The bot generates a unique trouble ticket number, stores the issue details along with the user's name and timestamp in MongoDB.
5. **Confirmation**: The user receives confirmation about their reported issue along with the generated ticket number.
6. **Rich UI**: The bot uses Dialogflow's custom payloads for visually appealing and interactive messages like lists.

***

## Tech Stack

| Technology           | Purpose                                |
|---------------------|--------------------------------------|
| **Node.js**          | Backend server and Dialogflow webhook |
| **Express.js**       | Web framework for Node.js             |
| **Dialogflow Fulfillment Library** | Connects Dialogflow intents with backend logic |
| **MongoDB**          | Database for storing user info and issues |
| **Randomstring**     | Generates unique trouble ticket IDs  |
| **Google Dialogflow**| Conversational AI platform for NLP   |

***

## Integration Guide

### Prerequisites

- Node.js installed
- MongoDB instance running locally or remotely
- Google Dialogflow agent set up with intents and entities as described below

### Dialogflow Setup

1. **Create an Agent** in Dialogflow console.
2. **Define Intents**:
   - `serviceintent`: Captures account number and triggers user identification.
   - `issue`: Captures issue number for reporting the problem.
   - `problem`: Used for custom payload presentation of issue options.
3. **Entities**: Create relevant entities like `acctnum` for account numbers and `issuenum` for issue selection.
4. **Fulfillment**: Enable webhook fulfillment and provide the URL of your backend server.

### Backend Setup

1. Clone this repository.
2. Install dependencies:
   ```bash
   npm install express dialogflow-fulfillment mongodb randomstring
   ```
3. Configure MongoDB URL in the source code (default is `mongodb://localhost:27017`).
4. Run the server:
   ```bash
   node chatbot_v1.js
   ```
5. Ensure your webhook URL in Dialogflow points to your server's `/dialogflow` endpoint.

***

## Code Highlights

- **User Identification**: Checks the MongoDB database to authenticate users based on their account number.
- **Issue Reporting**: Issues are mapped with numbers, and users select the issue using numeric input.
- **Ticketing**: Trouble ticket numbers are generated with the `randomstring` library.
- **Custom Payload**: Uses Dialogflow's Payload feature to show rich lists of issues.

***

## Sample Interaction Flow

```
User: Hi, I want to report an issue.
Bot: Please enter your account number.
User: 12345
Bot: Welcome John! How can I help you?
User: I have no internet connectivity.
Bot: Please press 4 for No connectivity.
User: 4
Bot: Your issue "No connectivity" is reported. Your ticket number is ABC1234.
```

***

## Folder & File Structure

```
/chatbot_v1.js       # Main backend server handling Dialogflow webhook
/package.json        # Node.js dependencies and scripts
```

***

## Future Enhancements

- Add support for more issue types and user intents
- Implement authentication and security improvements
- Integrate notification system for ticket status updates
- Use cloud MongoDB services for scalability

***


***

If you need, I can help generate a markdown file with this content ready to add to your repo. Would you like that?

[1](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/103581510/f58943d3-7ddd-4f2c-8f30-995af3049d6b/chatbot_v1.js)

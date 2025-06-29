# WhatsApp Chatbot - Spring Boot Application

This is a Java-based backend application built using Spring Boot. It simulates a basic WhatsApp chatbot that can respond to predefined user inputs and stores incoming messages in Firebase Firestore.

## Features

- Receives and processes incoming messages via a `/webhook` endpoint.
- Sends automated replies based on user input.
- Saves messages to Firebase Firestore.
- Built using RESTful APIs with Spring Boot.

## Technologies Used

- Java 17
- Spring Boot
- Firebase Admin SDK
- Maven
- Postman (for testing)

## Project Structure

```
whatsappbot/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/bot/whatsappbot/
│   │   │       ├── WhatsappbotApplication.java
│   │   │       ├── controller/
│   │   │       │   └── BotController.java
│   │   │       ├── model/
│   │   │       │   └── MessageRequest.java
│   │   │       └── service/
│   │   │           └── BotService.java
│   └── resources/
│       ├── application.properties
│       └── firebase-config.json 
└── pom.xml
```

## Setup Instructions

1. **Clone the Repository:**

```bash
git clone https://github.com/your-username/whatsappbot.git
cd whatsappbot
```

2. **Place your Firebase service account file**:

- Save your Firebase private key file as `firebase-config.json` inside `src/main/resources/`.

3. **Run the application:**

```bash
mvn spring-boot:run
```

## Testing Using Postman

Use Postman to send a POST request to:

```
POST http://localhost:8080/webhook
```

### Sample JSON Body:

```json
{
  "from": "911234567890",
  "message": "1"
}
```

### Expected Replies:
| Input | Bot Response |
|-------|--------------|
| hi    | Hello! How can I help you today? 1. Location 2. Contact 3. Help |
| 1     |  Location : Bengaluru, India. |
| 2     |  Contact us at : Phone : +91-1234567890 or Email : example@gmail.com |
| 3     |  Help: Please type 'hi' to go to the menu |
| other | Invalid choice |

##  Important Notes
- This is a basic chatbot simulation — real WhatsApp Business API integration would require WhatsApp Cloud API setup.

## License

This project is for educational and internship use only.

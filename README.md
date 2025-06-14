
# Waliin Chat Application

![Java](https://img.shields.io/badge/Java-17%2B-blue)
![JavaFX](https://img.shields.io/badge/JavaFX-19-purple)
![TCP](https://img.shields.io/badge/Protocol-TCP-green)

A real-time chat application with file sharing capabilities, built with Java and JavaFX.

## Project Structure

```
chat-app/
├── Client/          # JavaFX client application
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/chat/client/
│   │   │   ├── resources/         # FXML views and CSS
│   ├── pom.xml
│
├── Server/          # Chat server
│   ├── src/
│   │   ├── main/java/com/chat/server/
│   ├── pom.xml
│
└── Shared/          # Common classes
    ├── src/
    │   ├── main/java/com/chat/shared/
```

## Key Features

- 💬 Real-time text messaging (public and private)
- 📁 File sharing with progress tracking
- 👥 Dynamic online user list
- 🌐 TCP-based reliable communication
- 🧵 Multi-threaded server architecture

## How It Works

1. **Server** (`ServerMain.java`)
   - Listens on port 5555
   - Creates new thread for each client (`ClientHandler.java`)
   - Routes messages between clients

2. **Client** (`ChatController.java`)
   - JavaFX interface
   - Connects to server via TCP
   - Handles user interactions

3. **Shared Protocol** (`ChatMessage.java`)
   - Common message format
   - Supports text/files/commands
   - Serialized over network

## Getting Started

### Prerequisites
- Java 17+
- Maven 3.6+

### Running the Application
1. Start the server:
   ```bash
   cd Server/
   mvn compile exec:java -Dexec.mainClass="com.chat.server.ServerMain"
   ```

2. Launch clients:
   ```bash
   cd Client/
   mvn javafx:run
   ```

## Code Highlights

### Simplest Component (Shared)
```java
// Defines all message types
public enum MessageType {
    TEXT, FILE, LOGIN, LOGOUT, PING
}
```

### Core Message Class
```java
public class ChatMessage implements Serializable {
    private final MessageType type;
    private final String sender;
    private String text;
    private byte[] data; // For files
    
    // Serialization methods...
}
```


### Recommended Additions:
1. **For Demo Purposes**: Add screenshots of the client UI
2. **For Technical Depth**: Include sequence diagrams
3. **For Installation**: Add JavaFX SDK setup notes if needed

Would you like me to:
1. Create a more detailed installation guide?
2. Add architecture diagrams?
3. Include sample message flow explanations?

Made with ❤️ by [dulagudeta](https://github.com/dulagudeta)  
Feel free to tweak this for your needs!

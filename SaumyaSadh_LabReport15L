import java.io.IOException;
import java.net.URI;

class ChatHandler implements URLHandler {
    StringBuilder chatHistory = new StringBuilder();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("Saumya:\n%s", "Hello");
        } else if (url.getPath().equals("/add-message")) {
            String[] parameters = url.getQuery().split("&");
            String user = parameters[0].split("=")[1];
            String message = parameters[1].split("=")[1];

            chatHistory.append(user).append(": ").append(message).append("\n");

            return chatHistory.toString();
        } else {
            return "404 Not Found!";
        }
    }
}

class ChatServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new ChatHandler());
    }
}

This code represents a basic chat server that maintains a chat history. 
Users can add messages to the chat by making requests using the `/add-message` endpoint. 
The server concatenates the user's name, a colon `:`, the message, and a newline `\n` to form a chat entry. 
The entire chat history is accessible through the root endpoint `/`. Users can engage in conversations by adding messages,
and the server keeps track of the entire interaction history

/add-message?s=Hello&user=ssadh at the end of the query adds the string to the array.

![Image](addmessage-hello_ssadh.png)


/add-message?s=How are you&user=saumya

![Image](howareyou_saumya.png)


**Discussing the Code**













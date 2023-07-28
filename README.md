The CLI-based chat tool facilitates real-time communication between multiple clients through a Command Line Interface (CLI). The chat tool consists of two components: `client.py` (run by each individual user) and `server.py` (managing client connections and message broadcasting). The methodology for the CLI-based chat tool involves the following steps:

Client-Server Communication:
- The chat tool follows a client-server architecture, where multiple clients (users) connect to a central server to exchange messages.
- Each client is identified by a nickname chosen by the user.

2. Client Implementation (client.py):
    - The client initializes a socket and connects to the server using the socket's IP and port.
    - It uses two separate threads for sending and receiving messages concurrently.
    - The receive thread continuously listens for incoming messages from the server and prints them to the client's console.
    - The write thread allows the client to input messages, which are sent to the server for broadcasting.

3. Server Implementation (server.py):
    - The server initializes a socket and binds it to a specific host and port to listen for incoming client connections.
    - It uses a list to keep track of connected clients and their corresponding nicknames.
    - The server continuously accepts new client connections and assigns each a nickname.
    - For each connected client, a separate thread is created to handle message reception and broadcasting to all clients.

# minitalk

## 📝 Overview  
Minitalk is a simple data exchange program using UNIX signals. The **server** listens for messages sent by the **client** and prints them to the terminal. Communication is achieved through **SIGUSR1** and **SIGUSR2**, representing binary values.  

## 🔧 Key Concepts Learned  
- **UNIX Signals**: Process communication with `SIGUSR1` and `SIGUSR2`  
- **Process IDs (PID)**: Identifying and signaling processes (`getpid()`, `kill()`)  
- **Signal Handling**: Asynchronous event-driven message reception  
- **Memory Safety**: Avoiding segmentation faults, memory leaks, and unexpected crashes  

## 🚀 How It Works  
1. **The server** starts first and prints its PID.  
2. **The client** takes two arguments: the server's PID and the string to send.  
3. **The client** encodes the message into binary and transmits it using signals.  
4. **The server** decodes the message and prints it in real-time.  
5. **(Bonus)** The server acknowledges each received message by signaling the client.  

## 📌 Usage  
### **Compiling the program**  
```bash
make
```
### **Running the server**
```bash
./server
```
It will print its PID, which the client will use.

### **Running the client**
```bash
./client <server_PID> "Hello, Minitalk!"
```

## ✨ Bonus Features
- Server acknowledgment: Sends a signal back to the client after receiving a message
- Unicode support: Handles extended character sets
- Efficient messaging: The client waits for confirmation before sending the next signal
- Multi-client support: The server can receive messages from multiple clients without restarting

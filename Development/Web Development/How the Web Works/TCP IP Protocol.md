#tcpip-protocol-suite
# TCP/IP Protocol and Ports

## TCP/IP Protocol Suite

### 1. Transmission Control Protocol (TCP)

- **Connection-Oriented Protocol:** Establishes a connection between devices before data exchange.
- **Reliable Data Delivery:** Ensures data arrives intact and in order.
- **Flow Control:** Regulates the flow of data between sender and receiver.
- **Error Detection and Recovery:** Detects errors and retransmits lost data packets.

### 2. Internet Protocol (IP)

- **Connectionless Protocol:** Does not establish a connection before data transmission.
- **Routing:** Determines the best path for data packets to reach their destination.

## Ports

Ports are virtual endpoints for communication in a computer network. They allow multiple services or applications to operate simultaneously on a single device. Ports are divided into three ranges:

### 1. Well-Known Ports (0-1023)

- Reserved for system services or well-known applications.
- Examples:
  - Port 80: HTTP (Hypertext Transfer Protocol)
  - Port 443: HTTPS (HTTP Secure)
  - Port 21: FTP (File Transfer Protocol)
  - Port 25: SMTP (Simple Mail Transfer Protocol)

### 2. Registered Ports (1024-49151)

- Assigned to specific services or applications by the Internet Assigned Numbers Authority (IANA).
- Examples:
  - Port 3306: MySQL Database
  - Port 5432: PostgreSQL Database
  - Port 8080: HTTP Alternate (commonly used for web proxies)

### 3. Dynamic/Private Ports (49152-65535)

- Also known as ephemeral ports.
- Used by client applications for temporary communication sessions.
- Automatically assigned by the operating system.

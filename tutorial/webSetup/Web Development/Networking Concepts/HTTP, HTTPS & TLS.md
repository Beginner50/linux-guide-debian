There are various data transfer protocols over the internet but the most common are:
- HTTP
- HTTPS
- SMTP / POP3 / IMAP (For email servers)

#### 1) HTTP
HTTP is the data transfer protocol used for transferring web pages and media between a web server and a web client.

##### Mechanism
1) The client first sends an **HTTP request** to the web server.
2) The server then processes the request and sends back an **HTTP response** containing the requested resource (e.g HTML file)

- HTTP is stateless (Each request-response cycle is independent of others).
- HTTP is not encrypted (Data is transmitted in plain-text)
- HTTP uses port 80.

#### 2) HTTPS
HTTPS is the secure version of HTTP, encrypting data to ensure privacy and integrity during transmission, using **TLS/SSL**.

##### Mechanism
1) The process above is started using a **TLS/SSL handshake** (explained below), where the client and server agrees on the encryption keys and verify each other's identity using digital certificates.
2) Once the connection is secure, data is transmitted in encrypted form.

- HTTPS uses port 443.
- HTTPS provides:
	- **Encryption**: Protecting data from eavesdropping.
	- **Authentication**: Ensures the client is communicating with the intended server.
	- **Data Integrity**: Prevents tampering during transmission.

* * *
### TLS/SSL Handshake
SSL(Secure Socket Layer) is the outdated protocol for encrypting internet traffic and is replaced by TLS.

#### Mechanism:
1) The client initiates the handshake by sending a **Client Hello** message to the server which includes:
	- Supported TLS/SSL versions of the client (e.g TLS 1.3)
	- Cipher Suites (List of cryptographic algorithms like **AES**, **RSA**, **SHA-256** the client supports)
	- Random Bytes (Entropy for generating encryption keys)
	- Session ID (Optional, Used to resume a previous session)
	
2) The server responds by sending a **Server Hello** message to the client which contains the above except for the server this time.

3) The server then sends its **digital certificate** to the client which includes:
	- Server's Public Key
	- Server's Identity (Information about the server, e.g Domain name)
	- Certificate Authority Signature (A trusted CA verifies the server's identity and signs the certificate)
	The client in turn will verify the certificate by checking its:
	- Certificate Validity (e.g Expiry Date)
	- CA's signature to ensure the certificate is trusted

4) The server will then send a **Server Hello Done** message to indicate it has finished its part of the handshake.

5) The client will then send a **Finished** message encrypted using the public key of the server.

### Note:
The above steps have been grossly oversimplified to illustrate the core mechanism behind TLS handshake. In reality, there is another step which involves the client creating a pre-master secret key and changing the cipher used to transfer data before sending the Finished message.

HTTPS is notoriously hard to set up correctly due to the lack of free CA's signatures.
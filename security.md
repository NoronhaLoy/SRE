## Security

---

### **Authentication**
* **Definition**: The process of verifying the identity of a user or system.
* **Examples**:
  * Logging into a website with a username & password.
  * OAuth 2.0 login via Google or GitHub.
* **Best Practices**:
  * Use MFA (Multi-Factor Authentication) for sensitive systems.
  * Avoid storing plaintext passwords — use bcrypt or Argon2 for hashing.

---

### **Certificate**
* **Definition**: A digital document used to prove the ownership of a public key.
* **Contents**:
  * Public key
  * Owner information
  * Issuer details
  * Validity period
* **Example**:
  * `www.example.com` has an SSL certificate proving it owns the public key used in TLS communication.

---

### **Certificate Authority (CA)**
* **Definition**: A trusted entity that issues digital certificates after verifying the requester’s identity.
* **Examples**:
  * Let’s Encrypt (free)
  * DigiCert
  * GlobalSign
* **Flow**:
  1. Domain owner requests a certificate.
  2. CA verifies domain ownership.
  3. CA issues the certificate.

---

### **Cipher**
* **Definition**: An algorithm for encrypting or decrypting data.
* **Examples**:
  * AES (Advanced Encryption Standard)
  * RSA (Rivest–Shamir–Adleman)
* **Usage**:
  * AES-256-GCM is commonly used for encrypting sensitive data at rest.

---

### **Confidentiality**
* **Definition**: Ensuring that data is accessible only to authorized parties.
* **Example**:
  * Encrypting sensitive files so even if they are stolen, they are unreadable without the key.
* **Best Practices**:
  * Use encryption for data at rest (disk, database) and in transit (network).

---

### **Encryption**
* **Definition**: The process of converting plaintext into ciphertext using a key.
* **Types**:
  * **Symmetric**: Same key for encryption & decryption (e.g., AES).
  * **Asymmetric**: Public key for encryption, private key for decryption (e.g., RSA).
* **Example**:
  * Sending a message via HTTPS uses asymmetric encryption for key exchange and symmetric encryption for the actual data.

---

### **TLS (Transport Layer Security)**
* **Definition**: A cryptographic protocol providing secure communication over a network.
* **Example**:
  * HTTPS websites use TLS to encrypt communication between browser and server.
* **TLS Handshake Steps**:
  1. Client says “hello” and lists supported encryption methods.
  2. Server responds with its certificate & chosen encryption method.
  3. Client verifies certificate with CA.
  4. Secure session is established.

---

### **PKI (Public Key Infrastructure)**
* **Definition**: A framework that manages public-key encryption and digital certificates.
* **Components**:
  * Certificate Authorities (CAs)
  * Registration Authorities (RAs)
  * Certificate Revocation Lists (CRLs)
* **Example**:
  * PKI ensures that when you visit `https://bank.com`, you are talking to the real bank and not an imposter.

---

### **Signature**
* **Definition**: A cryptographic value that ensures data integrity and authenticity.
* **How It Works**:
  1. Create a hash of the data.
  2. Encrypt the hash with the sender’s private key.
  3. The recipient decrypts the signature with the sender’s public key and compares it with a freshly computed hash.
* **Example**:
  * Digital signatures in software packages (e.g., GPG signatures for Linux packages) ensure they have not been tampered with.

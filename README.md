# 🔐 Crypto Meetup - Secure Chat with Double Ratchet Algorithm

A secure, encrypted communication application that demonstrates how modern cryptographic techniques like the **Double Ratchet Algorithm** and **X3DH (Extended Triple Diffie-Hellman)** can be used to ensure confidentiality, forward secrecy, and post-compromise security in peer-to-peer communication.

---

## 📘 What is the Double Ratchet Algorithm?

The Double Ratchet algorithm, used in Signal Protocol, combines two types of ratchets:

* **Diffie-Hellman Ratchet (asymmetric):** Ensures forward secrecy by constantly replacing key pairs.
* **Symmetric-key Ratchet:** Ensures that each message uses a unique key for encryption, offering post-compromise security.

Together, they:

* Prevent message decryption even if one key is compromised.
* Allow for asynchronous message encryption/decryption.

---

## 🚀 Project Overview

This project simulates a chat session using the Signal-like protocol where two users (Alice and Bob) can securely exchange messages after an email-based OTP verification and key exchange. It supports:

* Asymmetric and symmetric encryption using the Double Ratchet algorithm.
* Identity verification using OTP via email.
* AES-based encrypted messaging.

---

## 🧩 Components

| File        | Purpose                                                                                |
| ----------- | -------------------------------------------------------------------------------------- |
| `client.py` | CLI interface for sending/receiving secure messages                                    |
| `server.py` | Manages OTP login, key exchange, and user session routing                              |
| `Code.py`   | Cryptographic logic implementing X3DH, Double Ratchet, encryption/decryption functions |

---

## 📂 How to Run the Project

### 1. 📦 Install Dependencies

Ensure Python 3.8+ is installed. Install required packages:

```bash
pip install cryptography pycryptodome
```

### 2. 🔑 Set Email Credentials

Export your email and password used for sending OTPs:

```bash
export MAIL=yourmail@gmail.com
export MAIL_PASSWORD=yourpassword
```

(You can use an App Password if Gmail blocks sign-ins.)

### 3. ▶️ Run the Server

```bash
python server.py
```

### 4. 💬 Start Clients

In separate terminals:

```bash
python client.py
```

You'll be asked for:

* Your email ID (institution domain is expected by default)
* An OTP sent to your email
* Then messaging can begin after secure key exchange.

---

## 🧠 How It Works

1. **Authentication**:

    * Server sends OTP to user’s email.
    * User submits OTP to proceed.

2. **Key Exchange**:

    * Implements X3DH to establish shared secrets.
    * Initializes Double Ratchet (Symmetric + DH key updates).

3. **Messaging**:

    * Each message is encrypted with a new symmetric key.
    * Keys are updated using the ratchet to ensure security.

---

## 🛠 Commands

```bash
# Start the server
python server.py

# Run a client
python client.py
```

---

## 📚 References

* Signal Protocol Documentation: [https://signal.org/docs/](https://signal.org/docs/)
* Double Ratchet Algorithm: [https://signal.org/docs/specifications/doubleratchet/](https://signal.org/docs/specifications/doubleratchet/)

---

## 🧑‍💻 Author

Maintained by [@4l0n3r](https://github.com/4l0n3r) ✨

Feel free to explore, contribute, or fork the project!

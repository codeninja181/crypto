# 💬 Secure Chat Handshake

*A Flask-powered sandbox for spinning up a private chat room using Diffie–Hellman to agree on a room key.*

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.7+-blue" />
  <img src="https://img.shields.io/badge/Framework-Flask-green" />
  <img src="https://img.shields.io/badge/Frontend-HTML%20%7C%20CSS%20%7C%20JS-yellow" />
  <img src="https://img.shields.io/badge/License-MIT-lightgrey" />
  <img src="https://img.shields.io/badge/Cryptography-Diffie--Hellman-red" />
</p>

---

## 📌 Overview

This sandbox walks through a **secure chat room handshake**. Set public room parameters, establish a shared room key in the open, then send sealed chat messages once Alice and Bob match keys.

The UI and copy are rebuilt for a chat-room narrative—lobby log, room beacons, participant cards, sealed chat traffic—so it’s unrecognizable from the earlier demo style.

---

## ✨ What’s inside (chat edition)

* 🧭 **Room settings**: public controls for `p` and `g`
* 🛰️ **Lobby log**: narrated four-step room handshake
* 👥 **Participant cards**: Alice/Bob private/public values and derived room key
* 📡 **Chat panel**: send/receive sealed messages in both directions
* 🔐 **Room key monitor**: confirms when the chat is ready
* 🎨 **New visual identity**: dark neon chat aesthetic, badges, and cards
* 🧮 **Server-side DH math** + a tiny XOR teaching cipher
* 🔄 **Reset room** to start a fresh session

---

## 🏗️ Tech Stack

### **Backend**

* Python 3.7+
* Flask

### **Frontend**

* HTML5
* CSS3
* Vanilla JavaScript

### **Cryptography**

* Custom Diffie–Hellman implementation
* XOR cipher for educational message encryption

---

## 📂 Project Structure

```
diffie-hellman-webapp/
│
├── app.py                     # Main Flask backend
├── requirements.txt           # Dependencies
├── README.md                  # Documentation
│
├── static/
│   ├── css/
│   │   └── style.css          # Stylesheet
│   └── js/
│       └── main.js            # Frontend logic
│
└── templates/
    └── index.html             # Main interface
```

---

## 🚀 Getting Started

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/yourusername/diffie-hellman-webapp.git
cd diffie-hellman-webapp
```

---

### 2️⃣ Install Dependencies

#### Create & Activate Virtual Environment

```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

#### Install Required Packages

```bash
pip install -r requirements.txt
```

---

### 3️⃣ Run the Application

```bash
python app.py
```

Once running, open the browser and go to:

👉 **[http://localhost:5000](http://localhost:5000)**

---

## 🧪 How It Works

### Chat flow at a glance

1. **Publish the lobby** — pick `p` and `g`.
2. **Keep personal secrets** — Alice holds `a`, Bob holds `b`.
3. **Broadcast room beacons** — share `A = g^a mod p` and `B = g^b mod p`.
4. **Lock the room key** — both derive the same `s`.
5. **Chat** — use `s` with the demo XOR cipher to seal and read messages.

---

## 🌐 API Endpoints

| Method | Endpoint         | Description      |
| ------ | ---------------- | ---------------- |
| GET    | `/`              | Load main UI     |
| POST   | `/generate_keys` | Generate DH keys |
| POST   | `/encrypt`       | Encrypt message  |
| POST   | `/decrypt`       | Decrypt message  |

---

## ⚠️ Security Notice

This chat is **for education and demos only**:

* XOR is not secure encryption
* Parameters are intentionally tiny for visibility
* No authentication, integrity, or padding

For real chat security, rely on:

✔ `cryptography` or `PyCryptodome`  
✔ Authenticated DH handshakes and AEAD ciphersuites (e.g., TLS)

---

## 📸 Optional: Add Screenshots

(Place screenshots in `/static/images/` and embed here)

```
![App Screenshot](static/images/screenshot.png)
```

---

## 🧑‍🏫 Ideal For

* Students learning cryptography
* Teachers demonstrating DHKE
* Cybersecurity workshops
* Mini projects / semester projects
* Flask beginners

---

## 📝 License

This project is licensed under the **MIT License**.
You are free to use, modify, and distribute it for educational use.

---

## ⭐ Contribute

Pull requests are welcome! Feel free to open:

* Issues
* Feature suggestions
* UI improvements

---

# 🔐 Cryptexa Chat

Secure 1-to-1 messaging powered by end-to-end encryption and Web3 authentication.

Cryptexa is a modern Flutter-based chat application that combines real-time messaging, NaCl-based end-to-end encryption, and WalletConnect authentication into a privacy-first communication platform.

Cryptexa Chat is a secure messaging application built with Flutter and GetX, designed around strong cryptographic principles and decentralized identity.
📌 Overview

Cryptexa Chat is a secure messaging application built with Flutter and GetX, designed around strong cryptographic principles and decentralized identity.

Each message is encrypted using:

X25519 (NaCl Box) for key exchange

SecretBox (XSalsa20-Poly1305) for symmetric message encryption

Encrypted payload storage via IPFS

Web3 login using WalletConnect

Only participants in a conversation can decrypt messages. The backend never has access to plaintext.

🚀 Features
🔐 End-to-End Encryption

Per-user X25519 keypair

Symmetric key generated per message

Symmetric key encrypted separately for each participant

No plaintext stored server-side

💬 Real-Time Messaging

Socket-based live message delivery

Auto join/leave chat rooms

Optimistic UI updates

📎 Encrypted File Sharing

File encryption using SecretBox

Metadata protection (name, type, size)

Stored securely via IPFS

🧾 Wallet-Based Authentication

Web3 login via WalletConnect

Message signing for secure identity verification

No passwords required

📱 Modern UI

Telegram/Signal-inspired interface

Elegant chat bubbles

Clean message states (pending / failed / encrypted)

🧠 Architecture

The project follows a modular clean structure:

lib/
 ├── core/
 │    ├── crypto/        # E2EE implementation
 │    ├── services/      # Session + Socket
 │    └── realtime/
 ├── data/
 │    ├── repositories/
 │    └── models/
 └── ui/

State management is handled using GetX, ensuring:

Reactive UI updates

Lightweight dependency injection

Clean separation of concerns

🔑 Cryptography Model

Each message is encrypted using the following process:

Generate random symmetric key

Encrypt message using SecretBox

Encrypt symmetric key twice:

Once for sender

Once for recipient

Store encrypted payload on IPFS

Backend only stores encrypted metadata

Decryption is done client-side only.

🛠 Tech Stack

Flutter

GetX

PineNaCl (X25519 + SecretBox)

WalletConnect v2

Socket-based Realtime

IPFS

Secure Storage

🔐 Security Principles

No plaintext message leaves the device

Keys stored securely using Flutter Secure Storage

Backend cannot decrypt conversations

Wallet-based identity eliminates password risks

🗺 Roadmap

Group chats with shared encryption

Push notifications (encrypted previews)

Message reactions

Message editing with re-encryption

Encrypted voice messages

Decentralized user discovery


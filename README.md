DAO Dashboard – Token & NFT Manager

A React Native application integrated with Firebase for managing Tokens and NFTs.
This project includes authentication, Firestore CRUD operations, and formatted token supply display.

Features

Firebase Authentication

User registration

User login

Logout

Token Management

Add Token (name, description, price, supply)

View and delete tokens

Human-readable supply format (K / MILLION / BILLION)

NFT Management

Add NFT (name, description, price, supply)

View and delete NFTs

Firestore Integration

Secure data storage

Numeric-safe price and supply handling

Dark UI Theme

Mobile-first design using React Native

Tech Stack

React Native

TypeScript

Firebase

Firebase Authentication

Cloud Firestore

Project Structure
src/
├── config/
│   └── firebase.ts
├── screens/
│   ├── LoginScreen.tsx
│   ├── RegisterScreen.tsx
│   └── CRUDScreen.tsx
├── App.tsx
└── ...

Firebase Configuration

Create a Firebase project.

Enable:

Authentication (Email/Password)

Cloud Firestore

Update firebase.ts with your credentials:

import { initializeApp } from 'firebase/app';
import { getAuth } from 'firebase/auth';
import { getFirestore } from 'firebase/firestore';

const firebaseConfig = {
  apiKey: 'YOUR_API_KEY',
  authDomain: 'YOUR_AUTH_DOMAIN',
  projectId: 'YOUR_PROJECT_ID',
  storageBucket: 'YOUR_STORAGE_BUCKET',
  messagingSenderId: 'YOUR_SENDER_ID',
  appId: 'YOUR_APP_ID',
};

const app = initializeApp(firebaseConfig);

export const auth = getAuth(app);
export const firestore = getFirestore(app);

Firestore Data Structure
Tokens Collection (items)
{
  "name": "DAO Token",
  "description": "Governance token",
  "price": 0.25,
  "supply": 1000000000,
  "createdAt": 1700000000000
}

NFTs Collection (nfts)
{
  "name": "Genesis NFT",
  "description": "Limited edition NFT",
  "price": 120,
  "supply": 1000,
  "createdAt": 1700000000000
}


Note:
The price and supply fields are always stored as numeric values in Firestore.

Supply Formatting

Supply values are stored as raw numbers but displayed in a readable format:

Stored Value	Display
500	500
1,500	1.5K
1,200,000	1.2 MILLION
10,000,000,000	10 BILLION
Running the Project

Install dependencies:

npm install


Run the application:

npm start


Or with Expo:

npx expo start

Firestore Security Rules (Basic Example)
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if request.auth != null;
    }
  }
}

Future Improvements

Edit token and NFT data

Token purchase logic with supply reduction

Tokenomics overview (circulating vs max supply)

DAO voting system

Marketplace interface

License

MIT License

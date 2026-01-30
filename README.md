DAO Dashboard

A simple React Native application using Firebase to manage Tokens and NFTs.

Features

User authentication (Login & Register)

Add, view, and delete Tokens

Add, view, and delete NFTs

Token and NFT price & supply stored as numbers

Supply displayed in readable format (K / MILLION / BILLION)

Firebase Authentication and Firestore integration

Tech Stack

React Native

TypeScript

Firebase (Auth & Firestore)

Project Structure
src/
├── config/firebase.ts
├── screens/
│   ├── LoginScreen.tsx
│   ├── RegisterScreen.tsx
│   └── CRUDScreen.tsx
├── App.tsx

Firebase Setup

Create a Firebase project

Enable Email/Password Authentication

Enable Cloud Firestore

Add your Firebase config in firebase.ts

Firestore Collections
Tokens (items)
{
  "name": "DAO Token",
  "description": "Governance token",
  "price": 0.25,
  "supply": 1000000000
}

NFTs (nfts)
{
  "name": "Genesis NFT",
  "description": "Limited NFT",
  "price": 120,
  "supply": 1000
}

Run the App
npm install
npm start


Or with Expo:

npx expo start

License

MIT License

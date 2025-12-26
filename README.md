# HerVoice

A trauma-informed, women-safety web platform that allows users to securely document harassment incidents, access legal guidance, and connect with verified lawyers.

## 🌟 Features

- **Secure Incident Documentation**: Document harassment incidents with timestamps, media evidence, and witness details
- **Privacy-First Design**: Strong privacy controls and anonymous reporting options
- **AI-Powered Legal Guidance**: Get instant legal advice via an empathetic chatbot
- **Verified Lawyers Directory**: Access verified lawyers specializing in women's rights
- **Anonymous Police Complaints**: Generate and file anonymous police complaints
- **Trauma-Aware UI**: Clean, accessible interface designed with trauma-informed principles

## 🛠️ Tech Stack

- **Frontend**: React (Vite) + Tailwind CSS
- **Backend**: Firebase (Authentication, Firestore, Storage, Cloud Functions)
- **AI**: OpenAI API via Firebase Cloud Functions
- **Security**: Firebase Security Rules, encryption, hashing

## 📋 Prerequisites

- Node.js 18+ and npm
- Firebase account and project
- OpenAI API key (for AI chatbot functionality)

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone <repository-url>
cd hervoice
```

### 2. Set Up Firebase Project

1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Create a new project or select an existing one
3. Enable the following services:
   - Authentication (Email/Password and Anonymous)
   - Firestore Database
   - Storage
   - Cloud Functions

### 3. Configure Firebase

1. Install Firebase CLI globally:
```bash
npm install -g firebase-tools
```

2. Login to Firebase:
```bash
firebase login
```

3. Initialize Firebase in the project:
```bash
firebase init
```
   - Select: Firestore, Functions, Storage, Hosting
   - Use existing project or create new
   - Follow prompts to configure

### 4. Set Up Frontend

1. Navigate to frontend directory:
```bash
cd frontend
```

2. Install dependencies:
```bash
npm install
```

3. Create `.env` file (copy from `.env.example`):
```bash
cp .env.example .env
```

4. Add your Firebase configuration to `.env`:
```
VITE_FIREBASE_API_KEY=your-api-key
VITE_FIREBASE_AUTH_DOMAIN=your-project.firebaseapp.com
VITE_FIREBASE_PROJECT_ID=your-project-id
VITE_FIREBASE_STORAGE_BUCKET=your-project.appspot.com
VITE_FIREBASE_MESSAGING_SENDER_ID=your-sender-id
VITE_FIREBASE_APP_ID=your-app-id
```

5. Update `frontend/src/config/firebase.js` with your Firebase config (or use environment variables)

### 5. Set Up Cloud Functions

1. Navigate to functions directory:
```bash
cd backend/functions
```

2. Install dependencies:
```bash
npm install
```

3. Set OpenAI API key in Firebase Functions config:
```bash
firebase functions:config:set openai.key="your-openai-api-key"
```

Or use environment variables:
```bash
export OPENAI_API_KEY="your-openai-api-key"
```

### 6. Deploy Security Rules

Deploy Firestore and Storage security rules:
```bash
firebase deploy --only firestore:rules,storage:rules
```

### 7. Deploy Cloud Functions

Deploy the Cloud Functions:
```bash
firebase deploy --only functions
```

### 8. Run Development Server

From the project root:
```bash
npm run dev
```

Or from the frontend directory:
```bash
cd frontend
npm run dev
```

The app will be available at `http://localhost:5173`

## 📁 Project Structure

```
hervoice/
├── frontend/                 # React frontend application
│   ├── src/
│   │   ├── components/      # Reusable React components
│   │   ├── contexts/        # React contexts (Auth, etc.)
│   │   ├── pages/           # Page components
│   │   ├── config/          # Configuration files
│   │   └── App.jsx          # Main app component
│   ├── public/              # Static assets
│   └── package.json
├── backend/
│   └── functions/           # Firebase Cloud Functions
│       ├── index.js          # Function definitions
│       └── package.json
├── docs/                     # Documentation
│   └── FIRESTORE_SCHEMA.md   # Database schema
├── firestore.rules          # Firestore security rules
├── storage.rules            # Storage security rules
├── firebase.json            # Firebase configuration
└── README.md
```

## 🔐 Security

- **Firestore Rules**: User-scoped access - users can only access their own data
- **Storage Rules**: Files are scoped to user IDs with size and type restrictions
- **Authentication**: Required for all operations
- **API Keys**: Never exposed on frontend - all AI operations via Cloud Functions

## 🎨 Design Principles

- **Trauma-Informed**: Soft colors, simple language, user control
- **Accessible**: WCAG-compliant, keyboard navigation, screen reader support
- **Privacy-First**: Anonymous options, encrypted data, user control
- **Non-Judgmental**: No dark patterns, no forced actions

## 📝 Data Models

See [docs/FIRESTORE_SCHEMA.md](docs/FIRESTORE_SCHEMA.md) for detailed schema documentation.

## 🧪 Development

### Running Locally

1. Start Firebase Emulators:
```bash
firebase emulators:start
```

2. In another terminal, start the frontend:
```bash
cd frontend
npm run dev
```

### Building for Production

```bash
cd frontend
npm run build
```

The built files will be in `frontend/dist/`

### Deploying

Deploy everything:
```bash
firebase deploy
```

Deploy specific services:
```bash
firebase deploy --only hosting      # Frontend
firebase deploy --only functions    # Cloud Functions
firebase deploy --only firestore    # Firestore rules
```

## 🤝 Contributing

This is a safety-critical application. When contributing:

1. Prioritize user privacy and security
2. Use trauma-informed language and design
3. Test thoroughly before submitting
4. Follow the existing code style
5. Document your changes

## 📄 License

MIT License - see LICENSE file for details

## 🆘 Support

For issues, questions, or support, please open an issue in the repository.

## ⚠️ Important Notes

- This application handles sensitive data. Always follow security best practices
- Never commit API keys or credentials to version control
- Test security rules thoroughly before deploying
- Regularly update dependencies for security patches
- Follow trauma-informed care principles in all user interactions

---

**Built with care for women's safety and empowerment** 🛡️



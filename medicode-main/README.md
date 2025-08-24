**MediCode: Your Multilingual AI Medical Assistant**

MediCode is a full-stack web application designed to provide accessible medical information and analysis using the power of Google's Gemini AI. It features an AI-powered medical chatbot and an image analysis tool for medical prescriptions and reports, all with comprehensive multilingual support in English, Tamil, and Hindi.

## Features

  * **AI Medical Chatbot**: Ask any health-related question and receive accurate, simplified medical explanations, common causes, symptoms, general advice, and guidance on when to see a doctor. Responses are provided in English, Tamil, and Hindi.
  * **Image Analysis for Medical Documents**: Upload images of prescriptions or medical reports to get clear, jargon-free explanations of medicines, their uses, or test results. Analysis is available in English, Tamil, and Hindi.
  * **Multilingual Support**: All AI-generated responses for both the chatbot and image analysis are provided in English, Tamil, and Hindi, catering to a diverse user base.
  * **Text-to-Speech**: Listen to the analysis results and chatbot responses in your preferred language.
  * **User-Friendly Interface**: An intuitive and responsive design built with React.
  * **Local Storage for Persistence**: Utilizes local storage for persisting data, with specific handling for Date objects in history items.

## Technologies Used

### Frontend

  * **React**: A JavaScript library for building user interfaces.
  * **TypeScript**: Adds static typing to JavaScript for improved code quality and maintainability.
  * **Lucide React**: An icon library for sleek UI elements.
  * **Custom Hooks**: `useTranslation`, `useLocalStorage`, `useTextToSpeech` for specific functionalities like translation, local storage persistence, and text-to-speech.

### Backend

  * **Node.js**: JavaScript runtime for server-side operations.
  * **Express.js**: A minimalist web framework for building the REST API.
  * **CORS**: Middleware enabling cross-origin requests from the frontend, specifically configured for `https://medicode4.netlify.app`.
  * **Body-Parser**: Handles parsing of incoming request bodies, including large image payloads up to 50MB.
  * **Dotenv**: Manages environment variables, such as the `GOOGLE_GEMINI_API_KEY`.
  * **OS Module**: Used for retrieving local network interface information for logging the server's IP address.

### AI Model

  * **Google Gemini API (gemini-2.0-flash)**: The powerful generative AI model driving both the medical assistant and image analysis features. The `GoogleGenerativeAI` client library is used to interact with the API.

## Getting Started

To set up and run MediCode locally, follow these steps:

### Prerequisites

  * Node.js (LTS version recommended)
  * npm or Yarn
  * Google Gemini API Key

### 1\. Clone the Repository

```bash
git clone <repository_url>
cd medicode-main
```

### 2\. Backend Setup

Navigate to the backend directory:

```bash
cd backend
```

Create a `.env` file in the backend directory and add your Gemini API key:

```
GOOGLE_GEMINI_API_KEY=YOUR_ACTUAL_GEMINI_API_KEY
```

Install backend dependencies:

```bash
npm install
```

Start the backend server:

```bash
npm start
```

The server should start on `http://0.0.0.0:5000`. You should see a confirmation message like `✅ Backend running at http://<your-local-ip-address>:5000`.

### 3\. Frontend Setup

Navigate back to the root directory:

```bash
cd ..
```

Create a `.env` file in the root directory and specify your backend URL:

```
VITE_BACKEND_URL=http://localhost:5000
```

*Note: If deploying, ensure this `VITE_BACKEND_URL` matches your deployed backend URL (e.g., `https://your-backend-domain.com`).*

Install frontend dependencies:

```bash
npm install
```

Start the frontend development server:

```bash
npm run dev
```

The frontend application should now be accessible in your web browser at `http://localhost:5173` (Vite's default port).

## Usage

1.  **Scanner Tab**: Upload an image of a medical prescription or report to get an AI-powered analysis in English, Tamil, and Hindi.
2.  **Chat Tab**: Engage with the AI medical assistant by typing your health-related questions. Receive responses in your chosen language.
3.  **Language Selection**: Toggle between English, Tamil, and Hindi for AI responses and analysis results.
4.  **Listen to Results**: Use the "Listen" button to hear the AI's analysis or chat response spoken aloud in the selected language.
5.  **Copy/Share**: Easily copy the generated text or share it with others.

## Project Structure

```
medicode-main/
├── backend/
│   ├── server.mjs          # Backend Express server
│   ├── package.json        # Backend dependencies
│   └── .env               # Backend environment variables
├── src/
│   ├── components/        # React UI components
│   │   ├── AnalysisResult.tsx
│   │   ├── MedicalChatbot.tsx
│   │   ├── ImageUpload.tsx
│   │   └── ...
│   ├── hooks/            # Custom React hooks
│   │   ├── useLocalStorage.ts
│   │   ├── useTextToSpeech.ts
│   │   └── useTranslation.ts
│   ├── services/         # API services
│   │   └── geminiApi.ts  # Frontend API calls to backend
│   └── utils/           # Utility functions
│       └── translations.ts
├── package.json          # Frontend dependencies
├── vite.config.ts       # Vite configuration
└── .env                 # Frontend environment variables
```

## Contributing

Contributions are welcome\! Please feel free to open issues or submit pull requests.

## License

This project is open-sourced under the MIT License. (You can specify your chosen license here).

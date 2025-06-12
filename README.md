🩺 #Project Title: AI-Powered Healthcare Assistant
🎯 Project Idea (Health Awareness)

The goal of this project is to develop a full-stack web application that offers personalized exercise guidance and health tracking using AI-based video analysis, along with a fitness chatbot for answering user queries. The system is designed to assist users (especially office workers or students) in maintaining physical wellness and preventing posture-related issues.
🛠️ Tools and Technologies Used
🔹 Frontend

    Framework: Next.js (React)

    Languages: TypeScript, JavaScript, HTML, CSS

    Styling: Tailwind CSS, Ant Design Components

    State Management: React Context

    HTTP Requests: Axios

    Authentication: Context API with LocalStorage

🔹 Backend

    Framework: FastAPI (Python)

    Database: MongoDB (via MongoClient)

    AI/ML Processing:

        MediaPipe: For pose estimation and landmark tracking

        OpenCV: For video frame processing and drawing overlays

    WebSockets: Real-time video feedback and exercise tracking

    Data Models: Pydantic for input validation

🔹 Database

    MongoDB (local): Used to store:

        User credentials

        Physical health attributes

        Repetition logs of neck exercises

💡 Core Features
✅ 1. User Authentication

    Sign up / Sign in using username or email

    Secure credential checks (stored in MongoDB)

    Profile data displayed on the dashboard

✅ 2. Patient Health Info Submission

    Collects:

        Gender, Age, Height, Hypertension, Diabetes, BMI, Mobility

    Data stored under User_healthcareaiAttributes collection

✅ 3. AI-Based Neck Exercise Tracking

    Real-time video captured from webcam

    MediaPipe analyzes the pose

    Detects 3 key movements:

        Forward/Backward tilt

        Side tilt

        Neck rotation

    Counts reps using angle tracking and movement thresholds

    Reps are stored in MongoDB after each session

✅ 4. Chatbot Assistant

    Accepts natural language queries

    Responds with fitness and nutrition tips (future upgrade: connect to GPT API or rule-based responses)

    Handles unexpected input errors with fallback messages

✅ 5. Admin/Developer Features

    Repetition counters per exercise

    Automatic frame encoding to Base64 for frontend rendering

    Reset and tracking logic per movement

    Modular code for other future exercises (WarriorPose, Leg Raises, Eye Exercise, etc.)

🧠 AI Logic Summary

    Pose landmarks are extracted using MediaPipe

    Angles are calculated between the nose and shoulder mid-point

    Movement classification is based on:

        Angle ranges

        Direction changes (up/down logic)

        History smoothing via deque

    Detected reps trigger a logging function to store them in the database

⚙️ Deployment Notes

    MongoDB must run locally on port 27017

    FastAPI runs on port 8000 (default)

    Next.js client runs on port 3000

    Real-time WebSocket connection established for live feedback

🌱 Future Enhancements

    JWT-based authentication with token expiration

    Integration with OpenAI/GPT API for advanced chatbot answers

    Real-time alert system for incorrect posture

    Dashboard graphs for progress tracking

    Support for mobile webcam and responsive UI

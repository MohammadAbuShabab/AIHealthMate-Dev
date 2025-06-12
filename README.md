🩺#Project Title: AI-Powered Healthcare Assistant
🎯 Project Overview

Problem Motivation:
In today’s fast-paced and sedentary lifestyle—especially for students, programmers, and office workers—many suffer from posture-related health issues, eye fatigue, and neck stiffness due to prolonged screen exposure and lack of movement. Yet, there are very few personalized and interactive platforms that assist users with real-time feedback and guided exercises without visiting a physical clinic or gym.

Solution:
This project addresses the gap by offering an AI-powered web platform that performs real-time exercise analysis using a webcam, tracks repetitions using body landmarks, and responds to user queries through a fitness chatbot—all from the comfort of home.
🛠️ Tools & Technologies Used
🔹 Frontend (Client-side)

    Framework: Next.js (React)

    Languages: TypeScript, JavaScript, HTML, CSS

    Styling: Tailwind CSS + Ant Design UI

    State Management: React Context API

    Data Fetching: Axios

    Authentication: Context API with LocalStorage

🔹 Backend (Server-side)

    Framework: FastAPI (Python)

    Database: MongoDB via pymongo

    AI Processing:

        MediaPipe (for real-time pose detection)

        OpenCV (for frame drawing and analysis)

    WebSockets: For live video communication between client and server

    Validation: Pydantic models

🔹 Database Schema (MongoDB)

    Users – stores credentials

    User_healthcareaiAttributes – stores physical attributes

    RepetitionLogs – stores completed reps per exercise session

💡 Core Features Breakdown
✅ 1. Authentication & Profile

    Sign up or log in using username/email

    Dashboard shows profile details

✅ 2. Health Info Input

    Collects BMI, sex, diabetes, hypertension, mobility, etc.

    Stored in a dedicated collection for later use by the AI module

✅ 3. Real-Time AI Exercise Assistant

    Uses MediaPipe + OpenCV for neck movement tracking

    Detects and tracks:

        ✅ Forward/Backward tilt

        ✅ Side tilt

        ✅ Head rotation

    Shows real-time reps count and feedback

    Stores reps automatically to MongoDB after each session

✅ 4. Fitness Chatbot

    Accepts user questions like:

        “What’s a good exercise for shoulder pain?”

        “Suggest me a diet plan.”

    Displays fallback message if input is unclear

    Future upgrade: Connect to GPT API for smart NLP answers

✅ 5. Developer/Technical Features

    Reset counters per exercise

    Encodes each frame to Base64 for live rendering on frontend

    Modular analyzer design (easily add future exercises like leg raises, eye strain, yoga poses)

🧠 AI & Pose Detection Logic

    Landmark Extraction: Using MediaPipe’s Pose model

    Angle Calculation: Between nose and midpoint of shoulders

    Classification:

        Based on thresholds and direction changes

        Maintains historical angle smoothing using deque

    Reps Logic:

        If movement switches from down → up → down = 1 rep

        Stored in DB after the session ends

🌱 Future Enhancements

    ⏳ JWT authentication with token expiration

    🤖 GPT-based intelligent chatbot integration

    ⚠️ Real-time alerts for incorrect posture

    📊 Graph-based dashboard for health progress

    📱 Mobile responsiveness and webcam support

📸 Screenshots 
🏠 Home Page
![Screenshot 2025-06-12 141414](https://github.com/user-attachments/assets/cb1fc4a9-e02d-4204-a39a-02a6238500a3)

🔐 Login / Signup
![Screenshot 2025-06-12 141439](https://github.com/user-attachments/assets/38b5fb6d-729f-41b5-9028-d9b7c0c8e766)
![Screenshot 2025-06-12 141451](https://github.com/user-attachments/assets/72e109fc-d3bc-4988-b479-8ca15c0162db)

🧍‍♂️ Health Info Form
![Screenshot 2025-06-12 141539](https://github.com/user-attachments/assets/9fdc1843-3bc1-4ca8-bbb1-694a31139387)
![Screenshot 2025-06-12 141624](https://github.com/user-attachments/assets/99388114-8792-453a-a2c8-7da3da998dcd)


🎥 Exercise Tracking Screen
![Screenshot 2025-06-12 141609](https://github.com/user-attachments/assets/d3497a73-23d7-48fd-8daa-7821dec5da23)

📊 Dashboard Stats (Progress)
![Screenshot 2025-06-12 141539](https://github.com/user-attachments/assets/b3e7f352-445e-4cfe-8fdc-e5be46acdd88)

🤖 Chatbot Interaction
![Screenshot 2025-06-12 141550](https://github.com/user-attachments/assets/fd42a85a-a0cf-4015-960f-caa6e949bc7f)




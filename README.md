## 💬 MERN Real-Time Chatroom with Audio Calling

This is a full-stack real-time chat application built using the MERN stack (MongoDB, Express, React, Node.js) and enhanced with:

🔒 JWT-based Authentication  
💬 Real-Time Messaging (Socket.IO)  
📁 File Uploads (Images, Videos, PDFs)  
📞 Audio Calling (WebRTC)  
🧑‍💼 Admin Controls (Manage Users & Messages)  

🌐 Deployed on Render (Backend) and Vercel (Frontend)  

# 📂 Project Structure

chatroom/  
├── client/             # React frontend  
│   ├── src/  
│   │   ├── pages/      # ChatRoom, Login, Register, AdminDashboard  
│   │   ├── components/ # CallPopup, Navbar  
│   │   ├── App.js  
│   │   └── ...  
│   └── public/  
│  
├── server/             # Node.js + Express backend  
│   ├── routes/         # auth.js, admin.js  
│   ├── models/         # User.js, Message.js  
│   ├── index.js        # Main backend + WebSocket logic  
│   └── .env  

# 🧰 Technology Stack

✅ Frontend (React)

| Module              | Purpose                       |
|---------------------|-------------------------------|
| react               | Core framework                |
| react-router-dom    | Routing (login/register/chat) |
| emoji-picker-react  | Emoji input in chat           |
| socket.io-client    | WebSocket connection to server|
| tailwindcss         | Styling                       |
| axios               | HTTP requests (login/register)|

✅ Backend (Node.js + Express)

| Module        | Purpose                         |
|---------------|---------------------------------|
| express       | API server and routing          |
| mongoose      | MongoDB interaction             |
| cors          | Enable cross-origin requests    |
| dotenv        | Load environment variables      |
| jsonwebtoken  | JWT authentication              |
| bcryptjs      | Password hashing                |
| socket.io     | Real-time messaging and signaling|

# 🔐 Authentication

JWT-based auth is used for login and protected routes.  
User roles: admin and user  
Token stored in local storage.  

# 💬 Chat Functionality

Real-time using Socket.IO  
Broadcast text or file messages to all users  
Files: Images, Videos, PDFs supported via FileReader & Base64  

# 📞 Audio Calling (WebRTC)

Used: RTCPeerConnection + navigator.mediaDevices.getUserMedia  
Signaling via Socket.IO  
ICE Candidates exchanged to establish P2P connection  
audio elements used to stream and play audio between peers  

# 🛠️ Admin Features

Admin dashboard route: /admin  
Promote user to admin, remove users  
Delete any message from the chat  

# 🚀 Deployment & Environment Setup

## Environment Variables

Create a `.env` file in the `server/` directory with the following variables:

```env
MONGO_URI=your_mongodb_connection_string
EMAIL_USER=your_gmail_address@gmail.com
EMAIL_PASS=your_gmail_app_password
JWT_SECRET=your_jwt_secret
NODE_ENV=production
PORT=5000
FRONTEND_URL=https://your-frontend-url.vercel.app
```

### Email Configuration

The application uses Gmail SMTP for OTP email delivery. To set up:

1. Enable 2-Factor Authentication on your Gmail account
2. Generate an App Password:
   - Go to Google Account settings → Security → 2-Step Verification → App passwords
   - Generate a new app password for "Mail"
   - Use this 16-character password as `EMAIL_PASS`
3. Set `EMAIL_USER` to your Gmail address and `EMAIL_PASS` to the app password

For development, if `EMAIL_USER` or `EMAIL_PASS` is not set, OTP codes will be logged to the console.

## Render Deployment

The backend is configured for Render deployment with the following settings in `render.yaml`:

- **Service Type:** Web Service
- **Runtime:** Node.js
- **Build Command:** `npm run build`
- **Start Command:** `npm start`
- **Environment Variables:** `NODE_ENV`, `PORT`, `MONGO_URI`, `SENDGRID_API_KEY`

# 👤 Credits

Created by Kodali Shanmukh Chowdary as a real-time communication project with MERN + WebRTC + Socket.IO integration.

# Note: Kindly check the spam mail for OTP to sign up.


📩 Email: kodalishanmukh6thfinger@gmail.com

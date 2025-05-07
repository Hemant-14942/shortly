Shortly 🚀
A Powerful, Secure, and User-Friendly URL Shortener

🌟 What is Shortly?
Shortly is a modern web application that lets you transform long, unwieldy URLs into short, manageable links. With robust authentication, user dashboards, and secure session management, Shortly is built for both simplicity and power.

✨ Features
🔗 URL Shortening: Instantly generate short links for any URL.

👤 User Accounts: Register, log in, and manage your own collection of links.

📋 Dashboard: View, edit, and delete your short links.

🛡️ Security: Passwords are hashed with Argon2, and all sessions use secure tokens.

🔄 Persistent Sessions: Stay logged in with secure, refreshable tokens.

📊 Analytics Ready: Database schema supports tracking and expansion.

🗂️ Project Structure
text
shortly/
├── app.js                    # Main server setup and middleware
├── package.json              # Project dependencies and scripts
├── drizzle.config.js         # Drizzle ORM configuration
├── /controllers              # Route controllers (e.g., auth, shortener)
│   └── auth.controller.js
├── /middlewares
│   └── verify-auth-middleware.js  # Handles authentication on every request
├── /models
│   └── shortener.model.js    # File-based link storage for fallback or testing
├── /routes
│   ├── auth.routes.js        # User authentication endpoints
│   └── shortener.routes.js   # URL shortener endpoints
├── /services
│   ├── auth-services.js      # Handles authentication/session logic
│   └── shortener-services.js # Handles CRUD for short links
├── /drizzle
│   └── schema.js             # Database schema for users, sessions, links
├── /public                   # Static assets (CSS, JS, images)
├── /views                    # EJS templates for rendering pages
└── /data
    └── links.json            # JSON storage for links (if using file model)
🚀 Quick Start
Clone the repository

bash
git clone https://github.com/Hemant-14942/shortly.git
cd shortly
Install dependencies

bash
npm install
Configure environment variables

Create a .env file with your database credentials and secrets.

Run database migrations

bash
npm run db:migrate
Start the server

bash
npm run dev
Open your browser

Visit http://localhost:3000

🛠️ How It Works
Authentication:
User sessions are managed with JWT access and refresh tokens, stored as secure HTTP-only cookies. Passwords are hashed with Argon2 for strong security.

Middleware:
Every request passes through verify-auth-middleware.js, which checks for valid tokens and refreshes them if needed.

Database:
Drizzle ORM with MySQL stores users, sessions, and short links. The schema enforces relationships and data integrity.

Short Link Management:
Users can create, edit, and delete their own short links. Each link is associated with the user who created it, ensuring privacy and control.

📦 Key Modules
File/Folder	Purpose
app.js	Sets up Express, middleware, and routes
auth.controller.js	Handles registration, login, and user session logic
verify-auth-middleware.js	Ensures authentication on every request, handles token refresh
shortener.model.js	File-based storage for links (fallback/testing)
auth-services.js	Authentication logic: hashing, tokens, sessions
shortener-services.js	CRUD operations for short links
schema.js	Defines users, sessions, and short_links tables
🗄️ Database Design
Users Table: Stores user info and hashed passwords.

Sessions Table: Tracks user sessions, IPs, and user agents.

Short Links Table: Maps original URLs to unique short codes, linked to users.

Relationships:

One user can have many short links and sessions.

Each short link belongs to a user.

🔒 Security Highlights
Argon2 for password hashing.

JWT for stateless, secure authentication.

Secure Cookies (httpOnly, secure flags).

Session Validation: Sessions can be invalidated on logout or expiration.

🧑‍💻 Example: Creating a Short Link
User logs in or registers.

Submits a long URL via the dashboard.

Backend generates a unique short code and stores it in the database.

User sees their new short link on their dashboard, ready to share!

📝 Contributing
Fork the repo and create a new branch for your feature or fix.

Follow the existing code style.

Submit a pull request with a clear description.

📄 License
ISC License

Shortly - The easiest way to shorten, manage, and share your links securely!

Made with ❤️ for the web community.

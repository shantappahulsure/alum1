
# Referral Network Hub

Referral Network Hub is a web application designed to help users discover professional opportunities and connect through a referral-focused network. It provides user authentication, profile management, network exploration, and password recovery functionality.

## Features

- User registration and login
- JWT-based authentication
- Password reset and recovery
- User profile viewing and editing
- Explore network and profiles
- Reusable company cards and UI components
- Responsive user interface
- Password hashing and security middleware
- Email integration using SMTP
- MongoDB database integration
- Docker support for local development

## Tech Stack

### Frontend
- Next.js 15
- React 19
- TypeScript
- Tailwind CSS
- Radix UI
- Axios
- React Hook Form
- Zod
- Framer Motion
- Recharts
- Lucide React

### Backend
- Node.js
- Express.js
- TypeScript
- MongoDB
- Mongoose
- JSON Web Tokens (JWT)
- bcryptjs
- Nodemailer
- Helmet
- CORS
- Express Rate Limit

### Tools
- Git and GitHub
- npm
- Docker
- Docker Compose

## Project Structure

```text
alum1-main/
├── frontend/
│   ├── app/
│   │   ├── (auth)/
│   │   ├── (main)/
│   │   └── (protected)/
│   ├── components/
│   ├── lib/
│   └── package.json
├── backend/
│   ├── auth-service/
│   │   ├── api/
│   │   │   ├── config/
│   │   │   ├── controllers/
│   │   │   ├── middleware/
│   │   │   ├── models/
│   │   │   ├── routes/
│   │   │   └── utils/
│   │   ├── Dockerfile
│   │   └── package.json
│   ├── docker-compose.yml
│   └── package.json
├── Documentation/
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
└── LICENSE
```

## Prerequisites

Before running the project, make sure you have installed:

- Node.js
- npm
- MongoDB or Docker
- Git

## Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/shantappahulsure/alum1.git
cd alum1-main
```

Replace `https://github.com/shantappahulsure/alum1.git` with your actual GitHub repository URL.

### 2. Configure the Backend

Navigate to the authentication service:

```bash
cd backend/auth-service
npm install
```

Create a `.env` file inside `backend/auth-service/` and configure the required environment variables:

```env
PORT=3001
NODE_ENV=development

MONGODB_URI=mongodb://127.0.0.1:27017/auth-service

JWT_SECRET=your_jwt_secret
JWT_REFRESH_SECRET=your_refresh_token_secret

CLIENT_URL=http://localhost:3000

EMAIL_HOST=smtp.example.com
EMAIL_PORT=587
EMAIL_SECURE=false
EMAIL_USER=your_email
EMAIL_PASSWORD=your_email_password
EMAIL_FROM=noreply@example.com
```

Use strong, unique JWT secrets and configure valid SMTP credentials before testing email functionality. Check the backend configuration file for any additional required variables.

### 3. Start the Backend

From `backend/auth-service/`, run:

```bash
npm run dev
```

The authentication service is configured to use port `3001` by default.

### 4. Configure the Frontend

Open a new terminal:

```bash
cd frontend
npm install
```

Create a `.env.local` file inside the `frontend/` directory:

```env
NEXT_PUBLIC_AUTH_API_URL=http://localhost:3001
```

Make sure this URL matches your backend API configuration.

### 5. Start the Frontend

Run:

```bash
npm run dev
```

Open your browser and visit:

http://localhost:3000

## Available Scripts

### Frontend

Run these commands from the `frontend/` directory.

| Command | Description |
|---|---|
| `npm run dev` | Start the development server |
| `npm run build` | Build the application for production |
| `npm run start` | Start the production server |
| `npm run lint` | Run the configured lint command |

### Backend

Run these commands from `backend/auth-service/`.

| Command | Description |
|---|---|
| `npm run dev` | Start the development server |
| `npm run build` | Compile TypeScript |
| `npm start` | Start the compiled application |
| `npm test` | Run the configured test script |

## Application Routes

| Route | Description |
|---|---|
| `/` | Home page |
| `/explore` | Explore the network |
| `/contact` | Contact page |
| `/login` | User login |
| `/signup` | User registration |
| `/forgot-password` | Password recovery |
| `/reset-password` | Reset password |
| `/profile` | User profile |
| `/profile/edit` | Edit profile |
| `/profile/[ID]` | View an individual profile |
| `/privacy-policy` | Privacy policy |
| `/terms-of-service` | Terms and conditions |

## Docker Setup

The project includes a Docker Compose configuration for running MongoDB and the authentication service.

From the `backend/` directory, run:

```bash
docker compose up --build
```

Make sure your environment variables and database settings are configured correctly before starting the services.

## Security Considerations

- Never commit `.env` or `.env.local` files.
- Never expose private API keys or JWT secrets in frontend code.
- Use strong, unique secrets for access and refresh tokens.
- Configure CORS and cookies correctly for production.
- Use HTTPS when deploying publicly.
- Configure SMTP credentials securely.
- Validate environment variables before deploying.

## Troubleshooting

### Backend Connection Issues

- Verify that the backend is running.
- Check the API URL in `frontend/.env.local`.
- Confirm that the backend port is correct.
- Review CORS settings and server logs.

### MongoDB Connection Issues

- Make sure MongoDB is running.
- Verify the `MONGODB_URI` value.
- When using Docker Compose, use the MongoDB service hostname instead of `localhost` from inside the backend container.

### Email Issues

- Verify SMTP host, port, username, and password.
- Check whether your email provider requires an app password.
- Review backend logs for email delivery errors.

## Contributing

Contributions are welcome!

1. Fork the repository.
2. Create a new branch.
3. Make your changes.
4. Test your changes.
5. Submit a pull request.

Please read `CONTRIBUTING.md` and `CODE_OF_CONDUCT.md` before contributing.

## License

See the `LICENSE` file in the repository for licensing information.

---

Developed with ❤️ using Next.js, Node.js, and MongoDB.

# Lead Generation System

A modern lead generation system with email notifications and n8n workflow automation.

## Features

- Modern, responsive lead generation form
- Real-time form validation
- Secure backend API with rate limiting
- n8n workflow integration for email notifications
- Comprehensive error handling and logging
- Production-ready security measures

## Tech Stack

### Frontend
- React 18
- TailwindCSS for styling
- React Toastify for notifications
- Axios for API calls

### Backend
- Node.js with Express
- Winston for logging
- Express Validator for input validation
- Helmet for security headers
- Rate limiting for API protection

### Automation
- n8n for workflow automation
- Email notifications via n8n

## Prerequisites

- Node.js (v14 or higher)
- npm or yarn
- n8n instance (local or cloud)
- Email service (SendGrid, Mailgun, etc.)

## Setup Instructions

### 1. Clone the Repository

```bash
git clone <repository-url>
cd lead-generation-system
```

### 2. Frontend Setup

```bash
cd client
npm install
```

Create a `.env` file in the client directory:
```
REACT_APP_API_URL=http://localhost:5000
```

### 3. Backend Setup

```bash
cd ../lead-server
npm install
```

Create a `.env` file in the lead-server directory:
```
PORT=5000
NODE_ENV=development
CLIENT_URL=http://localhost:3000
N8N_WEBHOOK_URL=your_n8n_webhook_url_here
N8N_API_KEY=your_n8n_api_key_here
```

### 4. n8n Setup

1. Install n8n locally or use n8n.cloud
2. Create a new workflow
3. Add a Webhook node
4. Configure the webhook URL
5. Add an Email node (SendGrid, Mailgun, etc.)
6. Configure email templates
7. Test the workflow

## Running the Application

### Development Mode

1. Start the backend:
```bash
cd lead-server
npm run dev
```

2. Start the frontend:
```bash
cd client
npm start
```

The application will be available at:
- Frontend: http://localhost:3000
- Backend: http://localhost:5000

### Production Mode

1. Build the frontend:
```bash
cd client
npm run build
```

2. Start the backend:
```bash
cd lead-server
npm start
```

## Deployment

### Frontend Deployment (Vercel/Netlify)

1. Connect your repository to Vercel/Netlify
2. Configure build settings:
   - Build command: `cd client && npm install && npm run build`
   - Output directory: `client/build`
3. Add environment variables:
   - `REACT_APP_API_URL`: Your backend API URL

### Backend Deployment (Heroku/Render)

1. Create a new app on Heroku/Render
2. Connect your repository
3. Add environment variables:
   - `PORT`
   - `NODE_ENV`
   - `CLIENT_URL`
   - `N8N_WEBHOOK_URL`
   - `N8N_API_KEY`

## Security Considerations

- All API endpoints are protected with rate limiting
- CORS is configured to only allow requests from the frontend
- Input validation is implemented on both frontend and backend
- Security headers are enabled via Helmet
- Sensitive data is not exposed in error messages
- API keys and secrets are stored in environment variables

## Extending the System

### Adding New Features

1. Additional Form Fields:
   - Add fields to the frontend form
   - Update backend validation
   - Modify n8n workflow to handle new data

2. CRM Integration:
   - Add CRM API endpoints to n8n workflow
   - Configure data mapping
   - Set up authentication

3. Analytics:
   - Add tracking code to frontend
   - Implement backend analytics endpoints
   - Configure n8n to store analytics data

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.
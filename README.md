# Dual-Purpose AI Chatbot Platform

A comprehensive AI chatbot system with dual interfaces for customer support and field service guidance, built with FastAPI, React, and LangChain.

## 🌟 Features

### Dual Interface System
- **Customer Support Interface**: Simplified interface for general customer inquiries
- **Field Service Interface**: Advanced interface with technical guidance and troubleshooting features

### AI-Powered Responses
- **RAG Implementation**: Retrieval-Augmented Generation for accurate, context-aware responses
- **Source Citation**: Automatic citation of knowledge base sources
- **Conversation Memory**: Maintains context across conversation sessions

### Knowledge Base Management
- **Document Upload**: Support for PDF, DOCX, and TXT files
- **Audience-Based Categorization**: Content targeting for different user roles
- **Version Control**: Track document versions and updates
- **Admin Control**: Full content management capabilities

### Administrative Features
- **User Management**: Role-based access control (Admin, Customer, Field Engineer)
- **Content Management**: Upload, categorize, and manage knowledge base documents
- **Analytics Dashboard**: Basic usage analytics and feedback tracking
- **Feedback System**: Collect and analyze user feedback

## 🏗️ Architecture

### Backend (FastAPI)
- **Framework**: FastAPI with async/await support
- **Database**: PostgreSQL with SQLAlchemy ORM
- **Vector Database**: ChromaDB for document embeddings
- **AI Framework**: LangChain with OpenAI GPT-4
- **Authentication**: JWT with bcrypt password hashing

### Frontend (React)
- **Framework**: React 18 with TypeScript
- **UI Library**: Material-UI (MUI)
- **State Management**: React Context API
- **HTTP Client**: Axios for API communication
- **Routing**: React Router v6

### Infrastructure
- **Containerization**: Docker and Docker Compose
- **CI/CD**: GitHub Actions with automated testing and deployment
- **Environment**: Configurable via environment variables

## 🚀 Quick Start

### Prerequisites
- Docker and Docker Compose
- Git
- OpenAI API key

### Local Development Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/syedfahimdev/ai-chatbot-platform.git
   cd ai-chatbot-platform
   ```

2. **Set up environment variables**
   ```bash
   cp env.example .env
   # Edit .env and add your OpenAI API key
   ```

3. **Start the application**
   ```bash
   docker-compose up --build -d
   ```

4. **Access the application**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:8000
   - API Documentation: http://localhost:8000/docs

### Demo Accounts
- **Admin**: admin@demo.com / admin123
- **Customer**: customer@demo.com / admin123
- **Field Engineer**: engineer@demo.com / admin123

## 📁 Project Structure

```
ai-chatbot-platform/
├── .github/workflows/          # GitHub Actions workflows
├── backend/                    # FastAPI backend
│   ├── app/
│   │   ├── api/v1/            # API endpoints
│   │   ├── core/              # Core configuration
│   │   ├── models/            # Database models
│   │   └── services/          # Business logic
│   ├── tests/                 # Backend tests
│   └── requirements.txt       # Python dependencies
├── frontend/                  # React frontend
│   ├── src/
│   │   ├── components/        # Reusable components
│   │   ├── contexts/          # React contexts
│   │   ├── pages/             # Page components
│   │   └── services/          # API services
│   └── package.json          # Node.js dependencies
├── docker-compose.yml         # Docker orchestration
├── env.example               # Environment template
└── README.md                 # This file
```

## 🔧 Configuration

### Environment Variables

Create a `.env` file based on `env.example`:

```bash
# Database Configuration
DATABASE_URL=postgresql+asyncpg://postgres:password@localhost:5432/ai_chatbot
POSTGRES_DB=chatbot_db
POSTGRES_USER=postgres
POSTGRES_PASSWORD=password

# OpenAI Configuration
OPENAI_API_KEY=your_openai_api_key_here
OPENAI_MODEL=gpt-4
OPENAI_TEMPERATURE=0.7
OPENAI_MAX_TOKENS=1000

# Vector Database Configuration
CHROMA_HOST=localhost
CHROMA_PORT=8000
CHROMA_COLLECTION_NAME=chatbot_documents

# Application Configuration
SECRET_KEY=your_secret_key_here_change_in_production
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30

# Frontend Configuration
REACT_APP_API_URL=http://localhost:8000
REACT_APP_WS_URL=ws://localhost:8000

# File Upload Configuration
MAX_FILE_SIZE=10485760  # 10MB
ALLOWED_EXTENSIONS=pdf,docx,txt

# Logging Configuration
LOG_LEVEL=INFO
LOG_FORMAT=json

# Development Configuration
DEBUG=true
ENVIRONMENT=development
```

## 🧪 Testing

### Backend Tests
```bash
cd backend
pytest tests/ -v
```

### Frontend Tests
```bash
cd frontend
npm test
```

### End-to-End Tests
```bash
# Run the application
docker-compose up -d

# Run health checks
curl http://localhost:8000/health
curl http://localhost:3000
```

## 🚀 Deployment

### GitHub Actions

The repository includes GitHub Actions workflows for:
- **CI/CD Pipeline**: Automated testing and building
- **Security Scanning**: Vulnerability scanning with Trivy
- **Dependency Review**: Automated dependency analysis

### Manual Deployment

1. **Build Docker images**
   ```bash
   docker-compose build
   ```

2. **Deploy to your platform**
   - AWS ECS
   - Google Cloud Run
   - Azure Container Instances
   - DigitalOcean App Platform
   - Heroku

### Production Considerations

- Set `DEBUG=false` in production
- Use strong `SECRET_KEY`
- Configure proper database credentials
- Set up SSL/TLS certificates
- Configure proper CORS settings
- Set up monitoring and logging

## 🔒 Security

- **Password Hashing**: bcrypt with salt
- **JWT Authentication**: Secure token-based auth
- **Input Validation**: Pydantic models for request validation
- **CORS Protection**: Configurable cross-origin settings
- **SQL Injection Prevention**: SQLAlchemy ORM with parameterized queries

## 📊 Monitoring

- **Structured Logging**: JSON-formatted logs with correlation IDs
- **Health Checks**: Built-in health check endpoints
- **Error Tracking**: Global exception handling
- **Performance Monitoring**: Request/response timing

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

- **Issues**: Report bugs and feature requests via GitHub Issues
- **Documentation**: API documentation available at `/docs` when running
- **Community**: Join our discussions in GitHub Discussions

## 🙏 Acknowledgments

- **FastAPI**: Modern, fast web framework
- **React**: A JavaScript library for building user interfaces
- **LangChain**: Framework for developing applications with LLMs
- **Material-UI**: React component library
- **OpenAI**: AI language models and APIs

---

**Generated by syed**

*Last updated: 2024-12-19* 
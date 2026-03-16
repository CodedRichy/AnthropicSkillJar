# UIgen

## Overview

UIgen is an AI-powered web application that provides an intelligent code generation and chat interface. Built with Next.js and integrated with Anthropic's Claude AI, it enables users to interact with AI models for code generation, project management, and real-time collaboration through a modern web interface.

## Features

- **AI-Powered Chat Interface**: Real-time conversation with Claude AI models
- **Code Generation**: Intelligent code creation and modification capabilities
- **Project Management**: Create, organize, and switch between multiple projects
- **File System Integration**: Virtual file system for managing project files
- **User Authentication**: Secure JWT-based authentication system
- **Real-time Collaboration**: Live chat with streaming responses
- **Modern UI**: Built with Radix UI components and Tailwind CSS
- **Responsive Design**: Optimized for desktop and mobile devices

## Architecture

The application follows a modern web architecture with clear separation of concerns:

### Main Components
- **Frontend**: Next.js 15 with React 19 and TypeScript
- **Backend**: Next.js API routes with server-side rendering
- **Database**: SQLite with Prisma ORM for data persistence
- **AI Integration**: Anthropic Claude AI via AI SDK
- **Authentication**: JWT-based session management

### Data Flow
1. User interactions flow through React components
2. API routes handle server-side logic and AI communication
3. Prisma manages database operations for users and projects
4. AI responses are streamed back to the client in real-time

### Key Services/Modules
- **Chat Context**: Manages AI conversation state and tool calls
- **File System Context**: Handles virtual file operations
- **Authentication Service**: JWT session management
- **Project Management**: CRUD operations for user projects

## Tech Stack

### Frontend
- **Next.js 15.3.3** - React framework with App Router
- **React 19.0.0** - UI library
- **TypeScript 5** - Type safety
- **Tailwind CSS 4** - Styling framework
- **Radix UI** - Component library
- **Monaco Editor** - Code editing capabilities

### Backend & Database
- **Node.js** - Runtime environment
- **Prisma 6.10.1** - Database ORM
- **SQLite** - Database engine
- **JWT (jose)** - Authentication tokens

### AI & APIs
- **Anthropic Claude AI** - AI model integration
- **AI SDK 4.3.16** - AI abstraction layer
- **Babel Standalone** - Code transformation

### Development Tools
- **ESLint** - Code linting
- **Vitest** - Testing framework
- **Testing Library** - Component testing
- **PostCSS** - CSS processing

## Repository Structure

```
/src
  /app              → Next.js App Router pages and layouts
  /components       → Reusable React components
    /auth          → Authentication components
    /chat          → Chat interface components
    /editor        → Code editor components
    /preview       → Preview components
    /ui            → Base UI components
  /lib              → Utility libraries and configurations
    /contexts      → React contexts for state management
    /prompts       → AI prompt templates
    /tools         → AI tool definitions
    /transform     → Code transformation utilities
  /actions          → Server actions for data operations
  /hooks            → Custom React hooks
/prisma             → Database schema and migrations
```

## Installation

### Prerequisites
- Node.js 18+ 
- npm or yarn package manager

### Setup Instructions

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd AnthropicSkillJar
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   ```bash
   cp .env.example .env
   ```
   Configure the following variables:
   - `ANTHROPIC_API_KEY` - Your Anthropic API key
   - `JWT_SECRET` - Secret for JWT token signing
   - `NODE_ENV` - Environment (development/production)

4. **Set up the database**
   ```bash
   npm run setup
   ```
   This command runs:
   - `npm install`
   - `npx prisma generate` - Generates Prisma client
   - `npx prisma migrate dev` - Runs database migrations

5. **Start the development server**
   ```bash
   npm run dev
   ```

The application will be available at `http://localhost:3000`.

## Usage

### Starting the Application
```bash
# Development mode with hot reload
npm run dev

# Production build
npm run build
npm run start
```

### Key Features
- **Anonymous Mode**: Use the application without authentication
- **User Accounts**: Sign up/sign in for persistent projects
- **Project Management**: Create and switch between multiple projects
- **AI Chat**: Interact with Claude AI for code generation and assistance
- **File Operations**: Create, edit, and manage virtual files within projects

### API Endpoints
- `POST /api/chat` - Handle AI chat requests with tool calling
- Authentication endpoints for user management

## Configuration

### Environment Variables
- `ANTHROPIC_API_KEY` - Required for AI functionality
- `JWT_SECRET` - JWT token secret (defaults to development key)
- `NODE_ENV` - Application environment

### Database Configuration
The application uses SQLite by default with the database file located at `prisma/dev.db`. The Prisma schema defines two main models:
- **User**: Authentication and user management
- **Project**: Project data with messages and metadata

## Development

### Development Commands
```bash
# Start development server with Turbopack
npm run dev

# Start with logging to file
npm run dev:daemon

# Run linting
npm run lint

# Run tests
npm run test
```

### Code Quality
- **ESLint**: Configured with Next.js rules
- **TypeScript**: Strict type checking enabled
- **Prettier**: Code formatting (configured via ESLint)

### Testing
- **Vitest**: Test runner with jsdom environment
- **Testing Library**: Component testing utilities
- Tests are located in `__tests__` directories throughout the codebase

## Testing

```bash
# Run all tests
npm run test

# Run tests in watch mode
npm run test -- --watch

# Run tests with coverage
npm run test -- --coverage
```

The testing setup uses Vitest with React Testing Library for component testing and jsdom for DOM simulation.

## Deployment

### Production Build
```bash
npm run build
npm start
```

### Database Reset
```bash
npm run db:reset
```

### Environment Considerations
- Ensure `ANTHROPIC_API_KEY` is set in production
- Use a secure `JWT_SECRET` in production
- Configure appropriate CORS and security headers
- Set `NODE_ENV=production`

## Roadmap

Based on the codebase analysis, potential future improvements include:

- **Enhanced AI Capabilities**: More sophisticated tool calling and code generation
- **Real-time Collaboration**: Multi-user project editing
- **Expanded File Types**: Support for more file formats and languages
- **Deployment Options**: Docker configuration and cloud deployment guides
- **Advanced Authentication**: OAuth integration and social login
- **Project Templates**: Pre-configured project starters
- **Export/Import**: Project backup and sharing capabilities

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes and commit them: `git commit -m 'Add feature'`
4. Push to the branch: `git push origin feature-name`
5. Open a pull request

### Development Guidelines
- Follow existing code style and patterns
- Add tests for new features
- Update documentation as needed
- Ensure all tests pass before submitting

## License

No license file was found in the repository. Please contact the repository maintainer for licensing information.

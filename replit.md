# Personal Portfolio Website - Prakash Deep

## Overview

This is a personal portfolio website for Prakash Deep, a Civil Engineering student at IIT Mandi. The application is built as a full-stack web application using a modern React frontend with a Node.js/Express backend. The site features sections for home, about, and contact, with a focus on showcasing the student's academic journey, interests, and providing a way for visitors to get in touch.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter (lightweight client-side routing)
- **UI Framework**: Radix UI components with shadcn/ui styling
- **Styling**: Tailwind CSS with custom CSS variables for theming
- **State Management**: TanStack Query (React Query) for server state
- **Build Tool**: Vite with hot module replacement in development

### Backend Architecture
- **Runtime**: Node.js with TypeScript
- **Framework**: Express.js for REST API
- **Database**: PostgreSQL with Drizzle ORM
- **Database Provider**: Neon Database (serverless PostgreSQL)
- **Email Service**: Nodemailer with Gmail SMTP
- **Session Storage**: PostgreSQL-backed sessions using connect-pg-simple

### Project Structure
- `client/` - React frontend application
- `server/` - Express.js backend API
- `shared/` - Shared TypeScript schemas and types
- `migrations/` - Database migration files

## Key Components

### Frontend Components
1. **Navigation**: Sticky header with smooth scrolling navigation
2. **Hero Section**: Main landing area with profile image and call-to-action buttons
3. **About Section**: Academic journey and personal interests showcase
4. **Contact Section**: Contact form with real-time validation
5. **Footer**: Social links and contact information

### Backend Features
1. **Contact API**: `/api/contact` endpoint for form submissions
2. **Email Integration**: Automatic email forwarding to personal email
3. **Data Validation**: Zod schema validation for all inputs
4. **Error Handling**: Centralized error handling middleware
5. **Request Logging**: Detailed API request/response logging

### Database Schema
- **users**: User authentication table (id, username, password)
- **contact_messages**: Contact form submissions (id, name, email, message, created_at)

## Data Flow

1. **Contact Form Submission**:
   - User fills out contact form on frontend
   - Form data validated using Zod schemas
   - POST request sent to `/api/contact` endpoint
   - Backend validates data and stores in database
   - Email sent to personal email address via Nodemailer
   - Success/error response returned to frontend
   - Toast notification displayed to user

2. **Page Navigation**:
   - Client-side routing handles navigation
   - Smooth scrolling implemented for anchor links
   - Mobile-responsive navigation with hamburger menu

## External Dependencies

### Frontend Dependencies
- **UI Components**: Radix UI primitives for accessible components
- **Styling**: Tailwind CSS for utility-first styling
- **Icons**: Lucide React for consistent iconography
- **State Management**: TanStack Query for server state caching
- **Form Handling**: React Hook Form with Zod validation

### Backend Dependencies
- **Database**: Drizzle ORM with PostgreSQL dialect
- **Email**: Nodemailer for SMTP email sending
- **Validation**: Zod for schema validation
- **Database Provider**: Neon Database serverless PostgreSQL

### Development Tools
- **Build System**: Vite for fast development and building
- **TypeScript**: Full type safety across the stack
- **ESBuild**: Fast backend bundling for production

## Deployment Strategy

### Development Environment
- Frontend served by Vite dev server with HMR
- Backend runs with tsx for TypeScript execution
- Database migrations handled by Drizzle Kit
- Environment variables for database and email configuration

### Production Build
- Frontend built to static files using Vite
- Backend bundled using ESBuild for Node.js
- Static files served by Express in production
- Database schema deployed using `drizzle-kit push`

### Environment Configuration
- `DATABASE_URL`: PostgreSQL connection string (required)
- `EMAIL_USER`: Gmail account for sending emails
- `EMAIL_PASS`: Gmail app password for authentication
- `NODE_ENV`: Environment mode (development/production)

### Build Scripts
- `npm run dev`: Start development servers
- `npm run build`: Build for production
- `npm run start`: Start production server
- `npm run db:push`: Deploy database schema changes

The application is designed to be deployed on platforms that support Node.js applications with PostgreSQL databases, such as Railway, Render, or similar cloud platforms. The frontend builds to static files that can be served by the Express backend or deployed separately to a CDN.
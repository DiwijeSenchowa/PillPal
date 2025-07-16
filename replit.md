# PillPal - Medication Reminder App

## Overview

PillPal is a medication management application designed to help users track and manage their medication schedules. It provides features for adding medications, tracking adherence, viewing history, and managing user profiles. The application is built with a modern React frontend and Node.js/Express backend, utilizing PostgreSQL for data persistence.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

The application follows a full-stack architecture with clear separation between client and server components:

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite for fast development and optimized builds
- **UI Framework**: Tailwind CSS with shadcn/ui components
- **State Management**: TanStack Query (React Query) for server state
- **Routing**: Wouter for lightweight client-side routing
- **Forms**: React Hook Form with Zod validation

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **Database**: PostgreSQL with Drizzle ORM
- **Database Provider**: Neon Database (serverless PostgreSQL)
- **Session Management**: PostgreSQL-based sessions with connect-pg-simple

## Key Components

### Database Schema
The application uses three main tables:
- **users**: Stores user profiles and notification preferences
- **medications**: Stores medication information and schedules
- **medicationLogs**: Tracks medication intake status and timing

### API Endpoints
- User management (`/api/user`)
- Medication CRUD operations (`/api/medications`)
- Medication logging (`/api/medication-logs`)
- Daily schedule retrieval (`/api/daily-schedule`)
- Adherence analytics (`/api/adherence-stats`)

### Frontend Pages
- **Home**: Today's medication schedule and adherence overview
- **Add Medication**: Form for adding new medications
- **History**: Medication history and analytics
- **Profile**: User profile and settings management

### UI Components
- **MedicationCard**: Interactive cards for medication tracking
- **Navigation**: Tab-based navigation system
- **NotificationAlert**: Reminder notifications
- Comprehensive shadcn/ui component library

## Data Flow

1. **User Authentication**: Single user system with default user ID
2. **Medication Management**: CRUD operations for medications
3. **Daily Schedule**: Real-time medication schedule generation
4. **Logging System**: Track medication intake with timestamps
5. **Analytics**: Adherence statistics and reporting

## External Dependencies

### Core Dependencies
- **@neondatabase/serverless**: Serverless PostgreSQL client
- **drizzle-orm**: Type-safe ORM for database operations
- **@tanstack/react-query**: Server state management
- **@radix-ui/***: Accessible UI primitives
- **react-hook-form**: Form management
- **zod**: Schema validation

### Development Tools
- **Vite**: Build tool with hot reload
- **TypeScript**: Type safety
- **Tailwind CSS**: Utility-first styling
- **esbuild**: Fast bundling for production

## Deployment Strategy

### Development
- Vite dev server for frontend with hot reload
- Node.js server with file watching via tsx
- Database migrations with Drizzle Kit

### Production Build
- Frontend: Vite build to `dist/public`
- Backend: esbuild bundle to `dist/index.js`
- Database: Push schema changes with `drizzle-kit push`

### Environment Configuration
- `DATABASE_URL` required for PostgreSQL connection
- Supports both development and production modes
- Replit-specific integrations for development environment

### Key Scripts
- `dev`: Development server with hot reload
- `build`: Production build for both frontend and backend
- `start`: Production server
- `db:push`: Database schema deployment

The application is designed for easy deployment on platforms like Replit, with built-in support for development tooling and runtime error handling.
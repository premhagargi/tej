# Appointment Booking App

## Overview

This is a full-stack appointment booking application built for managing business appointments. The app allows customers to view available time slots and book appointments, while providing business administrators with tools to manage and approve/deny booking requests. The application uses React for the frontend, Express.js for the backend, and PostgreSQL with Drizzle ORM for data persistence.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript using Vite as the build tool
- **UI Components**: Shadcn/ui component library built on Radix UI primitives
- **Styling**: Tailwind CSS with CSS variables for theming
- **State Management**: TanStack Query (React Query) for server state management
- **Routing**: Wouter for client-side routing
- **Form Handling**: React Hook Form with Zod validation

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **API Design**: RESTful API with JSON responses
- **Data Storage**: In-memory storage with interface for potential database integration
- **Validation**: Zod schemas for request/response validation
- **Error Handling**: Centralized error handling middleware

### Data Layer
- **ORM**: Drizzle ORM configured for PostgreSQL
- **Schema**: Two main entities - time slots and appointments
- **Storage Interface**: Abstract storage interface allowing for multiple implementations (currently in-memory)
- **Time Slots**: Generated programmatically for business hours (M-F, 9am-5pm, 30-minute intervals)

### Key Features
- **Customer Booking**: View weekly calendar, book available slots with contact information
- **Admin Management**: View all appointments, approve/deny requests, filter by status
- **Real-time Updates**: Automatic refresh of slot availability after booking actions
- **Responsive Design**: Mobile-first approach with responsive calendar layout
- **Toast Notifications**: User feedback for all booking and management actions

### Authentication
- No authentication system implemented - open access for both customer and admin views
- Views are distinguished by UI tabs rather than user roles

### API Endpoints
- `GET /api/slots` - Retrieve all time slots with availability
- `GET /api/appointments` - Get appointments (with optional status filtering)
- `POST /api/appointments` - Create new appointment booking
- `PATCH /api/appointments/:id` - Update appointment status (approve/deny)

### Development Setup
- **Build Tool**: Vite with hot module replacement
- **TypeScript**: Strict mode enabled with path mapping
- **Development Server**: Express server with Vite middleware integration
- **Asset Handling**: Static file serving with proper caching headers

## External Dependencies

### Core Framework Dependencies
- **@neondatabase/serverless** - Neon database driver for PostgreSQL
- **drizzle-orm** - TypeScript ORM for database operations
- **drizzle-kit** - Database schema management and migrations

### UI and Styling
- **@radix-ui/** components - Headless UI primitives for accessibility
- **tailwindcss** - Utility-first CSS framework
- **class-variance-authority** - Utility for creating variant-based component APIs
- **lucide-react** - Icon library

### Frontend Libraries
- **@tanstack/react-query** - Server state management and caching
- **@hookform/resolvers** - Form validation resolvers
- **react-hook-form** - Form state management
- **wouter** - Lightweight client-side router
- **zod** - Schema validation library

### Development Tools
- **vite** - Build tool and development server
- **tsx** - TypeScript execution for Node.js
- **esbuild** - JavaScript bundler for production builds
- **@replit/vite-plugin-runtime-error-modal** - Development error overlay
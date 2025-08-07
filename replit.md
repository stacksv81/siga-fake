# Schedule Management Application

## Overview

This is a full-stack schedule management application built with React and Express.js, designed for creating and managing academic schedules in Portuguese. The application allows users to create subjects with multiple time slots across different days, add them to a schedule grid, and manage conflicts between overlapping classes. It features a modern UI built with shadcn/ui components, uses Drizzle ORM for database operations with PostgreSQL for persistent data storage, and includes PDF generation functionality for exporting schedules.

## Recent Changes (August 2025)

- **Database Migration**: Migrated from in-memory storage to PostgreSQL for persistent data storage
- **PDF Generation**: Added PDF export functionality using jsPDF and html2canvas libraries
- **Multi-Schedule Support**: Enhanced to support subjects with multiple class times across different days
- **Portuguese Interface**: All UI elements and functionality are in Portuguese
- **Conflict Detection**: Improved conflict detection for overlapping time slots across multiple schedules per subject

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript and Vite for fast development and building
- **UI Components**: shadcn/ui component library built on Radix UI primitives for consistent, accessible design
- **Styling**: Tailwind CSS with custom CSS variables for theming and responsive design
- **State Management**: TanStack Query (React Query) for server state management and caching
- **Routing**: Wouter for lightweight client-side routing
- **Forms**: React Hook Form with Zod for form validation and type safety

### Backend Architecture
- **Framework**: Express.js with TypeScript for the REST API server
- **Database ORM**: Drizzle ORM for type-safe database operations and schema management
- **Data Storage**: In-memory storage implementation with interface for easy database switching
- **API Design**: RESTful endpoints for subjects and schedule management with proper error handling
- **Development Setup**: Custom Vite integration for development with HMR support

### Database Schema
- **Subjects Table**: Stores subject information (name, professor, day, time slots, credits)
- **Schedule Entries Table**: Maps subjects to user schedules with foreign key relationships
- **Schema Management**: Drizzle migrations for version-controlled database changes

### Key Features
- **Schedule Grid**: Visual time-slot grid showing daily schedules with drag-and-drop functionality
- **Conflict Detection**: Server-side validation preventing time slot overlaps
- **Subject Management**: CRUD operations for creating and managing subjects
- **Responsive Design**: Mobile-first approach with adaptive layouts
- **Real-time Updates**: Optimistic updates with automatic cache invalidation

### Data Flow
- Frontend makes API requests through a centralized query client
- Server validates requests and checks for scheduling conflicts
- Database operations are abstracted through storage interface
- Real-time UI updates through React Query's caching mechanism

## External Dependencies

### Core Technologies
- **@neondatabase/serverless**: PostgreSQL database connection for serverless environments
- **drizzle-orm**: Type-safe ORM for database operations and schema management
- **@tanstack/react-query**: Server state management and caching solution

### UI Framework
- **@radix-ui/react-***: Comprehensive set of accessible UI primitives (dialog, dropdown, select, etc.)
- **tailwindcss**: Utility-first CSS framework for rapid UI development
- **class-variance-authority**: Type-safe variant API for component styling
- **lucide-react**: Icon library for consistent iconography

### Form Management
- **react-hook-form**: Performant forms library with minimal re-renders
- **@hookform/resolvers**: Validation resolvers for React Hook Form
- **zod**: Schema validation library for type-safe form validation

### Development Tools
- **vite**: Fast build tool and development server
- **typescript**: Static type checking for enhanced developer experience
- **@replit/vite-plugin-***: Replit-specific development enhancements
- **wouter**: Lightweight routing library for React applications

### Utility Libraries
- **date-fns**: Date manipulation and formatting utilities
- **clsx**: Conditional className utility for dynamic styling
- **nanoid**: Unique ID generation for client-side operations
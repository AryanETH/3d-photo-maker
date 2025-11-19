# Photo3D - 2D to 3D Photo Transformation App

## Overview

Photo3D is a web application that transforms 2D photos into stunning 3D experiences using AI-powered depth estimation. Users can upload images and watch as the system processes them to create interactive 3D visualizations with depth maps and displacement effects. The application is built as a full-stack solution with a React frontend and Express backend, designed to handle the complete photo processing workflow from upload to 3D rendering.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **React SPA**: Built with React 18 using functional components and hooks
- **Routing**: Uses Wouter for lightweight client-side routing
- **State Management**: TanStack Query for server state management and caching
- **UI Framework**: Shadcn/ui components built on Radix UI primitives with Tailwind CSS
- **3D Rendering**: Three.js with React Three Fiber for interactive 3D photo viewing
- **Build Tool**: Vite for development and production builds with TypeScript support

### Backend Architecture
- **Express Server**: RESTful API with middleware for file uploads and request logging
- **File Processing**: Multer for handling multipart file uploads with image validation
- **Image Processing**: Sharp library for image metadata extraction and manipulation
- **Storage Strategy**: In-memory storage using Map-based implementation for photo metadata
- **API Design**: RESTful endpoints for photo upload, processing status, and retrieval

### Data Storage Solutions
- **Database**: PostgreSQL configured with Drizzle ORM
- **Schema**: Photos table with fields for original/processed paths, status tracking, and metadata
- **File Storage**: Local filesystem storage in uploads directory
- **Session Management**: PostgreSQL-backed sessions using connect-pg-simple

### Authentication and Authorization
- **Session-based**: Express sessions with PostgreSQL store
- **File Access**: Server-side validation for file access and uploads
- **CORS**: Configured for development and production environments

### Processing Pipeline
- **Upload Flow**: File validation → Storage → Metadata extraction → Database record creation
- **Processing States**: Uploaded → Processing → Completed/Failed status tracking
- **Real-time Updates**: Client polling for processing status using TanStack Query
- **3D Generation**: Depth map creation and displacement mesh generation for Three.js rendering

## External Dependencies

### Core Dependencies
- **@neondatabase/serverless**: PostgreSQL database connection for serverless environments
- **drizzle-orm & drizzle-kit**: Type-safe ORM with schema management and migrations
- **@tanstack/react-query**: Server state management and caching
- **@radix-ui/***: Unstyled, accessible UI component primitives
- **three & @react-three/fiber**: 3D graphics rendering and React integration

### Development and Build Tools
- **TypeScript**: Full type safety across frontend, backend, and shared schemas
- **Vite**: Fast development server and optimized production builds
- **ESBuild**: Backend bundling for production deployment
- **Tailwind CSS**: Utility-first CSS framework with custom design system

### Image Processing
- **multer**: File upload middleware with validation and storage configuration
- **sharp**: High-performance image processing for metadata and transformations

### UI and Styling
- **class-variance-authority**: Type-safe component variant management
- **clsx & tailwind-merge**: Conditional CSS class composition
- **lucide-react**: Consistent icon library throughout the application

The application uses a monorepo structure with shared TypeScript schemas between client and server, ensuring type safety across the full stack. The build process creates optimized bundles for both frontend and backend deployment.
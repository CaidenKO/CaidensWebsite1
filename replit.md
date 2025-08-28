# Overview

This is a full-stack web application built with React and Express.js, featuring a modern UI/UX design system. The application showcases a multi-tab interface with home, about, shop, and contact sections, all rendered as a single-page application. The backend is set up with Express.js and includes database integration using Drizzle ORM with PostgreSQL support.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture

The client is built with **React 18** using TypeScript and follows a component-based architecture:

- **UI Framework**: Uses shadcn/ui component library built on top of Radix UI primitives
- **Styling**: Tailwind CSS with a custom design system featuring CSS variables for theming
- **State Management**: React Query (@tanstack/react-query) for server state management
- **Routing**: Wouter for lightweight client-side routing
- **Build Tool**: Vite for fast development and optimized production builds

The application uses a tab-based navigation system where all content is rendered within a single page, switching between different content sections (Home, About, Shop, Contact) without traditional page navigation.

## Backend Architecture

The server follows a **REST API pattern** built with Express.js:

- **Runtime**: Node.js with ES modules
- **Framework**: Express.js with TypeScript
- **Database Layer**: Drizzle ORM for type-safe database operations
- **Storage Interface**: Abstracted storage pattern with both in-memory and database implementations
- **Development Setup**: Hot module replacement via Vite integration for seamless full-stack development

The backend implements a clean separation between route handlers, storage interfaces, and data models, making it easy to swap between different storage implementations.

## Data Storage Solutions

**Database**: PostgreSQL with Drizzle ORM providing:
- Type-safe database queries and mutations
- Schema migrations management
- Database connection via Neon serverless PostgreSQL
- In-memory fallback storage for development/testing

**Schema Design**: Currently includes a users table with basic authentication fields (id, username, password), designed to be easily extensible for additional entities.

## Authentication and Authorization

The application is structured to support session-based authentication:
- Session storage configured with connect-pg-simple for PostgreSQL-backed sessions
- User model includes username/password fields for basic authentication
- Storage interface provides user lookup and creation methods
- Ready for implementation of login/logout functionality

## External Dependencies

**UI Components**: 
- Radix UI primitives for accessible, unstyled components
- Lucide React for consistent iconography
- React Icons for additional icon sets

**Development Tools**:
- TypeScript for type safety across the full stack
- ESBuild for production server bundling
- Drizzle Kit for database schema management

**Database**: 
- Neon Database (serverless PostgreSQL)
- Connection managed via environment variables

**Styling**:
- Tailwind CSS with PostCSS processing
- Custom CSS variables for theme consistency
- Google Fonts integration (Inter, Architects Daughter, DM Sans, Fira Code, Geist Mono)

The architecture supports both development and production environments with appropriate tooling for each, including hot reloading in development and optimized builds for production deployment.
# FocusFlow - AI-Powered Daily Planner

## Overview

FocusFlow is a full-stack AI-powered daily planner that creates intelligent, location-aware schedules. The application combines natural language processing, optimization algorithms, and mapping capabilities to help users efficiently organize their daily tasks. It features a modern React frontend with a Node.js/Express backend, PostgreSQL database using Drizzle ORM, and includes PWA capabilities for offline usage.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript and Vite for build tooling
- **UI Library**: Shadcn/UI components built on Radix UI primitives
- **Styling**: TailwindCSS with CSS variables for theming and dark mode support
- **State Management**: TanStack Query (React Query) for server state management
- **Routing**: Wouter for lightweight client-side routing
- **PWA Support**: Service worker implementation with offline caching capabilities
- **Maps Integration**: Leaflet.js with OpenStreetMap tiles for location visualization

### Backend Architecture
- **Runtime**: Node.js with Express framework
- **Language**: TypeScript with ES modules
- **Authentication**: Session-based auth with Passport.js using LocalStrategy
- **Password Security**: Scrypt-based hashing with salt
- **Real-time Communication**: WebSocket server for live plan updates
- **API Design**: RESTful endpoints with consistent error handling

### Database & ORM
- **Database**: PostgreSQL with Drizzle ORM
- **Schema Management**: Drizzle Kit for migrations and schema generation
- **Connection**: Neon Database serverless PostgreSQL
- **Session Storage**: PostgreSQL-backed session store using connect-pg-simple
- **Data Validation**: Zod schemas for runtime type validation

### AI & NLP Services
- **Natural Language Processing**: Dual-mode approach with OpenAI GPT-4o integration and local fallback parser
- **Task Parsing**: Extracts structured task data from natural language input
- **Scheduling Optimization**: Custom algorithm using weighted scoring system considering urgency, duration, energy levels, and user priorities
- **Energy Windows**: Time-based energy level matching (high: 9-12, medium: 12-15, low: 15-18)

### Location Services
- **Geocoding**: Optional Nominatim API integration with local caching to respect rate limits
- **Maps**: Leaflet.js integration for task location visualization and route planning
- **Privacy**: Location services only enabled via environment variable flag

### Authentication & Security
- **Session Management**: Express-session with PostgreSQL store
- **Password Hashing**: Crypto.scrypt with timing-safe comparison
- **CSRF Protection**: Built into session configuration
- **Environment Variables**: Secure configuration for API keys and database credentials

### Real-time Features
- **WebSocket Connection**: Bidirectional communication for live plan updates
- **Auto-recomputing**: Automatic schedule recalculation when tasks change
- **Connection Management**: Automatic reconnection and error handling

### Development & Build Pipeline
- **Development**: Vite dev server with HMR and Express API proxy
- **Production Build**: Static React build served through Express
- **Type Safety**: Shared TypeScript schemas between frontend and backend
- **Code Quality**: ESBuild for server bundling, PostCSS for style processing

## External Dependencies

### Core Infrastructure
- **Database**: Neon Database (PostgreSQL serverless)
- **Maps**: OpenStreetMap tiles via Leaflet.js
- **Fonts**: Google Fonts (Inter font family)

### Optional Services
- **AI Processing**: OpenAI API (GPT-4o) for advanced natural language parsing
- **Geocoding**: Nominatim API for location coordinate resolution

### Development Tools
- **Package Management**: npm with package-lock.json
- **Build Tools**: Vite, ESBuild, PostCSS, TailwindCSS
- **Replit Integration**: Vite plugins for Replit-specific features and error handling

### UI Components
- **Component Library**: Radix UI primitives for accessible components
- **Icons**: Lucide React for consistent iconography
- **Charts**: Recharts for data visualization in analytics dashboard
- **Form Handling**: React Hook Form with Zod validation
- **Date Handling**: date-fns for date manipulation and formatting

### Utilities
- **Styling**: clsx and tailwind-merge for conditional CSS classes
- **Validation**: Zod for schema validation and type generation
- **UUID Generation**: nanoid for unique identifiers
- **WebSocket**: ws library for real-time communication
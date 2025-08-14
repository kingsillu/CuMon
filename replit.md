# The Curious Teens Blog

## Overview

The Curious Teens is a blog application that displays posts from a Medium RSS feed. It's built as a full-stack web application featuring a React frontend with TypeScript, an Express.js backend, and utilizes shadcn/ui components for the interface. The application fetches and displays blog posts from Medium through an RSS proxy endpoint to handle CORS restrictions.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript using Vite as the build tool
- **UI Library**: shadcn/ui components built on Radix UI primitives
- **Styling**: Tailwind CSS with custom CSS variables for theming
- **State Management**: TanStack Query (React Query) for server state management
- **Routing**: Wouter for client-side routing (lightweight React router alternative)
- **Build System**: Vite with hot module replacement and development server

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **Runtime**: Node.js with ES modules
- **API Design**: RESTful API with a single RSS proxy endpoint
- **Development**: tsx for TypeScript execution in development
- **Production Build**: esbuild for server bundling

### Data Layer
- **Database ORM**: Drizzle ORM configured for PostgreSQL
- **Database Provider**: Neon Database (serverless PostgreSQL)
- **Schema Management**: Drizzle Kit for migrations and schema management
- **Connection**: Environment-based database URL configuration

### External Dependencies

#### RSS Feed Integration
- **Medium RSS Feed**: Fetches content from `https://medium.com/@thecuriousteens/feed`
- **CORS Proxy**: Uses `api.rss2json.com` service to bypass CORS restrictions
- **Data Validation**: Zod schemas for RSS response validation and type safety

#### UI and Styling
- **Component System**: Complete shadcn/ui component library with Radix UI primitives
- **Typography**: Google Fonts (Inter and Charter) for modern, readable text
- **Icons**: Lucide React icon library
- **Responsive Design**: Mobile-first approach with Tailwind CSS breakpoints

#### Development Tools
- **Replit Integration**: Custom Vite plugins for Replit development environment
- **Error Handling**: Runtime error overlay for development debugging
- **Code Quality**: TypeScript strict mode with comprehensive type checking

#### Session Management
- **Session Storage**: PostgreSQL-based sessions using connect-pg-simple
- **User Storage**: In-memory storage implementation with interface for future database integration

The application follows a clean separation of concerns with shared TypeScript schemas between client and server, ensuring type safety across the full stack. 

### Recent Changes (August 4, 2025)

#### Static Deployment Configuration
- **Netlify Deployment**: Modified application to support static hosting without backend server dependency
- **Direct RSS Fetching**: Updated frontend to fetch RSS data directly from RSS2JSON API instead of proxy server
- **Build Configuration**: Added netlify.toml with proper build settings and SPA redirect rules
- **Static Assets**: Built application generates optimized static files in `/dist` with proper asset references

#### UI Layout Updates
- **Header Follow Button**: Moved Medium follow button from sidebar to main header area
- **Three-Column Layout**: "Stay Curious" section moved to left sidebar, main content center, "About" and "Recent Posts" on right
- **Typography**: Added bold "About The Curious Teens" heading with serif font styling
- **Clean Design**: Removed gradient backgrounds in favor of clean white cards with borders

The RSS proxy architecture has been adapted for static deployment while maintaining the same user experience and data flow from Medium to the interface.
# replit.md

## Overview

This is a full-stack web application for an AI-powered real estate lead generation and appointment scheduling service. The platform showcases AI agents that can make calls, qualify leads, and book appointments for real estate professionals. The application features a modern, animated landing page with comparison tables, process explanations, and premium visual effects including WebGL shader animations.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter (lightweight React router alternative)
- **State Management**: TanStack React Query for server state
- **Styling**: Tailwind CSS with CSS variables for theming
- **UI Components**: shadcn/ui component library (Radix UI primitives)
- **Animations**: Framer Motion for page transitions and micro-interactions
- **3D Graphics**: Three.js for WebGL shader animations as visual backgrounds

The frontend follows a component-based architecture with:
- Pages in `client/src/pages/`
- Reusable UI components in `client/src/components/ui/`
- Custom hooks in `client/src/hooks/`
- Utility functions in `client/src/lib/`

### Backend Architecture
- **Runtime**: Node.js with TypeScript
- **Framework**: Express.js
- **Build Tool**: Vite for frontend, esbuild for server bundling
- **Development**: Hot module replacement via Vite middleware

The server uses a simple structure:
- `server/index.ts` - Main entry point and middleware setup
- `server/routes.ts` - API route registration
- `server/storage.ts` - Data access layer with interface abstraction
- `server/vite.ts` - Development server with Vite integration
- `server/static.ts` - Production static file serving

### Data Storage
- **ORM**: Drizzle ORM with PostgreSQL dialect
- **Schema**: Defined in `shared/schema.ts` using Drizzle's type-safe schema builder
- **Validation**: Zod schemas auto-generated from Drizzle schemas via drizzle-zod
- **Current Storage**: In-memory storage implementation (`MemStorage` class) for development
- **Production Ready**: PostgreSQL configuration in `drizzle.config.ts`

### Build System
- **Frontend Build**: Vite with React plugin, outputs to `dist/public`
- **Server Build**: esbuild bundling with selective dependency externalization
- **TypeScript**: Shared configuration across client, server, and shared code

## External Dependencies

### Database
- **PostgreSQL**: Primary database (requires `DATABASE_URL` environment variable)
- **Drizzle Kit**: Database migrations and schema push (`npm run db:push`)

### UI Framework Dependencies
- **Radix UI**: Full suite of accessible primitives (dialog, dropdown, tabs, etc.)
- **shadcn/ui**: Component styling patterns configured in `components.json`
- **Embla Carousel**: For carousel/slider components
- **react-day-picker**: Calendar component
- **vaul**: Drawer component
- **cmdk**: Command palette component

### Animation & Graphics
- **Framer Motion**: React animation library
- **Three.js**: WebGL 3D graphics for shader effects
- **react-use-measure**: For measuring DOM elements in animations

### Form & Validation
- **React Hook Form**: Form state management
- **@hookform/resolvers**: Zod resolver for form validation
- **Zod**: Schema validation library

### Development Tools
- **Replit Plugins**: Runtime error overlay, cartographer, dev banner (development only)
- **PostCSS/Autoprefixer**: CSS processing for Tailwind
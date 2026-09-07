# Math Reasoning Annotation Tool

## Project Overview

An application for reviewing AI-generated math solutions, identifying the first reasoning error, and guiding a model through successive revisions. It makes the human feedback process explicit: error classification, targeted guidance, revised answers and a stored annotation history.

The project explores the design of a human annotation workflow. It records individual revisions and interventions; it does not establish a measured improvement in model performance.

## Functionality

This prototype demonstrates the following workflow:

- **Problem Library**: A collection of sample math problems across various categories (Algebra, Calculus, Geometry, Probability) with different difficulty levels
- **AI Solution Generation**: Integration with Claude to generate step-by-step solutions to math problems
- **Error Identification**: Interface for annotators to identify and classify specific errors in the AI's reasoning
- **Guided Feedback**: Structured protocol for providing increasingly detailed guidance across multiple iterations
- **Solution Revision**: Demonstration of how AI can revise solutions based on human feedback
- **Annotation Tracking**: Recording the full annotation history including all interventions and outcomes

## Annotation Workflow

1. **Guide Page**: Start by reviewing the annotation guidelines and process
2. **Problem Selection**: The system automatically selects an unannotated math problem
3. **Initial Review**: Examine the AI-generated solution and identify the first error in reasoning
4. **Error Classification**: Select the type of error (e.g., calculation error, conceptual misunderstanding)
5. **Guidance Provision**: Provide appropriate guidance without revealing the complete solution
6. **Solution Revision**: Review the AI's revised solution based on your guidance
7. **Iteration**: If errors persist, provide additional guidance with increasing specificity
8. **Completion**: Mark the solution as correct once all errors have been addressed

## Technical Implementation

### Frontend
- React with TypeScript for component-based UI
- Vite for fast development and building
- TailwindCSS and shadcn/ui for responsive design
- React Query for efficient data fetching and state management

### Backend
- Express.js with TypeScript for API endpoints
- Supabase for database storage and management
- Anthropic's Claude API for generating and revising solutions

### Data Flow
1. Problems are stored in Supabase database
2. When a problem is selected, Claude generates an initial solution
3. Annotator feedback is recorded and sent to Claude for solution revision
4. Complete annotation history is stored for future analysis

## Project status and local setup

Built in March–April 2025. The repository preserves the annotation interface, revision loop and database setup scripts from that implementation.

For local exploration, install frontend dependencies with `npm ci` and server dependencies with `npm ci --prefix server`. Configure the server using [server/.env.example](server/.env.example), then review the schema and seed scripts in `server/src/scripts/`. The root `npm run dev` command starts both development processes.

Review the frontend/server port configuration, model IDs, dependency versions and database access rules before connecting current services. The published source has not been revalidated end to end against today's APIs.

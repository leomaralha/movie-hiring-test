# Hiring Test: Cinema Ticket Selling Platform

## Objective
Build a simple fullstack application that allows users to browse movies, select showtimes, and purchase tickets. The system should manage simultaneous purchase requests using an in-memory queue to ensure no overbooking occurs.

## Tech Stack
- **Backend:** NestJS
- **Frontend:** React
- **Database:** TypeORM (with a relational database of your choice)
- **Queue:** In-memory queue (e.g., using NestJS’ built-in capabilities or custom implementation)

## Requirements

### 1. Backend Requirements
#### API Design
- **Movies Endpoint:**
  - Populate a movie catalog initially by consuming the [The Movie Database (TMDb) API](https://developers.themoviedb.org/3).
  - Store movie details in the database.
  - Provide endpoints to list available movies, search by title, and filter by genre.
- **Showtimes Endpoint:**
  - Allow CRUD operations for managing showtimes linked to movies.
- **Ticket Purchase Endpoint:**
  - Implement an endpoint to initiate a ticket purchase. This should:
    - Receive movie ID, showtime ID, and the number of tickets.
    - Utilize an in-memory queue to handle simultaneous requests and prevent overselling.
    - If the purchase is successful, decrement the available seats for the showtime.
    - Respond with success or failure, depending on seat availability.

#### Database Design
- Use TypeORM for managing database entities.
- Design tables for `Movies`, `Showtimes`, and `Tickets`.
- Establish relationships between entities (e.g., a movie can have multiple showtimes, a showtime can have multiple tickets).

#### Queue System
- Implement an in-memory queue to handle purchase requests.
- Ensure that no two requests for the same showtime are processed simultaneously.

### 2. Frontend Requirements
#### User Interface
- Use React to build a simple and intuitive UI.
- **Movie List Page:**
  - Display a list of movies retrieved from the backend.
  - Include functionality to search and filter movies.
- **Showtimes Page:**
  - Display available showtimes for a selected movie.
- **Ticket Purchase Page:**
  - Allow users to select the number of tickets for a specific showtime and initiate a purchase.
  - Display feedback based on the result of the purchase (success or failure).

#### State Management
- Use React's built-in state management (e.g., `useState`, `useEffect`) or any state management library of your choice (e.g., Redux) to handle the application state.

### 3. General Requirements
#### Code Quality
- Write clean, maintainable, and well-documented code.
- Use TypeScript across both backend and frontend for type safety.
- Include basic error handling for all API interactions.

#### Testing
- Write unit tests for critical parts of the backend (e.g., queue management, API endpoints).
- Optional: Write frontend tests using a testing library like Jest or React Testing Library.

#### Version Control
- Provide a GitHub repository link with your project.
- Include a well-structured commit history that reflects the development process.

## Submission Guidelines
- Submit your completed project as a GitHub repository link.
- Include a `README.md` file with instructions on how to set up and run the project locally.
- Your `README.md` should also include any assumptions made, limitations, or areas where you'd like to improve the project given more time.

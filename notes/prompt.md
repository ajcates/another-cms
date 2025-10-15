
You are a senior full-stack developer specializing in Node.js and modern web applications. Your task is to plan and create the foundational backend code for a personal portfolio and blog site.

### Project Overview
The backend will be a Koa.js application that serves a vanilla JavaScript single-page application (SPA), handles user authentication for a CMS, and manages content stored in flat files.

### Technical Specifications
- **Backend Framework:** Koa.js
- **Database:** TrivialDB
- **Authentication:** JSON Web Tokens (JWT)
- **Frontend Styling:** [Material Enlightenment](https://github.com/ajcates/material-enlightenment-css) CSS framework
- **Content Storage:** Markdown flat files located in a `/content` directory. The database will store metadata and paths to these files.

### Required Project Structure
Please create the following directory structure:
/
├── content/
│   ├── pages/
│   ├── posts/
│   └── portfolio/
├── public/
│   ├── css/
│   ├── js/
│   └── index.html
├── src/
│   ├── db/
│   ├── routes/
│   └── app.js
└── package.json

### Detailed Plan of Action

**1. Initial Setup:**
- Create the complete project directory structure as specified above.
- Initialize a `package.json` file.
- Install the following dependencies: `koa`, `koa-router`, `koa-bodyparser`, `koa-static`, `trivialdb`, `bcryptjs` (for password hashing), `jsonwebtoken`, and `koa-jwt` (for protecting routes).

**2. Database and Content:**
- In `/src/db/`, set up the TrivialDB instance.
- Define TrivialDB collections for `users`, `posts`, `pages`, and `portfolio`.
- The `users` collection should store objects with a `username` and a hashed `password`.
- Create one placeholder `.md` file in each of the subdirectories inside `/content`.

**3. Frontend Placeholder (`/public/index.html`):**
- Create a basic HTML5 boilerplate in `index.html`.
- Include a `<link>` tag to the Material Enlightenment CSS framework stylesheet. You can use a CDN link for now or plan for a local copy in `/public/css/`.

**4. Backend Server (`/src/app.js`):**
- Set up the main Koa.js server.
- Configure the `koa-static` middleware to serve static files from the `/public` directory.
- Integrate the body parser and router middleware.

**5. Authentication Routes (`/src/routes/auth.js`):**
- Create a new Koa router for authentication.
- Implement a `POST /api/login` route. It should:
    - Find the user in the `users` collection.
    - Compare the provided password with the stored hash using `bcryptjs`.
    - If valid, create and sign a JWT containing the user's ID or username, and return it.
- Implement a `POST /api/register` route as a way to add a user to the database with a properly hashed password.

**6. Protected Routes and SPA Fallback:**
- In your main router file, use the `koa-jwt` middleware to protect a sample API route, such as `GET /api/dashboard`. This route should only be accessible with a valid JWT.
- Implement a final catch-all route (`*`) that serves the `public/index.html` file. This is critical for allowing the frontend vanilla JS router to handle all page navigation.

Please provide the complete code for all the files and steps outlined in this plan. Ensure all code is modular and well-commented, especially the JWT implementation, TrivialDB setup, and the password hashing logic.



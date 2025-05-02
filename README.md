# Container Info App

This is a simple Node.js application that displays the hostname of the container it is running in. It uses Express.js to serve a static HTML page and provides an API endpoint to fetch the container's hostname.

## Features

- Serves a static HTML page (`index.html`) with a simple UI.
- Dynamically fetches and displays the hostname of the container serving the page.
- Uses a REST API endpoint (`/hostname`) to retrieve the hostname.

## How It Works

1. The `index.html` file:
   - Contains a script that fetches the hostname from the `/hostname` API endpoint when the page loads.
   - Dynamically updates the page to display the hostname in the `<div>` with the ID `hostname`.

2. The `server.js` file:
   - Sets up an Express.js server.
   - Serves static files (like `style.css`) from the `public/` directory.
   - Serves the main HTML page (`views/index.html`) at the root URL (`/`).
   - Provides an API endpoint (`/hostname`) that returns the container's hostname.

3. The `Dockerfile`:
   - Builds a lightweight container using the Node.js 18 Alpine image.
   - Installs dependencies and runs the application.

## Project Structure




## Running the Application

### Locally

1. Install [Node.js](https://nodejs.org/) if not already installed.
2. Run the following commands in the project directory:
   ```bash
   npm install express
   node server.js

### Using Docker

1.Build the Docker image:
  ```bash
  docker build -t container-info-app .
2.Run the container:
  ```bash
  docker run -p 5000:5000 container-info-app
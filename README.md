# Express.js JSON Body Parsing Issue

This repository demonstrates a common issue encountered when working with JSON request bodies in Express.js applications.  The problem revolves around the seemingly correct usage of `express.json()` middleware, yet the request body remains empty.

## Bug Description

The provided `bug.js` file contains an Express.js application that attempts to parse a JSON payload sent via a POST request to the `/user` endpoint.  Despite including `app.use(express.json())`, the `req.body` object remains empty. This leads to unexpected behavior and application errors.

## Solution

The solution, found in `bugSolution.js`, addresses this problem by explicitly ensuring that the `express.json()` middleware is placed **before** any route handlers that expect a JSON body. The order of middleware is crucial for proper execution.

## How to reproduce

1. Clone this repository.
2. Navigate to the project directory.
3. Run `node bug.js`.
4. Send a POST request to `http://localhost:3000/user` with a JSON payload (e.g., using Postman or curl).
5. Observe that the server logs an empty `req.body`.
6. Repeat steps 2-5 using `bugSolution.js` to see the corrected behavior.

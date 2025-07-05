Steps to Create and Containerize a Node.js API using Docker

    1. Create a project folder, e.g: 02-API-based-containerization.
    
    2. Convert that folder into a Node.js project:
        - Open the terminal inside the project folder.

        - Initialize a Node.js project by running:
                npm init -y
        - This creates a basic package.json file to manage your project dependencies.
    
    3. Install Express framework:
        - In the terminal, run:
                npm install express --save
        - This adds Express to your project and updates the package.json and package-lock.json files.
    
    4. Create a file named index.js inside the project folder.
        - This file will contain your API code.
    
        - Your folder structure should look like this:
                02-API-based-containerization/
                    ├── node_modules/
                    ├── index.js
                    ├── package-lock.json
                    └── package.json

    
    5. Write the following code in index.js:
        - This sets up a simple Express API that returns a JSON response.

                const express = require('express');
                const app = express();
                const port = 3000;

                app.get('/', (req, res) => {
                res.json([
                    {
                    name: 'Mary Jane',
                    email: 'maryjane@gmail.com'
                    }
                ]);
                });

                app.listen(port, () => {
                console.log(`Example app listening on port ${port}`);
                });


    6. Create a Dockerfile (case sensitive) inside the project folder.
            - This file will contain instructions for Docker to build your image.
    
    7. Write the following content in the Dockerfile:
            FROM node:latest
            WORKDIR /app
            COPY . .
            RUN npm install
            CMD ["node", "index.js"]

    8. Open your terminal/PowerShell in the project folder.(if not already).
        - Make sure you are in the folder that contains your code and Dockerfile.
    
    9. Build the Docker image with a name and tag:
            docker build --tag api-based-image:v1 .
    
    10. Run a Docker container from the image:
            docker run --name api-based-container -d -p 3000:3000 my-api-app:v1
        - This starts a container from your image, running the API and making it accessible on port 3000.

    12. Open your browser and visit: http://localhost:3000 
        - You should see the JSON response from your API.

🎉 Congratulations! You’ve created, containerized, and run a Node.js API inside Docker.

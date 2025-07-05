Steps to Host a Static Website using Docker and NGINX
    
    1. Create a project folder, e.g., static-website.

    2. Download a free sample website template from a trusted source.
            Example: https://templatemo.com/

    3.Extract the downloaded template and save it inside your project folder.
      Your folder structure should look like this:
            static-website/
                └── static-website-template/
                ├── index.html
                └── (other files and folders)
    
    4. Open your project folder in a text editor (e.g., VS Code).

    5. Create a new file named Dockerfile (case sensitive).

    6. Write your Dockerfile with the following content: 
            FROM nginx:latest
            COPY static-website-template/ /usr/share/nginx/html

    7. Open your terminal/PowerShell in the project folder.

    8. Build the Docker image with the command:
            docker build --tag static-website-image:v1 . 

    9. Run a Docker container from the image:
            docker run --name static-website-container -d -p 8050:80 static-website-image:v1 

    10. Open your browser and visit: http://localhost:8050 to see your static website running.
    
🎉 Congratulations! You have successfully hosted a static website locally using Docker and NGINX.

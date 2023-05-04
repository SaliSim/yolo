#RUNNING A DOCKER COMPOSE
 follow the steps on the README.md.
 start by updating the react scripts.
 start updating on client side 

npm uninstall react-scripts
npm install react-scripts

#steps to follow
get to client side
# Steps
1. Client side
    * Start by creating a Dockerfile 
        ```
        cd client/
        touch Dockerfile
        ```
    * Pick the best base image use on the dockerfile
    * Build the image
        ```
        sudo docker build . -t <dockerhubUsername\imageName:tag>

        ```
     * Push to Docker Hub
        ```
        sudo docker login
        sudo docker push <dockerhubUsername\imageName:tag>
        ```
2. Backend side
    * Create a Dockerfile 
        ```
        cd backend/
        touch Dockerfile
        ```
    * Similarly,pick the best base image to use on the dockerfile
    * Build the image
        ```
        sudo docker build . -t <dockerhubUsername\imageName:tag>

        ```
     * Push to Docker Hub
        ```
        sudo docker login
        sudo docker push <dockerhubUsername\imageName:tag>
        ```
  ---
  > We build an image and push to dockerhub so that upon running the docker compose the image is pulled.
  
3. Docker Compose
  We have 3 services running
    * Database
        1. Pulls an image from Docker Hub
        1. Has Volumes able to persist data when we remove our containers.
    * Client
    * Backend
   > Client communicates to the backend , backend communicates to the database and vice versa

       ```
       sudo docker compose up
If you clone this repo and run the above command, a link to the website will allow you to view and add products which should persist.
   
   
   

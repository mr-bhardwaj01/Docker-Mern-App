#Verify Docker 
![Screenshot 2025-04-23 150359](https://github.com/user-attachments/assets/c6465f49-df20-44df-886d-99601c3c93b3)



# A simple MERN stack application 

### Create a network for the docker containers

`docker network create demo`

![image](https://github.com/user-attachments/assets/50e3aaba-afb4-490d-89bb-a297f5a400dd)



### Build the client 

```sh
cd mern/frontend
docker build -t mern-frontend .
```

![Screenshot 2025-04-23 150415](https://github.com/user-attachments/assets/5a7f5d98-f00c-4330-9df9-ad880b3806c1)


### Run the client

`docker run --name=frontend --network=demo -d -p 5173:5173 mern-frontend`

### Verify the client is running

Open your browser and type `http://localhost:5173`

![image](https://github.com/user-attachments/assets/a1d6074a-6c42-477e-a2f3-d66dd6ad557e)


### Run the mongodb container

`docker run --network=demo --name mongodb -d -p 27017:27017 -v ~/opt/data:/data/db mongodb:latest`

![Screenshot 2025-04-23 151121](https://github.com/user-attachments/assets/c8973454-f0ef-4404-9cf2-6fa7497ae728)


### Build the server

```sh
cd mern/backend
docker build -t mern-backend .
```
![image](https://github.com/user-attachments/assets/38f8c0dd-1945-4fa4-9b57-0ae8e439e5b1)

### Run the server

`docker run --name=backend --network=demo -d -p 5050:5050 mern-backend`

![image](https://github.com/user-attachments/assets/f5681a92-e6c2-490e-a956-9a3456ada749)


## Using Docker Compose

`docker compose up -d`

![image](https://github.com/user-attachments/assets/f3c48f2d-6bbc-483f-8ad0-dd441f2e2573)

![image](https://github.com/user-attachments/assets/8c7be9cb-5043-41ea-a8b0-95782efa94fa)


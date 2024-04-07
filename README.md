# Fit Market Dashboard Front-End Application with NextJS
This is a guide to run the application in development mode. It's recommended to run the application in a containerized manner with **Docker**. This guideline will focus on running the app in a container. Most of the terminal commands are specific to **Linux** operating system. You can interpret those on another OS as well. The application is recommended to run on **Node v20.11.1**.

## Prerequisites
- Install **Docker Engine** ([Installation Guide](https://docs.docker.com/engine/install)) and **Docker Compose** ([Installation Guide](https://docs.docker.com/compose/install)) on your machine
- Install **Git** ([Installation Guide](https://git-scm.com/downloads))
## Getting Started
- Clone the repository from [here](https://github.com/scarecrow-11/fit-market-dashboard-frontend). You can run the following command
	```
	$ git clone https://github.com/scarecrow-11/fit-market-dashboard-frontend.git
	```
- Go to the project root folder named **/fit-market-dashboard-frontend** with the following command
	```
	$ cd ./fit-market-dashboard-frontend
	```
- Create a **docker-compose.yaml** file in the root folder. An example docker compose file is given below
	```
	version: '3.9'
	
	services:
		fmd-frontend:
			build:
				context: .
				dockerfile: Dockerfile
			restart: always
			environment:
				PORT: 3000
				API_BASE_URL: http://localhost:4000
			ports:
				- '3000:3000'
			volumes:
				- ./src:/app/src
	```
- Run the following command to spin up the containers
	```
	$ docker compose up
	```
## Usage
- Access the **NextJS** App on **[http://localhost:3000](http://localhost:3000)**
## Additional Information
- **NextJS** Documentation [here](https://nextjs.org/docs)
- **Docker** Documentation [here](https://docs.docker.com)

# United Airlines Oversale Simulation

This repository contains the code and documentation for the United Airlines Oversale Simulation project. This project was created by Group 5 for the ITWS Capstone class in Fall 2020 at Rensselaer Polytechnic Institute. Nothing outside of these files are required to run the project.   

## Folders

Each folder inside of this repo contains the files for one of the services for the project. They are as follows.
 - united-ui: React App used to render simulation information
 - gateway-service: Python app used to handle and proxy API requests
 - analytics-engine: Service used to run oversale simulations

There are also some files at the root of this directory, including the docker compose configuration for production deployments, as well as sample objects from the MongoDB collections, in order to help configure the product. 

## Development

Each service in this repository can run in its own shell, without having to build anything. Alternatively, running the docker-compose configuration with all of the images can work if you would like to only develop a single service. Each repository has a configuration file with variables that need to be set prior to running the application.

## Production
Each folder contains a readme that explains how to build the containers for each of the applications. Once they are built, you will simply need to run:
`docker-compose up -d`
to run the application in headless mode

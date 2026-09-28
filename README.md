# 📊 AI Sentiment Analysis Gateway

## Overview
A microservices-based application that analyzes the sentiment of customer reviews. It features a main backend API to handle client requests, a dedicated Python microservice to process the AI inference, and a relational database to store the results. 

This project demonstrates the ability to architect a polyglot system, integrate machine learning models into a web workflow, and manage the infrastructure using container orchestration.

## Tech Stack
*   **Gateway Backend:** Java, Spring Boot, Spring Data JPA
*   **AI Microservice:** Python, FastAPI, Hugging Face Transformers (or scikit-learn)
*   **Database:** PostgreSQL
*   **Infrastructure:** Docker, Docker Compose

## System Architecture
1.  A user submits a text review via a `POST` request to the Spring Boot API.
2.  The Spring Boot API saves the raw review to PostgreSQL with a "PENDING" status.
3.  The Spring Boot API makes a synchronous REST call to the Python FastAPI microservice.
4.  The Python service analyzes the text and returns a sentiment score (Positive, Neutral, Negative).
5.  The Spring Boot API updates the database record with the result and returns the final JSON to the user.

## Development Tasks (To-Do)
- [ ] Initialize a Spring Boot project and configure the PostgreSQL connection.
- [ ] Create the `Review` entity and JPA Repository.
- [ ] Write the Python FastAPI service with a simple sentiment analysis pipeline.
- [ ] Create a `Dockerfile` for the Spring Boot app.
- [ ] Create a `Dockerfile` for the Python app.
- [ ] Write a `docker-compose.yml` that networks the Spring Boot app, Python app, and a PostgreSQL image together.

## Getting Started
To spin up the entire local development stack (perfect for testing inside a WSL Ubuntu terminal):
`docker-compose up --build`

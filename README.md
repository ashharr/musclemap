# MuscleMap
*** 

## NOTE: This project is a work in progress. Contributions are welcome.

**MuscleMap** is a comprehensive fitness app designed to help you discover and track exercises targeting every muscle group. Whether you're a beginner or a pro, MuscleMap provides detailed workout options with varying difficulty levels to meet your fitness goals.

## Features

- Explore exercises for every muscle group
- Filter exercises by difficulty
- Detailed exercise information and instructions
- Built with Spring Boot (backend) and React (frontend)

## Getting Started

### Prerequisites

- Java 11 or later
- Node.js (v14 or later)
- MongoDB
- Maven

### Backend Setup

1. Clone the repository:
    ```bash
    git clone https://github.com/ashharr/musclemap.git
    cd musclemap/backend
    ```

2. Build and run the Spring Boot application:
    ```bash
    mvn clean install
    mvn spring-boot:run
    ```

3. Configure your MongoDB connection in `src/main/resources/application.properties`.

### Frontend Setup

1. Navigate to the frontend directory:
    ```bash
    cd ../frontend
    ```

2. Install dependencies:
    ```bash
    npm install
    ```

3. Start the React development server:
    ```bash
    npm start
    ```

4. Open your browser and go to `http://localhost:3000` to view the app.

## Documentation

- [API Documentation](backend/docs/ApiDesign.md)
- [Design & Architecture](backend/docs/architecture-diagrams/musclemap-er-diagram.png)

## Contributing

We welcome contributions to the MuscleMap project! Please follow the [contributing guidelines](README.md) for submitting pull requests and issues.

## Contact

For questions or feedback, please reach out to [your-email@example.com](mailto:your-email@example.com).


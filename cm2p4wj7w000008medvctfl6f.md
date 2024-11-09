---
title: "Project: Dynamic Three-Tier Voting Application"
datePublished: Fri Oct 25 2024 19:37:45 GMT+0000 (Coordinated Universal Time)
cuid: cm2p4wj7w000008medvctfl6f
slug: project-dynamic-three-tier-voting-application
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1729885145737/16b168f2-90c5-4539-8ff0-cecb1bba6111.jpeg
tags: frontend, backend, database, three-tier-application

---

## Overview

This project presents a dynamic three-tier voting application designed to capture the festive spirit of Kolkata during Sharodiya. The application enables users to participate in a voting system celebrating the local culture and festivities, focusing on the various pandals (temporary structures) built for the Durga Puja festival. Leveraging a robust tech stack—including Python, Node.js, .NET, Redis, and PostgreSQL—this app aims to deliver a seamless and efficient user experience.

## Goals

1. **Develop a Voting Application**: Enable users to cast votes for their favorite pandals during the Durga Puja festival.
    
2. **Implement a Three-Tier Architecture**: Structure the application to enhance scalability, maintainability, and performance.
    
3. **Utilize Modern Technologies**: Employ Python and Node.js for backend services, .NET for additional functionalities, Redis for caching, and PostgreSQL for persistent storage.
    
4. **Streamline Development with Docker**: Use Docker Compose to manage a multi-container architecture for easy deployment and orchestration.
    
5. **User Engagement**: Create a visually appealing and interactive frontend that encourages participation.
    

## Architecture Overview

The application is structured into three primary layers:

* **Frontend**: A responsive web interface that allows users to cast votes, view results, and interact with the application.
    
* **Backend**:
    
    * **Python Service**: Handles vote processing, business logic, and data interaction.
        
    * **Node.js Service**: Manages real-time updates, websocket connections, and user interactions.
        
    * **.NET Service**: Provides additional functionalities, such as user authentication and authorization.
        
* **Database**:
    
    * **PostgreSQL**: Serves as the primary database for persistent data storage, handling user data and vote records.
        
    * **Redis**: Acts as an in-memory cache to improve performance by storing frequently accessed data.
        

### Architecture Diagram

```typescript
plaintextCopy code[Frontend] <---> [Node.js Service] <---> [Python Service] <---> [PostgreSQL]
                           |
                           +--> [Redis]
```

## Steps to Build the Application

### Step 1: Set Up the Development Environment

1. **Clone the Repository**:
    
    ```typescript
    bashCopy codegit clone https://github.com/your-username/voting-application.git
    cd voting-application
    ```
    
2. **Install Prerequisites**: Ensure that you have the following installed on your machine:
    
    * [Docker](https://www.docker.com/)
        
    * Docker Compose
        
    * Programming languages: Python, Node.js, .NET Core SDK
        

### Step 2: Backend Development

#### Python Service

* **Create a Flask Application**:
    
    * Set up the basic Flask application to handle votes.
        
    * Define routes for voting and retrieving results.
        

```typescript
pythonCopy codefrom flask import Flask, request, jsonify
from flask_sqlalchemy import SQLAlchemy
from redis import Redis

app = Flask(__name__)
app.config['SQLALCHEMY_DATABASE_URI'] = 'postgresql://user:password@postgres/voting_app'
db = SQLAlchemy(app)
redis = Redis()

class Vote(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    pandal_name = db.Column(db.String(50), nullable=False)

@app.route('/vote', methods=['POST'])
def vote():
    pandal_name = request.json.get('pandal')
    new_vote = Vote(pandal_name=pandal_name)
    db.session.add(new_vote)
    db.session.commit()
    redis.incr(f'vote_count:{pandal_name}')  # Update Redis cache
    return jsonify(success=True), 201

@app.route('/results', methods=['GET'])
def results():
    votes = Vote.query.all()
    return jsonify(votes=[{'pandal': vote.pandal_name} for vote in votes])

if __name__ == '__main__':
    db.create_all()
    app.run(debug=True, host='0.0.0.0', port=5000)
```

#### Node.js Service

* **Set Up Express Application**:
    
    * Create a service to handle real-time voting updates.
        

```typescript
javascriptCopy codeconst express = require('express');
const http = require('http');
const socketIo = require('socket.io');

const app = express();
const server = http.createServer(app);
const io = socketIo(server);

app.use(express.json());

app.post('/update', (req, res) => {
    // Logic to handle real-time updates, e.g., notify users about new votes
    io.emit('newVote', req.body);
    res.send('Update received');
});

server.listen(3000, () => {
    console.log('Node.js service running on port 3000');
});
```

#### .NET Service

* **Create a .NET Core Web API**:
    
    * Set up a basic authentication controller to manage user logins.
        

```typescript
csharpCopy codeusing Microsoft.AspNetCore.Mvc;

[ApiController]
[Route("[controller]")]
public class AuthController : ControllerBase
{
    [HttpPost("login")]
    public IActionResult Login([FromBody] UserLogin userLogin)
    {
        // Simple authentication logic
        if (IsValidUser(userLogin))
        {
            return Ok();
        }
        return Unauthorized();
    }

    private bool IsValidUser(UserLogin userLogin)
    {
        // Validate user credentials
        return userLogin.Username == "admin" && userLogin.Password == "password";  // Example
    }
}
```

### Step 3: Database Setup

#### PostgreSQL Configuration

* **Docker Compose File**: Create a `docker-compose.yml` file to define the multi-container setup.
    

```typescript
yamlCopy codeversion: '3.8'
services:
  postgres:
    image: postgres:latest
    environment:
      POSTGRES_USER: user
      POSTGRES_PASSWORD: password
      POSTGRES_DB: voting_app
    ports:
      - "5432:5432"

  redis:
    image: redis:latest
    ports:
      - "6379:6379"
  
  python_service:
    build:
      context: ./python_service
    ports:
      - "5000:5000"
    depends_on:
      - postgres
  
  node_service:
    build:
      context: ./node_service
    ports:
      - "3000:3000"
  
  dotnet_service:
    build:
      context: ./dotnet_service
    ports:
      - "5001:5001"
```

### Step 4: Frontend Development

* **Create a Responsive Web Interface**: Use HTML, CSS, and JavaScript (or a frontend framework like React) to allow users to vote and view results.
    

#### Sample HTML Interface

```typescript
htmlCopy code<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Voting App</title>
    <style>
        body { font-family: Arial, sans-serif; }
        #results { margin-top: 20px; }
    </style>
</head>
<body>
    <h1>Vote for Your Favorite Pandal!</h1>
    <form id="voteForm">
        <input type="text" name="pandal" placeholder="Enter Pandal Name" required>
        <button type="submit">Vote</button>
    </form>
    <div id="results"></div>
    
    <script>
        document.getElementById('voteForm').addEventListener('submit', function(e) {
            e.preventDefault();
            const pandalName = this.pandal.value;

            fetch('/vote', {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify({ pandal: pandalName })
            })
            .then(response => response.json())
            .then(data => {
                console.log('Vote successful:', data);
                // Update results
                fetchResults();
            });
        });

        function fetchResults() {
            fetch('/results')
            .then(response => response.json())
            .then(data => {
                const resultsDiv = document.getElementById('results');
                resultsDiv.innerHTML = '<h2>Results:</h2>';
                data.votes.forEach(vote => {
                    resultsDiv.innerHTML += `<p>${vote.pandal}</p>`;
                });
            });
        }
    </script>
</body>
</html>
```

### Step 5: Running the Application

1. **Build and Run with Docker Compose**:
    
    * Execute the following command to build and start the application:
        
    
    ```typescript
    bashCopy codedocker-compose up --build
    ```
    
2. **Access the Application**: Open your browser and navigate to `http://localhost:5000` (or the port configured for your frontend).
    

### Step 6: Testing and Validation

* **Functional Testing**: Perform tests to ensure each component works as expected:
    
    * Verify that votes can be cast and stored in the PostgreSQL database.
        
    * Check that real-time updates are received in the frontend when new votes are submitted.
        
    * Validate the user authentication flow in the .NET service.
        
* **Load Testing**: Use tools like Apache JMeter or k6 to simulate high traffic and assess the application’s performance under load.
    

### Step 7: Deployment

* **Deploying to Cloud Platforms**: Consider deploying the application on platforms like AWS, Heroku, or DigitalOcean. Utilize services like AWS RDS for PostgreSQL and Elasticache for Redis for production readiness.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729884987430/76b67275-364d-4661-8b0b-efe87d9c409b.jpeg align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729884991902/a0cc02f8-0d86-45c8-a504-1844c9bf5d03.jpeg align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729884845184/95ffa829-a418-432e-940a-cb950271026b.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729885003536/4a70286e-2749-4fb2-849c-e793defe5a55.jpeg align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729885009205/52180ba1-7775-4898-83e2-d91e896b9583.jpeg align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729885012134/862c31e3-d0f4-4780-b6e3-c4594c2b4cf2.jpeg align="center")

### Conclusion

This dynamic three-tier voting application not only enhances user engagement during the festive season in Kolkata but also exemplifies modern development practices through its efficient architecture and tech stack. By utilizing Docker for orchestration, we ensure that the application is easy to manage and scale, meeting the demands of high user interaction.

### Future Enhancements

1. **Real-time Notifications**: Implement WebSockets or similar technologies to push real-time notifications to users about new votes or updates.
    
2. **Analytics Dashboard**: Create an admin interface that provides insights into voting trends, user engagement, and overall statistics.
    
3. **Mobile Application**: Develop a mobile app using React Native or Flutter to broaden access and improve user experience.
    
4. **Enhanced Security Features**: Incorporate JWT (JSON Web Tokens) for secure user authentication and role-based access control.
    
5. **User Feedback Mechanism**: Allow users to leave feedback or comments about their voting experience.
    
      
    

Thank Yu !!
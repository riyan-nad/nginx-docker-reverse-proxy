**DevOps Intern Assignment: Nginx Reverse Proxy + Docker**

This project sets up a simple system with:

1. **Two backend services**, each in a separate Docker container:
   - A **Go-based service** (service1) running on port `8001`
   - A **Flask-based service** (service2) running on port `8002`
2. An **Nginx reverse proxy** container that routes requests:
   - `/service1` → service 1
   - `/service2` → service 2
3. Everything is exposed through a single entry point:  
   **`http://localhost:8080`**


**Functional Requirements**

1. Use **Docker Compose** to manage and launch all containers.
2. The Nginx proxy supports:
   - Path-based routing (/service1, /service2)
   - Logging requests with timestamp, path, and user agent
3. The system should work with a single command:
   - docker-compose up --build


**How Routing Works**

When you open your browser and visit:
- http://localhost:8080/service1/hello
  ➤ You talk to Service 1 (the Go app)

- http://localhost:8080/service2/hello
  ➤ You talk to Service 2 (the Flask app)

1. All traffic goes through the Nginx reverse proxy, which listens on localhost:8080.
2. Nginx reads the URL path, and based on that:
   - If the path starts with /service1, it sends the request to the Go service.
   - If it starts with /service2, it sends it to the Flask service.
3. Docker lets Nginx talk to the services using their container names like service1 and service2. So everything looks like it's coming from one place (localhost:8080), but Nginx secretly routes them to the correct backend.


**Setup Instructions**

To build and run the entire system using Docker Compose:

1. Clone the repository:
   git clone https://github.com/riyan-nad/nginx-docker-reverse-proxy.git
   cd nginx-docker-reverse-proxyRun the following command:

2. Run the following command:
   docker-compose up --build

You can view the Docker Compose configuration here


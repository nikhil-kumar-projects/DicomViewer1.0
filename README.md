# DicomViewer1.0

## Prerequisites

Before you begin, ensure you have the following installed on your system:

### Backend - .NET Web API
- [.NET SDK 8.0 or later](https://dotnet.microsoft.com/download)

### Frontend - Angular
- [Node.js (v18.x or later)](https://nodejs.org/)
- [npm (v9.x or later)](https://www.npmjs.com/)
- [Angular CLI](https://angular.io/cli) (install globally with `npm install -g @angular/cli`)

## Backend: .NET Web API (Development Environment)

1. **Clone the repository**  
   ```bash
   git clone https://github.com/nikhil-kumar-projects/DicomViewer1.0.git
   cd DicomViewer1.0/WebApi
   ```

2. **Restore dependencies**  
   ```bash
   dotnet restore
   ```

3. **Build the project**  
   ```bash
   dotnet build
   ```

4. **Run the application**  
   ```bash
   dotnet run
   ```
   By default, the API will be accessible at `https://localhost:5001` or `http://localhost:5000`.

5. **Test the default endpoint using Swagger**  
   Visit `https://localhost:5001/swagger/index.html` in your browser or use a tool like Postman to verify the API is running.

---

## Container Deployment (Backend: .NET Web API )

1. **Navigate to the WebApi directory**  
   ```bash
   cd DicomViewer1.0/WebApi
   ```

2. **Build the Podman image**  
   ```bash
   podman build -t web-api .
   ```

3. **Run the Podman container**  
   ```bash
   podman run -d -p 5212:5000 --name web-api-container web-api
   ```

4. **View running containers**  
   ```bash
   podman ps
   ```

5. **View available images**  
   ```bash
   podman images
   ```

### Container Management

- **Test the containerized API**  
  Visit `http://localhost:5212/weatherforecast` in browser to verify the API is running.

- **Stop and remove the container (when needed)**  
  ```bash
  # For Docker
  docker stop web-api-container
  docker rm web-api-container
  
  # For Podman
  podman stop web-api-container
  podman rm web-api-container
  ```

- **Access container shell (for debugging)**  
  ```bash
  # For Docker
  docker exec -it web-api-container bash
  
  # For Podman
  podman exec -it web-api-container bash
  ```

---

## Frontend: Angular (Development Environment)

1. **Navigate to the frontend directory**  
   ```bash
   cd DicomViewer1.0/UI
   ```

2. **Install dependencies**  
   ```bash
   npm install
   ```

3. **Build the project**  
   ```bash
   ng build
   ```

4. **Run the application**  
   ```bash
   ng serve
   ```
   The application will be accessible at `http://localhost:4200` by default.

---

## Container Deployment (Frontend: Angular)

1. **Navigate to the UI directory**  
   ```bash
   cd DicomViewer1.0/UI
   ```

2. **Build the Podman image**  
   ```bash
   podman build -t dicom-viewer:latest .
   ```

3. **Run the Podman container**  
   ```bash
   podman run -d --name dicom-viewer -p 8080:80 dicom-viewer:latest
   ```

4. **View running containers**  
   ```bash
   podman ps
   ```

5. **View available images**  
   ```bash
   podman images
   ```

### Container Management

- **Test the containerized application**  
  Visit `http://localhost:8080` in browser to verify the Angular application is running.

- **Stop and remove the container (when needed)**  
  ```bash
  # For Docker
  docker stop dicom-viewer
  docker rm dicom-viewer
  
  # For Podman
  podman stop dicom-viewer
  podman rm dicom-viewer
  ```

- **Access container shell (for debugging)**  
  ```bash
  # For Docker
  docker exec -it dicom-viewer bash
  
  # For Podman
  podman exec -it dicom-viewer bash
  ```

---

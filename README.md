# DicomViewer1.0

## Prerequisites

Before you begin, ensure you have the following installed on your system:

### Backend - .NET Web API
- [.NET SDK 8.0 or later](https://dotnet.microsoft.com/download)

### Frontend - Angular
- [Node.js (v18.x or later)](https://nodejs.org/)
- [npm (v9.x or later)](https://www.npmjs.com/)
- [Angular CLI](https://angular.io/cli) (install globally with `npm install -g @angular/cli`)

---

## Backend: .NET Web API

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

## Frontend: Angular

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

## Notes

- Ensure both backend and frontend servers are running simultaneously for full functionality.
- If you encounter issues, ensure all prerequisites are installed and environment variables (if any) are configured.

# Stage 1: Build
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /src

# Copy solution and project files
COPY WebApi.sln ./
COPY webApi.Api/webApi.Api.csproj webApi.Api/

# Restore dependencies
RUN dotnet restore

# Copy all source files
COPY . ./

# Publish the WebApi project
RUN dotnet publish webApi.Api/webApi.Api.csproj -c Release -o /app/publish


# Stage 2: Runtime
FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS runtime
WORKDIR /app

# Copy the published output from the build stage
COPY --from=build /app/publish .

# Configure ASP.NET Core to listen on all interfaces
ENV ASPNETCORE_URLS=http://+:5000

# Expose the port the app runs on
EXPOSE 5000

# Run the application
ENTRYPOINT ["dotnet", "webApi.Api.dll"]
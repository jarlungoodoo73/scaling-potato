# Getting Started with Your C# Weather Application

Welcome! This guide will help you get up and running with your new C# weather application built with .NET 10.0, Blazor, and ASP.NET Core.

## Prerequisites

- [.NET 10.0 SDK](https://dotnet.microsoft.com/download/dotnet/10.0) or later
- [Visual Studio Code](https://code.visualstudio.com/) (recommended) or [Visual Studio 2022](https://visualstudio.microsoft.com/)
- [C# Dev Kit Extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csdevkit) for VS Code

## Quick Start

### Option 1: Using GitHub Codespaces (Recommended)

1. Click the "Code" button on the GitHub repository
2. Select "Codespaces" tab
3. Click "Create codespace on main"
4. Wait for the environment to initialize
5. Press F5 or use the "Run and Debug" panel to start both applications

### Option 2: Using Dev Container in VS Code

1. Clone the repository: `git clone https://github.com/jarlungoodoo73/scaling-potato.git`
2. Open the folder in VS Code
3. When prompted, click "Reopen in Container"
4. Wait for the container to build
5. Press F5 to start debugging

### Option 3: Local Development

1. **Clone the Repository**
   ```bash
   git clone https://github.com/jarlungoodoo73/scaling-potato.git
   cd scaling-potato
   ```

2. **Restore Dependencies**
   ```bash
   cd SampleApp
   dotnet restore
   ```

3. **Build the Projects**
   ```bash
   dotnet build
   ```

4. **Run the Backend API**
   ```bash
   cd BackEnd
   dotnet run
   ```
   The API will start on `http://localhost:8080` and `https://localhost:8081`

5. **Run the Frontend (in a separate terminal)**
   ```bash
   cd SampleApp/FrontEnd
   dotnet run
   ```
   The frontend will start on `http://localhost:5000` and `https://localhost:5001`

## Project Structure

```
scaling-potato/
├── SampleApp/
│   ├── BackEnd/           # ASP.NET Core Web API
│   │   ├── Program.cs     # API endpoints and configuration
│   │   └── ...
│   ├── FrontEnd/          # Blazor Web Application
│   │   ├── Pages/         # Blazor pages/components
│   │   ├── Data/          # Data models and services
│   │   └── ...
│   └── SampleApp.sln      # Solution file
├── .devcontainer/         # Dev container configuration
├── .github/workflows/     # CI/CD pipelines
└── images/                # Documentation images
```

## Key Features

### Backend API
- **Weather Forecast Endpoint**: GET `/weatherforecast` - Returns a 5-day weather forecast
- **OpenAPI/Swagger**: Available at `/openapi/v1.json`
- **Scalar API Documentation**: Interactive API docs at `/scalar` (development mode only)

### Frontend
- **Blazor Server App**: Server-side rendered Blazor application
- **Weather Display**: Fetches and displays weather data from the backend API
- **Responsive Design**: Works on desktop and mobile devices

## Testing the Application

### Test the Backend API

1. Navigate to `https://localhost:8081/scalar` (when running in development mode)
2. Find the "GetWeatherForecast" endpoint
3. Click "Test Request" to call the API
4. You should see a JSON response with 5 days of weather data

### Test the Frontend

1. Open your browser to the frontend URL (e.g., `https://localhost:5001`)
2. You should see the weather forecast displayed in a table
3. The data is fetched from the backend API

## Development Workflow

### Making Changes

1. **Modify Backend Code**: Edit files in `SampleApp/BackEnd/`
2. **Modify Frontend Code**: Edit files in `SampleApp/FrontEnd/`
3. **Hot Reload**: Both projects support hot reload - save your changes and see them immediately

### Building for Production

```bash
cd SampleApp
dotnet build --configuration Release
```

### Running Tests

```bash
cd SampleApp
dotnet test
```

## Common Tasks

### Adding a New API Endpoint

Edit `SampleApp/BackEnd/Program.cs`:

```csharp
app.MapGet("/hello", () => "Hello, World!")
   .WithName("SayHello");
```

### Adding a New Blazor Page

1. Create a new `.razor` file in `SampleApp/FrontEnd/Pages/`
2. Add the `@page` directive with a route
3. Implement your component

### Modifying the Weather Forecast

Edit the `WeatherForecast` record in `SampleApp/BackEnd/Program.cs` to add or modify properties.

## Troubleshooting

### Port Already in Use

If you get an error about ports being in use:
1. Stop any running instances of the application
2. Change the port in `appsettings.json` or `launchSettings.json`

### Build Errors

1. Ensure you have .NET 10.0 SDK installed: `dotnet --version`
2. Clean and rebuild: `dotnet clean && dotnet build`
3. Restore packages: `dotnet restore`

### Dependencies Not Restoring

1. Clear NuGet cache: `dotnet nuget locals all --clear`
2. Restore again: `dotnet restore`

## Next Steps

- Explore the [ASP.NET Core documentation](https://docs.microsoft.com/aspnet/core)
- Learn about [Blazor](https://docs.microsoft.com/aspnet/core/blazor)
- Check out [OpenAPI in ASP.NET Core](https://learn.microsoft.com/aspnet/core/fundamentals/openapi)
- Read the [CONTRIBUTING.md](readme.md#contributing) guide to contribute

## Need Help?

- Check the [README.md](readme.md) for more information
- Review the code comments in the source files
- Consult the [.NET documentation](https://docs.microsoft.com/dotnet)

Happy coding! 🚀

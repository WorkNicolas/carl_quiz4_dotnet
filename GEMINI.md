# MvcMovie Project Overview

This is an ASP.NET Core MVC web application developed with .NET 8.0. It serves as a movie database management system where users can create, read, update, and delete movie records.

## Technologies Used

- **Framework:** ASP.NET Core MVC (.NET 8.0)
- **Data Access:** Entity Framework Core (EF Core)
- **Database:** SQL Server (LocalDB)
- **Styling:** Bootstrap (via standard ASP.NET MVC template)
- **Tooling:** Visual Studio / .NET CLI

## Project Structure

- **Controllers/**: Contains the logic for handling HTTP requests (e.g., `MoviesController`, `HelloWorldController`, `HomeController`).
- **Models/**: Contains the data structures and view models (e.g., `Movie.cs`, `MovieGenreViewModel.cs`).
- **Data/**: Contains the database context (`MvcMovieContext.cs`) for EF Core.
- **Views/**: Contains the Razor view files (`.cshtml`) for the user interface.
- **Migrations/**: Contains the EF Core migration files for database schema evolution.
- **wwwroot/**: Contains static assets like CSS, JavaScript, and images.

## Building and Running

### Prerequisites

- [.NET 8.0 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)
- SQL Server LocalDB (installed with Visual Studio or as a standalone component)

### Key Commands

- **Restore dependencies:**
  ```powershell
  dotnet restore
  ```
- **Build the project:**
  ```powershell
  dotnet build
  ```
- **Run the application:**
  ```powershell
  dotnet run --project MvcMovie
  ```
  The application will typically be available at `https://localhost:7054` or `http://localhost:5081` (check `Properties/launchSettings.json` for details).

- **Update the database (Migrations):**
  ```powershell
  dotnet ef database update
  ```

## Development Conventions

- **MVC Pattern:** Strictly follows the Model-View-Controller architectural pattern.
- **Dependency Injection:** Services and database contexts are injected via the `Program.cs` file.
- **Seeding:** Initial data is seeded automatically in `Program.cs` using the `SeedData` class.
- **Validation:** Data annotations in `Movie.cs` are used for both client-side and server-side validation.
- **Search Logic:** The `MoviesController.Index` action handles both genre-based and title-based searching.

## Configuration

- Database connection strings are located in `appsettings.json` and `appsettings.Development.json`.
- Logging levels and other app-specific settings are also managed via `appsettings.json`.

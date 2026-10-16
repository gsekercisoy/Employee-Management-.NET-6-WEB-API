<div align="center">

**English** | [Türkçe](README_tr.md)

# Employee Management — .NET 6 Web API

Sample CRUD backend for employee records. Pairs with the
[Employee-Management-React](https://github.com/gsekercisoy/Employee-Management-React)
frontend.

</div>

## Tech stack

- .NET 6 (`net6.0`), ASP.NET Core Web API
- Entity Framework Core 6 + SQL Server
- Swashbuckle (Swagger, Development only)

## Endpoints

Base route `api/Employee`:

| Method | Endpoint | Description |
|---|---|---|
| GET | `/GetAll` | List all employees |
| GET | `/GetById/{id}` | Single employee |
| POST | `/Add` | Create employee |
| PUT | `/Update/{id}` | Update employee |
| DELETE | `/Delete/{id}` | Delete employee |

Model: `Employee { int ID, string? Name, string? Age, bool IsActive }` → table `Employees`.

## Getting started

```bash
dotnet restore
dotnet ef database update   # applies the bundled migration (DB: EmpCrudDB)
dotnet run --project sample-crud-be
```

- HTTPS: `https://localhost:7010` (HTTP: `http://localhost:5191`)
- Swagger UI (Development): `https://localhost:7010/swagger`
- SQL Server with Windows Authentication; connection name `CRUDS` in `appsettings.json`

## Structure

```
sample-crud-be/
  Controllers/EmployeeController.cs
  Models/Employee.cs, Models/EmployeeContext.cs
  Migrations/            # initial schema
  Program.cs, appsettings.json
```

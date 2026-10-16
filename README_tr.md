<div align="center">

[English](README.md) | **Türkçe**

# Employee Management — .NET 6 Web API

Çalışan kayıtları için örnek CRUD backend'i.
[Employee-Management-React](https://github.com/gsekercisoy/Employee-Management-React)
arayüzüyle birlikte çalışır.

</div>

## Teknolojiler

- .NET 6 (`net6.0`), ASP.NET Core Web API
- Entity Framework Core 6 + SQL Server
- Swashbuckle (Swagger, sadece Development)

## Uç noktalar

Temel route `api/Employee`:

| Yöntem | Uç nokta | Açıklama |
|---|---|---|
| GET | `/GetAll` | Tüm çalışanlar |
| GET | `/GetById/{id}` | Tek kayıt |
| POST | `/Add` | Kayıt ekleme |
| PUT | `/Update/{id}` | Kayıt güncelleme |
| DELETE | `/Delete/{id}` | Kayıt silme |

Model: `Employee { int ID, string? Name, string? Age, bool IsActive }` → `Employees` tablosu.

## Çalıştırma

```bash
dotnet restore
dotnet ef database update   # hazır migration'ı uygular (DB: EmpCrudDB)
dotnet run --project sample-crud-be
```

- HTTPS: `https://localhost:7010` (HTTP: `http://localhost:5191`)
- Swagger UI (Development): `https://localhost:7010/swagger`
- Windows kimlik doğrulamalı SQL Server; bağlantı adı `appsettings.json` içinde `CRUDS`

## Yapı

```
sample-crud-be/
  Controllers/EmployeeController.cs
  Models/Employee.cs, Models/EmployeeContext.cs
  Migrations/            # ilk şema
  Program.cs, appsettings.json
```

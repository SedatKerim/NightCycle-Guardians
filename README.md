# ✈️ Corporate Flight Reservation System

This project is a backend API for managing flight reservations within a company. Each company can register, create users (employees), and manage their flight bookings. Airport information is fetched from a public API and cached for performance.

---

## 📦 Technologies

- ASP.NET Core 8 (Controller-based API)
- Entity Framework Core
- PostgreSQL
- FluentValidation
- Swagger / OpenAPI
- IMemoryCache (for airport data)
- External API: [AirportGap](https://airportgap.com/docs)

---

## 📁 Project Structure

```
FlightReservationSystem/
 ┣ Controllers/
 ┣ Entities/
 ┣ DTOs/
 ┣ Services/
 ┣ Repositories/
 ┣ Data/
 ┣ Validators/
 ┗ Program.cs
```

---

## 🚀 Getting Started

### 1. Create Database

In PostgreSQL:

```sql
CREATE DATABASE flight_reservation;
```

### 2. Update Connection String in `appsettings.json`

```json
"ConnectionStrings": {
  "DefaultConnection": "Host=localhost;Port=5432;Database=flight_reservation;Username=postgres;Password=yourpassword"
}
```

### 3. Run EF Core Migrations

```bash
dotnet ef migrations add InitialCreate
dotnet ef database update
```

### 4. Run the App

```bash
dotnet run
```

---

## 📌 Features

- [x] Company and employee registration
- [x] Flight definition (from → to, date, time, price)
- [x] Booking creation and cancellation
- [x] Company-specific booking view
- [x] Cached airport data from AirportGap API

---

## 📥 Sample Seed Data (Flight)

```json
{
  "from_iata": "IST",
  "to_iata": "WAW",
  "departure": "2025-10-23T10:00:00Z",
  "arrival": "2025-10-23T12:30:00Z",
  "price": 129.99
}
```

---

## 🔒 Notes

- Authentication is not implemented yet. You can use a simple `X-CompanyId` header to simulate scoped access.
- Airport data is cached in memory for 1 hour to reduce external API calls.

---

## 👨‍💻 Contributing

This is an educational project to help developers learn about building a real-world Web API system. Future improvements may include:

- JWT Authentication
- Role-based access (Admin vs. User)
- Unit and integration tests

---

## 📧 Contact

For questions or support:  
**info@yourcompany.com**

# E-Commerce Web Application (ASP.NET Core MVC)

A full e-commerce web application built with **ASP.NET Core MVC**, **Entity Framework Core**, **ASP.NET Identity** and **SQL Server**, with an **Admin dashboard** and a **Customer storefront** including cart, favorites and **Stripe** checkout.

![.NET](https://img.shields.io/badge/.NET-8.0-512BD4?logo=dotnet)
![C#](https://img.shields.io/badge/C%23-239120?logo=csharp&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?logo=microsoftsqlserver&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-7952B3?logo=bootstrap&logoColor=white)
![Stripe](https://img.shields.io/badge/Payments-Stripe-635BFF?logo=stripe&logoColor=white)

## Screenshots

| | |
|---|---|
| ![Screenshot 1](images/1.png) | ![Screenshot 2](images/2.png) |
| ![Screenshot 3](images/3.png) | ![Screenshot 4](images/4.png) |
| ![Screenshot 5](images/5.png) | |

## Features

**Identity**
- Register, login and logout with **ASP.NET Identity**
- Email confirmation, resend confirmation, forget / reset password (OTP-based)
- Role-based access (Admin / Customer)

**Admin dashboard**
- CRUD for **Products** (with image upload / replace / delete), **Categories** and **Brands**
- User management: create users, change role, lock / unlock accounts

**Customer storefront**
- Home page with products, product details and related products
- Shopping **cart** (add, increase / decrease quantity, remove)
- **Favorites** list
- **Checkout** with **Stripe** (pay, success, cancel) and order creation

## Tech stack

| Layer | Technology |
|---|---|
| Framework | ASP.NET Core 8 MVC (Areas: Admin, Customer, Identity) |
| ORM | Entity Framework Core (Code First, migrations) |
| Database | SQL Server |
| Auth | ASP.NET Identity |
| Payments | Stripe.net |
| UI | Razor views, Bootstrap (Start Bootstrap templates) |

## Architecture

```
EComerceTestSamir/
├── Areas/
│   ├── Admin/Controllers      # Home, Product, Category, Brand, User
│   ├── Customer/Controllers   # Home, Cart, Favorite, Checkout
│   └── Identity/Controllers   # Account
├── Data/                      # ApplicationDbContext
├── Models/                    # Entities + ViewModels
├── Repositories/              # Generic Repository + specific repositories
│   └── IRepositories/
└── Utility/                   # Email sender, Stripe settings
```

- **Repository pattern** with Dependency Injection
- **ViewModels** to keep views decoupled from entities

## Getting started

1. Clone the repo and open `EComerceTestSamir.sln` in Visual Studio 2022.
2. Put your connection string and Stripe test key in **User Secrets** (never commit real keys):
   ```json
   {
     "ConnectionStrings": { "DefaultConnection": "Server=.;Database=ECommerce;Trusted_Connection=True;TrustServerCertificate=True" },
     "Stripe": { "SecretKey": "<your-stripe-test-key>" }
   }
   ```
3. Set the Gmail **App Password** used for sending emails as an environment variable named `EMAIL_APP_PASSWORD`.
4. Create the database:
   ```bash
   dotnet ef database update
   ```
5. Run the project.

## Author

**Samir Mohamed Hamed** — Backend .NET Developer
[LinkedIn](https://www.linkedin.com/in/samir-mohamed-dotnet) · [GitHub](https://github.com/Samirmohamedhamed)

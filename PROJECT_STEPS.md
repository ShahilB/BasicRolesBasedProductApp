# RoleBasedProductApp Project Documentation

## Project Overview
A simple ASP.NET Core MVC application with role-based authentication and product management. Features Admin and Manager roles, secure login, product CRUD, and security best practices.

## Steps and Tasks Completed

### 1. Project Setup
- Created ASP.NET Core MVC project.
- Configured Entity Framework Core with SQL Server.
- Set up Identity for authentication and role management.

### 2. Models
- `ApplicationUser`: Custom user model for Identity.
- `Product`: Model for product data.

### 3. Database and Seeding
- Added `DbInitializer` to seed roles (Admin, Manager) and default users:
  - Admin: Username `Admin`, Password `Admin@123`
  - Manager: Username `Manager`, Password `Manager@123`
- Updated seeding logic to allow login with username only.

### 4. Controllers
- `AccountController`: Handles login and logout.
- `ProductController`: Handles product CRUD with role-based access.
- `DashboardController`: Shows user info and roles.
- `ManagerController`: Shows access denied for unauthorized actions.
- `HomeController`: Displays the home page.

### 5. Views
- Created views for login, product list, create/edit product, dashboard, access denied, and home page.
- Used Bootstrap for responsive UI and tables.
- Added a shared layout with a navbar (Home, Products, Create Product, Dashboard, Login/Logout, username display).

### 6. Security Measures
- **HTTPS**: Enforced via `launchSettings.json` and `app.UseHttpsRedirection()`.
- **CSRF Protection**: Added `@Html.AntiForgeryToken()` to all forms and `[ValidateAntiForgeryToken]` to all POST actions.
- **Password Security**: Passwords are securely hashed by ASP.NET Identity.

### 7. Role-Based Access
- Only Admin can create or delete products.
- Admin and Manager can edit products.
- Manager sees an error message if trying to delete a product.

### 8. User Experience
- Login with username and password.
- Dashboard shows user info and roles.
- Error and success messages displayed on relevant pages.

### 9. Comments and Documentation
- Added comments to all controller methods for clarity.

---

## How to Run
1. Restore packages: `dotnet restore`
2. Apply migrations: `dotnet ef database update`
3. Run the app: `dotnet run`
4. Visit `https://localhost:5001` in your browser.

---

## Default Users
- **Admin**: Username `Admin`, Password `Admin@123`
- **Manager**: Username `Manager`, Password `Manager@123`

---

## Security Notes
- All forms are CSRF protected.
- All sensitive actions require authentication and proper roles.
- HTTPS is enforced

---



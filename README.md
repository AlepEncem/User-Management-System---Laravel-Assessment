# User Management System - Laravel Assessment

## Overview
A comprehensive User Management System built with Laravel featuring both Admin Panel and RESTful API endpoints.

## Features
- ✅ Complete CRUD operations for users
- ✅ Admin panel interface
- ✅ RESTful API endpoints
- ✅ Soft delete functionality
- ✅ Bulk delete operations
- ✅ Status filtering and search
- ✅ Pagination support
- ✅ Form validation using Laravel Form Requests

## Requirements
- PHP 8.2+
- MySQL 5.7+
- Composer
- Laravel 11.x

## Installation

1. Clone the repository:
```bash
git clone [your-repo-url]
cd testing_laravel
```

2. Install dependencies:

```bash
composer install
```

3. Copy environment file:

```bash
copy .env.example .env
```

4. Generate application key:

```bash
php artisan key:generate
```

5. Configure database in .env:
```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=user_management_db
DB_USERNAME=your_username
DB_PASSWORD=your_password
```
6. Run migrations and seeders:

```bash
php artisan migrate
php artisan db:seed
```

7. Start the server:

```bash
php artisan serve
```

Usage
Admin Panel
Access the admin panel at: http://localhost:8000/admin/users
Features:

View all users with pagination
Create new users
Edit existing users
Delete users (soft delete)
Filter by status
Search functionality

API Endpoints
Base URL: http://localhost:8000/api
MethodEndpointDescriptionGET/usersGet all users (paginated)GET/users/{id}Get specific userPOST/usersCreate new userPUT/users/{id}Update userDELETE/users/{id}Delete user (soft)DELETE/users/bulk/deleteBulk delete users
API Request Examples
Create User:
jsonPOST /api/users
{
    "name": "John Doe",
    "email": "john@example.com",
    "phone_number": "+1234567890",
    "password": "password123",
    "status": "active"
}
Update User:
jsonPUT /api/users/{id}
{
    "name": "Updated Name",
    "status": "inactive"
}
Bulk Delete:
jsonDELETE /api/users/bulk/delete
{
    "ids": [1, 2, 3]
}
Testing
Run tests using:
bashphp artisan test
Project Structure
├── app/
│   ├── Http/
│   │   ├── Controllers/
│   │   │   ├── Admin/
│   │   │   │   └── UserManagementController.php
│   │   │   └── Api/
│   │   │       └── UserController.php
│   │   └── Requests/
│   │       ├── StoreUserRequest.php
│   │       └── UpdateUserRequest.php
│   └── Models/
│       └── User.php
├── database/
│   ├── migrations/
│   └── seeders/
│       └── UserSeeder.php
├── resources/
│   └── views/
│       └── admin/
│           └── users/
├── routes/
│   ├── api.php
│   └── web.php
Design Decisions

Soft Deletes: Implemented to maintain data integrity and allow recovery
Form Requests: Used for centralized validation logic
Resource Controllers: Followed RESTful conventions
Pagination: Implemented for better performance with large datasets
Status Enum: Used active/inactive status for user management

Author- Alif Firdaus

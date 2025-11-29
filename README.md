📦 Warehouse Management System (WMS)

A lightweight but scalable Warehouse Management System built with .NET 8, featuring both a WinForms desktop client and an ASP.NET Core web app.
The solution follows Clean Architecture, keeping business logic, data access, and UI well-separated and easy to maintain.

✨ Features

Inventory Management: Items, locations, stock levels

Warehouse Operations: Receiving, putaway, picking, adjustments

Barcode Support: Scanner-friendly workflows

Lot & Serial Tracking: Optional per-item rules

Reports: Stock and movement reports with CSV export

Audit Trail: Every transaction logged

🖥 Interfaces
Desktop (WinForms)

Scanner-optimized

Quick keyboard actions

Real-time feedback

Web (ASP.NET Core)

Clean Bootstrap UI

Mobile-friendly

Dashboard & reporting pages

🏗️ Architecture

### Clean Architecture Implementation

```
┌─────────────────┐   ┌─────────────────┐
│   WinForms UI   │   │  ASP.NET Core   │
│   (Desktop)     │   │   (Web MVC)     │
└─────────────────┘   └─────────────────┘
         │                       │
         └───────────┬───────────┘
                     │
            ┌─────────────────┐
            │   Application   │  ← Use Cases, DTOs, Results
            │     Layer       │
            └─────────────────┘
                     │
            ┌─────────────────┐
            │     Domain      │  ← Entities, Value Objects, Services
            │     Layer       │
            └─────────────────┘
                     │
            ┌─────────────────┐
            │ Infrastructure  │  ← Data Access, External Services
            │     Layer       │
            └─────────────────┘


📂 Project Structure

```
📁 Warehouse Management System/
├── 🎯 Wms.Domain/                    # Domain Layer
│   ├── Entities/                     # Domain Entities (Item, Location, Stock, etc.)
│   ├── ValueObjects/                 # Value Objects (Barcode, Quantity)
│   ├── Enums/                       # Domain Enumerations (MovementType)
│   ├── Services/                    # Domain Services (IStockMovementService)
│   └── Repositories/                # Repository Interfaces
├── 🚀 Wms.Application/              # Application Layer
│   ├── UseCases/                    # Application Use Cases
│   │   ├── Receiving/               # Receiving Operations
│   │   ├── Inventory/               # Stock Management
│   │   ├── Items/                   # Item Management
│   │   ├── Locations/               # Location Management
│   │   ├── Picking/                 # Picking Operations
│   │   └── Reports/                 # Reporting
│   ├── DTOs/                        # Data Transfer Objects
│   └── Common/                      # Shared Application Logic
├── 🔧 Wms.Infrastructure/           # Infrastructure Layer
│   ├── Data/                        # Database Context & Configurations
│   ├── Repositories/                # Repository Implementations
│   └── Services/                    # External Service Implementations
├── 🖥️ Wms.WinForms/                 # WinForms Desktop Application
│   ├── Forms/                       # Application Forms
│   │   ├── DashboardForm.cs         # KPI Dashboard
│   │   ├── ReceivingForm.cs         # Item Receiving
│   │   ├── PutawayForm.cs           # Putaway Operations
│   │   ├── PickingForm.cs           # Order Picking
│   │   ├── InventoryForm.cs         # Stock Management
│   │   ├── ItemManagementForm.cs    # Item Master Data
│   │   └── LocationManagementForm.cs # Location Setup
│   ├── Common/                      # UI Helpers & Utilities
│   └── Program.cs                   # Application Entry Point
├── 🌐 Wms.ASP/                      # ASP.NET Core Web Application
│   ├── Controllers/                 # MVC Controllers
│   ├── Views/                       # Razor Views
│   ├── Models/                      # View Models
│   ├── wwwroot/                     # Static Assets
│   └── Program.cs                   # Web Application Entry Point
└── 🧪 Test Projects/                # Unit & Integration Tests
    ├── Wms.Domain.Tests/            # Domain Layer Tests
    ├── Wms.Application.Tests/       # Application Layer Tests
    └── Wms.Infrastructure.Tests/    # Infrastructure Layer Tests
```


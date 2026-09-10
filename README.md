# 🚗 Flutter SQLite Vehicle App

### Cross-Platform Vehicle Management Application

[![Flutter](https://img.shields.io/badge/Flutter-3.x-02569B?logo=flutter\&logoColor=white)](https://flutter.dev/)
[![Dart](https://img.shields.io/badge/Dart-2.x-0175C2?logo=dart\&logoColor=white)](https://dart.dev/)
[![SQLite](https://img.shields.io/badge/SQLite-Local_Database-003B57?logo=sqlite\&logoColor=white)](https://www.sqlite.org/)
[![Android](https://img.shields.io/badge/Android-Supported-3DDC84?logo=android\&logoColor=white)](https://developer.android.com/)
[![iOS](https://img.shields.io/badge/iOS-Supported-000000?logo=apple\&logoColor=white)](https://developer.apple.com/ios/)
[![Windows](https://img.shields.io/badge/Windows-Supported-0078D4?logo=windows\&logoColor=white)](https://learn.microsoft.com/windows/)
[![Web](https://img.shields.io/badge/Web-Supported-4285F4?logo=googlechrome\&logoColor=white)](https://flutter.dev/web)

A cross-platform **Flutter application for vehicle management with local SQLite persistence**.

The project demonstrates practical mobile application development using **Dart, Flutter, SQLite, state management, reusable UI components, form validation, local data persistence, theming, and platform-independent application architecture**.

The application was developed as a practical software development project in an educational environment, providing a hands-on example of how a relational database can be integrated into a cross-platform Flutter application.

---

## 🎯 Project Overview

The application provides a simple vehicle management workflow where users can create and manage vehicle records locally on the device.

The project combines:

* Cross-platform UI
* Local relational database
* CRUD operations
* Data models
* State management
* Form handling
* Input formatting
* Dynamic themes
* Reusable UI components

The goal is to demonstrate how a complete mobile application can be developed without requiring a remote backend for its core data operations.

---

## ✨ Features

### 🚘 Vehicle Management

The application provides functionality for managing vehicle records, including:

* Add vehicles
* Edit vehicles
* Display vehicle information
* Persist vehicle data locally
* Retrieve stored records

The domain model is represented by:

```text
Carro
```

The model is located under:

```text
lib/model/Carro.dart
```

The repository separates the vehicle model from the presentation and persistence layers.

---

## 🗄️ Local SQLite Database

One of the main technical characteristics of the project is the use of **SQLite for local persistence**.

The application uses the Flutter `sqflite` package:

```yaml
sqflite: ^2.0.2
```

and `path_provider` for platform-specific application storage paths.

This enables the application to maintain data locally without requiring an external API or cloud database.

### Persistence architecture

```text
┌─────────────────────────┐
│       Flutter UI        │
└────────────┬────────────┘
             │
             ▼
┌─────────────────────────┐
│    CarroProvider        │
│                         │
│ Application State       │
└────────────┬────────────┘
             │
             ▼
┌─────────────────────────┐
│  DatabaseProvider       │
│                         │
│ SQLite Access Layer     │
└────────────┬────────────┘
             │
             ▼
┌─────────────────────────┐
│         SQLite          │
│                         │
│ Local Relational Data   │
└─────────────────────────┘
```

The repository contains dedicated `CarroProvider.dart` and `DatabaseProvider.dart` components, demonstrating an explicit separation between application state and database access.

---

## 🏗️ Application Architecture

The project organizes the application into three main conceptual layers:

```text
lib/
│
├── model/
│
├── provider/
│
└── view/
```

This organization provides a basic separation between:

### Model

Represents the application's domain objects.

```text
lib/model/
└── Carro.dart
```

### Provider

Responsible for application state and persistence-related operations.

```text
lib/provider/
├── CarroProvider.dart
└── DatabaseProvider.dart
```

### View

Contains the user interface screens and reusable UI components.

```text
lib/view/
├── AdicionarCarro.dart
├── AlteraCarro.dart
└── MenuLateral.dart
```

This structure is visible directly in the repository.

---

## 🔄 CRUD Workflow

The application's core workflow can be represented as:

```text
                ┌──────────────┐
                │   Vehicle    │
                │    Screen    │
                └──────┬───────┘
                       │
              ┌────────┴────────┐
              │                 │
              ▼                 ▼
          Add Vehicle       Edit Vehicle
              │                 │
              └────────┬────────┘
                       │
                       ▼
                ┌──────────────┐
                │    Provider  │
                └──────┬───────┘
                       │
                       ▼
                ┌──────────────┐
                │    SQLite    │
                └──────────────┘
```

This demonstrates a complete local data lifecycle:

```text
Create
  ↓
Persist
  ↓
Retrieve
  ↓
Display
  ↓
Update
```

---

## 📱 Cross-Platform Development

The repository includes platform targets for:

```text
android/
ios/
web/
windows/
```

This means the project was structured as a Flutter application capable of targeting multiple platforms from a shared Dart codebase.

One of the major benefits of this architecture is code reuse:

```text
             ┌───────────────┐
             │  Dart / Flutter│
             │   Codebase     │
             └───────┬───────┘
                     │
       ┌─────────────┼─────────────┐
       │             │             │
       ▼             ▼             ▼
    Android         iOS          Windows
                                  │
                                  ▼
                                  Web
```

This illustrates the central value proposition of cross-platform application development.

---

## 🎨 Dynamic Theming

The application uses:

```yaml
easy_dynamic_theme: ^2.2.0
```

to support dynamic application themes.

This allows the UI architecture to accommodate theme changes without requiring separate implementations for each visual state.

---

## ⌨️ Input Formatting

The project also uses:

```yaml
mask_text_input_formatter: ^2.1.0
```

for formatted user input.

Input formatting is particularly useful for structured vehicle-related information where the application needs to guide the user toward a predefined format.

---

## 🧩 Reusable UI Components

The project includes a dedicated:

```text
MenuLateral.dart
```

component.

Separating reusable interface components from individual screens makes it easier to maintain consistent navigation and visual behavior across the application.

---

## 🛠️ Technology Stack

| Technology                    | Purpose                              |
| ----------------------------- | ------------------------------------ |
| **Flutter**                   | Cross-platform application framework |
| **Dart**                      | Programming language                 |
| **SQLite**                    | Local relational database            |
| **sqflite**                   | SQLite integration                   |
| **path_provider**             | Platform-specific storage paths      |
| **easy_dynamic_theme**        | Dynamic application themes           |
| **mask_text_input_formatter** | Structured input formatting          |
| **Material Design**           | Application UI                       |

The dependencies are defined in `pubspec.yaml`.

---

## 📂 Project Structure

```text
app_sqlite-3DS-noite-2022/
│
├── android/
│
├── ios/
│
├── lib/
│   │
│   ├── model/
│   │   └── Carro.dart
│   │
│   ├── provider/
│   │   ├── CarroProvider.dart
│   │   └── DatabaseProvider.dart
│   │
│   ├── view/
│   │   ├── AdicionarCarro.dart
│   │   ├── AlteraCarro.dart
│   │   └── MenuLateral.dart
│   │
│   ├── main.dart
│   └── themes.dart
│
├── test/
├── web/
├── windows/
│
├── analysis_options.yaml
├── pubspec.yaml
├── pubspec.lock
└── README.md
```

The repository currently follows this organization.

---

## 🚀 Getting Started

### Prerequisites

Install Flutter and configure your development environment:

```bash
flutter doctor
```

Verify that Flutter is available:

```bash
flutter --version
```

---

## 📥 Clone the Repository

```bash
git clone https://github.com/MarceloTTorres/app_sqlite-3DS-noite-2022.git
```

Enter the project:

```bash
cd app_sqlite-3DS-noite-2022
```

---

## 📦 Install Dependencies

Run:

```bash
flutter pub get
```

The project dependencies include SQLite, path handling, dynamic themes and input formatting.

---

## ▶️ Run the Application

For a connected device or emulator:

```bash
flutter run
```

To see available targets:

```bash
flutter devices
```

For a specific platform:

```bash
flutter run -d windows
```

or:

```bash
flutter run -d chrome
```

depending on the configured Flutter environment.

---

## 🧪 Testing

The repository includes a:

```text
test/
```

directory, providing a foundation for automated Flutter testing.

Run the test suite with:

```bash
flutter test
```

Static analysis can be executed with:

```bash
flutter analyze
```

These commands provide a basic quality workflow for Flutter applications.

---

## 🔄 Application Data Flow

The application follows a straightforward data flow:

```text
User Interaction
       │
       ▼
    Flutter View
       │
       ▼
   CarroProvider
       │
       ├───────────────┐
       │               │
       ▼               ▼
   Application      Database
     State          Operations
                       │
                       ▼
                    SQLite
                       │
                       ▼
                 Stored Data
```

This approach keeps the UI from being directly responsible for low-level database operations.

---

## 🧠 Software Engineering Concepts Demonstrated

Although the application is intentionally compact, it demonstrates several concepts relevant to professional mobile development.

### Cross-Platform Development

A single Flutter/Dart codebase targets multiple platforms.

### Local Persistence

SQLite provides structured relational storage directly on the device.

### Separation of Concerns

Models, providers, and views are organized separately.

### State Management

`CarroProvider` provides an abstraction for application-level vehicle state.

### Data Access Abstraction

`DatabaseProvider` separates SQLite access from the presentation layer.

### UI Component Reuse

Reusable components such as the side menu are separated from individual screens.

### Form-Oriented Application Design

The project contains dedicated screens for adding and modifying vehicles.

---

## 💡 Why SQLite?

A local SQLite database is particularly appropriate for applications that need:

* Offline operation
* Fast local access
* Structured relational data
* Low infrastructure requirements
* Local-first workflows
* Mobile data persistence

The architecture could later be extended to synchronize local data with a remote backend.

---

## ☁️ Possible Cloud Architecture

A natural evolution of the application would be to add a REST API and cloud synchronization.

```text
                   ┌─────────────────┐
                   │ Flutter Client  │
                   └────────┬────────┘
                            │
                 ┌──────────┴──────────┐
                 │                     │
                 ▼                     ▼
          Local SQLite            REST API
          Offline Data                │
                                      ▼
                              ┌───────────────┐
                              │ Cloud Backend │
                              └───────┬───────┘
                                      │
                                      ▼
                                ┌───────────┐
                                │ Database  │
                                └───────────┘
```

This would transform the application from a local-only system into an **offline-first mobile application with synchronization capabilities**.

---

## 🔮 Future Improvements

The current implementation provides a good foundation for further development.

### Architecture

* [ ] Introduce a formal repository layer
* [ ] Separate database entities from domain models
* [ ] Introduce dependency injection
* [ ] Introduce service classes
* [ ] Adopt a clearly defined state-management architecture

### Data

* [ ] Add database migrations
* [ ] Add relational entities
* [ ] Add indexes
* [ ] Add data validation
* [ ] Add persistent configuration
* [ ] Add database backup/export

### Mobile

* [ ] Improve responsive layouts
* [ ] Add Android-specific UX improvements
* [ ] Add iOS-specific UX improvements
* [ ] Improve accessibility
* [ ] Add localization
* [ ] Add dark/light theme persistence

### Backend

* [ ] Add REST API
* [ ] Add authentication
* [ ] Add cloud synchronization
* [ ] Implement offline-first synchronization
* [ ] Add conflict resolution
* [ ] Add server-side persistence

### Quality

* [ ] Expand unit tests
* [ ] Add widget tests
* [ ] Add integration tests
* [ ] Add CI/CD with GitHub Actions
* [ ] Add automated static analysis
* [ ] Add code coverage reporting

---

## 🧪 Recommended Testing Strategy

A more mature version of the application could use three testing layers:

```text
                    ┌──────────────┐
                    │ Integration  │
                    │    Tests     │
                    └──────┬───────┘
                           │
                 ┌─────────┴─────────┐
                 │   Widget Tests   │
                 └─────────┬─────────┘
                           │
              ┌────────────┴────────────┐
              │       Unit Tests        │
              │                         │
              │ Models / Providers / DB │
              └─────────────────────────┘
```

Potential unit tests include:

```text
Carro
 ├── Create
 ├── Update
 ├── Delete
 └── Validation

Database
 ├── Insert
 ├── Query
 ├── Update
 └── Delete

Provider
 ├── State changes
 ├── Loading
 └── Error handling
```

---

## 🌐 Internationalization Opportunity

A natural next step would be introducing internationalization using Flutter's localization infrastructure.

Potential languages:

```text
English
Portuguese
Spanish
French
```

This would allow the application to support international users without duplicating the UI implementation.

---

## 🔐 Security Considerations for a Future Backend

Because the current application stores data locally, security requirements are relatively limited.

If cloud synchronization is introduced, the architecture should include:

* Authentication
* Authorization
* Secure API communication
* Token management
* Input validation
* Secure local credential storage
* Server-side validation
* Database access controls

The mobile client should never be treated as a trusted source of business rules.

---

## 📈 From Local App to Production Architecture

A production-oriented evolution could look like:

```text
                         ┌──────────────────┐
                         │   Flutter Apps   │
                         │                  │
                         │ Android / iOS    │
                         └────────┬─────────┘
                                  │
                            HTTPS / REST
                                  │
                                  ▼
                         ┌──────────────────┐
                         │    API Gateway   │
                         └────────┬─────────┘
                                  │
                                  ▼
                         ┌──────────────────┐
                         │   Backend API    │
                         │                  │
                         │ Business Logic   │
                         └────────┬─────────┘
                                  │
                    ┌─────────────┴─────────────┐
                    │                           │
                    ▼                           ▼
              ┌───────────┐              ┌───────────┐
              │ Database  │              │   Cache   │
              └───────────┘              └───────────┘

                         ▲
                         │
                    Synchronization
                         │
                         ▼
                  ┌───────────────┐
                  │ Local SQLite  │
                  └───────────────┘
```

This would provide an excellent opportunity to demonstrate modern mobile architecture, offline-first design and cloud integration.

---

## 👨‍🏫 Educational Context

The repository name identifies the project as a **3rd-year Systems Development class project from 2022**.

This context is worth preserving because it demonstrates practical application of software development concepts in an educational environment.

The project can therefore be presented not only as a Flutter application, but also as an example of applying:

* Mobile development
* Database design
* Software architecture
* UI development
* Object-oriented programming
* Cross-platform development

to a concrete application.

---

## 💼 What This Project Demonstrates to Hiring Teams

This project provides evidence of several skills relevant to mobile and full-stack engineering roles.

### Cross-Platform Mobile Development

The application uses Flutter to target multiple platforms from a shared codebase.

### Local Database Integration

SQLite is integrated directly into the application using `sqflite`.

### Application Architecture

The project separates models, providers and views rather than placing the entire application inside a single screen or file.

### State Management

The dedicated provider layer demonstrates an attempt to isolate application state and operations from the UI.

### User Interface Development

Dedicated screens exist for vehicle creation and editing, together with reusable navigation components.

### Offline Capability

Because the application's data is stored locally, the core data workflow does not depend on network connectivity.

### Product Thinking

The project models a concrete domain instead of being only a technical demonstration.

---

## 📊 Project Maturity

| Area           | Current Implementation        | Future Opportunity                   |
| -------------- | ----------------------------- | ------------------------------------ |
| UI             | Flutter                       | Design system                        |
| Language       | Dart                          | Modern Dart                          |
| Persistence    | SQLite                        | Sync + cloud database                |
| State          | Provider-based structure      | Formal state-management architecture |
| Platforms      | Android / iOS / Web / Windows | Expand deployment                    |
| Testing        | Test directory                | Comprehensive test suite             |
| Backend        | Local-only                    | REST API                             |
| Authentication | Not central                   | OAuth / token-based auth             |
| CI/CD          | Not configured                | GitHub Actions                       |
| Localization   | Not implemented               | Multi-language support               |
| Offline        | Local persistence             | Offline-first synchronization        |

---

## 🎓 Learning Outcomes

This project demonstrates practical experience with:

* Dart
* Flutter
* Cross-platform application development
* SQLite
* Local data persistence
* CRUD operations
* State management
* Provider-based architecture
* Form development
* Input formatting
* Dynamic themes
* Reusable UI components
* Mobile application architecture
* Offline-capable application design

---

## 👨‍💻 Author

**Marcelo Torres**

Software Engineer | Full-Stack Developer | Technical Lead

GitHub: [@MarceloTTorres](https://github.com/MarceloTTorres)

---

## 📄 License

See the repository for licensing information.

---

## ⭐ About This Project

This project demonstrates how a relatively small Flutter application can combine **cross-platform development, local relational persistence, application state management and reusable UI architecture** into a complete mobile application.

Its natural evolution is toward an **offline-first architecture with cloud synchronization, automated testing, modern state management and CI/CD**, making it a strong foundation for demonstrating modern mobile engineering practices.

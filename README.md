# Intern_Project

This Flutter application provides a complete user management experience. It showcases how to:
- Manage state effectively using the BLoC pattern
- Integrate with external APIs to fetch and manage data
- Implement infinite scrolling and search functionality
- Organize the project using clean architecture principles for scalability and maintainability

🚀 Project Overview

This app is built as part of a Flutter developer assessment. It fetches user data from the DummyJSON API and displays it in a scrollable, searchable list. Upon selecting a user, the app shows detailed information including their posts and todos. A screen is also provided to create local posts.


<details>

<summary>✨ Key Features</summary>

- User listing with infinite scroll and real-time search
- Detailed user profiles with posts and todos
- Create post screen (local only)
- BLoC pattern for clean and scalable state management
- Error handling and loading indicators
- Organized project structure following best practices

</details>

💠 Setup Instructions

Clone the repository:

```ruby
git clone https://github.com/rishipatel125/flutter-user-management.git
cd flutter-user-management
```


Install dependencies:

```ruby
flutter pub get
```

Run the app:

```ruby
flutter run
```


💡 Ensure you have Flutter SDK installed. Use flutter doctor to verify your setup.

# 📁 Project Structure

This Flutter application follows a clean architecture pattern with BLoC state management. Below is an overview of the main directories and their purposes:

## 🏗️ Architecture Overview

```
lib/
├── blocs/          # State Management Layer
├── models/         # Data Models
├── repositories/   # Data Access Layer
├── services/       # External API Integration
├── screens/        # UI Presentation Layer
├── widgets/        # Reusable UI Components
├── utils/          # Helper Functions & Constants
└── main.dart       # Application Entry Point
```

## 📂 Directory Details

### `blocs/`
**Business Logic Components (BLoC)**
- Manages application state and business logic
- Organized by feature modules:
  - `user/` - User-related state management
  - `post/` - Post creation and management logic
  - `todo/` - Todo item state handling

### `models/`
**Data Models**
- Defines the structure of core entities
- Contains model classes for:
  - `User` - User entity with properties and methods
  - `Post` - Post data structure
  - `Todo` - Todo item model

### `repositories/`
**Data Access Layer**
- Abstracts data sources from business logic
- Contains repository interfaces and implementations
- Handles data fetching, caching, and persistence logic

### `services/`
**External Services**
- Manages API communication and HTTP requests
- Handles network operations and data serialization
- Integrates with external APIs and web services

### `screens/`
**UI Screens**
- Contains full-screen widgets and page layouts
- Main application screens include:
  - User listing and management
  - User detail views
  - Post creation interface
  - Navigation between different views

### `widgets/`
**Reusable Components**
- Custom UI components used across multiple screens
- Promotes code reusability and consistent design
- Contains common elements like buttons, cards, and form fields

### `utils/`
**Utilities & Helpers**
- Helper functions and utility classes
- Application constants and configuration
- Form validators and common functions
- Shared utilities used throughout the app

### `main.dart`
**Application Entry Point**
- Initializes the Flutter application
- Sets up app configuration, routing, and global providers
- Contains the root widget and app startup logic

## 🛠️ Tech Stack

- **Framework**: Flutter
- **State Management**: BLoC Pattern
- **Architecture**: Clean Architecture
- **Language**: Dart

🛆 State Management

Implemented using flutter_bloc. Each module (User, Post, Todo) has:  

Events: Trigger state transitions (e.g., FetchUsers, SearchUsers)  

States: Represent UI states (Loading, Loaded, Error)  

Bloc: Handles business logic  

📱 API

DummyJSON is used to simulate real-world backend interaction:

Users: https://dummyjson.com/users

Posts: https://dummyjson.com/posts/user/{userId}

Todos: https://dummyjson.com/todos/user/{userId}

Supports pagination (limit & skip) and search via query strings.


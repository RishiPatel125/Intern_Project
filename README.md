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

## 🛠️ State Management

This application uses the **BLoC (Business Logic Component)** pattern with `flutter_bloc` package for predictable state management. Each feature module follows a consistent structure:

### BLoC Architecture Pattern

```
Feature Module (User/Post/Todo)
├── Events     # User actions that trigger state changes
├── States     # Different UI states the app can be in
└── Bloc       # Business logic that processes events and emits states
```

### State Management Flow

**Events** → **Bloc** → **States** → **UI Updates**

#### 📤 Events (User Actions)
Events represent user interactions or system triggers:
- `FetchUsers` - Load user data from API
- `SearchUsers` - Filter users based on search query
- `LoadMoreUsers` - Pagination for additional users
- `CreatePost` - Submit new post data
- `UpdateTodo` - Modify todo item status

#### 📦 States (UI Representations)
States represent different conditions of the UI:
- `Loading` - Show loading indicators
- `Loaded` - Display data successfully
- `Error` - Handle and show error messages
- `Empty` - No data available state

#### ⚙️ Bloc (Business Logic)
The Bloc layer processes events and emits appropriate states:
- Handles API calls through repositories
- Manages data transformation and validation
- Implements error handling and loading states
- Maintains separation between UI and business logic

## 🌐 API Integration

The app integrates with **DummyJSON** API to simulate real-world backend interactions with RESTful endpoints.

### API Endpoints

| Feature | Endpoint | Description |
|---------|----------|-------------|
| **Users** | `https://dummyjson.com/users` | Fetch user list with pagination |
| **Posts** | `https://dummyjson.com/posts/user/{userId}` | Get posts by specific user ID |
| **Todos** | `https://dummyjson.com/todos/user/{userId}` | Retrieve todos for a user |

### API Features

#### 🔍 Search Functionality
```
GET /users/search?q={query}
```
- Real-time search across user data
- Filters by name, email, or username
- Debounced search to optimize API calls

#### 📄 Pagination Support
```
GET /users?limit={limit}&skip={skip}
```
- **limit**: Number of items per page (default: 10)
- **skip**: Number of items to skip for pagination
- Infinite scroll implementation for better UX

#### 🔧 Query Parameters
- `q` - Search query string
- `limit` - Items per page (pagination)
- `skip` - Offset for pagination
- `select` - Specific fields to return

### API Response Handling

The app handles various API scenarios:
- ✅ **Success responses** - Parse and display data
- ❌ **Error handling** - Network errors, timeouts, 404s
- ⏳ **Loading states** - Show appropriate loading indicators
- 🔄 **Retry mechanisms** - Allow users to retry failed requests

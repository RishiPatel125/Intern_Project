# 🚀 Flutter User Management App

A comprehensive Flutter application demonstrating modern mobile development practices with clean architecture, state management, and API integration.

## 📋 Project Overview

This Flutter application serves as a complete **user management solution** built as part of a Flutter developer assessment. The app demonstrates professional-level implementation of core mobile development concepts including state management, API integration, and user interface design.

### 🎯 Purpose & Goals

The application showcases expertise in:
- **State Management** - Implementing BLoC pattern for predictable and scalable state handling
- **API Integration** - Seamless integration with external REST APIs for data fetching and management
- **User Experience** - Infinite scrolling, real-time search, and responsive UI design
- **Architecture** - Clean architecture principles ensuring maintainability and scalability
- **Best Practices** - Following Flutter development standards and organized project structure

### 🌟 What This App Does

**Core Functionality:**
1. **Browse Users** - Fetches and displays user data from DummyJSON API in an intuitive, scrollable interface
2. **Search & Filter** - Real-time search functionality to quickly find specific users
3. **User Details** - Comprehensive user profiles showing personal information, posts, and todo items
4. **Content Creation** - Local post creation feature for user-generated content
5. **Seamless Navigation** - Smooth transitions between different app sections

### 🏗️ Technical Implementation

**Architecture Highlights:**
- **Clean Architecture** - Separation of concerns with distinct layers for UI, business logic, and data
- **BLoC Pattern** - Reactive state management ensuring predictable app behavior
- **Repository Pattern** - Abstracted data access layer for flexible data source management
- **Responsive Design** - Optimized for different screen sizes and orientations

## ✨ Key Features

<details>
<summary><strong>🔍 User Management & Search</strong></summary>

- **Infinite Scroll Pagination** - Smooth loading of user lists without performance issues
- **Real-time Search** - Instant filtering as you type with debounced API calls
- **Advanced Filtering** - Search across multiple user fields (name, email, username)
- **Loading States** - Professional loading indicators and skeleton screens
- **Error Handling** - Graceful error messages with retry functionality

</details>

<details>
<summary><strong>👤 User Profile System</strong></summary>

- **Detailed User Profiles** - Comprehensive view of user information and statistics
- **Related Content Display** - User's posts and todos organized in clean, readable format
- **Interactive Elements** - Expandable sections and smooth animations
- **Data Relationships** - Clear connection between users and their content

</details>

<details>
<summary><strong>📝 Content Management</strong></summary>

- **Local Post Creation** - Form validation and local storage of user-generated posts
- **Rich Text Input** - Support for formatted text and content creation
- **Draft Management** - Save and continue editing posts
- **Content Validation** - Client-side validation with helpful error messages

</details>

<details>
<summary><strong>🛠️ Technical Excellence</strong></summary>

- **BLoC State Management** - Predictable state transitions with clear event/state flow
- **Clean Code Architecture** - Organized, maintainable, and testable codebase
- **API Integration** - Robust HTTP client with error handling and retry logic
- **Performance Optimization** - Efficient rendering and memory management
- **Responsive Design** - Adaptive UI that works across different device sizes

</details>

<details>
<summary><strong>🎨 User Experience</strong></summary>

- **Intuitive Navigation** - Clear app flow with logical screen transitions
- **Visual Feedback** - Loading states, success messages, and error indicators
- **Accessibility Support** - Screen reader compatibility and touch-friendly interface
- **Consistent Design** - Unified visual language throughout the application

</details>

## 🎓 Learning Outcomes

This project demonstrates proficiency in:

- **Flutter Framework** - Advanced widget composition and lifecycle management
- **State Management** - BLoC pattern implementation for complex app states
- **API Integration** - RESTful API consumption with proper error handling
- **Code Organization** - Clean architecture principles and separation of concerns
- **User Experience Design** - Creating intuitive and responsive mobile interfaces
- **Testing Practices** - Unit testing for business logic and widget testing for UI components

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

<table>
<tr>
<td width="50%" align="center">
  <img src="https://github.com/user-attachments/assets/5017aa6b-d350-4af1-9e1c-649aaa218437" alt="project" width="200">
</td>
<td width="50%">

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

</td>
</tr>
</table>
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

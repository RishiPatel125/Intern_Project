# Intern_Project

Flutter User Management App

A Flutter application demonstrating user management functionality using the BLoC pattern, API integration, infinite scrolling, and clean architecture principles.

🚀 Project Overview

This app is built as part of a Flutter developer assessment. It fetches user data from the DummyJSON API and displays it in a scrollable, searchable list. Upon selecting a user, the app shows detailed information including their posts and todos. A screen is also provided to create local posts.

✨ Key Features

User listing with infinite scroll and real-time search

Detailed user profiles with posts and todos

Create post screen (local only)

BLoC pattern for clean and scalable state management

Error handling and loading indicators

Organized project structure following best practices

💠 Setup Instructions

Clone the repository:

git clone https://github.com/rishipatel125/flutter-user-management.git
cd flutter-user-management

Install dependencies:

flutter pub get

Run the app:

flutter run

💡 Ensure you have Flutter SDK installed. Use flutter doctor to verify your setup.

🧱 Project Architecture

The project follows a Clean Architecture approach, separating concerns across layers and using the flutter_bloc package for state management.

lib/ ├── blocs/   
│ ├── user/  
│ ├── post/  
│ └── todo/  
├── models/  
├── repositories/ 
├── services/  
├── screens/ 
├── widgets/  
├── utils/  
└── main.dart  

# Description of Key Folders:  

### blocs/  
Contains BLoC logic for managing state.  
└─ Subfolders for user, post, and todo modules.  

### models/  
Defines data models for User, Post, and Todo entities.  

### repositories/  
Repository interfaces and their implementations for data access.  

### services/  
Handles API integrations and HTTP calls.  

### screens/  
Comprises UI screens such as user list, user detail, and create post.  

### widgets/  
Includes reusable UI components.  

### utils/  
Utility helpers, such as constants and validators.  

### main.dart  
The main entry point of the application.  

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


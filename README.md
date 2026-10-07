# To-Do App

A modern and user-friendly To-Do application built with **Flutter and Dart**, designed to help users organize and manage their daily tasks efficiently.

The application provides user authentication, task management, profile customization, password management, language settings, and Firebase integration for storing and managing user data.

The project also uses **Cubit for state management**, **Provider for dependency management**, and **Cloud Firestore** as the cloud database.

## Project Overview

The To-Do App is designed to provide a simple and organized way for users to manage their daily tasks.

Users can create an account, log in, add tasks, edit existing tasks, manage their profile, change their password, and customize the application language.

The application is connected to Firebase for authentication and cloud data storage, allowing user-related data and tasks to be managed through the backend.

The main application flow is:

```text
Splash Screen
      ↓
Start Screen
      ↓
Authentication
      ↓
Home
      ↓
Today's Tasks
      ↓
Add / Edit Tasks
      ↓
Profile & Settings
```

## Features

### 🔐 Authentication

The application provides a complete authentication flow using Firebase Authentication.

Users can:

* Create a new account
* Log in to their account
* Log out of the application
* Manage their account information
* Change their password

Authentication state is handled through dedicated Cubits and repository-based data handling.

### 📝 Task Management

The application allows users to manage their daily tasks.

Users can:

* Add new tasks
* View their tasks
* Edit existing tasks
* Manage today's tasks
* Update task information

Task-related operations are connected to the application's backend data layer.

### 📅 Today's Tasks

Users can access a dedicated screen for viewing their tasks for the current day.

The Today Tasks feature provides a focused view of the tasks that need to be managed throughout the day.

### ✏️ Edit Tasks

Users can open an existing task and update its information through the Edit Task screen.

This provides a convenient way to keep task information up to date without recreating the task.

### 👤 Profile Management

The application includes a profile section where users can manage their account-related settings.

Users can:

* Update their name
* Change their password
* Access language settings
* Manage their account preferences

### 🌐 Language Support

The application includes language management functionality.

Users can access the language settings screen and select their preferred application language.

Language state is handled using a dedicated `LanguageCubit`.

### ☁️ Firebase Integration

The application uses Firebase services for backend functionality.

Firebase is initialized when the application starts and is used for:

* User authentication
* Cloud Firestore data storage
* User-related data management
* Task data management

The project uses:

* Firebase Authentication
* Cloud Firestore
* Firebase Core

## State Management

The application uses **Cubit** from the Flutter BLoC package to manage application state.

Different Cubits are responsible for different application features, including:

* `LoginCubit`
* `RegisterCubit`
* `HomeCubit`
* `UpdateNameCubit`
* `ChangePasswordCubit`
* `LanguageCubit`
* `AddTaskCubit`
* `TodayTasksCubit`

This approach separates UI responsibilities from application logic and makes the code easier to organize and maintain.

### Cubit Flow

```text
User Interaction
       ↓
     Cubit
       ↓
 Business Logic
       ↓
 Repository
       ↓
 Firebase
       ↓
 State Changes
       ↓
      UI
```

The UI reacts to state changes emitted by the corresponding Cubits.

## Application Architecture

The project follows a feature-oriented structure that separates the application's presentation, state management, and data layers.

A simplified architecture can be represented as:

```text
┌──────────────────────────┐
│      Flutter UI          │
│    Screens & Widgets     │
└────────────┬─────────────┘
             │
             ▼
┌──────────────────────────┐
│          Cubit           │
│   State & Business Logic │
└────────────┬─────────────┘
             │
             ▼
┌──────────────────────────┐
│       Repository         │
│      Data Handling       │
└────────────┬─────────────┘
             │
             ▼
┌──────────────────────────┐
│         Firebase         │
│ Auth & Cloud Firestore   │
└──────────────────────────┘
```

The project also uses **Provider** to provide the authentication repository to the required Cubits.

## Technologies Used

### Frontend

* Flutter
* Dart
* Material Design

### State Management

* Flutter BLoC
* Cubit

### Dependency / Data Management

* Provider
* Repository Pattern

### Backend & Database

* Firebase Authentication
* Cloud Firestore
* Firebase Core

### Local Storage

* Hive
* Hive Flutter

### UI & Localization

* Flutter ScreenUtil
* Flutter SVG
* Google Fonts
* Flutter Localizations

### Development Tools

* Android Studio
* Visual Studio Code
* Git
* GitHub

## Flutter Concepts Applied

This project applies several important Flutter concepts, including:

* Stateless Widgets
* Stateful Widgets
* Custom Widgets
* Widget composition
* Screen navigation
* Named routes
* Forms and validation
* User interaction
* Firebase integration
* Cloud Firestore
* Firebase Authentication
* Cubit state management
* Provider
* Repository Pattern
* Dependency management
* Local storage
* Localization
* Responsive UI
* Screen adaptation
* Asset management
* SVG assets
* Theme and styling
* Asynchronous programming
* Separation of UI and business logic

## Application Screens

The application contains several screens covering the complete user journey:

```text
Splash Screen
      ↓
Start Screen
      ↓
Login / Register
      ↓
Home Screen
      ↓
Today's Tasks
      ↓
Add Task
      ↓
Edit Task
      ↓
Profile
      ↓
Update Name
      ↓
Change Password
      ↓
Language Settings
```

### Splash Screen

The application starts with a splash screen before navigating to the appropriate starting point.

### Start Screen

The start screen introduces the application and provides access to the authentication flow.

### Login & Registration

Users can either log in to an existing account or create a new account.

### Home Screen

The home screen acts as the main entry point after authentication and provides access to the application's main functionality.

### Today's Tasks

Users can view and manage their daily tasks from the dedicated task screen.

### Add Task

Users can create new tasks and add them to their task list.

### Edit Task

Existing tasks can be opened and updated whenever changes are needed.

### Profile

The profile section provides access to account and application settings.

### Account Settings

Users can update their name and change their password.

### Language Settings

Users can select their preferred application language.

## Application Flow

### 1. Starting the Application

```text
Application Launch
       ↓
Splash Screen
       ↓
Start Screen
```

### 2. Authentication

```text
Start Screen
       ↓
Login / Register
       ↓
Firebase Authentication
       ↓
Home
```

### 3. Task Management

```text
Home
 ↓
Today's Tasks
 ↓
Add Task
 ↓
Task List
 ↓
Edit Task
```

### 4. Profile Management

```text
Home
 ↓
Profile
 ↓
Update Name
 ↓
Change Password
 ↓
Language Settings
```

## Error & State Handling

Cubit is used to manage the different states of application operations.

A typical operation can follow:

```text
Initial
   ↓
Loading
   ↓
Success
```

or:

```text
Initial
   ↓
Loading
   ↓
Error
```

This allows the UI to react appropriately while authentication, task operations, or other backend operations are being performed.

## Responsive UI

The application uses `flutter_screenutil` to support responsive sizing and screen adaptation.

The project initializes ScreenUtil with a design size of:

```text
375 × 812
```

This helps maintain consistent UI proportions across different screen sizes.

## Project Structure

The project follows a feature-based organization.

A simplified representation is:

```text
lib/
│
├── features/
│   │
│   ├── cubit/
│   │   ├── login_cubit.dart
│   │   ├── register_cubit.dart
│   │   ├── home_cubit.dart
│   │   ├── add_task_cubit.dart
│   │   ├── today_tasks_cubit.dart
│   │   ├── language_cubit.dart
│   │   ├── update_name_cubit.dart
│   │   └── change_password_cubit.dart
│   │
│   ├── data/
│   │   └── repository/
│   │
│   └── view/
│       ├── authentication/
│       ├── starting app/
│       └── tasks/
│
├── firebase_options.dart
└── main.dart
```

The exact project structure may evolve as additional features are added.

## Installation & Setup

### Prerequisites

Make sure you have the following installed:

* Flutter SDK
* Dart SDK
* Android Studio or Visual Studio Code
* Android Emulator or a physical device
* Git
* A Firebase project

Check your Flutter installation:

```bash
flutter doctor
```

### Clone the Repository

```bash
git clone https://github.com/Rawda11-Mohamed/to_do_app.git
```

Navigate to the project:

```bash
cd to_do_app
```

### Install Dependencies

Run:

```bash
flutter pub get
```

### Firebase Configuration

The project uses Firebase Authentication and Cloud Firestore.

To configure Firebase for your own Firebase project:

1. Create a Firebase project.
2. Add the required Flutter platforms.
3. Enable Firebase Authentication.
4. Enable Cloud Firestore.
5. Configure the Flutter application using FlutterFire.
6. Make sure the generated Firebase configuration matches your project.

Then run:

```bash
flutterfire configure
```

### Run the Application

Connect an Android device or start an emulator, then run:

```bash
flutter run
```

## Learning Outcomes

This project provided practical experience with:

* Flutter application development
* Dart programming
* Firebase Authentication
* Cloud Firestore
* CRUD-style task management
* Cubit and Flutter BLoC
* Provider
* Repository Pattern
* Dependency management
* Firebase integration
* Local storage with Hive
* Localization
* Responsive UI using ScreenUtil
* Named route navigation
* Form handling and validation
* State-driven UI
* Separation of UI and business logic
* Feature-based project organization

## Future Improvements

The application can be extended with additional features such as:

* Task completion tracking
* Task priorities
* Task categories
* Due dates and reminders
* Notifications
* Task search
* Task filtering and sorting
* Dark mode
* More advanced profile management
* Additional localization options
* Improved offline support

## Conclusion

The **To-Do App** is a Flutter-based task management application that combines a clean mobile interface with Firebase backend services.

The project demonstrates practical implementation of **authentication, task management, Cloud Firestore, Cubit state management, Provider, repository-based data handling, localization, and responsive UI development**.

It provides a strong example of building a complete Flutter application while applying real-world concepts such as state management, backend integration, data persistence, and separation of responsibilities.
## 📸 Screenshots
<img width="720" height="786" alt="image" src="https://github.com/user-attachments/assets/58e32492-5e08-46dc-841a-f5d586309977" />

<img width="720" height="787" alt="image" src="https://github.com/user-attachments/assets/85386867-8956-4908-ac67-ecb0b8b85efa" />
<img width="718" height="781" alt="image" src="https://github.com/user-attachments/assets/9ed06d4c-270e-45e2-b09d-9cdcef6e2bfb" />
<img width="720" height="796" alt="image" src="https://github.com/user-attachments/assets/1dcb591b-8fff-420f-8a46-b0bdeebc3c37" />
<img width="720" height="795" alt="image" src="https://github.com/user-attachments/assets/eadfd645-42be-4b12-b37c-73aafd16ef7e" />
<img width="720" height="566" alt="image" src="https://github.com/user-attachments/assets/182b588f-8e06-4ee9-a25c-c438c97bb27c" />

<table>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/d2f28d55-10f4-4be3-b6e1-0c5c495fd0cd" width="220" height="480" style="object-fit: cover;"></td>
    <td><img src="https://github.com/user-attachments/assets/f4a6bcae-694b-4a83-b0f2-22950c513664" width="220" height="480" style="object-fit: cover;"></td>
    <td><img src="https://github.com/user-attachments/assets/a5ab15d3-a16f-49b7-8b93-85dc460b9e66" width="220" height="480" style="object-fit: cover;"></td>
    <td><img src="https://github.com/user-attachments/assets/08c62a87-ce2d-488c-bc4f-9493454fbb47" width="220" height="480" style="object-fit: cover;"></td>
  </tr>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/a925a9de-69e4-44e4-8cdc-5b216e989621" width="220" height="480" style="object-fit: cover;"></td>
    <td><img src="https://github.com/user-attachments/assets/2338b401-4c22-4e8d-bf47-a6be8390586e" width="220" height="480" style="object-fit: cover;"></td>
    <td><img src="https://github.com/user-attachments/assets/e2c00744-d687-4eaf-bccf-125ba5f904b2" width="220" height="480" style="object-fit: cover;"></td>
    <td><img src="https://github.com/user-attachments/assets/29a6e62a-8b06-4fda-85a6-ad53d0ccf26e" width="220" height="480" style="object-fit: cover;"></td>
  </tr>
  <tr>
</td>
      

    <td><img src="https://github.com/user-attachments/assets/29a6e62a-8b06-4fda-85a6-ad53d0ccf26e" width="220" height="480" style="object-fit: cover;"></td>
    <td><img src="https://github.com/user-attachments/assets/e2c00744-d687-4eaf-bccf-125ba5f904b2" width="220" height="480" style="object-fit: cover;"></td>
  </tr>
</table>

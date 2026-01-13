# 📱 TaskFlow - Task Management App

A beautiful and fully functional task management application built with Flutter as part of Week 3 Final Project for Flutter Internship Program.

![Flutter](https://img.shields.io/badge/Flutter-3.5.4-02569B?style=flat&logo=flutter)
![Dart](https://img.shields.io/badge/Dart-3.0+-0175C2?style=flat&logo=dart)
![License](https://img.shields.io/badge/License-MIT-green)

## ✨ Features

### Core Functionality
- ✅ **Create Tasks** - Add new tasks with title and optional description
- ✅ **Read Tasks** - View all tasks in an organized list
- ✅ **Update Tasks** - Edit existing task details
- ✅ **Delete Tasks** - Remove tasks with confirmation dialog
- ✅ **Mark Complete** - Toggle task completion status with visual feedback
- ✅ **Data Persistence** - All data saved locally using SharedPreferences
- ✅ **User Authentication** - Login and signup with form validation

### Additional Features
- 🎨 **Modern UI Design** - Beautiful gradient theme with smooth animations
- 📊 **Progress Tracking** - Visual dashboard showing task completion percentage
- 🔐 **Form Validation** - Comprehensive input validation on all forms
- 🎭 **Splash Screen** - Animated welcome screen with app branding
- 🔄 **Smooth Transitions** - Page transitions with fade and slide animations
- 📑 **Task Organization** - Separate sections for active and completed tasks
- 🌟 **Empty State** - Helpful message when no tasks exist
- 🚪 **Logout** - Secure logout functionality

## 📸 Screenshots

| Splash Screen | Login Screen | Home Screen |
|--------------|--------------|-------------|
| Animated splash with logo | User authentication | Task list with progress |

| Add Task | Edit Task | Task Completed |
|----------|-----------|----------------|
| Create new tasks | Modify existing tasks | Mark tasks as done |

## 🚀 Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:

- **Flutter SDK** (3.0.0 or higher) - [Install Flutter](https://docs.flutter.dev/get-started/install)
- **Dart SDK** (comes with Flutter)
- **Git** - [Install Git](https://git-scm.com/downloads)
- **IDE** - VS Code, Android Studio, or IntelliJ IDEA
- **Chrome** (for web testing) or an Android/iOS emulator

### Check Your Flutter Installation

```bash
flutter doctor
```

This command checks your environment and displays a report of the status of your Flutter installation.

## 📥 Installation

### Step 1: Clone the Repository

```bash
git clone https://github.com/AlizayAhmed/TaskFlow.git
cd TaskFlow
```

### Step 2: Install Dependencies

```bash
flutter pub get
```

This will download all the required packages specified in `pubspec.yaml`.

### Step 3: Run the App

#### For Chrome (Web)
```bash
flutter run -d chrome
```

#### For Android Emulator
```bash
flutter run
```

#### For iOS Simulator (macOS only)
```bash
flutter run -d ios
```

#### For Windows Desktop
```bash
flutter run -d windows
```

### Step 4: Hot Reload

While the app is running, you can make changes to the code and:
- Press `r` in the terminal for hot reload
- Press `R` for hot restart
- Press `q` to quit

## 📂 Project Structure

```
taskflow/
├── lib/
│   └── main.dart                 # Main application file with all code
├── android/                      # Android-specific files
├── ios/                          # iOS-specific files
├── web/                          # Web-specific files
├── windows/                      # Windows-specific files
├── test/                         # Test files
├── .gitignore                    # Git ignore file
├── pubspec.yaml                  # Project dependencies
└── README.md                     # This file
```

### Code Structure in main.dart

```
main.dart
├── TaskManagementApp            # Root widget with theme configuration
├── SplashScreen                 # Animated splash screen
├── LoginScreen                  # User login interface
├── SignUpScreen                 # User registration interface
├── HomeScreen                   # Main task list view
├── Task                         # Task data model
├── TaskCard                     # Individual task widget
├── AddTaskDialog                # Dialog for creating tasks
└── EditTaskDialog               # Dialog for editing tasks
```

## 📦 Dependencies

### pubspec.yaml

```yaml
name: taskflow
description: "A beautiful task management Flutter application."
publish_to: 'none'
version: 1.0.0+1

environment:
  sdk: ^3.5.4

dependencies:
  flutter:
    sdk: flutter
  cupertino_icons: ^1.0.8
  shared_preferences: ^2.2.2

dev_dependencies:
  flutter_test:
    sdk: flutter
  flutter_lints: ^4.0.0

flutter:
  uses-material-design: true
```

### Package Details

| Package | Version | Purpose |
|---------|---------|---------|
| **flutter** | SDK | Core Flutter framework |
| **cupertino_icons** | ^1.0.8 | iOS-style icons |
| **shared_preferences** | ^2.2.2 | Local data persistence |

### Installing/Updating Dependencies

```bash
# Get dependencies
flutter pub get

# Upgrade dependencies
flutter pub upgrade

# Check for outdated dependencies
flutter pub outdated
```

## 🎯 How to Use

### 1. First Launch
- The app opens with an animated splash screen
- After 3 seconds, you're redirected to the login screen

### 2. Sign Up / Login
- **New User**: Tap "Sign Up" and create an account with:
  - Full Name
  - Email (must contain @)
  - Password (minimum 6 characters)
  - Confirm Password
- **Existing User**: Enter email and password, then tap "Sign In"

### 3. Home Screen
- View your task list with progress tracking
- See completion percentage in the progress card
- Tasks are organized into:
  - **Active Tasks** - Tasks you haven't completed yet
  - **Completed Tasks** - Tasks marked as done

### 4. Add a Task
- Tap the **"+ Add Task"** floating action button
- Enter task title (required)
- Add description (optional)
- Tap **"Add Task"** to save

### 5. Complete a Task
- Tap the **circular checkbox** next to any task
- The task moves to the "Completed Tasks" section
- Progress percentage updates automatically

### 6. Edit a Task
- Tap on any **task card**
- Edit the title or description
- Tap **"Update"** to save changes

### 7. Delete a Task
- Tap the **delete icon** (🗑️) on any task
- Confirm deletion in the dialog
- Task is permanently removed

### 8. Logout
- Tap the **logout icon** in the top-right corner
- Confirm logout in the dialog
- You'll be redirected to the login screen

## 💾 Data Persistence

The app uses **SharedPreferences** to store data locally on your device.

### Stored Data

| Key | Type | Description |
|-----|------|-------------|
| `isLoggedIn` | bool | User login status |
| `userName` | String | User's full name |
| `userEmail` | String | User's email address |
| `tasks` | String (JSON) | Array of all tasks |

### Task Data Model

```dart
{
  "id": "1705234567890",              // Unique timestamp ID
  "title": "Complete Flutter App",     // Task title (required)
  "description": "Add all features",   // Task description (optional)
  "isCompleted": false,                // Completion status
  "createdAt": "2026-01-14T10:30:00Z" // ISO 8601 timestamp
}
```

### Data Operations

- **Save**: Automatically saves after every add, edit, delete, or status change
- **Load**: Loads on app startup
- **Clear**: Cleared on logout (except tasks persist)

### Viewing Stored Data

#### Windows
```
%LOCALAPPDATA%\Google\Chrome\User Data\Default\Local Storage
```

#### Android
```bash
adb shell
run-as com.example.taskflow
cd app_flutter
ls
```

## 🧪 Testing

### Manual Testing Checklist

#### Authentication
- [ ] Splash screen displays for 3 seconds
- [ ] Login form validates empty fields
- [ ] Login form validates email format
- [ ] Login form validates password length (min 6 chars)
- [ ] Sign up form validates all fields
- [ ] Sign up validates password match
- [ ] Successful login navigates to home screen
- [ ] Logout returns to login screen

#### Task Management
- [ ] Can add task with title only
- [ ] Can add task with title and description
- [ ] Cannot add task without title
- [ ] Task appears immediately after creation
- [ ] Can edit task title
- [ ] Can edit task description
- [ ] Can toggle task completion status
- [ ] Can delete task with confirmation
- [ ] Canceling delete keeps the task

#### Data Persistence
- [ ] Tasks persist after app restart
- [ ] Login status persists after app restart
- [ ] User name displays correctly after restart
- [ ] Completed tasks remain completed after restart
- [ ] Progress percentage is accurate after restart

#### UI/UX
- [ ] Progress card shows correct percentage
- [ ] Active tasks section shows incomplete tasks only
- [ ] Completed tasks section shows completed tasks only
- [ ] Empty state displays when no tasks exist
- [ ] Animations are smooth
- [ ] Forms show validation errors
- [ ] Success/error messages display correctly

### Debugging

```bash
# Run in debug mode with verbose output
flutter run -v

# Run with specific device
flutter run -d chrome

# Check for errors
flutter analyze

# Format code
flutter format .
```

### Flutter DevTools

```bash
# Open DevTools
flutter pub global activate devtools
flutter pub global run devtools
```

## 🏗️ Building for Production

### Android APK

```bash
# Build APK
flutter build apk --release

# Build App Bundle (for Google Play)
flutter build appbundle --release
```

Output location: `build/app/outputs/flutter-apk/app-release.apk`

### iOS

```bash
# Build for iOS (requires macOS)
flutter build ios --release
```

### Web

```bash
# Build for web
flutter build web --release
```

Output location: `build/web/`

### Windows

```bash
# Build for Windows
flutter build windows --release
```

Output location: `build/windows/runner/Release/`

## 👤 Author

**Your Name**
- GitHub: [@yourusername](https://github.com/yourusername)
- Email: alizay1206@gmail.com
- LinkedIn: [Your LinkedIn](https://linkedin.com/in/yourprofile)

## 📊 Version History

- **v1.0.0** (January 14, 2026)
  - Initial release
  - All core features implemented
  - Splash screen added
  - Authentication system added

---

**Submission Date**: January 14, 2026

**Course**: Flutter Development Internship - Week 3 Final Project

**Made with ❤️ using Flutter**

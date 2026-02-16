# 🏋️ Flutter Fitness Management App

A Flutter-based fitness management application that allows users to manage exercise records, schedules, diet recommendations, and exercise analysis.  
The app uses the **Provider** package for state management.

---

## 📱 Features

- ✅ View today’s exercise records
- 🔥 Calculate total calories burned
- 📊 View exercise analysis
- 💡 Receive exercise recommendations
- 🗓 Manage daily schedules
- 🍽 Get diet recommendations
- ⚙ Configure diet settings
- ➕ Add new exercise records
- ⏰ Get recommended exercise time based on schedule

---

## 🏗 Project Structure

```
lib/
│
├── main.dart
├── user_data_provider.dart
├── home_page.dart
├── schedule_list_screen.dart
├── exercise_card.dart
└── widgets/
    └── custom_button.dart
```

---

## 🧠 State Management

This project uses the **Provider** package for global state management.

### UserDataProvider

`UserDataProvider` is responsible for managing:

- Exercise records
- User schedules
- Calorie calculations
- Exercise time recommendations

### Key Methods

- `calculateTotalCalories()`  
  → Calculates total calories burned for the day

- `recommendExerciseTime()`  
  → Recommends available exercise time based on saved schedules

- `removeExercise(index)`  
  → Removes an exercise record

- `deleteSchedule(index)`  
  → Deletes a schedule entry

- `dailyExercises`  
  → List of exercise records

- `schedules`  
  → List of schedule entries

---

# 🏠 HomePage Overview

`HomePage` serves as the main dashboard of the application.

### Components

## 1️⃣ Total Calories Card

Displays:
- Total calories burned today
- Button to navigate to exercise progress screen
- Button to receive exercise recommendations

---

## 2️⃣ Recommended Exercise Time

```dart
final TimeOfDay? recommendedTime = userData.recommendExerciseTime();
```

- Displays recommended workout time if available
- Shows a fallback message if no free time exists

---

## 3️⃣ Exercise List

Built using `ListView.builder`.

Each item includes:
- Exercise name
- Calories burned
- Date
- Delete button

---

## 4️⃣ FloatingActionButton

Navigates to the schedule input screen.

---

## 5️⃣ Bottom Navigation Buttons

| Button | Function |
|--------|----------|
| Input Info | Navigate to BMI input screen |
| Diet Recommendation | Navigate to diet recommendation screen |
| Diet Settings | Navigate to diet settings screen |
| Add Exercise | Navigate to add exercise screen |

---

# 🗓 ScheduleListScreen Overview

Displays saved user schedules.

### Features

## 1️⃣ Schedule List

```dart
final schedules = userData.schedules;
```

Each schedule displays:
- Activity name
- Start time
- End time
- Delete button

---

## 2️⃣ Delete Schedule

```dart
userData.deleteSchedule(index);
```

Removes the selected schedule from the list.

---

## 3️⃣ Recommended Exercise Time

Displays suggested workout time calculated from the schedule data.

---

# 🧩 CustomButton Widget

Reusable button component.

### Properties

- `label` → Button text
- `icon` → IconData
- `onPressed` → Callback function

---

# 📊 Data Model Examples

### Exercise Data

```dart
class ExerciseData {
  final String name;
  final double calories;
  final String date;
}
```

---

### Schedule Data

```dart
{
  "activity": "Class",
  "start": TimeOfDay(hour: 9, minute: 0),
  "end": TimeOfDay(hour: 11, minute: 0)
}
```

---

# 🔁 Navigation Structure

The app uses **Named Routes** for navigation.

### Main Routes

- `/bmi_input`
- `/diet_recommendation`
- `/diet_settings`
- `/add_exercise`
- `/progress`
- `/exercise_recommendation`
- `/schedule_input`

---

# 🚀 Getting Started

```bash
flutter pub get
flutter run
```

---

# 🛠 Technologies Used

- Flutter
- Dart
- Provider
- Material Design

---

# 📌 Future Improvements

- Firebase integration
- Graph-based statistics
- Calendar UI integration
- Dark mode support
- Material 3 upgrade

---

# 👨‍💻 Purpose

This project was developed for learning Flutter state management and implementing health-related application features.

---

# 📄 License

This project is for educational purposes.

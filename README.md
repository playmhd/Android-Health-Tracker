# Health Tracker

A simple Android app for tracking daily calories, protein, and carbohydrates. Set your calorie limit, log your three daily meals, and see your progress at a glance.

**Version:** 1.0.0  
**Minimum Android version:** Android 8.0 (API 26)

## Features

- **Daily calorie limit:** Choose your own target and change it anytime.
- **Three daily meals:** Log breakfast, lunch, and dinner.
- **Nutrition tracking:** Enter calories, protein, and carbohydrates for each meal.
- **Automatic totals:** See your total calories and nutrients update as you save meals.
- **Calorie progress bar:** View calories consumed, remaining calories, and the amount over your limit.
- **Edit and remove meals:** Correct entries and automatically update the totals.
- **Daily history:** Browse previous dates while keeping each day's meals separate.
- **Offline storage:** Save your journal locally without an account or internet connection.
- **Form recovery:** Keep unfinished meal entries when rotating the screen.

## Meal entries

Each day includes three meal slots:

1. Breakfast
2. Lunch
3. Dinner

For each meal, enter:

- Meal name (optional)
- Calories in kcal
- Protein in grams
- Carbohydrates in grams

Nutrition values are entered manually. Decimal values are supported, and `0` is valid for a nutrient.

## How to use

1. Tap **Set target** and enter your daily calorie limit.
2. Tap a meal card and enter its nutrition values.
3. Tap **Save meal** to update the totals and progress bar.
4. Tap a saved meal to edit or remove it.
5. Use the date arrows to view previous days.

A new day starts with empty meal entries while previous records remain saved. Changing your calorie target updates the comparison for all dates.

The progress bar stops at 100%, while the actual calorie total and amount over your target remain visible.

## Build and run

### Requirements

- JDK 17
- Android SDK Platform 37.0
- Android SDK Build Tools 36.0.0
- An Android phone or emulator running Android 8.0 or later

### Android Studio

1. Clone or download the repository.
2. Open the project folder in Android Studio.
3. Install the required SDK components and let Gradle sync.
4. Select the `app` run configuration and your device or emulator.
5. Click **Run**.

### Command line

Set `JAVA_HOME` to your JDK 17 installation and configure your Android SDK path in `local.properties`.

Build on Windows:

```powershell
.\gradlew.bat :app:assembleDebug
```

Build on macOS or Linux:

```bash
chmod +x gradlew
./gradlew :app:assembleDebug
```

The APK is generated at:

```text
app/build/outputs/apk/debug/app-debug.apk
```

## Installation

Transfer the generated APK to your Android phone and open it to install. Allow installation from the app used to open the file when prompted.

Alternatively, connect a device with USB debugging enabled and run:

```bash
adb install -r app/build/outputs/apk/debug/app-debug.apk
```

## Technology

- Java
- Android native UI components
- SharedPreferences for local storage
- BigDecimal for accurate decimal nutrition calculations
- Gradle for the Android project build

## Testing

Run the core checks on Windows:

```powershell
.\scripts\test-core.ps1
```

The first version passed **51 core checks** covering nutrient totals, meal editing and removal, input validation, calorie progress, and journal encoding. The development APK compiled successfully and its signature was verified. Visual interaction testing on a phone or emulator was still pending.

## Data storage

Meals and the calorie target are stored locally on the device. Android backup is disabled for journal data. Uninstalling the app clears its saved entries.


# Tip Calculator

A modern Android application built using Java, designed to calculate tips and total bill amounts based on user input. This app adheres to Material Design principles and incorporates updated UI/UX practices.

---

## Features

- **Dynamic Input:** Users can input a bill amount and adjust the tip percentage using a SeekBar.
- **Real-time Calculations:** Automatically updates the tip amount and total bill as the user modifies the values.
- **Modern UI:** Utilizes Material Design with modern styling elements like elevations and consistent spacing.
- **Responsive Design:** Ensures compatibility across devices with various screen sizes.

---

## Screenshots

*(Add screenshots of the app interface here)*

---

## How It Works

### 1. Bill Amount Input
Users enter the bill amount through an `EditText` field. The input is formatted as currency dynamically using `NumberFormat`.

### 2. Tip Adjustment
A `SeekBar` allows users to select a tip percentage between 0% and 100%. The current percentage is displayed using a `TextView`.

### 3. Calculation
The app calculates:
- Tip amount: `billAmount * percent`
- Total bill: `billAmount + tip`

The results are displayed in formatted `TextView` components.

---

## Code Highlights

### MainActivity
The core functionality is implemented in `MainActivity.java`. Key components include:

#### Formatters:
```java
private static final NumberFormat currencyFormat = NumberFormat.getCurrencyInstance();
private static final NumberFormat percentFormat = NumberFormat.getPercentInstance();
```
These formatters ensure the display adheres to local currency and percentage standards.

#### Dynamic Updates:
- **Bill Amount:** `TextWatcher` updates the calculations when the user changes the input.
- **Tip Percentage:** `OnSeekBarChangeListener` updates the tip percentage and recalculates the totals.

#### Example:
```java
private void calculate() {
    percentTextView.setText(percentFormat.format(percent));
    double tip = billAmount * percent;
    double total = billAmount + tip;
    tipTextView.setText(currencyFormat.format(tip));
    totalTextView.setText(currencyFormat.format(total));
}
```

---

## Modern Enhancements

While the project is inspired by earlier practices, it integrates modern Android development principles:

- **Material Design:**
  - Elevation and padding provide a clean and structured layout.
  - Consistent color themes enhance usability and aesthetics.
- **Improved Accessibility:**
  - Larger touch targets for interactive elements.
  - Clear contrast ratios for better visibility.

- **Best Practices:**
  - Use of `AppCompatActivity` for better backward compatibility.
  - Refactored layouts for maintainability and readability.

---

## Tech Stack

- **Language:** Java
- **Framework:** Android SDK
- **Design:** Material Design
- **Dependencies:** None (native Android components)

---

## Setup and Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/tip-calculator.git
   ```

2. Open the project in Android Studio.

3. Build and run the app on an emulator or a physical device.

---

## Directory Structure
```
TipCalculator/
|-- app/
    |-- src/
        |-- main/
            |-- java/com/deitel/tipcalculator/MainActivity.java
            |-- res/
                |-- layout/activity_main.xml
                |-- values/
                    |-- styles.xml
                    |-- strings.xml
```

---

## Acknowledgments

- Based on the "Tip Calculator" project from **Deitel's Android for Programmers**.
- Modernized with inspiration from Google's [Material Design Guidelines](https://material.io/design).

---

## License

This project is licensed under the MIT License. See the LICENSE file for details.


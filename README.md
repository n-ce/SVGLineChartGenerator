# Line Chart Scalable Vector Graphics (SVG) Generator

This project is a lightweight, zero-dependency utility designed to dynamically render a line chart directly into an HTML document using **pure JavaScript and SVG**. It serves as a proof-of-concept and development sandbox for creating interactive data visualizations without relying on external charting libraries (like Chart.js or D3.js).

## 🚀 Key Features

* **Zero Dependencies:** Uses only native JavaScript and standard HTML/CSS/SVG elements.
* **Dynamic Rendering:** The chart updates in real-time as the user provides input data.
* **Scalable Vector Graphics (SVG):** Ensures the chart is infinitely scalable and retains clarity at any resolution.
* **Chronological Tracking:** Optimized for tracking data over sequential points in time (e.g., attempts, commits, or intervals).

## 💡 How It Works

The generator leverages basic math to transform an array of data values into SVG coordinates, which are then used to draw the chart elements.

| Component | Function | Mechanism |
| :--- | :--- | :--- |
| **Data Input** | Accepts a simple **comma-separated string of numerical values** from an input field. | Real-time parsing and filtering via the `oninput` event. |
| **Coordinate Scaling** | Maps the numerical data range (Min to Max) to the fixed dimensions of the SVG container (`viewBox`). | Uses proportional scaling factors ($\text{Scale}_X, \text{Scale}_Y$) to place points accurately. |
| **Line Drawing** | Connects all calculated coordinates to form the trend line. | Constructs the SVG **`<path>`** element's `d` attribute using **`M`** (MoveTo) and **`L`** (LineTo) commands. |
| **Interactivity** | Provides simple data feedback on hover. | Embeds the native SVG **`<title>`** element within data point markers. |

## 📊 Axis Definition

The chart is built on a two-dimensional grid defined as follows:

| Axis | Interpretation | Data Source |
| :--- | :--- | :--- |
| **X-Axis (Chronological Index)** | Represents the sequential order of the data points (Attempt 1, 2, 3...). | The **index position** of the data value within the input array. |
| **Y-Axis (Magnitude)** | Represents the measured value or magnitude of the data point. | The raw **numerical value** itself, scaled vertically from zero to the maximum recorded value.

## 🛠️ Usage

To test the generator:

1.  Save the code as a single `.html` file.
2.  Open the file in any modern web browser.
3.  Modify the data in the input field (e.g., `10, 25, 18, 40, 32`). The chart will immediately adjust its scale, axes, and line path to reflect the new data set.

This utility demonstrates a highly efficient method for incorporating simple, self-rendered visualizations into any web environment, avoiding external libraries entirely.

# Academic Weather Dashboard

## Summary
This project delivers a responsive and informative web-based weather dashboard. It visually represents city temperatures using a Chart.js bar graph and calculates the average temperature from a given dataset. Designed for academic submission, the application emphasizes clean code, clear UI, and robust functionality, meeting specified requirements for data visualization and calculation.

## Setup
To set up and run this project, follow these simple steps:
1.  **Save the File**: Download or copy the provided `index.html` file to your local computer.
2.  **No Additional Dependencies**: This project is self-contained. The `weather.json` data is simulated directly within the HTML's JavaScript for ease of deployment, negating the need for separate JSON files or server-side setup. The Chart.js library is loaded directly from a Content Delivery Network (CDN).
3.  **Open in Browser**: Simply open the `index.html` file with any modern web browser (e.g., Google Chrome, Mozilla Firefox, Microsoft Edge, Safari).

## Usage
Once you open `index.html` in your web browser:
1.  The page will automatically load and display a title, followed by a bar chart.
2.  The bar chart (`#temp-chart`) illustrates the temperatures of several global cities, with each bar representing a city's temperature in degrees Celsius.
3.  Below the chart, an element (`#avg-temp`) will display the calculated average temperature across all cities presented in the dataset.
The application is fully static and does not require any user interaction beyond initial loading.

## Main Code Logic
The core functionality resides within the JavaScript section of `index.html`, executed after the Document Object Model (DOM) is fully loaded:

1.  **Data Simulation**: An array of JavaScript objects, `weatherData`, is used to simulate the `weather.json` attachment. Each object contains a `city` name and its corresponding `temperature`.
2.  **Data Extraction**: The `map` array method is employed to efficiently extract two separate arrays: `cities` (for chart labels) and `temperatures` (for chart data).
3.  **Average Temperature Calculation**:
    *   The `reduce` method sums all temperature values.
    *   The total sum is then divided by the number of entries (`temperatures.length`) to compute the average.
    *   The `toFixed(1)` method is used to format the average temperature to one decimal place, ensuring clean presentation.
    *   Robustness is added by checking if `temperatures.length > 0` to prevent division by zero in case of empty data.
4.  **Display Average Temperature**: The calculated `averageTemperature` is dynamically updated into the `<p>` element with the ID `avg-temp`, providing immediate feedback to the user.
5.  **Chart Initialization (Chart.js)**:
    *   The `canvas` element with the ID `temp-chart` is selected, and its 2D rendering context (`ctx`) is obtained.
    *   A new `Chart` instance is created, configured as a `'bar'` type.
    *   The `data` object within the chart configuration binds the `cities` array to `labels` and the `temperatures` array to the `data` property of the `datasets`.
    *   Custom `backgroundColor` and `borderColor` arrays are defined for visual appeal.
    *   The `options` object enhances user experience with `responsive: true` (for adaptability to screen size), `maintainAspectRatio: false` (to allow flexible chart sizing), a descriptive `title`, and custom `scales` with appropriate labels for both X and Y axes, including unit suffixes for clarity.

## License
This project is made available under the **MIT License**. This permissive license allows for broad use, modification, and distribution, both for commercial and non-commercial purposes, provided the original copyright notice and permission notice are included in all copies or substantial portions of the software.

```
MIT License

Copyright (c) 2023 [Your Name/Institution]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## Contact
For any inquiries, feedback, or further discussion regarding this project, please feel free to reach out:
[Your Name/Email Address/GitHub Profile Link] (e.g., student@example.com / github.com/yourusername)
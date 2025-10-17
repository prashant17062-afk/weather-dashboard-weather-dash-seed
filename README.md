# Academic Grading System & City Information Dashboard

## Summary
This project provides a simple, web-based tool designed for academic purposes, featuring a student grade calculator and an interactive city information display. The grade calculator allows users to input a numeric score (0-100) and instantly see the corresponding letter grade (A, B, C, D, F) and a pass/fail status. A new enhancement in this version includes a city filter dropdown, enabling users to select a city and view its associated humidity percentage.

## Setup
To set up and run this application, no special server environment or complex installation is required.
1.  **Save the file:** Save the provided `index.html` content into a file named `index.html`.
2.  **Open in browser:** Simply open the `index.html` file using any modern web browser (e.g., Chrome, Firefox, Edge, Safari).

The application is entirely client-side, using HTML, CSS, and JavaScript.

## Usage

### Student Grade Calculator
1.  **Enter Grade:** Locate the "Enter Numeric Grade (0-100)" input field.
2.  **Input Value:** Type a numeric grade between 0 and 100 into the field. A default value of 75 is pre-filled.
3.  **Calculate:** Click the "Calculate Letter Grade" button.
4.  **View Results:** The "Input Grade," "Letter Grade," and "Grade Status" (Pass/Fail) will update automatically in the "Result Section" below the button. Invalid inputs (non-numeric, or outside 0-100) will display an error message.

### City Information Filter
1.  **Select City:** Find the "Select a City" dropdown filter.
2.  **Choose an Option:** Click on the dropdown and select one of the available cities (e.g., London, New York, Tokyo).
3.  **View Info:** The "Selected City" and "Humidity" fields in the "Info Section" will immediately update to display the name of the chosen city and its corresponding humidity percentage.

## Main Code Logic

The application's functionality is driven by two primary JavaScript functions, executed on `DOMContentLoaded` to ensure the page elements are fully loaded before interaction.

### `calculateGrade()`
This function is responsible for the grade calculation logic:
1.  **Element References:** It first queries the DOM to get references to the input field (`#grade-input`) and the output `<span>` elements (`#display-grade`, `#letter-grade`, `#grade-status`).
2.  **Input Parsing & Validation:** It parses the input value as an integer. Robust validation checks if the input is a valid number and falls within the 0-100 range. If not, appropriate error messages are displayed.
3.  **Grade Logic:** Using a series of `if-else if` statements, it determines the letter grade (A, B, C, D, F) based on standard academic grading scales.
    *   90-100: A
    *   80-89: B
    *   70-79: C
    *   60-69: D
    *   0-59: F
4.  **Status Determination:** Simultaneously, it assigns a "Pass" or "Fail" status, where grades D and above are considered "Pass," and F is "Fail."
5.  **Display Update:** Finally, it updates the `textContent` of the respective `<span>` elements to display the calculated grade and status.

### `initializeCityFilter()`
This new function manages the city information display:
1.  **Element References:** It retrieves references to the city filter dropdown (`#city-filter`) and the display `<span>` elements (`#selected-city`, `#city-humidity`).
2.  **`updateCityInfo(selectedOption)` Helper:** A nested helper function is defined to handle the actual updating of the display. It extracts the city name from the `textContent` of the selected `<option>` element and retrieves the humidity percentage from a custom `data-humidity` HTML attribute associated with that option. It then updates the `textContent` of `#selected-city` and `#city-humidity`.
3.  **Event Listener:** An `eventListener` is attached to `#city-filter` for the `change` event. Whenever a new option is selected in the dropdown, this listener triggers, identifying the new selection and calling `updateCityInfo()` to refresh the display.
4.  **Initial State:** Upon `DOMContentLoaded`, `initializeCityFilter()` is called. It retrieves the initially selected option from the dropdown and uses `updateCityInfo()` to populate the city information display immediately when the page loads, ensuring a consistent user experience.

## License
This project is licensed under the MIT License. Please refer to the `index.html` file for the full license text.

## Contact
For any questions or feedback, please contact:
[Your Name/Organization Name]
[Your Contact Email/GitHub Profile]
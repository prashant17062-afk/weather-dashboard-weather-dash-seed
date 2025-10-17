# Weather Dashboard

A simple web application that displays city temperatures in a bar chart using Chart.js. It loads data from a `weather.json` file and calculates the average temperature.

## Setup

1.  Create a `weather.json` file in the same directory as `index.html`. The file should contain an array of objects, where each object represents a city and its temperature. Example:

    ```json
    [
      {"city": "London", "temperature": 15},
      {"city": "New York", "temperature": 22},
      {"city": "Tokyo", "temperature": 28}
    ]
    ```

2.  Open `index.html` in your web browser.

## Usage

The dashboard will display a bar chart showing the temperature for each city in the `weather.json` file. The average temperature is also displayed below the chart.

## License

MIT License
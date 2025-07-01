COMPANY NAME : CODTECH IT SOLUTIONS

NAME : S NIVILA

INTERN ID : CT04DF2638

DOMAIN : JAVA

DURATION : 4 WEEKS

MENTOR : NEELA SANTHOSH

🌐 Task 2: REST API Integration

The objective of this task is to build a simple and functional Java-based REST client that fetches real-time weather data from a public REST API and displays it in a clean, structured format.
The project demonstrates how to perform HTTP GET requests in Java using the HttpClient class (Java 11+), handle network responses, and parse JSON responses using the org.json library. It combines core Java concepts with real-world API integration, making it an ideal beginner project to understand RESTful communication.
In this task, a Java application consumes a **public REST API** to fetch and display structured weather data based on user input. The application uses:

- `HttpURLConnection` to send an HTTP GET request
- A public weather API (like OpenWeatherMap)
- A JSON parser (`org.json` or similar) to interpret the response
- Displaying relevant information like weather conditions, temperature, and humidity in a structured format

Users are prompted to enter a city name, and the application fetches the corresponding weather conditions, temperature, and humidity. This task demonstrates how to handle HTTP requests and parse JSON in Java.

🎯 Objective

• Build a Java application that:

• Sends HTTP GET requests to an external REST API.

• Parses JSON data received from the server.

• Extracts and displays key weather details in a user-friendly format.

• Learn how to work with:

• HttpClient, HttpRequest, and HttpResponse

• org.json for JSON parsing

• Java exception handling for network errors

• Real-time user input and dynamic URL generation

📌 Technologies Used

• Java SE 11+

• HTTP Networking (java.net.http)

• JSON Parsing (org.json)

• Scanner for console input

• BlueJ IDE or any modern Java IDE

🌐 API Used

• OpenWeatherMap API

• Endpoint used: https://api.openweathermap.org/data/2.5/weather

• Parameters: q (city), appid (API key), units (metric)

📂 Files

WeatherApp.java: The main Java program that connects to the API and displays weather data.

Dependencies: org.json JAR (must be included in your project).

🔍 Functional Overview

The program performs the following key operations:

1. User Input
Prompts the user to enter the city name via the console.

Scanner scanner = new Scanner(System.in);
System.out.print("Enter city name: ");
String city = scanner.nextLine().trim();

2. HTTP Request Construction
Constructs a URL with the API key and city.
Uses Java 11’s HttpClient and HttpRequest to send the request.

HttpClient client = HttpClient.newHttpClient();
HttpRequest request = HttpRequest.newBuilder().uri(URI.create(url)).build();

3. JSON Parsing
Parses the JSON response using org.json.JSONObject.
Checks for API errors using the cod field.
Extracts data like city name, temperature, feels-like temperature, and weather description.

JSONObject json = new JSONObject(responseBody);
String cityName = json.getString("name");
JSONObject main = json.getJSONObject("main");
double temp = main.getDouble("temp");
double feelsLike = main.getDouble("feels_like");
String description = json.getJSONArray("weather").getJSONObject(0).getString("description");

4. Formatted Output
Displays the fetched weather details in a human-readable format:

--- Weather Report ---
City: Chennai
Temperature: 31.5 °C
Feels Like: 34.1 °C
Weather: clear sky

5. Error Handling
Catches common issues like invalid API keys or city names.
Handles exceptions gracefully and displays error messages.

System.out.println("API Error: " + message);
System.out.println("❌ Error fetching weather data: " + e.getMessage());

✅ Output



📦 How to Run (Using BlueJ)

• Open BlueJ and create a new project.

• Add the WeatherApp.java file to the project.

• Add json-20210307.jar to your project library (for org.json).

• Compile the program.

• Right-click the class and select void main(String[] args) to run.

• Enter a city name when prompted.

• View weather data in the console.

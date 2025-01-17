# Weather App Documentation

![image](https://github.com/user-attachments/assets/4e0bd5b5-7397-4fb4-8bd8-2295e4f4cee2)

---

## **Project Details**  

### Developer Information  
- **Name:** Rohit Navinchandra Kandpal  
- **Company:** CODTECH IT SOLUTIONS PVT. LTD.  
- **Employee ID:** CT08DHC  
- **Domain:** Full Stack Web Development  

### Internship Duration  
- **Start Date:** 20th December 2024  
- **End Date:** 20th January 2025  

### Mentor  
- **Name:** Neela Santhosh Kumar  

This project is part of my professional journey at CODTECH IT SOLUTIONS, showcasing my expertise in full-stack web development and dedication to building innovative solutions under expert guidance.  

---

## **Project Overview**

Welcome to the **Weather App** project!

This is an ongoing **weather information** application built with **Next.js** and **TailwindCSS**. The app is designed to provide users with **accurate, real-time weather details** for any city across the globe. The application fetches weather data, air quality information, and more to give a comprehensive view of the weather for any given location.

### **Current Status**
- The project is currently under **active development**.
- **Bug Fixes**: A few bugs are still being resolved.
- **Upcoming Features**: Several additional features are planned for future releases.

### **Goal**
The main objective of this project is to allow users to:
- View **current weather data** for any city.
- Access a **5-day weather forecast**.
- Check **air pollution levels** in any region.
- Enjoy a **responsive design**, accessible from both **desktop** and **mobile** devices.

---

## **Table of Contents**

1. **Getting Started**
2. **Project Structure**
3. **Environment Variables**
4. **Available Scripts**
5. **Features**
6. **API Endpoints**
7. **Known Issues**
8. **Contributing**
9. **License**
10. **Contact**

---

## **1. Getting Started**

To set up the project locally and start contributing or running it, follow the steps below.

### **Step-by-Step Instructions**

1. **Clone the Repository**  
   First, clone the repository to your local machine using the following command:
   ```bash
   git clone https://github.com/iamrohitkandpal/CODTECH_ADVANCE_TASK_01.git
   ```

2. **Navigate to the Project Folder**  
   Change into the project directory:
   ```bash
   cd weather-app
   ```

3. **Install Dependencies**  
   Run the following command to install all the necessary dependencies:
   ```bash
   npm install
   ```

4. **Run the Development Server**  
   Start the development server with this command:
   ```bash
   npm run dev
   ```

5. **Open the Application in a Browser**  
   Navigate to `http://localhost:3000` to see the app running locally.

---

## **2. Project Structure**

The project structure is organized to ensure that the code is modular and easy to maintain. Below is the structure of the project:

```
weather-app/
├── .next/                            # Build files and cache
├── app/                               # Main application files
│   ├── api/                           # API routes
│   ├── Components/                    # Reusable components
│   ├── context/                       # Context API for global state
│   ├── globals.css                    # Global CSS
│   ├── layout.tsx                     # Layout file
│   ├── page.tsx                       # Main page component
│   └── utils/                         # Utility functions
├── components/                        # UI Components
│   └── ui/                            # Custom UI components like buttons, dialogs, etc.
├── lib/                               # Libraries and helper functions
├── public/                            # Static assets (images, fonts)
├── .env                               # Environment variables
├── .gitignore                         # Git ignore file
├── next.config.mjs                    # Next.js configuration
├── package.json                       # Project dependencies
├── tailwind.config.ts                 # Tailwind CSS configuration
└── tsconfig.json                      # TypeScript configuration
```

---

## **3. Environment Variables**

To run the app locally, you'll need an **API Key** from **OpenWeatherMap**. Follow these steps:

1. Go to [OpenWeatherMap](https://openweathermap.org/api) and sign up for an API key.
2. Create a `.env` file in the root directory of the project.
3. Add your API key as follows:

```
OPENWEATHERMAP_API_KEY=your_api_key_here
```

---

## **4. Available Scripts**

Here are the available npm scripts to manage the project:

- **`npm run dev`**: Starts the development server at `http://localhost:3000`.
- **`npm run build`**: Builds the application for production.
- **`npm run start`**: Runs the production build of the app.
- **`npm run lint`**: Lints the codebase for any style or syntax issues.

---

## **5. Features**

The **Weather App** includes several exciting features:

- **Current Weather**: Get the latest weather details for any city.
- **5-Day Forecast**: View the weather forecast for the upcoming 5 days.
- **Air Quality Data**: Access information about the air quality in your location.
- **Responsive Design**: The app is optimized for both **desktop** and **mobile devices**, ensuring a seamless experience across all devices.

---

## **6. API Endpoints**

Here are the core API endpoints for interacting with the weather data.

### **1. Geocoded Data**

- **Endpoint**: `/api/geocoded`
- **Method**: `GET`
- **Description**: Fetches geocoded data (latitude and longitude) for a given city.
  
  **Query Parameters**:
  - `search` (string): The city to search for.

  **Example Request**:
  ```bash
  curl -X GET "http://localhost:3000/api/geocoded?search=London"
  ```

  **Example Response**:
  ```json
  [
    {
      "name": "London",
      "lat": 51.5074,
      "lon": -0.1278,
      "country": "GB"
    }
  ]
  ```

---

### **2. Weather Data**

- **Endpoint**: `/api/weather`
- **Method**: `GET`
- **Description**: Fetches weather data for a given latitude and longitude.

  **Query Parameters**:
  - `lat` (number): Latitude of the location.
  - `lon` (number): Longitude of the location.

  **Example Request**:
  ```bash
  curl -X GET "http://localhost:3000/api/weather?lat=51.5074&lon=-0.1278"
  ```

  **Example Response**:
  ```json
  {
    "weather": [
      {
        "description": "clear sky",
        "icon": "01d"
      }
    ],
    "main": {
      "temp": 289.92,
      "feels_like": 287.15,
      "temp_min": 288.71,
      "temp_max": 290.93,
      "pressure": 1013,
      "humidity": 82
    }
  }
  ```

---

### **3. Air Pollution Data**

- **Endpoint**: `/api/pollution`
- **Method**: `GET`
- **Description**: Fetches air pollution data for a given latitude and longitude.

  **Query Parameters**:
  - `lat` (number): Latitude of the location.
  - `lon` (number): Longitude of the location.

  **Example Request**:
  ```bash
  curl -X GET "http://localhost:3000/api/pollution?lat=51.5074&lon=-0.1278"
  ```

  **Example Response**:
  ```json
  {
    "list": [
      {
        "main": {
          "aqi": 1
        },
        "components": {
          "co": 201.94,
          "no": 0.01,
          "no2": 0.02,
          "o3": 61.19,
          "so2": 0.05,
          "pm2_5": 0.5,
          "pm10": 0.54,
          "nh3": 0.01
        }
      }
    ]
  }
  ```

---

## **7. Known Issues**

Currently, the app is under development, and there are a few issues to be addressed:

- **API Key Not Loading**: Ensure the `.env` file is correctly set up. The server must be restarted after any changes.
- **UI Bugs**: Some components may not render correctly on all devices.
- **Missing Features**: A few features are still under development, and might not be fully functional.

---

## **8. Contributing**

We welcome contributions to the project! If you'd like to help, follow these steps:

1. **Fork the repository**: Click the "Fork" button on the repository page.
2. **Create a new branch**: 
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. **Make your changes and commit**:
   ```bash
   git commit -m "Add your commit message"
   ```
4. **Push to your branch**:
   ```bash
   git push origin feature/your-feature-name
   ```
5. **Create a Pull Request**: Open a pull request on GitHub.

---

## **9. License**

This project is licensed under the **MIT License**. For more information, see the LICENSE file.

---

Thank you for your interest in the Weather App! Stay tuned for more updates.

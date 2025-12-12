# Weather App

A native iOS weather application built with Swift and UIKit that allows users to check current weather conditions for any city worldwide using the OpenWeatherMap API.

## Features

- 🌤️ **Real-time Weather Data**: Get current weather information for any city
- 📍 **City Search**: Enter any city name to fetch weather details
- 💾 **Favorite City**: Save your favorite city using the toggle switch for quick access
- 📊 **Detailed Weather Information**: View temperature, min/max temperatures, weather description, and conditions
- 🎨 **Modern UI**: Clean and intuitive user interface with custom components
- 🔄 **Loading Indicators**: Visual feedback during API requests
- ⚠️ **Error Handling**: Comprehensive error handling with user-friendly alerts

## Requirements

- iOS 13.0 or later
- Xcode 12.0 or later
- Swift 5.0 or later
- Active internet connection
- OpenWeatherMap API key

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/DURODOLA-ABDULKABIR/Weather-App2
cd Weather-App2
```

### 2. Open the Project

Open `WeatherApp.xcodeproj` in Xcode.

### 3. Configure API Key

The app uses OpenWeatherMap API. The API key is currently configured in `WeatherApp/Others/Constants.swift`:

```swift
struct AppID {
    static let appID = "fd6189e087550e277f1ff2a8c51423ab"
}
```

**⚠️ Important**: For production use, consider:
- Moving the API key to a secure configuration file
- Using environment variables or a secrets manager
- Not committing API keys to version control

To get your own API key:
1. Sign up at [OpenWeatherMap](https://openweathermap.org/api)
2. Get your free API key
3. Replace the `appID` value in `Constants.swift`

### 4. Build and Run

1. Select your target device or simulator
2. Press `Cmd + R` or click the Run button
3. The app will launch on your device/simulator

## Project Structure

```
WeatherApp/
├── Assets.xcassets/          # App icons and color assets
├── CustomComponents/          # Reusable UI components
│   ├── CustomButtons/
│   └── CustomTextFields/
├── Delegates/                # App and Scene delegates
├── Model/                    # Data models (WeatherResponse, Weather, Main, etc.)
├── NetworkService/           # Network layer and API communication
│   ├── NetWorkService.swift
│   ├── NetworkRoute.swift
│   └── NetworkError.swift
├── Others/                   # Constants and error definitions
├── Protocols/                # Protocol definitions
├── Storyboards/              # UI storyboards
├── UserDefaultManager/       # UserDefaults wrapper for persistence
├── ViewControllers/          # View controllers
│   ├── HomeViewController/
│   └── WeatherDetailsViewController/
└── ViewModel/                # Business logic and network coordination
```

## Architecture

The app follows a **MVVM (Model-View-ViewModel)** architecture pattern:

- **Model**: Data structures (`AppModel.swift`) representing weather data
- **View**: View controllers and storyboards for UI presentation
- **ViewModel**: `WeatherDetailsNetwork` class handling business logic and API calls
- **Protocols**: `WeatherDetailsProtocol` for delegate-based communication

### Key Components

- **NetworkService**: Singleton service handling all HTTP requests
- **WeatherDetailsNetwork**: ViewModel class coordinating API calls and data transformation
- **UserDefault**: Helper class for persisting favorite city
- **Custom Components**: Reusable UI components (buttons, text fields)

## Usage

1. **Launch the App**: Open the app on your device
2. **Enter City Name**: Type the name of any city in the text field
3. **Get Weather**: Tap the "Get Details" button to fetch weather information
4. **Save Favorite City**: Toggle the switch to save your current city for quick access next time
5. **View Details**: The app displays:
   - Current temperature
   - Minimum and maximum temperatures
   - Weather description
   - Weather icon (clouds, rain, or sunny)
   - Current date
   - City name

## API Information

The app uses the [OpenWeatherMap Current Weather API](https://openweathermap.org/current):
- **Base URL**: `https://api.openweathermap.org/data/2.5/weather?`
- **Units**: Metric (Celsius)
- **Response Format**: JSON

## Technologies Used

- **Swift**: Programming language
- **UIKit**: iOS UI framework
- **Storyboards**: Visual UI design
- **URLSession**: Network requests
- **Codable**: JSON parsing
- **UserDefaults**: Local data persistence
- **OpenWeatherMap API**: Weather data source

## Error Handling

The app handles various error scenarios:
- Empty city name validation
- Network errors
- API errors (400, 404, 500)
- Decoding errors
- Unknown errors

All errors are displayed to users via alert controllers with clear messages.

## Testing

The project includes:
- **WeatherAppTests**: Unit tests
- **WeatherAppUITests**: UI tests

Run tests using `Cmd + U` in Xcode.

## Future Enhancements

Potential improvements:
- Location-based weather detection
- Weather forecast (5-day/7-day)
- Multiple city support
- Weather history
- Dark mode optimization
- Unit and integration tests
- Dependency injection for better testability

## License

This project is available for use as specified in the repository.

## Author

Created by durodola

---

**Note**: Make sure you have an active internet connection to fetch weather data. The app requires network access to communicate with the OpenWeatherMap API.

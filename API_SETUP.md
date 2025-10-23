# API Setup Guide for Packing Planner

This guide will help you connect your Packing Planner to real external data sources for weather information and socket types.

## Weather API Setup (WeatherAPI.com)

The app uses **WeatherAPI.com** to fetch real weather forecasts for your trips.

### Steps to Set Up:

1. **Get a Free API Key**
   - Visit [WeatherAPI.com](https://www.weatherapi.com/signup.aspx)
   - Sign up for a free account (no credit card required)
   - Copy your API key from the dashboard

2. **Add the API Key to Your App**
   - Open `index.html` in a text editor
   - Find line **1731** (search for `WEATHER_API_KEY`)
   - Replace `'YOUR_WEATHER_API_KEY_HERE'` with your actual API key:
   ```javascript
   const WEATHER_API_KEY = 'your_actual_api_key_here';
   ```
   - Save the file

3. **Test It Out**
   - Open the app in your browser
   - Create a new trip with a destination
   - Check the Outfit Planner section to see real weather forecasts!

### What You Get:
- ✅ Real weather forecasts for up to 3 days (free tier)
- ✅ Temperature in both Fahrenheit and Celsius
- ✅ Weather condition emojis (sun, clouds, rain, snow, etc.)
- ✅ Automatic fallback to default values for dates beyond the forecast

---

## Socket Type Information (REST Countries API)

The app uses the **REST Countries API** to fetch electrical socket/plug information.

### No Setup Required!
- ✅ The REST Countries API is completely free and requires no API key
- ✅ Automatically fetches plug types and voltage information
- ✅ Works for most countries worldwide

### What You Get:
- ⚡ Electrical socket types (e.g., Type A/B, Type C, Type G)
- ⚡ Voltage information (e.g., 220V, 110V)
- ⚡ Automatic fallback to regional defaults if country not found

---

## Features Without API Key

Even without setting up the Weather API, the app will still work perfectly:
- Socket information will still be fetched automatically
- Weather will show default values (☀️ 72°F)
- All other features work normally

---

## Troubleshooting

### Weather Not Showing:
1. Make sure you've added your API key on line 1731
2. Check the browser console (F12) for any error messages
3. Verify your API key is active at [WeatherAPI.com Dashboard](https://www.weatherapi.com/my/)

### Socket Information Not Showing:
1. Try using the full country name (e.g., "Paris, France" instead of just "Paris")
2. The REST Countries API may be temporarily down - it will fall back to regional defaults

### API Rate Limits:
- **WeatherAPI.com Free Tier**: 1 million calls/month
- **REST Countries API**: No rate limits

---

## Privacy & Data

- All trip data is stored locally in your browser's `localStorage`
- API calls are made directly from your browser to the API providers
- No data is sent to any third-party servers except the weather and country APIs

---

## Support

For issues with:
- **WeatherAPI**: Visit [WeatherAPI Documentation](https://www.weatherapi.com/docs/)
- **REST Countries API**: Visit [REST Countries Documentation](https://restcountries.com/)
- **Packing Planner App**: Check the code comments in `index.html`

---

Enjoy planning your trips with real weather data! 🌍✈️


import requests

api_key = '7202567f40985ccf058d0a170568c226'

user_input = input("Enter city: ")

weather_data = requests.get(
    f"https://api.openweathermap.org/data/2.5/weather?q={user_input}&units=metric&APPID={api_key}")

weather =weather_data.json()['weather'][0]['main']
temp = round(weather_data.json()['main']['temp'])

print(f"The weather in {user_input} is: {weather}")
print(f"The temperature in {user_input} is: {temp}°C")

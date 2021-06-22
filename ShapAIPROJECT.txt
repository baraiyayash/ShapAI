import requests
from datetime import datetime

api_key = 'ba7fdbf71559536a7ac6a2daaaa47918'
location = input("enter the city name:")

complete_api_link = "http://api.openweathermap.org/data/2.5/weather?q=bhavnagar&appid=ba7fdbf71559536a7ac6a2daaaa47918"
api_link = requests.get(complete_api_link)
api_data = api_link.json()


temp_city =((api_data['main']['temp'])-273.15)
weather_desc = api_data['weather'][0]['description']
hmdt = api_data['main']['humidity']
wind_spd = api_data['wind']['speed']
date_time = datetime.now().strftime("%d %b %Y | %I:%M:%S %p")


print("current temperature is: {:.2f} deg c".format(temp_city))
print("current weather desc:",weather_desc)
print("current humidity:",hmdt,'%')
print("current wind speed:",wind_spd,'kmph')


    

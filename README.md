# python-rest-api-json
Python program to fetch and display data from a public REST API using the requests library and process JSON responses.
import requests

# Public API URL
url = "https://jsonplaceholder.typicode.com/users"

try:
    # Sending GET request
    response = requests.get(url)

    # Convert response to JSON
    data = response.json()

    print("User Details:\n")

    # Displaying user data
    for user in data:
        print("ID:", user["id"])
        print("Name:", user["name"])
        print("Email:", user["email"])
        print("City:", user["address"]["city"])
        print("-" * 30)

except requests.exceptions.RequestException as e:
    print("Error:", e)

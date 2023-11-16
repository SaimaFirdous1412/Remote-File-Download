# Remote-File-Download
import requests

def download_file(url, local_filename):
    response = requests.get(url)
    
    if response.status_code == 200:
        with open(local_filename, 'wb') as file:
            file.write(response.content)
        print(f"File downloaded successfully to {local_filename}")
    else:
        print(f"Failed to download file. Status code: {response.status_code}")

# Example usage:
url = "https://example.com/yourfile.txt"
local_filename = "yourfile.txt"
download_file(url, local_filename)

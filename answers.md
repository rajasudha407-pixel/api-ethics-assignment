import requests
import os

API_URL = "https://healthstats-api.example.com/records"
API_KEY = os.getenv("API_KEY")

records = []
for page in range(1, 101):
    response = requests.get(API_URL, params={"page": page, "key": API_KEY})
    time.sleep(1)
    data = response.json()
cleaned_records = []
for record in data["results"]:
    cleaned = {
        "age": calculate_age(record["date_of_birth"]),
        "zip_prefix": record["zip_code"][:3],
        "job_title": record["job_title"],
        "diagnosis_notes": deidentify_text(record["diagnosis_notes"])
    }
    cleaned_records.append(cleaned)
save_to_database(cleaned_records)

# NYC Taxi Dataset

The datasets used in this project come from the official NYC Taxi & Limousine Commission (TLC) Trip Record Data:

🔗 [NYC TLC Trip Record Data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)

---

## 📥 Download Instructions
The full datasets (Yellow, Green, FHV, High Volume FHV) are **not included in this repo** due to size. This project used Green
Taxi Trips data.
You can download them directly from the NYC TLC website:

- **Yellow Taxi Trips** → [Download](https://www.nyc.gov/assets/tlc/downloads/pdf/data_dictionary_trip_records_yellow.pdf)  
- **Green Taxi Trips** → [Download](https://www.nyc.gov/assets/tlc/downloads/pdf/data_dictionary_trip_records_green.pdf)  
- **For-Hire Vehicles (FHV)** → [Download](https://www.nyc.gov/assets/tlc/downloads/pdf/data_dictionary_trip_records_fhv.pdf)  

---

⚠️ **Note**: In production, data ingestion is done dynamically via **Azure Data Factory** pipelines, pulling directly from these URLs instead of manual downloads.


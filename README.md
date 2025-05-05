# Airline Data Management and Analysis Using Power BI

## 📌 Project Overview
This project leverages **Power BI** to analyze airline operations data, providing actionable insights for improving efficiency and customer satisfaction. The analysis covers flight schedules, passenger details, and ticket booking trends.



## 🎯 Objectives
- Clean and transform raw airline data using **Power Query**.
- Model data relationships for comprehensive analysis.
- Perform calculations using **DAX** to derive key metrics.
- Create interactive dashboards for real-time decision-making.
- Deploy the solution with **Row-Level Security (RLS)** and scheduled refreshes.



## 📂 Datasets
1. **Flight_Information**:  
   - Columns: `FlightID`, `FlightNumber`, `Airline`, `Destination`, `Status`.  
2. **Passenger_Information**:  
   - Columns: `PassengerID`, `FlightID`, `SeatNumber`.  
3. **Ticket_Information**:  
   - Columns: `TicketID`, `FlightID`, `BookingStatus`.  



## 🛠️ Methodology
### 1. **Data Preparation & Cleaning**
- Removed duplicates and handled missing values.
- Formatted columns (e.g., `FlightID` as Whole Number, `Status` as Text).
- **Tool Used**: Power Query Editor.  

### 2. **Data Modeling**
- Established **one-to-many** relationships using `FlightID` as the key.
- Verified referential integrity and cross-filter direction.  

### 3. **Enhanced Data Insights**
- Added a conditional column (`Flight_Performance`) to classify flights as **"Best"** (On Time) or **"To Be Improved"** (Delayed/Cancelled).
- Extracted flight numbers using **"Column from Examples"**.  

### 4. **DAX Calculations**
- **Key Measures**:
  - `Total_Passengers = COUNT(Passenger_Information[PassengerID])`
  - `Total_Tickets_Booked = COUNT(Ticket_Information[TicketID])`
  - `Best_Flights = FILTER(Flight_Information, Flight_Information[Flight_Performance] = "Best")`

### 5. **Visualization & Dashboard**
- **Charts**:
  - **Stacked Bar Chart**: Passenger count by airline.
  - **Donut Chart**: Ticket booking statuses.
  - **Heatmap**: Flights by airline and destination.
- **Interactive Features**:
  - Slicers for `Airline` and `Destination`.
  - Tooltips for detailed metrics.
  - Navigation buttons for airline-specific pages.  

### 6. **Power BI Service Deployment**
- Published to workspace **"AirDMA"**.
- Configured **Row-Level Security (RLS)** for `Airline A`.
- Set up **scheduled refresh** daily at 5 PM.  



## 📊 Key Insights
- **Airline D** had the highest passenger count (28).
- **Los Angeles** was the most popular destination (42 passengers).
- **22% of tickets** were in "Pending" status, indicating potential revenue leakage.  



## 🔧 Recommendations
1. Investigate delays for flights marked **"To Be Improved"**.
2. Optimize ticket confirmation processes to reduce **"Pending"** statuses.  



## 📦 Project Structure
```
├── Data/                    # Raw datasets (CSV/Excel)
├── PowerBI/                 # Power BI files (.pbix)
├── Documentation/           # Final report (PDF)
└── README.md                # Project overview
```



## 🚀 How to Use
1. **Open the `.pbix` file** in Power BI Desktop.
2. **Refresh data** if needed (ensure data source paths are correct).
3. Explore the **interactive dashboard** for insights.  

---

## 📜 License
This project is licensed under the MIT License.  

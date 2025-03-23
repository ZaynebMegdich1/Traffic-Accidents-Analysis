
# **DAX Measures for Traffic Accidents Analysis**  

## **1. Traffic Accidents in 2024**  

### **1.1 Total Injuries 2024**  
```DAX
2024 Injuries = SUM('2024_Month'[blesses])
```  
This measure calculates the total number of people injured in traffic accidents in 2024.  

### **1.2 Total Fatalities 2024**  
```DAX
2024 Fatalities = SUM('2024_Month'[tues])
```  
This measure calculates the total number of people killed in traffic accidents in 2024.  

### **1.3 Total Accidents 2024**  
```DAX
2024 Total Accidents = SUM('2024_Month'[accidents])
```  
This measure calculates the total number of traffic accidents in 2024.  

---

## **2. Traffic Accidents in 2025**  

### **2.1 Total Injuries 2025**  
```DAX
2025 Injuries = SUM('2025_Months'[Blesses])
```  
This measure calculates the total number of people injured in traffic accidents in 2025.  

### **2.2 Total Fatalities 2025**  
```DAX
2025 Fatalities = SUM('2025_Months'[Tues])
```  
This measure calculates the total number of people killed in traffic accidents in 2025.  

### **2.3 Total Accidents 2025**  
```DAX
2025 Total Accidents = SUM('2025_Months'[Accidents])
```  
This measure calculates the total number of traffic accidents in 2025.  

---

## **3. Yearly Changes in Traffic Accidents**  

### **3.1 Accidents Change**  
```DAX
Accidents Change = DIVIDE( ([2025 Total Accidents] - [2024 Total Accidents]), [2024 Total Accidents])
```  
This measure calculates the percentage change in the total number of accidents between 2024 and 2025.  

### **3.2 Injuries Change**  
```DAX
Injuries Change = DIVIDE( ([2025 Injuries] - [2024 Injuries]), [2024 Injuries])
```  
This measure calculates the percentage change in the number of injuries between 2024 and 2025.  

### **3.3 Fatalities Change**  
```DAX
Fatalities Change = DIVIDE( ([2025 Fatalities] - [2024 Fatalities]), [2024 Fatalities])
```  
This measure calculates the percentage change in the number of fatalities between 2024 and 2025.  

---

## **4. Supporting Tables**  

### **4.1 Month Table**  
```DAX
MonthTable = 
ADDCOLUMNS(
    CALENDAR(DATE(2024,1,1), DATE(2025,12,31)), 
    "Year", YEAR([Date]), 
    "Month", FORMAT([Date], "MMMM"),
    "Month Number", MONTH([Date])
)
```  
This DAX expression creates a month table for the date range between January 2024 and December 2025. It generates year, month, and month number columns for time-based analysis.  

---


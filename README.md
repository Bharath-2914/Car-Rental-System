# Car-Rental-System

# 🚗 Car Rental System

A **C++ and MySQL-based Car Rental System** that allows users to view available cars, book a car, and update rental records in a **MySQL database**.

## 📌 Features
- **View Available Cars**: Fetches available cars from the MySQL database.
- **Car Booking System**: Users can book a car by entering its serial number.
- **Database Integration**: Uses **MySQL** to store and update car records.
- **Availability Check**: Prevents users from booking an already rented car.

## 🛠️ Technologies Used
- **C++**
- **MySQL**
- **Windows API (Sleep, system calls)**

## 🚀 How to Run
### 1️⃣ Prerequisites
- Install **MySQL Server** and create a database.
- Install **MySQL Connector/C++**.
- Install **MinGW** or **Visual Studio** for C++ compilation.

### 2️⃣ MySQL Setup
Run the following SQL queries to create the required database and table:
```sql
CREATE DATABASE mydb;
USE mydb;

CREATE TABLE cars (
    Serial INT PRIMARY KEY,
    Brand VARCHAR(50),
    Model VARCHAR(50),
    Rent INT,
    Avail BOOLEAN
);
```

### 3️⃣ Configure MySQL Credentials
Modify the **database credentials** in the C++ code:
```cpp
const char* HOST = "localhost";
const char* USER = "root";
const char* PW = "yourpassword";  // Replace with your MySQL password
const char* DB = "mydb";
```

### 4️⃣ Compile and Run the Program
#### Using MinGW (Windows)
```sh
g++ -o car_rental car_rental.cpp -I"C:\Path\To\MySQL\include" -L"C:\Path\To\MySQL\lib" -lmysql
```
Run the executable:
```sh
./car_rental
```

#### Using Visual Studio (Windows)
- Open the **Developer Command Prompt**.
- Navigate to the project directory.
- Run:
  ```sh
  cl /EHsc car_rental.cpp /I "C:\Path\To\MySQL\include" /link /LIBPATH:"C:\Path\To\MySQL\lib" libmysql.lib
  ```

## 📂 Project Structure
```
📦 Car Rental System
 ┣ 📜 car_rental.cpp  # Main C++ source code
 ┣ 📜 README.md       # Project documentation
 ┣ 📜 database.sql    # MySQL setup script
```

## 🎮 System Flow
1️⃣ **Program connects to the MySQL database.**  
2️⃣ **Car data is inserted** into the database (if not already present).  
3️⃣ **Displays all available cars** with their rent.  
4️⃣ **User selects a car** by entering the **serial number**.  
5️⃣ **Database updates availability**, preventing multiple bookings.  

## 🏆 Future Enhancements
- Implement **user authentication** for rentals.
- Add **return functionality** for rented cars.
- Improve **error handling** and **input validation**.

## 🤝 Contributing
Feel free to contribute! Fork the repository, make changes, and submit a pull request.

## 📜 License
This project is **open-source** and free to use.

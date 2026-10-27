# Medical Store Stock Alert System

A Spring Boot + MySQL based system to manage medical store inventory and automatically alert shopkeepers about expired and near-expiry medicines.

> **Main Objective:** To prevent financial loss and health risks caused by the sale of expired medicines by replacing the manual notebook system with an automated alert system.

### 🚀 Features

*   **Add Medicine:** Add medicine with Name, Manufacturing Date, Expiry Date, Quantity, and Price.
*   **Smart Alerts:**
    *   🔴 **Red Alert:** Medicine is Expired (Exp Date < Today)
    *   🟠 **Orange Alert:** Medicine will expire within 30 days
    *   ⚫ **Out of Stock:** Quantity is 0
*   **Block Expired Sale:** System automatically prevents the sale of expired medicines.
*   **Loss Calculation:** Dashboard shows total financial loss due to expired stock.
*   **Live Dashboard:** Clean `index.html` dashboard to view all stock status at a glance.

### 🛠️ Tech Stack

*   **Backend:** Java 17, Spring Boot 3.x, Spring MVC, Spring Data JPA
*   **Frontend:** HTML, CSS, JavaScript
*   **Database:** MySQL
*   **Build Tool:** Maven (pom.xml)

### 📁 Project Structure

MedicalStore-SpringBoot-MySQL/
├── src/main/java/com/medicalstore/
│   ├── MedicalStoreApplication.java  # Main file to run the project
│   ├── Medicine.java                 # Model / Entity class
│   ├── MedicineController.java       # Controller
│   └── MedicineRepository.java       # Repository for MySQL
├── src/main/resources/
│   ├── application.properties        # DB Configuration
├── index.html                        # Main Dashboard
└── pom.xml

### ⚙️ Installation

1.  Create a database named `medical_store` in MySQL.
2.  Update `application.properties`:
    spring.datasource.url=jdbc:mysql://localhost:3306/medical_store
    spring.datasource.username=root
    spring.datasource.password=your_password
3.  Run: `mvn spring-boot:run`
4.  Open: `http://localhost:8080`

### 💻 Core Logic in Medicine.java

if (qty == 0) return "Out of Stock";
if (expDate.isBefore(LocalDate.now())) return "Expired";
if (days <= 30) return "Expiring Soon";

### 🔮 Future Scope

*   Bill generation
*   Low stock SMS Alert
*   Barcode scanning

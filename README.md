
# Medical Records Management System

## Overview

The **Medical Records Management System** is a Java-based application designed to simplify the management of patient records, doctor appointments, and prescription handling. It ensures secure data storage and efficient handling of medical history and user operations.

## Features

- **Patient Management:**
  - Add, list, and find patients.
  - Store and retrieve patient medical histories.

- **Appointment Management:**
  - Schedule, view, and update doctor appointments.

- **Prescription Management:**
  - Issue and manage patient prescriptions.

- **Reporting:**
  - Generate detailed reports on medical records and appointment usage.

- **Database Integration:**
  - Persistent data storage using MySQL for patient and appointment records.

## Technologies Used

- **Programming Language:** Java
- **Database:** MySQL
- **Libraries:** JDBC for database connectivity

## Main Classes and Their Roles

### 1. **MedicalRecordsSystem**
The entry point of the application. It provides the main menu interface and handles user input for medical record operations.

### 2. **User (Abstract Class)**
A base class for all user types in the system.
- **Fields:** `userId`, `username`, `role`
- **Methods:** 
  - `getUserId()`
  - `getUsername()`
  - `getRole()`

### 3. **Admin (Subclass of User)**
Represents an admin with extended privileges.
- **Role:** Manage users, appointments, and prescriptions.

### 4. **Patient**
Represents a patient in the system.
- **Fields:** `id`, `name`, `contact`, `medicalHistory`
- **Methods:** 
  - `getId()`
  - `getName()`
  - `getContact()`
  - `getMedicalHistory()`

### 5. **Doctor**
Represents a doctor in the system.
- **Fields:** `id`, `name`, `specialty`
- **Methods:** 
  - `getId()`
  - `getName()`
  - `getSpecialty()`

### 6. **Appointment**
Handles appointment scheduling.
- **Fields:** `id`, `patient`, `doctor`, `dateTime`
- **Methods:** 
  - `getId()`
  - `getPatient()`
  - `getDoctor()`
  - `getDateTime()`

### 7. **Prescription**
Manages prescriptions issued to patients.
- **Fields:** `id`, `patient`, `doctor`, `medicine`, `dosage`
- **Methods:** 
  - `getId()`
  - `getPatient()`
  - `getDoctor()`
  - `getMedicine()`
  - `getDosage()`

### 8. **MedicalHistory**
Tracks the medical history of patients.
- **Fields:** `id`, `patient`, `historyDetails`

### 9. **DatabaseHandler**
Manages database connections and operations.
- **Methods:** 
  - `connect()`
  - `disconnect()`

### 10. **ScheduleManager**
Handles appointment schedules.

### 11. **NotificationService**
Sends reminders and notifications to patients.

### 12. **ReportGenerator**
Generates reports on patients, doctors, and appointments.

## How to Run

1. Ensure you have Java and MySQL installed on your system.
2. Set up the database:
   - Create a database named `medical_records`.
   - Use the following command to create the `Patients` table:
     ```sql
     CREATE TABLE Patients (
       id INT PRIMARY KEY AUTO_INCREMENT,
       name VARCHAR(255),
       contact VARCHAR(255),
       medicalHistory TEXT
     );
     ```
3. Update database credentials in `DatabaseHandler`:
   ```java
   connection = DriverManager.getConnection("jdbc:mysql://localhost:3306/medical_records", "your_username", "your_password");
   ```


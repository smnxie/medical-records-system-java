
# Database Schema

## Tables

### Patients
| Column         | Type        | Description              |
|----------------|-------------|--------------------------|
| `id`           | INT         | Primary Key              |
| `name`         | VARCHAR(50) | Name of the patient      |
| `contact`      | VARCHAR(15) | Contact information      |
| `medicalHistory` | TEXT       | Medical history of the patient |

### Appointments
| Column         | Type        | Description              |
|----------------|-------------|--------------------------|
| `id`           | INT         | Primary Key              |
| `patientId`    | INT         | Foreign Key (Patients.id)|
| `doctor`       | VARCHAR(50) | Doctor's name            |
| `appointmentDate` | DATETIME | Appointment date/time    |

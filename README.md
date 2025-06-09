# Hostel Management System 🏨

:contentReference[oaicite:1]{index=1} :contentReference[oaicite:2]{index=2}.

---

## 🔍 Table of Contents
- [Features](#features)
- :contentReference[oaicite:3]{index=3}
- :contentReference[oaicite:4]{index=4}
- [Prerequisites](#prerequisites)
- :contentReference[oaicite:5]{index=5}
- [Usage](#usage)
- :contentReference[oaicite:6]{index=6}
- [Contributing](#contributing)
- [License](#license)

---

## 🛠 Features

- **Admin Panel**
  - :contentReference[oaicite:7]{index=7}
  - :contentReference[oaicite:8]{index=8}
  - :contentReference[oaicite:9]{index=9}
  - :contentReference[oaicite:10]{index=10}
  - :contentReference[oaicite:11]{index=11}
  
- **Student Portal**
  - :contentReference[oaicite:12]{index=12}
  - :contentReference[oaicite:13]{index=13}
  - :contentReference[oaicite:14]{index=14}
  - :contentReference[oaicite:15]{index=15}

---

## 🧠 Architecture & Diagrams

- :contentReference[oaicite:16]{index=16}
- :contentReference[oaicite:17]{index=17}  
:contentReference[oaicite:18]{index=18}

---

## 💻 Tech Stack

- :contentReference[oaicite:19]{index=19}
- :contentReference[oaicite:20]{index=20}
- :contentReference[oaicite:21]{index=21}
- :contentReference[oaicite:22]{index=22}

---

## 📋 Prerequisites

- :contentReference[oaicite:23]{index=23}
- :contentReference[oaicite:24]{index=24}
- MySQL server
- Git

---

## ⚙️ Setup & Running Locally

1. :contentReference[oaicite:25]{index=25}
   ```bash
   git clone https://github.com/lewi01/hostel-management-system.git
   cd hostel-management-system
2. Configure the database
- Create a MySQL database (e.g. hostel_db)
- Update src/main/resources/application.properties:
```bash
spring.datasource.url=jdbc:mysql://localhost:3306/hostel_db
spring.datasource.username=YOUR_DB_USER
spring.datasource.password=YOUR_DB_PASS
spring.jpa.hibernate.ddl-auto=update
```
3. Build & Run
- Via Maven wrapper:
```bash
./mvnw clean spring-boot:run

```
Or via Maven (if installed):
```bash
mvn clean package
java -jar target/hostel-management-system-0.0.1-SNAPSHOT.jar
```

4. Access the application
- Backend API served at: http://localhost:8080

🚀 Usage
Admin
- Use POST/PUT/DELETE endpoints to manage:

- /api/hostels
- /api/rooms
- /api/students
- /api/payments

View:

- Booking statuses
- Payment reports

Student
Use:
- GET /api/rooms?available=true
- POST /api/bookings
- POST /api/payments
- GET /api/students/{id}/balance

📊 Entity Overview
Entity	Key Fields
Hostel	id, name, address, totalRooms
Room	id, hostelId, roomNumber, capacity, price
Student	id, name, email, contactInfo
Booking	id, studentId, roomId, startDate, endDate
Payment	id, bookingId, amount, date, status

This aligns with the ER diagram.

🤝 Contributing
Contributions are welcome. Steps:

1. Fork this repository
2. Create a feature branch: git checkout -b feature/AwesomeFeature
3. Commit your changes: git commit -m 'Add feature'
4. Push to your branch: git push origin feature/AwesomeFeature
5. Open a Pull Request



![HostelManagementUseCase](https://user-images.githubusercontent.com/68944324/185670047-8b9bc053-c6b2-457d-9cec-2991b478cd92.png)


ENTITY RELATIONSHIP DIAGRAM

 ![hostel entity relationship diagram drawio](https://user-images.githubusercontent.com/68944324/185670187-73cfafe8-24f3-47bb-a662-21fff19c5b84.png)


The privileges allowed to the Hostel Admin are

- To add new hostel and rooms
- To delete hostel and rooms
- To decide number of occupants per room and the cost
- To view all student who have booked
- To view all student who have payed fully and partially
- To delete students when after every semester
- To view all booked rooms per hostel

Hostel Admin is the one who maintains the complete database of students,maintain rooms as well as payments.

The privileges allowed to the Hostel students are

- To view nonBooked rooms and hostel
- To book a room of their choice if not fully booked
- To pay for the room
- To check their remaining balance
- To view their room & hostel details

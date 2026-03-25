# WasteTrack — Waste Collection and Vehicle Management System

WasteTrack is a centralized, role-based web platform designed to digitize and streamline municipal solid waste collection and complaint handling. It connects citizens, vehicle operators, and administrators to improve operational efficiency and transparency.

## Features

### For Citizens
* **Report Issues:** Submit waste-related complaints (e.g., uncollected garbage, overflowing bins) with location and description.
* **Track Progress:** View the status of submitted complaints (Open, In Progress, Resolved, Closed) in real-time.
* **Public Statistics:** View community-wide waste collection analytics and department summaries.

### For Managers (Administrators)
* **Department Management:** Oversee employees and vehicles assigned to specific zones (e.g., South Zone, West Zone).
* **Complaint Assignment:** Review incoming complaints and assign them to specific employees and vehicles.
* **Analytics Dashboard:** Access SQL views for pending complaints, vehicle usage, and employee performance.

### For Employees (Drivers/Cleaners)
* **Task Management:** View assigned collection tasks, including location, vehicle ID, and route.
* **Status Updates:** Update task progress (e.g., "Mark Resolved") directly from the mobile-friendly dashboard.
* **Waste Recording:** Log the weight and type of waste collected per route.

## Tech Stack

* **Frontend:** HTML5, CSS3 (with CSS Variables and Flexbox/Grid), JavaScript (Vanilla).
* **Backend:** Node.js with Express framework.
* **Database:** MySQL with relational mapping and normalized tables.
* **Authentication:** Role-based access control (RBAC) with password hashing via `bcryptjs` and session management via `express-session`.

## Project Structure

```text
waste-track/
├── assets/             # Images and static assets
├── middleware/         # Auth and role-validation middleware
├── routes/             # Express API routes (complaints, employees, views, etc.)
├── server.js           # Main application entry point
├── db.js               # MySQL database connection pool
├── database_setup.sql  # Database schema and seed data
├── *.html              # Frontend page templates (manager, employee, head, etc.)
└── style.css           # Global application styling
```

### Database Schema**
The system utilizes a relational model with several key tables:

* **Employee**: Stores user credentials, contact info, and roles (Head, Manager, Employee).

* **Department**: Manages different municipal zones.

* **Vehicle**: Tracks waste collection vehicles and their maintenance status.

* **Route**: Defines collection paths and distances.

* **Complaints**: Records citizen-reported issues and their current resolution status.

⚙️ **Setup Instructions**
Prerequisites
Node.js (v18+)

MySQL Server

---

### Installation
**Clone the repository:**
```bash
git clone [https://github.com/dedlinux777/waste-track.git](https://github.com/dedlinux777/waste-track.git)
cd waste-track
```

**Install dependencies:**
```bash
npm install
```


**Database Configuration:**

* Create a database named waste_track.
* Import the database_setup.sql file into your MySQL instance to create tables and seed initial data.
* Update your credentials in db.js.

**Seed the database:**
```bash
npm seed
```

**Start the server:**
```bash
npm start
```

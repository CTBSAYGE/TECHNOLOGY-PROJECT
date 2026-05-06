# TECHNOLOGY-PROJECT
# PassGuard — Pedagogical Password Vault

PassGuard is a web application that lets a user store credentials securely and teaches good security habits through clear visualizations and feedback.  
It is built as a first‑year capstone project, combining **cybersecurity**, **web development**, and **data visualization**.

---

## 1. Team

- **Project Lead / Integrator:** TCHEUTCHOUA FONKOU LEROY  
- **Cybersecurity Lead:** _Name_ VICTOR JEFF NGOY NGOY 
- **Front-end Developer:** _Name_ VICTOR JEFF NGOY NGOY 
- **Back-end Developer:** _Name_ ROMAIN TESSIERES 
- **Database & Queries:** _Name_ROMAIN TESSIERES AND AZEMO KAREL LEKANE  
- **Data Visualization:** _Name_ TCHEUTCHOUA FONKOU LEROY 

---

## 2. Features

### 2.1 Cybersecurity

- Master password protected with a strong hash (e.g. `password_hash` / bcrypt in PHP).  
- Password strength scoring based on:
  - Length  
  - Character variety  
  - Presence in a “common passwords” list (e.g. top 1000 from rockyou).  
- Detection of reused passwords across the user’s vault.  
- Built‑in password generator with configurable length and character classes.

### 2.2 Web development

- Account creation, master‑password login, logout, and session timeout.  
- CRUD interface to **add / edit / view / delete** stored credentials.  
- Front‑end password generator in JavaScript with **copy‑to‑clipboard**.

### 2.3 Data & visualization

- Personal security dashboard with an overall **vault strength score (0–100)**.  
- Distribution chart: weak / medium / strong passwords.  
- List view of weak or duplicated passwords with recommendations.  
- (Optional) Trend over time as the user improves passwords.

---

## 3. Minimum Viable Product

At final defense, the MVP must provide:

- Master‑password login.  
- Full CRUD on credentials.  
- Strength scoring on every saved password.  
- Overall dashboard score.

---

## 4. Tech stack

- **Front-end:** HTML, CSS, JavaScript (forms, validation, charts).  
- **Back-end:** PHP (authentication, business logic, API).  
- **Database:** MySQL / MariaDB (SQL schema + queries).  
- **Charts:** Chart.js (or similar) for dashboards.  
- **Security:** `password_hash` / bcrypt, prepared statements, basic hardening.

---

## 5. Architecture overview

- **Browser (client):**
  - Login / registration forms.  
  - Credential management screens.  
  - Dashboard with charts and statistics.  
  - JS password generator and copy‑to‑clipboard.

- **Web server (PHP back-end):**
  - Authentication (login, logout, session management).  
  - CRUD endpoints for credentials.  
  - Password strength scoring and reuse detection.  
  - Aggregation queries for dashboard metrics.  

- **Database (SQL):**
  - `users` table (accounts, hashed master password).  
  - `credentials` table (site, username, encrypted password, metadata).  
  - Optional tables for history / logs.

---

## 6. Installation & setup

### 6.1 Prerequisites

- PHP (version X+).  
- Web server (Apache / Nginx) with PHP support.  
- MySQL / MariaDB (or compatible SQL database).  
- Composer (if you use dependencies) — optional.

### 6.2 Steps

1. **Clone the repository**

   ```bash
   git clone https://github.com/your-org/passguard.git
   cd passguard
mysql -u your_user -p passguard_db < database/passguard.sql

**PROJECT STRUCTURE**
passguard/
├── public/              # Public entry (index.php, assets)
├── src/
│   ├── Auth/            # Login, registration, session
│   ├── Controllers/     # Page controllers
│   ├── Models/          # User, Credential, etc.
│   ├── Services/
│   │   ├── Security/    # Hashing, strength scoring, reuse detection
│   │   └── Dashboard/   # Aggregations for charts
│   └── Views/           # PHP/HTML templates
├── database/
│   └── passguard.sql    # Schema + sample data
├── assets/
│   ├── css/
│   ├── js/
│   └── img/
├── README.md
└── composer.json        # If using Composer

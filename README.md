# 🏡 Family Directory & Invitation Manager

> A secure, high-performance web-based family directory and event invitation management platform designed to streamline relative tracking, monitor invitation lifecycles, and facilitate direct communication.

---

## 🏗️ Architecture & Technical Overview

This application is engineered as a lightweight, responsive single-page application (SPA) utilizing vanilla web technologies combined with a cloud backend. 

### Technology Stack
- **Frontend Layer:** HTML5, CSS3, Modern Vanilla JavaScript (ES6+)
- **Styling & UI:** Custom CSS Custom Properties (`:root` variables), CSS Grid, Flexbox, responsive layouts with mobile-first media queries
- **Backend & Database:** [Supabase](https://supabase.com/) (PostgreSQL relational database, Row-Level Security, and Supabase Auth)
- **External Dependencies:** Supabase JavaScript Client (`@supabase/supabase-js` via CDN)

---

## 📊 Core Features & Capabilities

- **Authentication & Authorization:** Secure session-based sign-in and user session validation powered by Supabase Auth.
- **Real-Time Statistical Analytics:** Instant calculation and rendering of metrics including total records, paternal vs. maternal breakdowns, and active invitations.
- **Dynamic Filtering & Search:** Multi-parameter data filtering by family side, invitation status, and real-time keyword search across names, phone numbers, locations, and personal notes.
- **Direct Communication Integrations:** Deep-linking integrations enabling one-click phone dialing (`tel:`) and direct WhatsApp messaging (`wa.me`) utilizing sanitized phone strings.
- **CRUD Operations:** Full record lifecycle management through responsive modal dialogs equipped with client-side validation and state handling.
- **Data Portability:** Local CSV export functionality supporting UTF-8 character encoding for robust backup and spreadsheet interoperability.
- **Internationalization (i18n):** Real-time language switching capabilities supporting English, Hindi (हिन्दी), and Gujarati (ગુજરાતી).

---

## 🗄️ Database Schema Reference

The application interfaces with a Supabase PostgreSQL table named `relatives`. Below is the structural schema definition required for proper operation:

| Column Name | Data Type | Constraints / Attributes | Description |
| :--- | :--- | :--- | :--- |
| `id` | UUID / INT | Primary Key | Unique identifier for each record |
| `name` | TEXT | `NOT NULL` | Full name of the relative |
| `relation` | TEXT | `NOT NULL` | Familial relationship (e.g., Uncle, Cousin) |
| `side` | TEXT | `NOT NULL` | Family lineage category (`Paternal`, `Maternal`, `In-Laws`) |
| `phone` | TEXT | Nullable | Contact telephone number |
| `city` | TEXT | Nullable | City or village of residence |
| `status` | TEXT | Default: `Pending` | Invitation lifecycle status (`Pending`, `Sent`, `Confirmed`) |
| `invitation_date` | DATE | Nullable | Timestamp of when the invitation was issued |
| `rsvp_status` | TEXT | Default: `Pending` | Attendance confirmation (`Pending`, `Accepted`, `Declined`) |
| `notes` | TEXT | Nullable | Supplementary remarks or dietary/accommodation details |
| `updated_at` | TIMESTAMPTZ | Default: `NOW()` | Record modification timestamp |

---

## ⚙️ Installation & Deployment

### Prerequisites
- A modern web browser
- A configured Supabase project with the corresponding `relatives` table and authentication credentials enabled.

### Setup Instructions

1. **Clone the Repository**
   ```bash
   git clone [https://github.com/Hiteshsuthar400/Family_Dashboard.git](https://github.com/Hiteshsuthar400/Family_Dashboard.git)

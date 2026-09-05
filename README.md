# 📌 Campus Trade

A web-based marketplace where university students can buy, sell, and rent secondhand items — books, gadgets, cycles, furniture, and more — directly with each other on campus. No shipping, no middlemen: just post, chat, agree on a meetup, and trade.

> Built as a Web Technology course project. Stack: **PHP, MySQL, HTML5, CSS3, JavaScript, Bootstrap 5**.

---

## ✨ Features

**Authentication**
- Secure registration & login (passwords hashed with `password_hash()`)
- Role-based access: Admin / Student
- CSRF-protected forms across the app

**Marketplace**
- Post, edit, and delete item listings (with image upload)
- Browse with category filter, keyword search, and pagination
- Item detail pages with seller profile & ratings

**Transactions**
- Send a buy/rent request with a proposed meetup location & time
- Seller can Accept / Reject requests
- Mark a transaction Completed → item automatically marked Sold
- Buyer and seller can rate & review each other after a completed transaction

**Community & Trust**
- Wishlist — save items to revisit later
- In-app chat between buyer and seller, tied to each item
- Report a listing → Admin can review and remove it

**Admin Panel**
- Manage users (block/unblock)
- Manage categories
- Review and act on reported listings
- Dashboard with quick stats

---

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML5, CSS3 (custom design system), JavaScript, Bootstrap 5.3 |
| Backend | PHP (Core PHP, PDO) |
| Database | MySQL |
| Fonts | Space Grotesk + Inter (Google Fonts) |

---

## 📂 Folder Structure

```
aiub-campus-trade/
├── admin/          # Admin panel (users, categories, reports)
├── auth/           # Register, login, logout
├── student/        # Browse, post, requests, chat, wishlist, reviews
├── includes/       # Shared header/footer
├── config/         # DB connection + CSRF helper
├── assets/         # CSS, JS, uploaded images
├── schema.sql      # Full database schema (import this first)
└── index.php       # Landing page
```

---

## 🚀 Setup (XAMPP)

1. Install [XAMPP](https://www.apachefriends.org/) and start **Apache** + **MySQL**.
2. Copy this folder into `htdocs/aiub-campus-trade`.
3. Open `http://localhost/phpmyadmin`, create a database named **`aiub_campus_trade`**.
4. Go to the **Import** tab and import `schema.sql` — this creates all tables and seeds default categories.
5. Visit `http://localhost/aiub-campus-trade/` in your browser.
6. Register an account. To make an account an admin, open the `users` table in phpMyAdmin and change that row's `role` from `student` to `admin`.

### Default DB connection (`config/db.php`)
```
host: localhost
username: root
password: (empty — default for XAMPP)
dbname: aiub_campus_trade
```

---

## 🗄 Database Overview

| Table | Purpose |
|---|---|
| `users` | Accounts, roles, block status |
| `categories` | Item categories |
| `products` | Listings (sell/rent, condition, status) |
| `requests` | Buy/rent requests between buyer & seller |
| `messages` | Chat between buyer & seller, per item |
| `reviews` | Post-transaction ratings |
| `wishlist` | Saved items per user |
| `reports` | Flagged listings for admin review |

---

## 👥 Team

_Add your team members' names and student IDs here._

## 📄 License

This project was built for academic purposes as part of a university course.

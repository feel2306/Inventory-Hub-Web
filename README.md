# 📦 Inventory Hub

A web-based inventory management system built with vanilla HTML, CSS, and JavaScript — powered by [Supabase](https://supabase.com) as the backend.

---

## 🚀 Features

- 🔐 **User Authentication** — Register and login with email & password
- 📊 **Dashboard** — View full inventory table with expiry alerts (items expiring within 7 days)
- 📥 **Stock In** — Add new items with category, quantity, expiry date, buying & selling price
- ✏️ **Update** — Update selling price of existing inventory items
- 🛒 **Sell** — Record sales transactions with automatic stock deduction and profit calculation
- 🗑️ **Delete** — Remove items from inventory
- 📋 **Sales Report** — View complete sales history with quantity, total amount, profit, and date
- 🚚 **Suppliers** — Add and manage supplier contacts (name, email, mobile)
- 👤 **Profile** — View account details and logout

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | HTML5, CSS3, JavaScript (ES6+) |
| UI Framework | Bootstrap 5.3 |
| Icons | Bootstrap Icons |
| Font | Poppins (Google Fonts) |
| Backend / DB | Supabase (PostgreSQL) |

---

## 📁 Project Structure

```
inventory-hub/
│
├── css/
│   ├── main.css          # Global styles (navbar, dashboard, forms)
│   └── lr.css            # Login & Register page styles
│
├── img/
│   └── Login_img.jpg     # Background image for login/register
│
├── js/
│   ├── login.js          # Login logic
│   ├── register.js       # Registration & validation
│   ├── dash.js           # Dashboard inventory table + expiry alerts
│   ├── stock.js          # Stock-in form logic
│   ├── sell.js           # Sell items & record sales
│   ├── update.js         # Update selling price
│   ├── del.js            # Delete inventory item
│   ├── report.js         # Sales report table
│   ├── sup.js            # Suppliers add & list
│   └── profile.js        # Profile display & logout
│
├── home.html             # Landing page
├── login.html            # Login page
├── register.html         # Registration page
├── navbar.html           # Shared navigation bar (loaded via fetch)
├── dashborad.html        # Inventory dashboard
├── stock.html            # Add stock
├── sell.html             # Sell items
├── update.html           # Update prices
├── delete.html           # Delete items
├── report.html           # Sales report
├── sup.html              # Suppliers
└── profile.html          # User profile
```

---

## 🗄️ Supabase Database Tables

### `users`
| Column | Type |
|--------|------|
| id | uuid (PK) |
| username | text |
| email | text |
| mobile | text |
| password | text |

### `inventory`
| Column | Type |
|--------|------|
| id | int (PK) |
| user_id | uuid (FK → users) |
| item_name | text |
| category | text |
| quantity | int |
| exp_date | date |
| buying_price | numeric |
| selling_price | numeric |
| arrived | date |

### `sales`
| Column | Type |
|--------|------|
| id | int (PK) |
| user_id | uuid (FK → users) |
| item_name | text |
| quantity_sold | int |
| selling_price | numeric |
| total_amount | numeric |
| profit | numeric |
| sold_date | timestamp |

### `suppliers`
| Column | Type |
|--------|------|
| id | int (PK) |
| user_id | uuid (FK → users) |
| supplier_name | text |
| email | text |
| phone | text |


---

## ⚠️ Known Limitations

- Passwords are stored as plain text in Supabase. For production, use Supabase Auth with hashed passwords.
- No role-based access control — all users see only their own data (filtered by `user_id`).
- Categories in Stock In are currently hardcoded (Groceries, Coldrinks, Namkeen).

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 🙋‍♂️ Author

Built by **[Feel]**

# Tenya Security Group Ltd – Website Package
**Integrity With Excellence**

---

## 📁 FILES INCLUDED

| File | Description |
|------|-------------|
| `index.html` | Main public-facing website |
| `admin.html` | Admin dashboard (all management) |
| `backend.php` | PHP backend API (connects to MySQL) |
| `README.md` | This guide |

---

## 🚀 QUICK START (No Backend)

The website works **immediately** without any backend setup:
- Open `index.html` in a browser — full website loads
- Open `admin.html` — admin dashboard loads (login: ****)
- All form submissions are stored in browser **localStorage**
- The admin dashboard reads from localStorage and displays everything

This is perfect for **testing and demonstrations**.

---

## 🌐 FULL DEPLOYMENT (With PHP Backend)

### Step 1 – Web Hosting
Upload all files to your hosting (Hostinger, cPanel, etc.) via FTP or File Manager.

### Step 2 – Create MySQL Database
In your cPanel → MySQL Databases:
1. Create database: `tenya_db`
2. Create user: `tenya_user` with a strong password
3. Assign full privileges to the user on the database

### Step 3 – Configure backend.php
Edit `backend.php` and update lines 18–21:
```php
define('DB_HOST', 'localhost');
define('DB_NAME', 'tenya_db');      // your database name
define('DB_USER', 'tenya_user');    // your database username
define('DB_PASS', 'your_password'); // your database password
define('ADMIN_EMAIL', 'admin@tenyasecurity.co.ke'); // your email
```

### Step 4 – Create Database Tables
Visit: `https://yoursite.com/backend.php?setup=1`
You should see: `{"ok":true,"message":"Database tables created successfully!"}`

### Step 5 – Connect Frontend to Backend
In `index.html`, find this line:
```javascript
const API = 'backend.php';
```
If your backend is on a different domain, update to the full URL:
```javascript
const API = 'https://yoursite.com/backend.php';
```

---

## 🔐 ADMIN DASHBOARD

**URL:** `yoursite.com/admin.html`
**Default Login:** `admin` / `tenya2025`

### Features:
- **Dashboard** – Overview of all activity (quotes, messages, applications)
- **Blog Posts** – Create, publish, and delete blog articles
- **Careers** – Post and remove job listings
- **Company Profile** – Update contact info, stats, social links
- **Quote Requests** – View all quote submissions from website visitors
- **Messages** – View all contact form submissions
- **Applications** – View job applications, shortlist candidates
- **Marketing Team** – Add/remove marketing team members and assign roles
- **Campaigns** – Create marketing campaigns and assign to team members

### To change the admin password:
In `admin.html`, find and update:
```javascript
const CREDS = {admin:'tenya2025'};
```
Change `tenya2025` to your preferred password.

---

## 📤 UPLOADING YOUR LOGO & IMAGES

1. In the Admin Dashboard → **Company Profile** → **Logo & Images**
2. Upload your images to a free image host:
   - [Cloudinary.com](https://cloudinary.com) (recommended, free)
   - [Imgur.com](https://imgur.com)
3. Paste the image URLs into the fields and click Save

Alternatively, upload images directly to your hosting and reference them as:
`https://yoursite.com/images/logo.png`

---

## 📧 EMAIL NOTIFICATIONS

When users submit a quote, contact form, or job application, the backend sends an email notification to `ADMIN_EMAIL`. This uses PHP's `mail()` function.

For reliable email delivery, configure **SMTP** on your hosting (most cPanel hosts support this via Pepipost, SendGrid, or SMTP2GO).

---

## 🛠 CUSTOMIZATION

### Brand Colors
In `index.html`, edit the CSS variables at the top:
```css
:root {
  --navy: #0d1b3e;   /* Dark navy blue */
  --red: #d62828;    /* Brand red */
}
```

### Contact Details
Search for `+254 700 000 000` and `info@tenyasecurity.co.ke` and replace with your real details.

### Services
Search for `services-grid` in `index.html` and edit/add service cards.

---

## 📱 PAGES / SECTIONS

The website is a single-page application with these sections:
- **Hero** – Main banner with CTA
- **About** – Company overview and key features
- **Services** – All security services offered
- **Why Us** – Key stats and differentiators
- **Quote Banner** – Quick quote request form
- **Blog** – Latest news and articles
- **Careers** – Open positions with apply modal
- **Contact** – Contact form and company details
- **Footer** – Links and social media

---

## 💬 SUPPORT

For customization or technical help, contact your developer.
Website designed for: **Tenya Security Group Ltd** – Nairobi, Kenya.

# 👟 JOD Shoes Store &mdash; Luxury Footwear E-Commerce Platform

[![React](https://img.shields.io/badge/React-18.3.1-61DAFB?logo=react&logoColor=black)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-5.2-646CFF?logo=vite&logoColor=white)](https://vitejs.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.4-38B2AC?logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![Node.js](https://img.shields.io/badge/Node.js-Express_4.19-339933?logo=node.js&logoColor=white)](https://nodejs.org/)
[![PHP](https://img.shields.io/badge/PHP-8.x_PDO-777BB4?logo=php&logoColor=white)](https://www.php.net/)
[![MySQL](https://img.shields.io/badge/MySQL-8.x_%2F_MariaDB-4479A1?logo=mysql&logoColor=white)](https://www.mysql.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

An enterprise-grade, full-stack luxury footwear e-commerce application featuring a high-conversion storefront, dynamic catalog filtering, rich interactive shopping cart, secure multi-step checkout, and a comprehensive, password-protected administrator management suite.

---

## 🌟 Key Features

### 🛍️ Customer Storefront
- **Dynamic Hero & Showcase**: Interactive banners, seasonal promotions, trending collections, and category highlights.
- **Categorized Catalogs**: Dedicated collections for **Men, Women, Kids, Premium, Sports, Sneakers, Formal, Casual**, and **Running**.
- **Search & Filters**: Instant search by keywords, category filtration, price sorting, and availability flags.
- **Product Details**: High-resolution image galleries, size selection, stock alerts, user reviews, and AI-recommended related pairs.
- **Interactive Cart**: Real-time subtotal calculation, coupon voucher applications, and item quantity controls.
- **Seamless Checkout**: Address verification, order notes, payment mode selection, and immediate order generation.
- **Customer Account & Orders**: JWT-authenticated customer sign-up/login, order tracking, and delivery timeline view.
- **Offline Resilience & Fallback**: Client service includes built-in mock resilience, ensuring smooth catalog browsing even if the backend database is temporarily offline.

### 🛡️ Administrative Control Center (`/admin`)
- **Dashboard Metrics**: Real-time sales revenue, visitor traffic statistics, order fulfillment ratios, and conversion rates.
- **Product Management (CRUD)**: Create, edit, inspect, toggle visibility, and adjust stock counts across shoe lines.
- **Order Pipeline**: Track customer orders through status states: `Pending` ➔ `Processing` ➔ `Shipped` ➔ `Delivered` ➔ `Cancelled`.
- **Customer Directory**: Inspect registered shoppers, purchase records, and manage access statuses.
- **Category & Taxonomy Management**: Organize store departments, hero imagery, and sorting priority.
- **Inventory & Low-Stock Alerts**: Real-time warnings for low-inventory footwear variants.
- **Inquiry & Feedback Inbox**: Centralized hub for customer contact messages and inquiries.
- **Store Settings & Analytics**: System configuration, discount rules, and business performance analytics.

---

## 🛠️ Technology Stack

| Layer | Technologies |
|---|---|
| **Frontend** | React 18, Vite 5, Tailwind CSS, Framer Motion, Lucide React, React Icons, Axios, React Router DOM v6, React Hot Toast |
| **Backend (Node.js)** | Node.js, Express.js 4.19, `mysql2/promise`, JWT (`jsonwebtoken`), `bcryptjs`, Cookie-Parser, CORS |
| **Backend (PHP / Alternative)** | PHP 8.x PDO API with RESTful endpoints, JSON response formats, CORS headers |
| **Database** | MySQL / MariaDB (via XAMPP, Laragon, or standalone MySQL Server) |
| **Architecture** | RESTful API Client-Server architecture with offline client fallback resilience |

---

## 📂 Project Structure

```text
Shoes Store/
├── client/                     # React + Vite Frontend Application
│   ├── public/                 # Static assets & favicon
│   ├── src/
│   │   ├── assets/             # Brand logos & static illustrations
│   │   ├── components/         # Reusable UI components (Navbar, Footer, ShoeCard, Modal, etc.)
│   │   ├── context/            # Global state (CartContext, AuthContext, Theme)
│   │   ├── data/               # Local sample product & category datasets
│   │   ├── layouts/            # MainLayout (Store) & AdminLayout (Control Panel)
│   │   ├── pages/              # User views (Home, ProductDetails, Cart, Checkout, Orders, Auth)
│   │   │   └── admin/          # Admin views (Dashboard, Products, Orders, Customers, Inventory, etc.)
│   │   ├── services/           # Central API client (api.js) with fallback mock storage
│   │   ├── App.jsx             # Master route definitions
│   │   ├── main.jsx            # React root mount
│   │   └── index.css           # Tailwind CSS directives & custom styling
│   ├── .env                    # Frontend environment configuration
│   ├── package.json            # Client scripts & dependencies
│   ├── tailwind.config.js      # Custom theme, brand palettes & animations
│   └── vite.config.js          # Vite bundler configuration
│
├── backend/                    # Node.js / Express REST API Server
│   ├── config/
│   │   ├── db.js               # Database connection initiator
│   │   └── mysql.js            # MySQL connection pool configuration
│   ├── controllers/            # Request handlers (auth, products, orders, admin, contact)
│   ├── middleware/             # Auth JWT verification, role validation, error handler
│   ├── models/                 # Database models & schemas
│   ├── routes/                 # Express API routes (/api/auth, /api/products, etc.)
│   ├── utils/                  # Seed scripts and helper utilities
│   ├── .env                    # Server port, database credentials, JWT secret
│   ├── package.json            # Node backend dependencies
│   └── server.js               # Express application entry point
│
├── backend-php/                # Alternative PHP REST API (for XAMPP/Apache deployments)
│   ├── api/                    # PHP endpoints (auth, products, cart, orders, admin)
│   ├── config/                 # PDO database connector & utility helpers
│   └── .htaccess               # URL rewrite & CORS directives
│
├── database/                   # Database Schemas & Migrations
│   └── jod_shoes_store.sql     # Full MySQL schema, tables, and seed dataset
│
└── README.md                   # Project documentation
```

---

## 🚀 Getting Started

Follow these steps to set up the project locally on your machine.

### Prerequisites
- [Node.js](https://nodejs.org/) (v18.0.0 or higher recommended)
- [npm](https://www.npmjs.com/) (v9.0.0 or higher)
- [MySQL](https://www.mysql.com/) / [XAMPP](https://www.apachefriends.org/) (Apache + MySQL)

---

### Step 1: Database Setup (MySQL)

1. Launch **XAMPP Control Panel** and start **MySQL** (and **Apache** if using the PHP backend).
2. Open **phpMyAdmin** (`http://localhost/phpmyadmin`) or your preferred MySQL client.
3. Import the database file:
   - File location: `database/jod_shoes_store.sql`
   - Alternatively, execute the following in your MySQL terminal:
     ```bash
     mysql -u root -p < "database/jod_shoes_store.sql"
     ```
4. This creates the `jod_shoes_store` database with all required tables (`users`, `admins`, `categories`, `products`, `orders`, `order_items`, `cart`, `contact_messages`) and pre-populated catalog items.

---

### Step 2: Configure & Start Node.js Backend

1. Navigate to the `backend` folder:
   ```bash
   cd backend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Verify your `backend/.env` file:
   ```env
   PORT=5001
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_NAME=jod_shoes_store
   DB_USER=root
   DB_PASSWORD=
   JWT_SECRET=antigravity_super_secret_jwt_key_2026_luxury_store
   NODE_ENV=development
   ```
4. Start the backend API server:
   ```bash
   npm run dev
   # or
   npm start
   ```
   *The server will start on `http://localhost:5001` (with automatic port increment if 5001 is busy).*

---

### Step 3: Configure & Start Frontend (Client)

1. In a new terminal window, navigate to the `client` directory:
   ```bash
   cd client
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Verify your `client/.env` file:
   ```env
   VITE_API_BASE_URL=http://localhost/jod-shoes-store/backend-php/api
   VITE_NODE_API_URL=http://localhost:5001/api
   ```
4. Run the development server:
   ```bash
   npm run dev
   ```
5. Open your browser and navigate to:
   ```
   http://localhost:5173
   ```

> [!TIP]
> **Browser Note**: For the optimal viewing experience and interactive demo feature compatibility, opening the application in **Google Chrome** is recommended.

---

## 🔑 Default Credentials

The imported database includes pre-configured accounts for testing:

### 🛡️ Store Administrator
| Role | Email | Password | Admin Panel URL |
|---|---|---|---|
| **Super Admin** | `admin@jodshoes.com` | `password` | [`http://localhost:5173/admin-login`](http://localhost:5173/admin-login) |
| **Secondary Admin** | `admin406@gmail.com` | `admin406` | [`http://localhost:5173/admin-login`](http://localhost:5173/admin-login) |

### 👤 Customer Account
| Role | Email | Password | Storefront Login URL |
|---|---|---|---|
| **Customer** | `john@example.com` | `password` | [`http://localhost:5173/login`](http://localhost:5173/login) |

*(You can also register any new account instantly on the [`/signup`](http://localhost:5173/signup) page).*

---

## 🔌 API Endpoints Reference

The backend exposes RESTful endpoints supporting both JSON and URL-encoded payloads:

### Authentication & Users
| Method | Endpoint | Description | Auth Required |
|---|---|---|---|
| `POST` | `/api/auth/register` | Register a new customer account | No |
| `POST` | `/api/auth/login` | Authenticate customer & receive JWT | No |
| `POST` | `/api/auth/admin-login` | Authenticate store administrator | No |
| `GET` | `/api/auth/profile` | Retrieve authenticated user profile | Yes (Bearer) |
| `POST` | `/api/auth/logout` | Revoke session / clear auth | Yes |

### Products & Catalog
| Method | Endpoint | Description | Auth Required |
|---|---|---|---|
| `GET` | `/api/products` | Fetch all products with filter/pagination | No |
| `GET` | `/api/products/:id` | Fetch detailed product information | No |
| `GET` | `/api/products/category/:slug` | Fetch products by category | No |
| `POST` | `/api/products` | Add new shoe product | Admin Only |
| `PUT` | `/api/products/:id` | Update product information/stock | Admin Only |
| `DELETE` | `/api/products/:id` | Delete product from catalog | Admin Only |

### Orders & Checkout
| Method | Endpoint | Description | Auth Required |
|---|---|---|---|
| `POST` | `/api/orders` | Place a new customer order | Yes (Bearer) |
| `GET` | `/api/orders/my-orders` | Fetch logged-in user's order history | Yes (Bearer) |
| `GET` | `/api/orders/:id` | Fetch specific order details | Yes (Bearer) |

### Admin Management
| Method | Endpoint | Description | Auth Required |
|---|---|---|---|
| `GET` | `/api/admin/stats` | Dashboard statistics & sales summaries | Admin Only |
| `GET` | `/api/admin/orders` | View and filter all store orders | Admin Only |
| `PATCH` | `/api/admin/orders/:id/status` | Update order delivery status | Admin Only |
| `GET` | `/api/admin/customers` | List all registered customers | Admin Only |
| `GET` | `/api/admin/inventory` | Low-stock and stock ledger review | Admin Only |

---

## 🧪 Build & Production Deployment

To create an optimized production build of the frontend:

```bash
cd client
npm run build
```

This compiles optimized HTML, CSS, and JS bundles into the `client/dist/` directory, ready for deployment on Vercel, Netlify, AWS S3/CloudFront, or any Apache/Nginx web server.

To preview the production build locally:
```bash
npm run preview
```

---

## 🤝 Contributing

Contributions, feedback, and pull requests are welcome!
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the **MIT License** — feel free to use and adapt it for personal and commercial projects.

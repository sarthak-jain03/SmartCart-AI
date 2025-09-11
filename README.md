# Smart Grocery Store – Dynamic Price Prediction

# Project Link: https://smart-grocery-store.vercel.app/

##  Overview

Smart Grocery Store is a **full-stack MERN (MongoDB, Express.js, React.js, Node.js) web application** integrated with a **Machine Learning model** to help grocery retailers reduce product wastage and maximize profits.

The system dynamically adjusts product prices based on factors like **expiry date, demand, stock levels, and base price**, ensuring that perishable items are sold before they expire.



---

## Features

*  **User Authentication** (JWT + Cookies)
*  **Product Management** (Add, View, Update products)
*  **ML-Powered Price Prediction**:

  * Inputs: Product name, company, category, base price, days to expiry, inventory, demand
  * Output: Suggested **offer price**
*  **Shopping Experience**: Browse products by category, add to cart, place orders
*  **Manager Dashboard**: Visualize demand, stock, and dynamic pricing
*  Secure APIs with JWT authentication
*  Fully functional **React frontend** connected to **Node.js backend**

---

##  Machine Learning Model

* **Algorithm**: Random Forest Regressor
* **Trained on**: Cleaned dataset of perishable grocery products
* **Saved as**:

  * `model.pkl` → trained ML model
  * `product_encoder.pkl`, `company_encoder.pkl`, `category_encoder.pkl` → label encoders
* **Prediction API**: Flask microservice serving ML predictions

Example Input:

```json
{
  "product_name": "Milk",
  "company": "Amul",
  "category": "Dairy",
  "base_price": 50,
  "expiry_days": 2,
  "inventory": 100,
  "demand": 70
}
```

Example Output:

```json
{
  "predicted_price": 42.75
}
```

---

## Tech Stack

### Frontend (React.js)

* React + Context API for state management
* JWT Authentication with cookies
* Axios interceptors for API calls
* UI: TailwindCSS / Shadcn

### Backend (Node.js + Express.js)

* RESTful APIs for users, products, orders
* JWT Authentication
* Axios to communicate with Python ML API

### Machine Learning Service (Python)

* Flask REST API
* Scikit-learn (Random Forest)
* Pandas + Joblib for model persistence

### Database

* MongoDB (Atlas / Local)

---

## Project Structure

```
Smart-Grocery-Store/
│── client/                # React frontend
│── server/                # Node.js backend
│   ├── routes/            # API routes
│   ├── controllers/       # Controllers (e.g., product.controller.js)
│   ├── models/            # MongoDB models
│   ├── middlewares/       # Auth, error handling
│   └── ...
│── ml-api/                # Python ML microservice
│   ├── app.py             # Flask server
│   ├── model.pkl          # Trained ML model
│   ├── encoders.pkl       # Label encoders
│   └── requirements.txt
```

---

##  Installation & Setup

### 1. Clone Repo

```bash
git clone https://github.com/sarthak-jain03/Smart-Grocery-Store.git
cd smart-grocery-store
```

### 2. Backend Setup (Node.js)

```bash
cd server
npm install
```

Create `.env` file:

```
MONGO_URI=your_mongodb_connection
JWT_SECRET=your_jwt_secret
PORT=5000
```

Run backend:

```bash
npm run dev
```

### 3. Frontend Setup (React.js)

```bash
cd ../client
npm install
npm start
```

### 4. ML API Setup (Python)

```bash
cd ../ml-api
pip install -r requirements.txt
python app.py
```

---

## 🔗 API Endpoints

### Backend (Node.js)

* `POST /api/auth/register` → Register user
* `POST /api/auth/login` → Login user
* `POST /api/product/add-product` → Add new product
* `GET /api/product/all` → Fetch all products
* `POST /api/ml/predict-price` → Get dynamic price (calls ML API)

### ML API (Flask)

* `POST /predict` → Predict price

---

## Future Improvements

* 📈 Demand forecasting using time-series models
* 🤖 Advanced ML models (XGBoost, LSTM for demand prediction)
* 📲 Mobile App version
* 💳 Online Payments Integration

---

## 👨‍💻 Team

* **Sarthak Jain** – Full Stack + Machine Learning
  

---


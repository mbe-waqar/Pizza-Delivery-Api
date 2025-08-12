# 🍕 Pizza Delivery API

A REST API for a Pizza delivery service built for fun and learning with **FastAPI**, **SQLAlchemy** and **PostgreSQL**.

## 🛠️ Tech Stack

- **FastAPI** - Modern, fast web framework for building APIs
- **SQLAlchemy** - SQL toolkit and Object-Relational Mapping
- **PostgreSQL** - Open source relational database
- **Python 3.8+** - Programming language

## 📋 API Routes

| Method | Route | Functionality | Access |
|--------|-------|---------------|---------|
| `POST` | `/auth/signup/` | Register new user | All users |
| `POST` | `/auth/login/` | Login user | All users |
| `POST` | `/orders/order/` | Place an order | All users |
| `PUT` | `/orders/order/update/{order_id}/` | Update an order | All users |
| `PUT` | `/orders/order/status/{order_id}/` | Update order status | Superuser |
| `DELETE` | `/orders/order/delete/{order_id}/` | Delete/Remove an order | All users |
| `GET` | `/orders/user/orders/` | Get user's orders | All users |
| `GET` | `/orders/orders/` | List all orders made | Superuser |
| `GET` | `/orders/orders/{order_id}/` | Retrieve an order | Superuser |
| `GET` | `/orders/user/order/{order_id}/` | Get user's specific order | All users |
| `GET` | `/docs/` | View API documentation | All users |

## 🚀 How to Run the Project

### Prerequisites

- **PostgreSQL** - [Download and install](https://www.postgresql.org/download/)
- **Python 3.8+** - [Download and install](https://www.python.org/downloads/)
- **Git** - [Download and install](https://git-scm.com/downloads/)

### Installation Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/pizza-delivery-api.git
   cd pizza-delivery-api
   ```

2. **Create and activate virtual environment (venv)**
   
   Using `pipenv`:
   ```bash
   pipenv install
   pipenv shell
   ```
   
   Or using `virtualenv`:
   ```bash
   python -m venv venv
   
   # On Windows
   venv\Scripts\activate
   
   # On macOS/Linux
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up PostgreSQL database**
   
   Update your database URI in `database.py`:
   ```python
   engine = create_engine(
       'postgresql://postgres:<username>:<password>@localhost/<db_name>',
       echo=True
   )
   ```
   
   Replace:
   - `<username>` - Your PostgreSQL username
   - `<password>` - Your PostgreSQL password  
   - `<db_name>` - Your database name

5. **Initialize the database**
   ```bash
   python init_db.py
   ```

6. **Run the API**
   ```bash
   uvicorn main:app --reload
   ```

The API will be available at `http://localhost:8000`

## 📖 API Documentation

Once the server is running, you can access:

- **Interactive API docs (Swagger UI)**: `http://localhost:8000/docs`
- **Alternative API docs (ReDoc)**: `http://localhost:8000/redoc`

## 🔐 Authentication

The API uses JWT (JSON Web Tokens) for authentication. To access protected routes:

1. Register a new user via `/auth/signup/`
2. Login via `/auth/login/` to receive your JWT token
3. Include the token in the Authorization header: `Bearer <your-token>`

## 🍕 Features

- **User Authentication**: Register and login functionality
- **Order Management**: Create, read, update, and delete pizza orders
- **Role-based Access**: Different permissions for regular users and superusers
- **Order Status Tracking**: Update and track order status
- **RESTful Design**: Clean and intuitive API endpoints
- **Auto-generated Documentation**: Interactive API documentation with Swagger UI

## 🗂️ Project Structure

```
pizza-delivery-api/
├── main.py              # FastAPI application entry point
├── database.py          # Database configuration
├── init_db.py          # Database initialization script
├── requirements.txt     # Python dependencies
├── models/             # SQLAlchemy models
├── routers/            # API route handlers
├── schemas/            # Pydantic schemas
└── auth/              # Authentication logic
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- FastAPI team for the amazing framework
- SQLAlchemy for the powerful ORM
- PostgreSQL for the robust database system

---

**Made with ❤️ by Waqar Ali for learning and fun!**

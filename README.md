# source code link : https://1024terabox.com/s/1veP2VT-NyrPvJcaOnkdY_w

# E-Commerce Store

A FULLY FUNCTIONAL, PRODUCTION-READY e-commerce platform built with Django, REST API, and modern frontend technologies.

## Features

### User Features
- User registration & login with JWT authentication
- Product browsing with categories and search
- Shopping cart functionality
- Wishlist system
- Order placement and tracking
- Product reviews and ratings
- Secure checkout with Stripe payment integration

### Admin Features
- Dashboard analytics
- Product management (CRUD operations)
- Category management
- Order management
- User management
- Inventory control
- Sales reports

### Technical Features
- RESTful API architecture
- JWT token-based authentication
- Responsive Bootstrap frontend
- PostgreSQL database (production) / SQLite (development)
- Docker containerization
- Nginx reverse proxy
- Gunicorn WSGI server

## Tech Stack

**Backend:**
- Python 3.11+
- Django 6.0+
- Django REST Framework
- PostgreSQL/SQLite
- JWT Authentication
- Stripe Payment Integration

**Frontend:**
- HTML5, CSS3
- Bootstrap 5
- Vanilla JavaScript
- Responsive design

**Deployment:**
- Docker
- Docker Compose
- Nginx
- Gunicorn

## Quick Start (Development)

1. **Clone the repository:**
```bash
git clone <repository-url>
cd ecommerce
```

2. **Navigate to backend directory:**
```bash
cd backend
```

3. **Create virtual environment:**
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

4. **Install dependencies:**
```bash
pip install -r requirements.txt
```

5. **Set up environment variables:**
```bash
# Copy .env.example to .env and update values
cp .env.example .env
```

6. **Run migrations:**
```bash
python manage.py migrate
```

7. **Create superuser:**
```bash
python manage.py createsuperuser
```

8. **Load sample data:**
```bash
python manage.py create_sample_data
```

9. **Start development server:**
```bash
python manage.py runserver
```

10. **Access the application:**
- Frontend: http://localhost:8000
- Admin Panel: http://localhost:8000/admin
- API Docs: http://localhost:8000/api/

## Production Deployment with Docker

1. **Build and start services:**
```bash
docker-compose up --build
```

2. **Run migrations:**
```bash
docker-compose exec web python manage.py migrate
```

3. **Create superuser:**
```bash
docker-compose exec web python manage.py createsuperuser
```

4. **Load sample data:**
```bash
docker-compose exec web python manage.py create_sample_data
```

5. **Access the application:**
- Frontend: http://localhost
- Admin Panel: http://localhost/admin

## API Endpoints

### Authentication
- `POST /api/auth/register/` - User registration
- `POST /api/auth/login/` - User login
- `POST /api/auth/logout/` - User logout
- `GET /api/auth/profile/` - Get user profile
- `PUT /api/auth/profile/` - Update user profile

### Products
- `GET /api/products/` - List products
- `GET /api/products/{slug}/` - Product details
- `GET /api/products/categories/` - List categories
- `POST /api/products/create/` - Create product (admin)
- `PUT /api/products/{slug}/update/` - Update product (admin)

### Cart
- `GET /api/cart/` - Get cart
- `POST /api/cart/` - Add to cart
- `PUT /api/cart/items/{id}/` - Update cart item
- `DELETE /api/cart/items/{id}/` - Remove from cart
- `DELETE /api/cart/` - Clear cart

### Orders
- `GET /api/orders/` - List orders
- `POST /api/orders/create/` - Create order
- `GET /api/orders/{order_number}/` - Order details
- `PATCH /api/orders/{order_number}/status/` - Update order status (admin)

### Payments
- `POST /api/payments/create/` - Create payment
- `POST /api/payments/confirm/` - Confirm payment
- `GET /api/payments/` - List payments

## Admin Credentials

After running `createsuperuser`, use the credentials you created to access the admin panel at `/admin/`.

Default sample admin (if using sample data):
- Email: admin@eshop.com
- Password: (set during superuser creation)

## Environment Variables

Create a `.env` file in the backend directory with the following variables:

```env
DEBUG=True
SECRET_KEY=your-secret-key-here
DATABASE_URL=sqlite:///db.sqlite3

# Stripe Configuration
STRIPE_PUBLISHABLE_KEY=pk_test_your_key
STRIPE_SECRET_KEY=sk_test_your_key
STRIPE_WEBHOOK_SECRET=whsec_your_webhook_secret

# Email Configuration
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_HOST_USER=your-email@gmail.com
EMAIL_HOST_PASSWORD=your-app-password
EMAIL_USE_TLS=True
```

## Project Structure

```
ecommerce/
├── backend/
│   ├── users/              # User management
│   ├── products/           # Product management
│   ├── cart/               # Shopping cart
│   ├── orders/             # Order processing
│   ├── payments/           # Payment integration
│   ├── admin_panel/        # Admin functionality
│   ├── ecommerce/          # Main Django project
│   ├── manage.py
│   ├── requirements.txt
│   └── Dockerfile
├── frontend/
│   ├── templates/          # HTML templates
│   └── static/             # Static files
├── media/                  # Media files
├── docker-compose.yml
├── nginx.conf
└── README.md
```

## Security Features

- Password hashing with bcrypt
- JWT token authentication
- CSRF protection
- SQL injection prevention (ORM)
- Rate limiting
- Role-based access control
- Secure environment variables

## Testing

Run tests with:
```bash
python manage.py test
```

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Open a pull request

## License

This project is licensed under the MIT License.

## Support

For support, email mahdiislam237@gmail.com or open an issue in the repository.

Razorpay Payment Failure Handling System

A Django-based payment integration project using Razorpay Test Mode. This application demonstrates payment order creation, checkout, payment status verification, and server-side reconciliation to handle successful, failed, or interrupted payments.

 Features

* Razorpay payment gateway integration
* Django backend for payment processing
* Test checkout for ₹50
* Server-side payment verification
* Payment failure and error handling
* Payment status reconciliation
* Simple checkout interface
* Environment-based configuration for API credentials

Tech Stack

* **Backend:** Python, Django
* **Payment Gateway:** Razorpay
* **Frontend:** HTML, CSS
* **Configuration:** Environment variables
* **Database:** Django-supported database

Project Structure

```text
razorpay_failure_django/
│
├── config/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
│
├── payments/
│   └── ...
│
├── templates/
│   └── ...
│
├── .env.example
├── .gitignore
├── manage.py
├── requirements.txt
└── README.md
```

## Requirements

* Python 3.10 or later
* pip
* Git
* A Razorpay account with Test Mode enabled

## Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/ikram1234/razorpay-payment-failure-diagram.git
cd razorpay-payment-failure-diagram
```

### 2. Create a virtual environment

Windows:

```powershell
python -m venv .venv
.venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure environment variables

Copy `.env.example` to `.env`.

Add your Razorpay Test Mode credentials using the variable names expected by `config/settings.py`.

Example:

```env
RAZORPAY_KEY_ID=your_test_key_id
RAZORPAY_KEY_SECRET=your_test_key_secret
```

Do not commit your `.env` file or share your API secret.

### 5. Apply database migrations

```bash
python manage.py migrate
```

### 6. Start the development server

```bash
python manage.py runserver
```

Open the application in your browser:

http://127.0.0.1:8000/

## Payment Testing

The demo checkout is configured for a ₹50 test payment.

1. Start the Django development server.
2. Open the checkout page.
3. Click **Pay ₹50**.
4. Use Razorpay Test Mode credentials and test payment details.
5. Check the payment result and server-side status reconciliation.

Only use test credentials and test payment details. No real money should be transferred during testing.

## Payment Failure Handling

The project is intended to demonstrate how a payment application can respond to:

* Failure to create a payment order
* Failed or cancelled checkout
* Interrupted payment attempts
* Payment status verification
* Reconciliation of payment status on the server

A browser success message alone should not be treated as proof of payment capture. The backend must verify the payment with the payment provider before marking the payment as successful.

## Security

* Store credentials in environment variables.
* Never expose Razorpay API secrets in frontend code.
* Never upload `.env` to GitHub.
* Use Razorpay Test Mode for development.
* Verify payment signatures and confirm payment status on the backend.
* Use HTTPS and production-ready settings before deployment.

## Future Improvements

* Add a payment transaction history page.
* Implement webhook-based payment status updates.
* Add automated unit and integration tests.
* Add structured logging and error monitoring.
* Deploy the application to AWS using a CI/CD pipeline.

## Author

**Ikram1234**

GitHub: https://github.com/ikram1234

## Disclaimer

This project is intended for learning and demonstration purposes. It is not a production-ready payment system. Additional security checks, testing, monitoring, and production configuration are required before handling real transactions.

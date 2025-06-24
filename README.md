# Django Phone Number Authentication

![Django Phone Auth System](https://media.geeksforgeeks.org/wp-content/uploads/20231006174619/majjekbehbe.png)

Implement secure phone number-based authentication in Django by replacing traditional username/password login.

## Key Features
- **Phone-as-primary-identifier** - No usernames required
- **Custom User Model** - Extends `AbstractUser`
- **OTP-ready architecture** - Easily integrate verification
- **Admin-compatible** - Full Django admin support
- **Production-grade** - Scalable and secure

## Implementation

### 1. Custom User Model
```python
# models.py
from django.contrib.auth.models import AbstractUser

class User(AbstractUser):
    username = None
    phone = models.CharField(max_length=15, unique=True)
    
    USERNAME_FIELD = 'phone'
    REQUIRED_FIELDS = []

    objects = UserManager()


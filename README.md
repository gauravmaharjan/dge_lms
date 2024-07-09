# DGE LMS Project Configuration Guide

 This guide will help you set up and configure the project environment.

## Prerequisites

Before you begin, ensure you have the following installed on your machine:

- PHP (version >= 8.0)
- Composer
- Symfony CLI
- MySql

## Installation

Follow these steps to get the project up and running on your local machine:

1. **Clone the repository:**
2. **Install Dependencies:** composer install
3. **ENV Setup:** 
Ensure .env file has: APP_ENV = dev  
                      APP_SECRET setup
                      DATABASE_URL="mysql://root@127.0.0.1:3306/dge_lms"
                      MESSENGER_TRANSPORT_DSN=doctrine://default?auto_setup=0
4. **Database Setup:** Use any Mysql database with username=root password='' and create a database named <dge_lms>
                       php bin/console doctrine:database:create
                       php bin/console doctrine:schema:update --force
                       php bin/console doctrine:migrations:migrate
5. **Use symfony CLI:** symfony server:start


## API Testing

Use Postman or any other API testing tool: 

**GET All Guest Loyalty Rewards:**

- **Method:** `GET`
- **URL:** `http://localhost:8000/api/guest-loyalty-rewards/`
- **Headers:** (none required)
- **Body:** (none)

**GET a Specific Guest Loyalty Reward:**

- **Method:** `GET`
- **URL:** `http://localhost:8000/api/guest-loyalty-rewards/{id}`
- **Headers:** (none required)
- **Body:** (none)

**Create a New Guest Loyalty Reward:**

 - **Method:** `POST`
 - **URL:** `http://localhost:8000/api/guest-loyalty-rewards/`
 - **Headers:** `Content-Type: application/json`
 - **Body:**
 ```json
 {
     "name": "Test Reward",
     "description": "Description of the test reward.",
     "points_required": "22"
 }
 ```

**Update an Existing Guest Loyalty Reward:**

  -**Method:** `PUT or PATCH`
  -**URL:** `http://localhost:8000/api/guest-loyalty-rewards/{id}`
  -**Headers:** `Content-Type: application/json`
 - **Body:**
 ```json
     {
         "name": "Updated Reward Name",
         "description": "Updated description."
     }
 ```

 **Delete a Guest Loyalty Reward:**

- **Method:** `GET`
- **URL:** `http://localhost:8000/api/guest-loyalty-rewards/{id}`
- **Headers:** (none required)
- **Body:** (none)

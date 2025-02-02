# BharatFD Backend Assignment

## Overview
This is my submission for the BharatFD Backend Assignment. I have successfully completed all the required tasks and functionalities outlined in the assignment. Below is an overview of how the project works.

## Tech Stack Used
- **Backend**: Django
- **Database**: SQLite3 (In-Memory)
- **Caching**: Redis
- **Containerization**: Docker

## Assumptions Made
- The `.env` file has not been used to store the secret key to avoid complications while testing the application on a different system. Instead, the key is kept as-is for ease of access.
- An in-memory database (SQLite3) is used since no specific database requirement was mentioned. This also improves application latency compared to using a cloud database.
- The default Django Admin Panel is utilized instead of building a custom one. To access it, you may use the provided superuser account or create a new one.
- Unit tests are configured as a Docker service, meaning they will only execute when Docker is installed and running. The "wait-for-it.sh" script is used to ensure all services are up before testing begins.

## Superuser Credentials
- **Username**: `testaccount`
- **Password**: `1234`

## Implemented Features
- REST APIs to manage FAQs
- WYSIWYG editor support in the admin panel
- Cached translations to optimize repeated translation requests
- Docker containerization for seamless deployment and isolation

## Running the Project

### Step 1: Install Docker (if not already installed)
- **For Windows**: Start Docker by clicking on the application icon.
- **For Linux**: Use the following command to start Docker:
  ```sh
  systemctl start docker
  ```

### Step 2: Start the Services with Docker Compose
```sh
docker-compose up --build
```

### Step 3: Verify that All Services are Running
- The test service will execute automatically to display the unit test results.


### Step 4: Manually Run Test Cases (if needed)
```sh
docker-compose run test
```

## API Endpoints
| Method | Endpoint | Description |
|--------|---------|-------------|
| **GET** | `/api/faq` | Retrieve all FAQs |
| **GET** | `/api/faq/:lang` | Retrieve FAQs in a specific language (defaults to English for unsupported languages) |
| **POST** | `/api/add_faq` | Add a new FAQ (requires "question" and "answer" fields in the request body) |

## License
This project is for assessment purposes only and does not include any licensing terms.


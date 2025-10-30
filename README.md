# Tripz Holidays Mock Server

A mock server for the Tripz Holidays travel booking application, providing RESTful API endpoints for testing and development purposes.

## Project Overview

Tripz Holidays Mock Server is a JSON-based mock API server designed to simulate backend functionality for a travel booking application. This mock server helps developers test and develop frontend applications without needing a complete backend infrastructure. It provides endpoints for managing destinations, bookings, users, and travel packages.

## Features

- **RESTful API Endpoints**: Full CRUD operations for all resources
- **JSON-based Database**: Simple file-based data storage using `tripzholidays_db.json`
- **Multiple Resources**: 
  - Destinations
  - Travel Packages
  - Bookings
  - User Management
  - Reviews and Ratings
- **Quick Setup**: Minimal configuration required to get started
- **CORS Enabled**: Cross-origin requests supported for frontend integration
- **Search and Filter**: Query parameters for filtering and searching data

## Prerequisites

- Node.js (v12 or higher)
- npm or yarn package manager

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/monkovatechnologies/tripzholidays-mockServer.git
cd tripzholidays-mockServer
```

### 2. Install Dependencies

```bash
npm install
# or
yarn install
```

### 3. Install JSON Server (if not already installed)

```bash
npm install -g json-server
# or
yarn global add json-server
```

### 4. Start the Mock Server

```bash
json-server --watch tripzholidays_db.json --port 3000
```

The server will start at `http://localhost:3000`

### 5. Access the API

Once running, you can access:
- API Root: `http://localhost:3000`
- Sample endpoint: `http://localhost:3000/destinations`

## API Usage

### Base URL

```
http://localhost:3000
```

### Available Endpoints

Refer to `README_Tripzholidays_Mock_API.md` for detailed API documentation including:

- **GET** requests for fetching data
- **POST** requests for creating new entries
- **PUT/PATCH** requests for updating existing entries
- **DELETE** requests for removing entries

### Example Requests

#### Get All Destinations
```bash
curl http://localhost:3000/destinations
```

#### Get Specific Destination by ID
```bash
curl http://localhost:3000/destinations/1
```

#### Create New Booking
```bash
curl -X POST http://localhost:3000/bookings \
  -H "Content-Type: application/json" \
  -d '{"userId": 1, "destinationId": 5, "bookingDate": "2025-11-15"}'
```

#### Update Booking
```bash
curl -X PUT http://localhost:3000/bookings/1 \
  -H "Content-Type: application/json" \
  -d '{"userId": 1, "destinationId": 5, "bookingDate": "2025-11-20", "status": "confirmed"}'
```

#### Delete Booking
```bash
curl -X DELETE http://localhost:3000/bookings/1
```

### Query Parameters

JSON Server supports various query parameters:

- **Filter**: `?field=value`
- **Paginate**: `?_page=1&_limit=10`
- **Sort**: `?_sort=field&_order=asc`
- **Search**: `?q=searchterm`

## Database Structure

The mock database (`tripzholidays_db.json`) contains the following collections:

- `destinations` - Travel destinations with details
- `packages` - Travel packages and deals
- `bookings` - User bookings and reservations
- `users` - User account information
- `reviews` - Customer reviews and ratings

## Development

### Running in Development Mode

```bash
npm run dev
```

### Custom Port

To run on a different port:

```bash
json-server --watch tripzholidays_db.json --port 8080
```

### Enable CORS

CORS is enabled by default in JSON Server, but you can customize headers if needed.

## Testing

You can test the API using:

- **Postman**: Import endpoints and test manually
- **cURL**: Command-line testing (examples above)
- **Browser**: GET requests can be tested directly in the browser
- **Frontend Application**: Integrate with your React/Angular/Vue application

## Documentation

For detailed API documentation, please refer to:
- [README_Tripzholidays_Mock_API.md](./README_Tripzholidays_Mock_API.md) - Complete API endpoint documentation

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License.

MIT License

Copyright (c) 2025 Monkova Technologies

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

## Support

For issues, questions, or suggestions:
- Open an issue on GitHub
- Contact: Monkova Technologies

## Acknowledgments

- Built with [JSON Server](https://github.com/typicode/json-server)
- Created by Monkova Technologies

---

**Happy Coding! 🚀✈️**

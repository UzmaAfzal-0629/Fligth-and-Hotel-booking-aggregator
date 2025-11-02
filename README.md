# TravelEase - Flight and Hotel Booking Platform

A comprehensive MERN stack application for flight and hotel booking with real-time search capabilities and user management.

## Features

### Backend Features
- **Authentication System**: JWT-based secure authentication
- **MongoDB Integration**: Mongoose ODM for data management
- **RESTful API**: Complete API endpoints for all operations
- **Amadeus API Integration**: Real-time flight data
- **Hotel Management**: CRUD operations for hotel bookings
- **Booking System**: Complete booking management with status tracking
- **Security**: Helmet, CORS, and rate limiting middleware

### Frontend Features
- **Modern React**: React 18 with hooks and context API
- **Responsive Design**: Mobile-first approach with custom CSS
- **Authentication**: Secure user registration and login
- **Flight Search**: Advanced search with autocomplete
- **Hotel Search**: Filtering and booking capabilities
- **User Dashboard**: Booking history and profile management
- **Professional UI**: Custom CSS styling (no external dependencies)

## Technology Stack

### Backend
- **Runtime**: Node.js
- **Framework**: Express.js
- **Database**: MongoDB with Mongoose
- **Authentication**: JWT (JSON Web Tokens)
- **Security**: Helmet, CORS, Express Rate Limit
- **API Integration**: Amadeus Travel API

### Frontend
- **Framework**: React.js 18
- **Routing**: React Router DOM
- **Styling**: Custom CSS (Tailwind-independent)
- **Icons**: Lucide React
- **HTTP Client**: Axios
- **State Management**: React Context API

## Installation

### Prerequisites
- Node.js (v14 or higher)
- MongoDB (local or Atlas)
- Amadeus API credentials

### Setup Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/Amit-887/Flight-and-Hotel-Aggregator-.git
   cd Flight-and-Hotel-Aggregator-
   ```

2. **Install dependencies**
   ```bash
   npm run setup
   ```

3. **Environment Configuration**
   Create a `.env` file in the root directory:
   ```env
   PORT=5001
   MONGODB_URI=mongodb://localhost:27017/travelease
   JWT_SECRET=your_jwt_secret_key
   AMADEUS_CLIENT_ID=your_amadeus_client_id
   AMADEUS_CLIENT_SECRET=your_amadeus_client_secret
   ```

4. **Seed Database** (Optional)
   ```bash
   npm run seed
   ```

5. **Start Development Server**
   ```bash
   npm run dev:full
   ```

## Available Scripts

### Root Directory
- `npm run setup` - Install all dependencies (backend + frontend)
- `npm run dev:full` - Start both backend and frontend servers
- `npm run server` - Start backend server only
- `npm run client` - Start frontend server only
- `npm run build` - Build frontend for production
- `npm run seed` - Populate database with sample data

### Client Directory
- `npm start` - Start React development server
- `npm run build` - Build for production
- `npm test` - Run tests

## API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `GET /api/auth/me` - Get current user

### Flights
- `GET /api/flights/search` - Search flights
- `GET /api/flights/locations` - Get airport locations

### Hotels
- `GET /api/hotels` - Get all hotels
- `GET /api/hotels/:id` - Get hotel by ID
- `POST /api/hotels` - Create new hotel (admin)

### Bookings
- `GET /api/bookings` - Get user bookings
- `POST /api/bookings` - Create new booking
- `PUT /api/bookings/:id` - Update booking
- `DELETE /api/bookings/:id` - Cancel booking

## Application Structure

```
├── client/                 # React frontend
│   ├── src/
│   │   ├── components/    # Reusable components
│   │   ├── pages/         # Page components
│   │   ├── context/       # React context
│   │   ├── utils/         # Utility functions
│   │   └── ...
├── models/                # MongoDB models
├── routes/                # Express routes
├── middleware/            # Custom middleware
├── utils/                 # Backend utilities
├── server.js              # Main server file
└── package.json           # Dependencies
```

## Key Features

### User Authentication
- Secure registration and login
- JWT token-based authentication
- Protected routes and middleware

### Flight Search
- Real-time flight data from Amadeus API
- Airport autocomplete functionality
- Advanced search filters
- Multiple travel classes support

### Hotel Booking
- Comprehensive hotel listings
- Advanced filtering options
- Location-based search
- Rating and price filters

### User Dashboard
- Booking history management
- Profile information
- Booking status tracking
- Responsive design

## Security Features

- **JWT Authentication**: Secure token-based authentication
- **Password Hashing**: bcryptjs for password security
- **Rate Limiting**: Prevent API abuse
- **CORS Protection**: Cross-origin resource sharing
- **Helmet**: Security headers
- **Input Validation**: Server-side validation

## Custom CSS Implementation

This project uses **custom CSS** instead of Tailwind CSS, providing:
- **Zero Dependencies**: No external CSS frameworks
- **Custom Design System**: Consistent styling across components
- **Responsive Design**: Mobile-first approach
- **Performance**: Optimized CSS without unused styles
- **Maintainability**: Organized CSS structure

## Database Models

### User Model
```javascript
{
  name: String,
  email: String (unique),
  password: String (hashed),
  phone: String,
  createdAt: Date
}
```

### Hotel Model
```javascript
{
  name: String,
  location: String,
  description: String,
  price: Number,
  rating: Number,
  amenities: [String],
  images: [String]
}
```

### Booking Model
```javascript
{
  user: ObjectId,
  type: String (flight/hotel),
  details: Object,
  status: String,
  totalAmount: Number,
  createdAt: Date
}
```

## Deployment

### Production Build
```bash
npm run build
```

### Environment Variables for Production
```env
NODE_ENV=production
PORT=5001
MONGODB_URI=your_production_mongodb_uri
JWT_SECRET=your_production_jwt_secret
AMADEUS_CLIENT_ID=your_amadeus_client_id
AMADEUS_CLIENT_SECRET=your_amadeus_client_secret
```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

**Amit Kumar**
- GitHub: [@UzmaAfzal-0629](https://github.com/UzmaAfzal-0629)
- Project: [Flight and Hotel Aggregator](https://github.com/UzmaAfzal-0629/Fligth-and-Hotel-booking-aggregator)

## Acknowledgments

- Amadeus Travel API for flight data
- React.js community for excellent documentation
- MongoDB for robust database solutions
- Express.js for the powerful backend framework

# Grocery Store E-Commerce Application

A full-stack web application for an online grocery store, built with React for the frontend and Node.js/Express for the backend. The application allows users to browse products by categories, add items to a shopping cart, place orders, and manage their accounts. Administrators can manage users, categories, products, and orders through a dedicated admin panel.

## Tech Stack / Technologies Used

### Frontend
- **React** (v18.3.1) - JavaScript library for building user interfaces
- **React Router DOM** (v6.24.0) - Declarative routing for React
- **Axios** (v1.7.2) - HTTP client for making API requests
- **React Toastify** (v10.0.5) - Toast notifications
- **Bootstrap Icons** (v1.11.3) - Icon library
- **React Slideshow Image** (v4.3.1) - Image slideshow component
- **Bootstrap CSS** - CSS framework for styling
- **Font Awesome** - Icon font library
- **jQuery** - JavaScript library for DOM manipulation

### Backend
- **Node.js** with **Express.js** (v4.19.2) - Web framework for Node.js
- **MongoDB** with **Mongoose** (v8.4.4) - NoSQL database and ODM
- **Multer** (v1.4.5-lts.1) - Middleware for handling file uploads
- **CORS** (v2.8.5) - Middleware for enabling Cross-Origin Resource Sharing

### Development and Testing
- **React Scripts** (v5.0.1) - Build scripts and development server for React
- **Jest** and **React Testing Library** - Testing frameworks
- **Nodemon** - Tool for automatically restarting the server during development

## Features

### User Features
- User registration and login
- Browse products by categories
- Search products
- View product details
- Add products to shopping cart
- Checkout and place orders
- View order history
- Change password
- Contact page

### Admin Features
- Manage users (view, search, delete)
- Manage product categories (add, update, delete)
- Manage products (add, update, delete)
- View and update order status
- View all orders and order details

### General Features
- Responsive design with Bootstrap
- Image upload for products and categories
- Toast notifications for user feedback
- Session-based authentication

## Project Folder Structure

```
grocery/
├── package.json                 # Project dependencies and scripts
├── server.js                    # Express server and API endpoints
├── public/                      # Static files served by React
│   ├── index.html               # Main HTML file
│   ├── manifest.json            # Web app manifest
│   ├── robots.txt               # Robots file for SEO
│   ├── css/                     # Stylesheets
│   │   ├── bootstrap.css
│   │   ├── font-awesome.css
│   │   ├── jstarbox.css
│   │   └── style.css
│   ├── fonts/                   # Font files
│   ├── images/                  # Static images
│   ├── js/                      # JavaScript libraries
│   │   ├── bootstrap.js
│   │   ├── easing.js
│   │   ├── easyResponsiveTabs.js
│   │   ├── jquery-1.11.1.min.js
│   │   ├── jquery.mycart.js
│   │   ├── jquery.vide.min.js
│   │   ├── jquery.zoomtoo.js
│   │   ├── jstarbox.js
│   │   ├── modernizr.custom.js
│   │   ├── move-top.js
│   │   └── Uploads/             # Uploaded images (categories/products)
│   └── video/                   # Video files
├── src/                         # React application source
│   ├── App.css                  # Main app styles
│   ├── App.js                   # Main React component
│   ├── App.test.js              # App component tests
│   ├── index.css                # Global styles
│   ├── index.js                 # React app entry point
│   ├── reportWebVitals.js       # Performance monitoring
│   ├── setupTests.js            # Test setup
│   └── Components/              # React components
│       ├── AdminHeader.js       # Header for admin users
│       ├── AdminHome.js         # Admin dashboard
│       ├── Categories.js        # Product categories page
│       ├── Changepassword.js    # Change password page
│       ├── Checkout.js          # Checkout process
│       ├── Contact.js           # Contact page
│       ├── Details.js           # Product details page
│       ├── Footer.js            # Site footer
│       ├── Header.js            # Main site header
│       ├── Home.js              # Home page
│       ├── ListofUsers.js       # Admin: list all users
│       ├── Login.js             # Login page
│       ├── ManageCategory.js    # Admin: manage categories
│       ├── ManageProduct.js     # Admin: manage products
│       ├── OrderHistory.js      # User order history
│       ├── OrderItems.js        # Order items view
│       ├── OrderSummary.js      # Order summary
│       ├── Products.js          # Products listing
│       ├── Projectroutes.js     # Application routing
│       ├── Register.js          # User registration
│       ├── SearchProducts.js    # Product search
│       ├── SearchUser.js        # Admin: search users
│       ├── Showcart.js          # Shopping cart
│       ├── UpdateStatus.js      # Admin: update order status
│       └── ViewOrders.js        # Admin: view orders
```

## Installation Steps

1. **Clone the repository:**
   ```
   git clone https://github.com/BhavyaSharma17/Grocery-store.git
   cd grocery
   ```

2. **Install dependencies:**
   ```
   npm install
   ```

3. **Set up MongoDB:**
   - Install MongoDB on your system
   - Start MongoDB service (default port 27017)
   - The application connects to `mongodb://127.0.0.1:27017/projectdb`

4. **Create uploads directory:**
   - Ensure the `public/Uploads/` directory exists for file uploads

## Environment Variables

No environment variables are required. The MongoDB connection string is hardcoded in `server.js`. For production deployment, consider moving sensitive configurations to environment variables.

## How to Run the Project

### Development Mode

1. **Start the backend server:**
   ```
   npm run server / nodemon server
   ```
   This starts the Express server on port 9000 using Nodemon.

2. **Start the React frontend:**
   ```
   npm start
   ```
   This starts the React development server on port 3000.

3. **Access the application:**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:9000

### Production Mode

1. **Build the React application:**
   ```
   npm run build
   ```
   This creates a production build in the `build` folder.

2. **Serve the built application:**
   - The built files in `build` can be served by any static file server
   - The backend server (`server.js`) should be started separately in production

## API / Modules Overview

The backend provides RESTful APIs for all application functionality:

### User Management
- `POST /api/register` - User registration
- `POST /api/login` - User login
- `GET /api/searchuser` - Search users
- `GET /api/getallusers` - Get all users
- `DELETE /api/deluser/:uid` - Delete user
- `PUT /api/changepassword` - Change password

### Categories
- `POST /api/savecategory` - Add category
- `GET /api/getallcat` - Get all categories
- `PUT /api/updatecategory` - Update category
- `DELETE /api/delcategory/:id` - Delete category

### Products
- `POST /api/saveproduct` - Add product
- `GET /api/fetchprodsbycatid` - Get products by category
- `GET /api/getproddetails` - Get product details
- `GET /api/fetchnewprods` - Get newest products
- `GET /api/searchproducts` - Search products
- `PUT /api/updateproduct` - Update product

### Shopping Cart
- `POST /api/savetocart` - Add to cart
- `GET /api/getcart` - Get cart items
- `DELETE /api/deletecart` - Clear cart
- `DELETE /api/delcartitem/:uid` - Remove cart item

### Orders
- `POST /api/saveorder` - Place order
- `GET /api/getallorders` - Get all orders (admin)
- `GET /api/getuserorders` - Get user orders
- `GET /api/getorderid` - Get latest order
- `GET /api/getorderproducts` - Get order products
- `PUT /api/updatestatus` - Update order status
- `PUT /api/updatestock` - Update product stock

## Future Improvements or Roadmap

- Implement payment gateway integration (e.g., Razorpay, PayPal)
- Add user reviews and ratings for products
- Implement email notifications for orders
- Add inventory management features
- Implement user profile management
- Add product recommendations
- Mobile app development
- Multi-language support
- Advanced search and filtering options

## Contributing

Pull requests are welcome!  
For major changes, please open an issue first to discuss what you would like to change.

## License

This project is licensed under the [MIT License](https://choosealicense.com/licenses/mit/).


Made with ❤️ by [Bhavya Sharma](https://github.com/BhavyaSharma17)
# Server Routes Coordination Guidelines

## Route Integration Order in server.js

```javascript
// Current route order in server.js:
app.use('/api/auth', require('./routes/authRoutes'));           // Shared - Authentication
app.use('/api/products', require('./routes/productRoutes'));     // Member 1 - Products
app.use('/api/orders', require('./routes/orderRoutes'));         // Member 2 - Orders
app.use('/api/customs', require('./routes/customizationRoutes')); // Member 3 - Customizations
app.use('/api/custom-requests', require('./routes/customRequestRoutes')); // Member 3 - Custom Requests
app.use('/api/promos', require('./routes/promoRoutes'));         // Member 4 - Promotions
app.use('/api/reviews', require('./routes/reviewRoutes'));       // Member 5 - Reviews
app.use('/api/media', require('./routes/mediaRoutes'));          // Member 6 - Media
```

## Adding New Routes

When adding new routes to `server.js`, follow this order:

1. **Authentication routes** (always first)
2. **Core entities** (products, orders)
3. **Customization features** (customizations, custom requests)
4. **Marketing features** (promos, reviews)
5. **Media/storage** (always last)

## Route Naming Conventions

### Member 1 (Products):
- `GET /api/products` - Get all products
- `GET /api/products/:id` - Get single product
- `POST /api/products` - Create product (admin)
- `PUT /api/products/:id` - Update product (admin)
- `DELETE /api/products/:id` - Delete product (admin)

### Member 2 (Orders):
- `GET /api/orders` - Get user orders
- `GET /api/orders/:id` - Get single order
- `POST /api/orders` - Create order
- `PUT /api/orders/:id/status` - Update order status
- `PUT /api/orders/:id/cancel` - Cancel order

### Member 3 (Customizations):
- `GET /api/customs` - Get customizations
- `POST /api/customs` - Create customization
- `PUT /api/customs/:id/approve` - Approve customization (admin)
- `PUT /api/customs/:id/reject` - Reject customization (admin)

### Member 3 (Custom Requests):
- `GET /api/custom-requests` - Get custom requests
- `POST /api/custom-requests` - Create custom request
- `PUT /api/custom-requests/:id/quote` - Provide quote (admin)

### Member 4 (Promos):
- `GET /api/promos` - Get active promos
- `POST /api/promos` - Create promo (admin)
- `PUT /api/promos/:id` - Update promo (admin)
- `DELETE /api/promos/:id` - Delete promo (admin)

### Member 5 (Reviews):
- `GET /api/reviews` - Get reviews
- `POST /api/reviews` - Create review
- `PUT /api/reviews/:id` - Update review
- `DELETE /api/reviews/:id` - Delete review

### Member 6 (Media):
- `POST /api/media/upload` - Upload media
- `GET /api/media/photos/:category` - Get photos by category
- `GET /api/media/categories/stats` - Get category stats

## Route Security

### Public Routes (No Authentication):
- `GET /api/products` - Browse products
- `GET /api/promos` - View active promos
- `GET /api/reviews` - Read reviews

### User Routes (Require Authentication):
- `GET /api/orders` - View own orders
- `POST /api/orders` - Create order
- `POST /api/customs` - Create customization
- `POST /api/reviews` - Create review

### Admin Routes (Require Admin Role):
- `POST /api/products` - Create product
- `PUT /api/products/:id` - Update product
- `DELETE /api/products/:id` - Delete product
- `PUT /api/customs/:id/approve` - Approve customization
- `PUT /api/customs/:id/reject` - Reject customization
- `POST /api/promos` - Create promo
- `PUT /api/promos/:id` - Update promo
- `DELETE /api/promos/:id` - Delete promo

## Middleware Integration

Each member should use appropriate middleware:

```javascript
// Authentication middleware
const { protect } = require('../middleware/authMiddleware');

// Admin middleware
const { admin } = require('../middleware/adminMiddleware');

// Example usage in route files:
router.post('/', protect, admin, createProduct);  // Admin only
router.post('/', protect, createOrder);           // Authenticated users
router.get('/', getProducts);                     // Public access
```

## Route Testing

Each member should test their routes:

```javascript
// Test your routes using the provided test files:
node testApi.js  // General API testing
node testDb.js   // Database connection testing
```

## Conflicts Prevention

1. **Route paths**: Ensure no duplicate route paths
2. **HTTP methods**: Use appropriate HTTP methods (GET, POST, PUT, DELETE)
3. **Middleware order**: Apply middleware in correct order
4. **Response formats**: Use consistent response structure across all routes

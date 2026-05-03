# File Division Structure for 6 Team Members

## Member 1: Product & Inventory Manager
**Branch:** `feature/product-management`

### Backend Files (Owned)
- `backend/models/Product.js`
- `backend/controllers/productController.js`
- `backend/routes/productRoutes.js`
- `backend/seedProducts.js`
- `backend/uploads/` (product images)

### Frontend Files (Owned)
- `frontend/src/screens/ProductListScreen.js`
- `frontend/src/screens/HomeScreen.js` (product display sections)

### API Services (Owned)
- `getProducts()` in `frontend/src/services/api.js`

---

## Member 2: Order & Transaction Lead
**Branch:** `feature/order-management`

### Backend Files (Owned)
- `backend/models/Order.js`
- `backend/controllers/orderController.js`
- `backend/routes/orderRoutes.js`

### Frontend Files (Owned)
- `frontend/src/screens/CheckoutScreen.js`
- `frontend/src/screens/OrderHistoryScreen.js`

### API Services (Owned)
- `getOrders()`, `cancelOrder()` in `frontend/src/services/api.js`

---

## Member 3: Personalized Customization Specialist
**Branch:** `feature/customization-system`

### Backend Files (Owned)
- `backend/models/Customization.js`
- `backend/controllers/customizationController.js`
- `backend/routes/customizationRoutes.js`
- `backend/controllers/customRequestController.js`
- `backend/routes/customRequestRoutes.js`
- `backend/models/CustomRequest.js`

### Frontend Files (Owned)
- `frontend/src/screens/CustomizationScreen.js`
- `frontend/src/screens/CustomRequestScreen.js`
- `frontend/src/screens/CustomerCustomRequestsScreen.js`
- `frontend/src/screens/AdminCustomRequestScreen.js`

### API Services (Owned)
- All customization and custom request APIs in `frontend/src/services/api.js`

---

## Member 4: Promotions & Discount Engine
**Branch:** `feature/promo-system`

### Backend Files (Owned)
- `backend/models/PromoCode.js`
- `backend/controllers/promoController.js`
- `backend/routes/promoRoutes.js`
- `backend/seedPromos.js`

### Frontend Files (Owned)
- `frontend/src/screens/PromoScreen.js`
- Promo-related components in `frontend/src/screens/CheckoutScreen.js`

### API Services (Owned)
- Promo-related API calls (to be added to `frontend/src/services/api.js`)

---

## Member 5: Customer Feedback & Rating Moderator
**Branch:** `feature/review-system`

### Backend Files (Owned)
- `backend/models/Review.js`
- `backend/controllers/reviewController.js`
- `backend/routes/reviewRoutes.js`

### Frontend Files (Owned)
- `frontend/src/screens/ReviewScreen.js`
- Review components in product detail screens

### API Services (Owned)
- Review APIs (to be added to `frontend/src/services/api.js`)

---

## Member 6: Media Storage & Deployment Engineer
**Branch:** `feature/media-deployment`

### Backend Files (Owned)
- `backend/models/Media.js`
- `backend/controllers/mediaController.js`
- `backend/routes/mediaRoutes.js`
- `backend/uploads/` (all media storage)
- `backend/.env` (deployment configuration)
- `backend/server.js` (media routes and deployment config)

### Frontend Files (Owned)
- `frontend/src/screens/MediaScreen.js`
- `frontend/src/screens/MediaGalleryScreen.js`
- Image picker components across all screens

### API Services (Owned)
- `uploadMedia()`, `getPhotosByCategory()`, `getCategoryStats()` in `frontend/src/services/api.js`

---

## Shared Files (All Members - Coordinate Changes)

### Backend Shared
- `backend/server.js` - Route integration (each member adds their routes)
- `backend/models/User.js` - User references across all modules
- `backend/controllers/authController.js` - Authentication needed by all
- `backend/routes/authRoutes.js` - Authentication routes
- `backend/middleware/` - Authentication and admin middleware
- `backend/package.json` - Dependencies management
- `backend/testApi.js`, `backend/testDb.js`, `backend/testDb2.js` - Testing utilities

### Frontend Shared
- `frontend/src/services/api.js` - API service layer (each member adds their endpoints)
- `frontend/src/screens/LoginScreen.js` - Authentication
- `frontend/src/screens/RegisterScreen.js` - User registration
- `frontend/src/screens/AdminScreen.js` - Admin dashboard (shared components)
- `frontend/App.js` - Navigation and routing
- `frontend/package.json` - Dependencies management

## Coordination Rules

1. **Shared Files**: Always create pull requests for shared file changes
2. **API Services**: Add endpoints in alphabetical order within each section
3. **Server Routes**: Add routes in designated sections (see SERVER_ROUTES.md)
4. **Model References**: Use proper MongoDB relationships to avoid circular dependencies
5. **Frontend Navigation**: Coordinate navigation flow between different screens

## File Modification Guidelines

### DO Modify:
- Your assigned files (any changes needed)
- Shared files through pull requests only

### DO NOT Modify:
- Other members' assigned files without permission
- Core configuration files without team discussion

### Testing:
- Test your changes before committing
- Ensure no breaking changes to shared dependencies
- Verify API endpoints work correctly

# Project Roadmap: Futuristic Dropshipping Store

## Phase 0: Environment & Setup
- [x] Initialize Git repository <!-- id: 9 -->
- [x] Create `.gitignore` (node_modules, .env, dist, etc.) <!-- id: 10 -->
- [ ] Set up Monorepo structure (if using TurboRepo) or simple Client/Server pointers <!-- id: 11 -->
- [ ] **Frontend Setup (Apps/Store)**
    - [ ] Initialize Next.js 14+ (App Router, TypeScript)
    - [ ] Install Tailwind CSS & Configure `tailwind.config.ts`
    - [ ] Install Framer Motion, Lucide React (Icons), clsx, tailwind-merge
    - [ ] Setup absolute imports (`@/components`, `@/lib`, etc.)
    - [ ] Create `.env.local` template
- [ ] **Backend Setup (Server)**
    - [ ] Initialize Node.js + Express project
    - [ ] Install TypeScript, ts-node, nodemon
    - [ ] Setup folder structure (controllers, models, routes, middleware, config, utils)
    - [ ] Install Dependencies: `express`, `mongoose`, `dotenv`, `cors`, `helmet`, `morgan`
    - [ ] Create `.env` template
- [ ] **Database Setup**
    - [ ] Create MongoDB Atlas Cluster
    - [ ] Get Connection String
    - [ ] Whitelist IP addresses

## Phase 1: Frontend Foundation (Futuristic Vexo Design)
- [ ] **Design System & Global Styles**
    - [ ] Define CSS Variables for Colors (Obsidian Black, Neon Blue, Metallic Gold)
    - [ ] Configure Typography (Inter / Space Grotesk)
    - [ ] Create reusable simple components: `Button` (Glow effect), `Input`, `Card`
- [ ] **Layout Architecture**
    - [ ] Build `Navbar` (Floating, Glassmorphism, Responsive)
    - [ ] Build `Footer` (Clean links, social icons)
    - [ ] Create `Layout` wrapper with Smooth Scroll (Lenis or similar optional)
- [ ] **Homepage Strategy**
    - [ ] Hero Section (Video/High-res Image, Animated Text, CTA)
    - [ ] Featured Collections (Hover reveal effects)
    - [ ] Trending Products Grid (3D tilt or glow on hover)
    - [ ] Trust Badges / USP Section (Icons with motion)

## Phase 2: Backend Foundation
- [ ] **Server Core**
    - [ ] Setup Express App instance with CORS & JSON parsing
    - [ ] Create Global Error Handling Middleware
    - [ ] Create Async Wrapper for controllers
    - [ ] Setup Logger (Winston/Morgan)
- [ ] **Database Connection**
    - [ ] Implement Mongoose connection logic using Async/Await
    - [ ] Handle connection errors gracefully

## Phase 3: Database & Models
- [ ] **User Model** (`name`, `email`, `password`, `role`, `address`, `history`)
- [ ] **Product Model** (`title`, `slug`, `price`, `discount`, `images[]`, `stock`, `category`, `variants`)
- [ ] **Order Model** (`user`, `products`, `total`, `status`, `paymentInfo`, `shippingAddress`)
- [ ] **Coupon Model** (`code`, `discount`, `expiry`)
- [ ] **Seed Script**
    - [ ] Create script to seed initial Admin user
    - [ ] Create script to seed dummy Products

## Phase 4: Auth System
- [ ] **Backend Auth**
    - [ ] Install `bcryptjs`, `jsonwebtoken`
    - [ ] create `authController.register` (Hash password)
    - [ ] create `authController.login` (Generate JWT)
    - [ ] create `authMiddleware` (Verify Token)
    - [ ] create `adminMiddleware` (Check Role)
- [ ] **Frontend Auth**
    - [ ] Install `zustand` or `redux-toolkit` for State Management
    - [ ] Create Auth Store (User, Token, Login/Logout actions)
    - [ ] Build Login Page (Futuristic Form)
    - [ ] Build Register Page
    - [ ] Implement Protected Routes (HOC or Middleware)

## Phase 5: Product System
- [ ] **Backend API**
    - [ ] `GET /api/products` (Pagination, Filtering, Sorting)
    - [ ] `GET /api/products/:slug` (Single Product details)
    - [ ] `POST /api/products` (Admin only, Cloudinary/S3 Image Upload)
    - [ ] `PUT /api/products/:id` (Admin only)
    - [ ] `DELETE /api/products/:id` (Admin only)
- [ ] **Frontend Browsing**
    - [ ] Build `ProductCard` Component (Image swap on hover)
    - [ ] Build `Shop` Page (Grid layout, Sidebar filters)
    - [ ] Build `ProductDetails` Page
        - [ ] Image Gallery (Zoom effect)
        - [ ] Variant Selector (Size/Color)
        - [ ] "Add to Cart" Sticky Button
        - [ ] Related Products Slider

## Phase 6: Cart & Checkout
- [ ] **Cart Logic**
    - [ ] Create Cart Store (Add, Remove, Update Qty, Calculate Total)
    - [ ] Persist Cart to LocalStorage
    - [ ] Build `CartDrawer` (Slide-in from right)
- [ ] **Checkout Logic**
    - [ ] Build `Checkout` Page (Step wizard: Shipping -> Payment)
    - [ ] Address Form with Validation
    - [ ] Order Summary Component

## Phase 7: Payment Integration (Razorpay)
- [ ] **Backend Integration**
    - [ ] Install `razorpay` SDK
    - [ ] Create `initiatePayment` endpoint (Creates Order ID)
    - [ ] Create `verifyPayment` endpoint (HMAC signature verification)
- [ ] **Frontend Integration**
    - [ ] Load Razorpay Script dynamically
    - [ ] Handle Payment Success/Failure events
    - [ ] Redirect to `OrderSuccess` page on success

## Phase 8: Order Management
- [ ] **Backend Orders**
    - [ ] `POST /api/orders` (Create order after payment verify)
    - [ ] `GET /api/orders/my-orders` (User history)
    - [ ] `GET /api/admin/orders` (Admin view all)
    - [ ] `PUT /api/admin/orders/:id` (Update status: Processing -> Shipped)
- [ ] **Frontend Orders**
    - [ ] Build `OrderHistory` Page for Users
    - [ ] Order Details View (Tracking status visualizer)

## Phase 9: Admin Dashboard
- [ ] **Layout**
    - [ ] Admin Sidebar Layout (distinct from Main Store)
- [ ] **Dashboard Home**
    - [ ] Stats Cards (Total Sales, Orders, Users)
    - [ ] Recent Orders Table
- [ ] **Product Management**
    - [ ] Product List Table (Edit/Delete actions)
    - [ ] Add Product Form (Rich Text Editor, Image Drag & Drop)
- [ ] **Order Management**
    - [ ] Order List Table (Filter by status)
    - [ ] Status Updater Dropdown

## Phase 10: Deployment & Production Hardening
- [ ] **Security Checklist**
    - [ ] Setup Helmet & Rate Limiting (express-rate-limit)
    - [ ] Sanitize Inputs (express-mongo-sanitize, xss-clean)
    - [ ] Secure Cookies (HttpOnly)
    - [ ] Audit dependencies (`npm audit`)
- [ ] **Environment Variables**
    - [ ] Verify all secrets are in Production Env
- [ ] **Frontend Deployment (Vercel)**
    - [ ] Connect Repo
    - [ ] Set Environment Variables
    - [ ] Build & Deploy
- [ ] **Backend Deployment (Render/Railway)**
    - [ ] Connect Repo
    - [ ] Set Environment Variables
    - [ ] Build Command (`npm install && npm run build`)
    - [ ] Start Command (`npm start`)

## Phase 11: Testing & Optimization
- [ ] **Testing**
    - [ ] Manual User Flow Walkthrough (Register -> Buy -> Admin Check)
    - [ ] Cross-browser testing (Chrome, Safari, Mobile)
- [ ] **Performance**
    - [ ] Optimize Images (Next.js Image)
    - [ ] Code Splitting
    - [ ] Lightshouse Audit (Aim for 90+ Performance)
- [ ] **SEO**
    - [ ] Add Metadata (Title, Description) to all pages
    - [ ] Generate Sitemap.xml
    - [ ] Add Structured Data (Schema.org) for Products

---

## Execution Rules

1. **Atomic Features:** Only complete one feature from the checklist at a time.
2. **Git Hygiene:** Commit after every completed feature checkbox. Message format: `feat: add product card component`.
3. **Quality Gate:** Do not move to the next phase until the current phase passes manual testing.
4. **Separation of Concerns:** Keep business logic in Backend Controllers, and UI logic in Frontend Components.
5. **Coupling:** Keep frontend and backend loosely coupled. Frontend should only communicate via API.
6. **No "Tutorial Code":** Write cleaner, modular, and scalable code from day one.

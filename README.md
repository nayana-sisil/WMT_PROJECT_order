# Ego Creation Project - Team Collaboration Setup

## Project Overview
This is a personalized e-commerce mobile application with backend API, divided among 6 team members for parallel development.

## Quick Start for Team Members

### 1. Setup Your Development Environment
```bash
# Clone the repository
git clone <repository-url>
cd Ego_Creation_Project-master

# Install backend dependencies
cd backend
npm install

# Install frontend dependencies
cd ../frontend
npm install
```

### 2. Switch to Your Assigned Branch
```bash
# Replace with your assigned branch
git checkout feature/[your-branch-name]
```

### 3. Start Development Servers
```bash
# Backend (in backend folder)
npm run dev

# Frontend (in frontend folder)
npm start
```

## Team Structure

| Member | Role | Branch | Entity |
|--------|------|--------|--------|
| 1 | Product & Inventory Manager | `feature/product-management` | Product |
| 2 | Order & Transaction Lead | `feature/order-management` | Order |
| 3 | Personalized Customization Specialist | `feature/customization-system` | Customization |
| 4 | Promotions & Discount Engine | `feature/promo-system` | PromoCode |
| 5 | Customer Feedback & Rating Moderator | `feature/review-system` | Review |
| 6 | Media Storage & Deployment Engineer | `feature/media-deployment` | Media |

## Important Documentation

- **[BRANCH_ASSIGNMENTS.md](./BRANCH_ASSIGNMENTS.md)** - How to use Git branches
- **[FILE_DIVISION.md](./FILE_DIVISION.md)** - Detailed file ownership
- **[SERVER_ROUTES.md](./SERVER_ROUTES.md)** - API route coordination
- **[WORKFLOW_GUIDE.md](./WORKFLOW_GUIDE.md)** - Team workflow and processes

## Project Structure

```
Ego_Creation_Project-master/
├── backend/                 # Node.js/Express API
│   ├── controllers/         # API controllers
│   ├── models/             # MongoDB models
│   ├── routes/             # API routes
│   ├── middleware/         # Authentication & admin middleware
│   ├── uploads/            # Media storage
│   └── server.js           # Main server file
├── frontend/               # React Native/Expo mobile app
│   ├── src/
│   │   ├── screens/        # Mobile screens
│   │   └── services/       # API service layer
│   └── App.js              # Main app component
└── docs/                   # Documentation files
```

## Development Guidelines

### Do's
- Work only on your assigned files
- Test your changes before committing
- Create pull requests for shared file changes
- Follow the established naming conventions
- Document your API endpoints

### Don'ts
- Modify other members' files without permission
- Push directly to main branch
- Leave console.log statements in code
- Break existing functionality
- Ignore code review feedback

## Communication

- **Daily Standups**: 15 minutes - Progress and blockers
- **Weekly Reviews**: Code review and integration
- **Emergency Issues**: Team chat with relevant member tags

## Deployment

- **Staging**: Weekly integration testing
- **Production**: Monthly coordinated deployment
- **Rollback**: Always have rollback plan ready

## Getting Help

1. Check the documentation files first
2. Ask questions in team chat
3. Schedule meetings for complex issues
4. Document solutions for future reference

## Success Metrics

- All CRUD operations functional
- Mobile app responsive and user-friendly
- Clean integration of all modules
- Successful deployment to production
- Happy team members with clear ownership

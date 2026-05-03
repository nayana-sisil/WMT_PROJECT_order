# Branch Assignments for 6 Team Members

## Git Branch Structure
- **main**: Production-ready code
- **feature/product-management**: Member 1 - Product & Inventory Manager
- **feature/order-management**: Member 2 - Order & Transaction Lead
- **feature/customization-system**: Member 3 - Personalized Customization Specialist
- **feature/promo-system**: Member 4 - Promotions & Discount Engine
- **feature/review-system**: Member 5 - Customer Feedback & Rating Moderator
- **feature/media-deployment**: Member 6 - Media Storage & Deployment Engineer

## How to Use This Structure

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd Ego_Creation_Project-master
   ```

2. **Switch to your assigned branch:**
   ```bash
   git checkout feature/[your-branch-name]
   ```

3. **Work on your assigned files only** (see FILE_DIVISION.md for details)

4. **Push changes:**
   ```bash
   git add .
   git commit -m "Your descriptive message"
   git push origin feature/[your-branch-name]
   ```

5. **Create pull requests** to main branch when ready for integration

## Branch Protection Rules
- Never push directly to main branch
- Always create pull requests for code review
- Resolve conflicts before merging
- Test your changes thoroughly before PR

## Integration Schedule
- **Weekly**: Merge meetings for conflict resolution
- **Bi-weekly**: Integration testing on staging
- **Monthly**: Production deployment coordination

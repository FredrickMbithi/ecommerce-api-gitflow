# E-Commerce API with GitFlow

Backend API practice project demonstrating GitFlow workflow methodology for team-based development.

## Project Overview

This repository serves as a **GitFlow workflow training project** for building an e-commerce backend API. The focus is on learning proper Git branching strategies, version control best practices, and collaborative development workflows.

## GitFlow Workflow

GitFlow is a branching model for Git that defines a strict branching structure designed around project releases.

### Branch Types

1. **`main`** (or `master`) — Production-ready code
   - Only stable, release-ready code
   - Tagged with version numbers (v1.0.0, v1.1.0, etc.)
   - Never commit directly to main

2. **`develop`** — Integration branch
   - Latest delivered development changes
   - Base for feature branches
   - Continuous integration happens here

3. **`feature/*`** — New features
   - Branch from: `develop`
   - Merge back to: `develop`
   - Naming: `feature/user-authentication`, `feature/product-catalog`

4. **`release/*`** — Preparing new production releases
   - Branch from: `develop`
   - Merge to: `main` and `develop`
   - Naming: `release/1.0.0`
   - Only bug fixes, no new features

5. **`hotfix/*`** — Emergency production fixes
   - Branch from: `main`
   - Merge to: `main` and `develop`
   - Naming: `hotfix/security-patch`

## GitFlow Commands

### Initialize GitFlow
```bash
git flow init
# Accept defaults or customize branch names
```

### Feature Development
```bash
# Start new feature
git flow feature start user-authentication

# Work on feature (add commits)
git add .
git commit -m "Add user login endpoint"

# Finish feature (merges to develop)
git flow feature finish user-authentication
```

### Release Process
```bash
# Start release
git flow release start 1.0.0

# Bump version, update changelog
# Fix last-minute bugs

# Finish release (merges to main and develop, tags main)
git flow release finish 1.0.0
```

### Hotfix Process
```bash
# Start hotfix
git flow hotfix start security-patch

# Fix the issue
git add .
git commit -m "Fix SQL injection vulnerability"

# Finish hotfix (merges to main and develop, tags main)
git flow hotfix finish security-patch
```

## E-Commerce API Features (Planned)

This project will implement a backend API for managing:

### Products
- `GET /api/products` — List all products
- `GET /api/products/:id` — Get product details
- `POST /api/products` — Create new product (admin)
- `PUT /api/products/:id` — Update product (admin)
- `DELETE /api/products/:id` — Delete product (admin)

### Users
- `POST /api/auth/register` — User registration
- `POST /api/auth/login` — User login
- `GET /api/users/profile` — Get user profile
- `PUT /api/users/profile` — Update profile

### Orders
- `POST /api/orders` — Create new order
- `GET /api/orders` — List user's orders
- `GET /api/orders/:id` — Get order details
- `PUT /api/orders/:id/status` — Update order status (admin)

### Cart
- `GET /api/cart` — Get user's cart
- `POST /api/cart/items` — Add item to cart
- `DELETE /api/cart/items/:id` — Remove item from cart
- `PUT /api/cart/items/:id` — Update item quantity

## Tech Stack (Planned)

- **Backend Framework:** Django REST Framework or Express.js
- **Database:** PostgreSQL or MongoDB
- **Authentication:** JWT (JSON Web Tokens)
- **Documentation:** Swagger/OpenAPI
- **Testing:** pytest (Django) or Jest (Node.js)

## GitFlow Learning Objectives

By working with this repository, you will learn:

1. **Branch Management**
   - Creating and switching between branches
   - Merging feature branches
   - Resolving merge conflicts

2. **Version Control Best Practices**
   - Semantic versioning (MAJOR.MINOR.PATCH)
   - Meaningful commit messages
   - Git history hygiene

3. **Team Collaboration**
   - Pull request workflows
   - Code review process
   - Continuous integration

4. **Release Management**
   - Preparing releases
   - Tagging versions
   - Hotfix workflows

## Getting Started

### Prerequisites
- Git 2.5+ (for GitFlow support)
- Git Flow extensions (optional but recommended)

### Install Git Flow (Optional)

**macOS:**
```bash
brew install git-flow
```

**Ubuntu/Debian:**
```bash
sudo apt-get install git-flow
```

**Windows:**
```bash
# Download from https://gitforwindows.org/
# Or use WSL with apt-get
```

### Clone and Setup

```bash
# Clone the repository
git clone https://github.com/FredrickMbithi/ecommerce-api-gitflow.git
cd ecommerce-api-gitflow

# Initialize GitFlow (if using git-flow extensions)
git flow init -d  # -d accepts defaults

# Start working on a feature
git flow feature start product-api
```

## Workflow Example

### Scenario: Adding User Authentication

```bash
# 1. Start feature branch
git checkout develop
git flow feature start user-authentication

# 2. Implement authentication
# (create files, write code)

# 3. Commit changes
git add .
git commit -m "Implement JWT-based user authentication"

# 4. Finish feature (merges to develop)
git flow feature finish user-authentication

# 5. Push develop branch
git push origin develop
```

### Scenario: Preparing v1.0.0 Release

```bash
# 1. Start release
git flow release start 1.0.0

# 2. Update version numbers, changelog
# 3. Fix minor bugs if needed
# 4. Commit changes

# 5. Finish release (creates tag, merges to main and develop)
git flow release finish 1.0.0

# 6. Push everything
git push origin main develop --tags
```

## Resources

**GitFlow Documentation:**
- [Original GitFlow Model](https://nvie.com/posts/a-successful-git-branching-model/) by Vincent Driessen
- [Atlassian GitFlow Tutorial](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)
- [Git Flow Cheatsheet](https://danielkummer.github.io/git-flow-cheatsheet/)

**Git Best Practices:**
- [Conventional Commits](https://www.conventionalcommits.org/)
- [Semantic Versioning](https://semver.org/)

## License

Educational project - MIT License

## Author

Fredrick Mbithi  
ALX Software Engineering Student

---

**Project Focus:** GitFlow Workflow Practice  
**Learning Path:** Version Control & Team Collaboration  
**Status:** Training Repository

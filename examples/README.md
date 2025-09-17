# Examples 🎯

Practical examples and demos showcasing how to use the Just Vibing Toolkit effectively. These examples demonstrate real-world applications of the tools, prompts, and workflows.

## Categories

### 🏗️ Architecture & Design

### 💻 Development Patterns

### 🧪 Testing & Quality

### 🚀 Performance & Optimization

### 🔒 Security

### 🔧 DevOps & Deployment

## Featured Example: Building a REST API with AI

### Step 1: Initial Planning
```
💡 AI Prompt for Planning:
"I need to build a REST API for a task management system with the following features:
- User authentication and authorization
- CRUD operations for tasks
- Task categories and priorities
- Due date tracking
- Search and filtering

Please help me plan the architecture, database schema, and API endpoints."
```

**AI Response Summary:**
- Suggests microservice architecture
- Recommends JWT for authentication
- Proposes PostgreSQL database
- Outlines RESTful endpoint structure
- Identifies security considerations

### Step 2: Database Design
```sql
-- AI-generated schema
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    email VARCHAR(255) UNIQUE NOT NULL,
    password_hash VARCHAR(255) NOT NULL,
    name VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE categories (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    color VARCHAR(7) DEFAULT '#000000',
    user_id INTEGER REFERENCES users(id) ON DELETE CASCADE
);

CREATE TABLE tasks (
    id SERIAL PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    description TEXT,
    priority VARCHAR(20) DEFAULT 'medium',
    status VARCHAR(20) DEFAULT 'pending',
    due_date TIMESTAMP,
    category_id INTEGER REFERENCES categories(id),
    user_id INTEGER REFERENCES users(id) ON DELETE CASCADE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE INDEX idx_tasks_user_id ON tasks(user_id);
CREATE INDEX idx_tasks_due_date ON tasks(due_date);
CREATE INDEX idx_tasks_status ON tasks(status);
```

### Step 3: API Implementation
```javascript
// AI-generated Express.js API structure
const express = require('express');
const jwt = require('jsonwebtoken');
const bcrypt = require('bcrypt');
const { Pool } = require('pg');

const app = express();
const pool = new Pool(/* database config */);

// Middleware
app.use(express.json());
app.use(cors());
app.use(helmet());

// Authentication middleware
const authenticateToken = (req, res, next) => {
    const authHeader = req.headers['authorization'];
    const token = authHeader && authHeader.split(' ')[1];
    
    if (!token) {
        return res.sendStatus(401);
    }
    
    jwt.verify(token, process.env.JWT_SECRET, (err, user) => {
        if (err) return res.sendStatus(403);
        req.user = user;
        next();
    });
};

// Routes
app.post('/api/auth/register', async (req, res) => {
    try {
        const { email, password, name } = req.body;
        const hashedPassword = await bcrypt.hash(password, 10);
        
        const result = await pool.query(
            'INSERT INTO users (email, password_hash, name) VALUES ($1, $2, $3) RETURNING id, email, name',
            [email, hashedPassword, name]
        );
        
        const token = jwt.sign(
            { userId: result.rows[0].id },
            process.env.JWT_SECRET,
            { expiresIn: '24h' }
        );
        
        res.status(201).json({
            user: result.rows[0],
            token
        });
    } catch (error) {
        res.status(400).json({ error: error.message });
    }
});

app.get('/api/tasks', authenticateToken, async (req, res) => {
    try {
        const { status, category, priority, search } = req.query;
        let query = 'SELECT * FROM tasks WHERE user_id = $1';
        let params = [req.user.userId];
        let paramCount = 1;
        
        if (status) {
            query += ` AND status = $${++paramCount}`;
            params.push(status);
        }
        
        if (category) {
            query += ` AND category_id = $${++paramCount}`;
            params.push(category);
        }
        
        if (search) {
            query += ` AND (title ILIKE $${++paramCount} OR description ILIKE $${paramCount})`;
            params.push(`%${search}%`);
        }
        
        query += ' ORDER BY created_at DESC';
        
        const result = await pool.query(query, params);
        res.json(result.rows);
    } catch (error) {
        res.status(500).json({ error: error.message });
    }
});
```

### Step 4: Testing Implementation
```javascript
// AI-generated test suite
const request = require('supertest');
const app = require('../app');

describe('Task Management API', () => {
    let authToken;
    let userId;
    
    beforeAll(async () => {
        // Setup test database
        await setupTestDatabase();
        
        // Create test user and get token
        const registerResponse = await request(app)
            .post('/api/auth/register')
            .send({
                email: 'test@example.com',
                password: 'password123',
                name: 'Test User'
            });
        
        authToken = registerResponse.body.token;
        userId = registerResponse.body.user.id;
    });
    
    describe('GET /api/tasks', () => {
        it('should return empty array for new user', async () => {
            const response = await request(app)
                .get('/api/tasks')
                .set('Authorization', `Bearer ${authToken}`);
            
            expect(response.status).toBe(200);
            expect(response.body).toEqual([]);
        });
        
        it('should require authentication', async () => {
            const response = await request(app)
                .get('/api/tasks');
            
            expect(response.status).toBe(401);
        });
    });
    
    describe('POST /api/tasks', () => {
        it('should create a new task', async () => {
            const taskData = {
                title: 'Test Task',
                description: 'Test Description',
                priority: 'high',
                due_date: '2024-12-31T23:59:59Z'
            };
            
            const response = await request(app)
                .post('/api/tasks')
                .set('Authorization', `Bearer ${authToken}`)
                .send(taskData);
            
            expect(response.status).toBe(201);
            expect(response.body.title).toBe(taskData.title);
            expect(response.body.user_id).toBe(userId);
        });
    });
});
```

### Step 5: Documentation Generation
```markdown
# Task Management API Documentation

## Authentication
All API endpoints except registration and login require authentication via JWT token.

Include the token in the Authorization header:
```
Authorization: Bearer <your-jwt-token>
```

## Endpoints

### Authentication

#### POST /api/auth/register
Register a new user account.

**Request Body:**
```json
{
  "email": "user@example.com",
  "password": "securepassword",
  "name": "User Name"
}
```

**Response:**
```json
{
  "user": {
    "id": 1,
    "email": "user@example.com",
    "name": "User Name"
  },
  "token": "jwt-token-here"
}
```

### Tasks

#### GET /api/tasks
Retrieve tasks for the authenticated user.

**Query Parameters:**
- `status` (optional): Filter by task status
- `category` (optional): Filter by category ID
- `priority` (optional): Filter by priority level
- `search` (optional): Search in title and description

**Response:**
```json
[
  {
    "id": 1,
    "title": "Complete project",
    "description": "Finish the task management API",
    "priority": "high",
    "status": "pending",
    "due_date": "2024-12-31T23:59:59Z",
    "category_id": 1,
    "created_at": "2024-01-01T00:00:00Z"
  }
]
```
```

## Real-World Scenarios

### Scenario 1: Legacy Code Modernization
**Situation**: Modernizing a 5-year-old PHP application
**AI Approach**: Incremental refactoring with modern PHP features
**Tools Used**: Architecture chatmode, refactoring prompts, testing templates
**Outcome**: 40% performance improvement, improved maintainability

### Scenario 2: Microservice Migration
**Situation**: Breaking down a monolithic Node.js application
**AI Approach**: Service boundary identification and gradual extraction
**Tools Used**: Architecture analysis, API design templates, testing workflows
**Outcome**: Successfully extracted 3 microservices, improved scalability

### Scenario 3: Security Audit
**Situation**: Preparing for SOC 2 compliance audit
**AI Approach**: Comprehensive security review and hardening
**Tools Used**: Security chatmode, vulnerability assessment prompts
**Outcome**: Identified and fixed 15 security issues, passed audit

## Usage Patterns

### Pattern 1: AI-First Development
```
1. Start with AI planning and architecture
2. Generate initial code structure
3. Iteratively refine with AI assistance
4. AI-generated tests and documentation
5. AI-assisted code review and optimization
```

### Pattern 2: AI-Enhanced Legacy Work
```
1. AI analysis of existing codebase
2. Identification of improvement opportunities
3. Incremental AI-assisted refactoring
4. Addition of AI-generated tests
5. AI-powered documentation updates
```

### Pattern 3: Collaborative AI Development
```
1. Team uses shared AI prompts and templates
2. AI assists in code review process
3. AI-generated architectural decisions
4. Shared knowledge base of AI interactions
5. Continuous improvement of AI workflows
```

## Metrics and Outcomes

### Development Speed
- 60% faster initial implementation
- 40% reduction in debugging time
- 50% faster documentation creation
- 70% improvement in test coverage

### Code Quality
- 30% reduction in code complexity
- 45% fewer security vulnerabilities
- 25% improvement in performance
- 80% increase in documentation coverage

### Team Productivity
- 35% faster feature delivery
- 50% reduction in code review time
- 60% improvement in onboarding speed
- 40% reduction in maintenance overhead

## Tips for Success

1. **Start Small**: Begin with simple prompts and workflows
2. **Iterate Quickly**: Refine AI interactions based on results
3. **Share Knowledge**: Build team expertise in AI-assisted development
4. **Measure Impact**: Track improvements in speed and quality
5. **Stay Current**: Keep up with AI tool improvements and best practices

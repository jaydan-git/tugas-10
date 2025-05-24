# tugas-10

### Frontend:
- ReactJS
- Axios
- React Router
- (Optional) Tailwind CSS

### Backend:
- NodeJS
- Express
- MySQL
- JWT
- bcrypt

---

##  Database Structure (ERD)

### 1. `users`
| Field          | Type        | Description              |
|----------------|-------------|--------------------------|
| id             | INT (PK)    | Auto-increment ID        |
| name           | VARCHAR     | User full name           |
| email          | VARCHAR     | Unique, for login        |
| password       | VARCHAR     | Hashed password          |
| bio            | TEXT        | Short user bio           |
| profile_pic    | TEXT        | URL to profile picture   |
| created_at     | TIMESTAMP   | Account creation time    |

### 2. `posts`
| Field          | Type        | Description              |
|----------------|-------------|--------------------------|
| id             | INT (PK)    | Auto-increment ID        |
| user_id        | INT (FK)    | Reference to users.id    |
| content        | TEXT        | Post content             |
| created_at     | TIMESTAMP   | Time of posting          |

---

## 🔧 Function List

### Backend:
- Register new user (with hashed password)
- Login (generate JWT)
- Middleware to protect routes
- Get and update user profile
- Change password
- Create and retrieve posts

### Frontend:
- Auth pages (Register/Login)
- Profile display & edit
- Post feed display
- Create new post
- (Optional) Like, delete, edit post

---

##  API / Route List

### Authentication
- `POST /api/register` – Register user
- `POST /api/login` – Login, return JWT

### User Profile
- `GET /api/profile` – Get current user info (protected)
- `PUT /api/profile` – Update user info (protected)
- `PUT /api/profile/password` – Change password (protected)

### Posts
- `GET /api/posts` – Get all posts (protected)
- `POST /api/posts` – Create new post (protected)

*(Optional routes for stretch goals)*
- `PUT /api/posts/:id` – Edit own post
- `DELETE /api/posts/:id` – Delete own post
- `POST /api/posts/:id/like` – Like post

---

##  Component List (Frontend)

### Auth
- `LoginPage`
- `RegisterPage`

### Profile
- `ProfilePage`
- `EditProfileForm`
- `ChangePasswordForm`

### Posts
- `PostFeedPage`
- `PostCard`
- `NewPostForm`

### Layout & Utility
- `Navbar`
- `ProtectedRoute`
- `AxiosInstance.js` – Axios with JWT token
- `AuthContext.js` – Global auth state

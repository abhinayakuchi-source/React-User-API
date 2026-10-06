# 👥 React User API

A responsive React application that retrieves and displays user information from a public REST API using React Hooks and the JavaScript Fetch API.

This project was developed as part of a **React Hands-On Training Exercise** to practice API integration, state management, asynchronous data fetching, loading states, error handling, and deployment.

---

## 🚀 Live Demo

🔗 https://abhinayakuchi-source.github.io/React-User-API/

---

## 📌 GitHub Repository

🔗 https://github.com/abhinayakuchi-source/React-User-API

---

## 📖 Project Overview

The **React User API** application fetches user information from the JSONPlaceholder REST API and displays the retrieved information in a clean and professional table.

The project demonstrates how React can be used to:

- Manage data using `useState()`
- Perform API requests using `useEffect()`
- Retrieve data using `fetch()`
- Convert API responses into JSON
- Dynamically render user information
- Display a loading state while the API request is in progress
- Handle API request failures
- Style the application using CSS
- Build and deploy a React application

---

## ✨ Features

- 📡 Fetches user information from an external REST API
- 👤 Displays User ID
- 📝 Displays User Name
- 🔐 Displays Username
- 📧 Displays Email
- ⏳ Displays `Loading...` while fetching data
- ❌ Displays an error message if the API request fails
- 📊 Displays users in a structured table
- 🎨 Clean and professional user interface
- 🖱️ Table row hover effects
- 📱 Responsive layout
- ⚡ Built using React and Vite
- 🌐 Deployed using GitHub Pages

---

## 🛠️ Technologies Used

| Technology | Purpose |
|------------|---------|
| React.js | Building the user interface |
| JavaScript (ES6+) | Application logic |
| HTML5 | Page structure |
| CSS3 | Styling and responsive design |
| Vite | Development and production build tool |
| REST API | Retrieving user data |
| JSON | Data format |
| Git | Version control |
| GitHub | Source code hosting |
| GitHub Pages | Application deployment |

---

## 🔗 API Used

### JSONPlaceholder Users API

**API Endpoint:**

https://jsonplaceholder.typicode.com/users

This public API provides sample user information in JSON format.

### Sample API Response

```json
[
  {
    "id": 1,
    "name": "Leanne Graham",
    "username": "Bret",
    "email": "Sincere@april.biz"
  },
  {
    "id": 2,
    "name": "Ervin Howell",
    "username": "Antonette",
    "email": "Shanna@melissa.tv"
  }
]
```

---

## ⚛️ React Concepts Used

### 1. useState()

`useState()` is used to store the users, loading state, and error state.

```javascript
const [users, setUsers] = useState([]);
const [loading, setLoading] = useState(true);
const [error, setError] = useState("");
```

### 2. useEffect()

`useEffect()` is used to call the API when the Users component is loaded.

```javascript
useEffect(() => {
    // API request
}, []);
```

The empty dependency array `[]` ensures that the API request runs when the component mounts.

### 3. fetch()

The Fetch API is used to retrieve user information.

```javascript
fetch("https://jsonplaceholder.typicode.com/users")
```

### 4. JSON Response

The API response is converted into JavaScript data using:

```javascript
response.json()
```

### 5. map()

The `.map()` method is used to dynamically display each user.

```javascript
users.map((user) => (
    <tr key={user.id}>
        <td>{user.id}</td>
        <td>{user.name}</td>
        <td>{user.username}</td>
        <td>{user.email}</td>
    </tr>
))
```

---

## ⏳ Loading State

The application initially sets the loading state to `true`.

```javascript
const [loading, setLoading] = useState(true);
```

While the API request is in progress, the application displays:

```text
Loading...
```

This is handled using:

```javascript
if (loading) {
    return <h2 className="loading">Loading...</h2>;
}
```

After the API successfully returns the data:

```javascript
setLoading(false);
```

The user list is then displayed.

---

## ❌ Error Handling

The application handles API request failures using `.catch()`.

```javascript
.catch(() => {
    setError("Failed to fetch users");
    setLoading(false);
});
```

The response status is also checked:

```javascript
if (!response.ok) {
    throw new Error("Failed to fetch users");
}
```

If the API request fails, the application displays:

```text
Failed to fetch users
```

---

## 📊 User Information Displayed

| Field | Description |
|-------|-------------|
| ID | Unique identification number of the user |
| Name | Full name of the user |
| Username | Username associated with the user |
| Email | Email address of the user |

---

## 📁 Project Structure

```text
React-User-API/
│
├── public/
│
├── src/
│   ├── App.jsx
│   ├── App.css
│   ├── Users.jsx
│   └── main.jsx
│
├── .gitignore
├── index.html
├── package.json
├── package-lock.json
├── vite.config.js
└── README.md
```

---

## 🧩 Main Components

### Users.jsx

The `Users` component is responsible for:

- Managing user state
- Calling the API
- Handling loading state
- Handling errors
- Displaying user information

### App.jsx

The `App` component renders the `Users` component.

### App.css

The CSS file contains styling for:

- User container
- User table
- Table headers
- Table rows
- Loading message
- Error message
- Hover effects
- Page layout
- Responsive design

---

## 💻 Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/abhinayakuchi-source/React-User-API.git
```

### 2. Navigate to the Project

```bash
cd React-User-API
```

### 3. Install Dependencies

```bash
npm install
```

### 4. Start the Development Server

```bash
npm run dev
```

The application will run locally at:

```text
http://localhost:5173/
```

---

## 🏗️ Production Build

To create an optimized production build:

```bash
npm run build
```

The production files will be generated inside:

```text
dist/
```

---

## 🌐 Deployment

The application is deployed using **GitHub Pages**.

The project uses the `gh-pages` package for deployment.

### Deployment Commands

```bash
npm run build
npm run deploy
```

### Deployment Process

```text
React Application
       ↓
npm run build
       ↓
Vite Production Build
       ↓
dist/
       ↓
gh-pages
       ↓
GitHub Pages
       ↓
Live Application
```

### Vite Configuration

The repository base path is configured as:

```javascript
base: '/React-User-API/'
```

### Live Deployment URL

https://abhinayakuchi-source.github.io/React-User-API/

---

## 🔄 Application Flow

```text
User Opens Application
          ↓
App.jsx Loads
          ↓
Users Component Renders
          ↓
useState() Initializes
          ↓
useEffect() Executes
          ↓
fetch() Sends API Request
          ↓
JSONPlaceholder API
          ↓
API Returns User Data
          ↓
response.json()
          ↓
setUsers(data)
          ↓
setLoading(false)
          ↓
Users Displayed in Table
```

---

## ❌ Error Flow

```text
Users Component
       ↓
API Request
       ↓
Request Fails
       ↓
.catch()
       ↓
setError()
       ↓
setLoading(false)
       ↓
Error Message Displayed
```

---

## 🎯 Training Requirements Completed

This project fulfills all the requirements of the React Hands-On exercise:

- ✅Created a Users component
- ✅Used `useState()` to store users
- ✅Used `useEffect()` to call the API
- ✅Used `fetch()` to retrieve data
- ✅Displayed User ID
- ✅Displayed Name
- ✅Displayed Username
- ✅Displayed Email
- ✅Displayed `Loading...` while the API request is in progress
- ✅ Added an error message if the API request fails
- ✅Added CSS styling
- ✅ Built the application using Vite
- ✅Deployed the application using GitHub Pages

---

## 📚 Learning Objectives

This project provided practical experience with:

- React functional components
- React Hooks
- `useState()`
- `useEffect()`
- State management
- API integration
- REST APIs
- Fetch API
- JSON data handling
- JavaScript Promises
- `.then()`
- `.catch()`
- Conditional rendering
- List rendering
- `.map()`
- React `key` property
- Loading states
- Error handling
- CSS styling
- Vite
- Git and GitHub
- GitHub Pages deployment

---

## 🧪 Testing

The application was tested for:

- ✅ Successful API response
- ✅ User data rendering
- ✅ Loading state
- ✅ API error handling
- ✅ Table rendering
- ✅ CSS styling
- ✅ Responsive layout
- ✅ Production build
- ✅ GitHub Pages deployment

---

## 🔮 Future Enhancements

Possible improvements for future versions:

- 🔍 Search users by name
- 🔃 Sort users by ID or name
- 📄 Add pagination
- 👤 Create individual user profile pages
- 🔄 Add a refresh button
- 🔁 Add a retry button after API failure
- 🌙 Add dark mode
- 📱 Improve mobile table experience
- ✨ Add animations and transitions
- 📊 Display additional user information
- 🔔 Add user-friendly notifications

---

## 📌 Project Status

```text
✅ Completed
✅ API Integration Working
✅ Loading State Implemented
✅ Error Handling Implemented
✅ Professional UI
✅ Responsive Layout
✅ Production Build Successful
✅ GitHub Pages Deployment Successful
```

---

## 👩‍💻 Author

**Abhinaya Kuchi**

B.Tech – Artificial Intelligence and Data Science

---

## 📜 License

This project was developed for educational and training purposes.

---

## 🔗 Project Links

**GitHub Repository:**  
https://github.com/abhinayakuchi-source/React-User-API

**Live Demo:**  
https://abhinayakuchi-source.github.io/React-User-API/

**API Endpoint:**  
https://jsonplaceholder.typicode.com/users

---

⭐ If you found this project useful, consider giving the repository a star!

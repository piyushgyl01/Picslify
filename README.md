# **Picslify**

A full-stack photo album management app where you can create albums, upload images, share collections with friends, and organize your precious memories. Built with a React frontend, Express/Node backend, MongoDB database, Cloudinary storage, and JWT-based authentication.

## **Demo Link**
- **Frontend**: [Live Demo](https://picslify-frontend.vercel.app) 
- **Backend API**: [https://playground-021-backend.vercel.app](https://playground-021-backend.vercel.app)

## **Login**
**Demo User** Username: `piyush.gyl`, Password: `secret123`  
*Create your own account or use demo credentials to explore all features*

## **Quick Start**

```bash
git clone https://github.com/<your-username>/picslify.git
cd picslify

# Backend Setup
cd server
npm install
# Create .env file with your MongoDB and Cloudinary credentials
npm run dev

# Frontend Setup (new terminal)
cd ../client  
npm install
npm run dev
```

## **Technologies**
* **Frontend**: React 19, Redux Toolkit, Bootstrap 5, Vite
* **Backend**: Node.js, Express, MongoDB, Mongoose
* **Storage**: Cloudinary (image hosting)
* **Authentication**: JWT, bcrypt
* **File Upload**: Multer
* **Styling**: Bootstrap Icons, Custom CSS

## **Demo Video**
Watch a walkthrough (7 minutes) of all major features of this app: [Video Link](https://youtu.be/zx37Y3YBYgI)

## **Features**

### **Album Management**
* Create photo albums with custom names, descriptions, and cover images
* Edit album details and delete albums
* View all your albums in an organized grid layout

### **Photo Upload & Organization**
* Upload multiple image formats (JPEG, PNG, GIF) up to 5MB
* Add metadata: names, tags, person tagging, favorite marking
* Advanced search by tags, person names, and favorites

### **Sharing & Collaboration**
* Share albums with other users by username
* View albums shared with you by others
* Comment system for shared photo discussions

### **User Experience**
* Advanced search functionality across all your photos
* Grid and list view modes for browsing
* Responsive design for all devices
* Profile management with avatar support

### **Authentication & Security**
* Secure user registration and login
* Protected routes and API endpoints
* Password change functionality
* JWT token-based authentication

## **API Reference**

### **Authentication**
**POST /auth/register**  
Register a new user  
Sample Response: `{ message: "User registered successfully" }`

**POST /auth/login**  
User login with credentials  
Sample Response: `{ token, user: { _id, username, name }, message: "Logged in" }`

**GET /auth/me**  
Get current user profile (protected)  
Sample Response: `{ _id, username, name, profilePicture }`

### **Albums**
**GET /albums**  
List all user's albums (protected)  
Sample Response: `{ albums: [{ _id, name, description, albumCover, ... }] }`

**POST /albums**  
Create a new album (protected)  
Sample Response: `{ message: "Album created successfully", album: { ... } }`

**GET /albums/shared**  
Get albums shared with current user  
Sample Response: `{ albums: [{ _id, name, owner, sharedUsers, ... }] }`

**POST /albums/:id/share**  
Share album with other users (protected)  
Sample Response: `{ message: "Album shared successfully", album: { ... } }`

### **Images**
**POST /albums/:albumId/images**  
Upload image to album (protected, multipart/form-data)  
Sample Response: `{ message: "Image uploaded successfully", image: { ... } }`

**GET /albums/:albumId/images**  
Get all images in an album (protected)  
Sample Response: `{ images: [{ _id, file, name, tags, person, isFavorite, ... }] }`

**PUT /albums/:albumId/images/:imageId/favorite**  
Toggle favorite status (protected)  
Sample Response: `{ message: "Favorite status updated", image: { ... } }`

### **Search**
**GET /search/images**  
Search images by query, tags, person, favorites (protected)  
Sample Response: `{ images: [{ _id, name, file, tags, person, ... }] }`

## **Contact**

For bugs, feature requests, or collaboration opportunities, please reach out to piyush2022ug@gmail.com

---

*Built with ❤️ to help preserve and share your precious memories*
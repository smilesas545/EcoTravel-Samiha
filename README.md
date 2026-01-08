EcoTravel - Sustainable Adventure Finder

A responsive, interactive website for discovering eco-friendly travel destinations with Firebase authentication and database integration.

🌟 Features
 🔐 User Authentication
- Login/Signup System - Email/password authentication using Firebase
- User Profile - Displays user avatar and name in the header
- Secure Sessions - Automatic session management with Firebase Auth

🗺️ Travel Destinations
- Interactive Destination Cards - Showcase eco-friendly travel locations
- Wishlist Functionality- Save favorite destinations (requires login)
- Star Ratings - Visual rating system for each destination
- Eco-Badges - Categorization of destinations by sustainability type

 📱 Responsive Design
- Mobile-First Approach - Fully responsive across all device sizes
- Hamburger Menu - Collapsible navigation for mobile devices
- Touch-Friendly - Optimized for both mouse and touch interactions

 🎨 Modern UI/UX
- Clean Aesthetic - Eco-themed color palette (greens, blues, earth tones)
- Smooth Animations - CSS transitions and hover effects
- Modal Windows- Elegant authentication modal with tab switching
- Visual Feedback - Interactive elements with clear state changes

 🔥 Firebase Integration
- Firebase Authentication- User management and session handling
- Cloud Firestore- User data and wishlist storage
- Real-time Updates - Dynamic content based on user state

 🏗️ Project Structure

HTML Structure
- Header - Navigation with authentication state
- Hero Section - Main banner with search functionality
- Features Section - Key benefits of EcoTravel
- Destinations Section - Interactive destination cards
- Stats Section - Impact statistics
- Newsletter Section - Email subscription form
- Footer - Contact information and links
- Auth Modal - Login/Signup overlay

 CSS Architecture
- *CSS Variables - Consistent color scheme and design tokens
- Mobile-First Media Queries - Responsive breakpoints
- Component-Based Styles - Modular CSS for reusable components
- Transition Effects - Smooth animations throughout

JavaScript Modules
1. Firebase Configuration - Initialization and setup
2. Authentication Manager - User login/logout/signup
3. UI Controller - Modal, navigation, and interactive elements
4. Data Handler - Destinations, wishlist, and user data
5. Event Listeners - User interaction handlers

🔧 Setup Instructions

 1. Firebase Setup
1. Create a Firebase project at [firebase.google.com](https://firebase.google.com)
2. Enable Authentication (Email/Password method)
3. Create a Firestore Database (start in test mode for development)
4. Get your Firebase configuration from project settings

 2. Configuration
Replace the placeholder Firebase config in the script section with your actual configuration:
```javascript
const firebaseConfig = {
    apiKey: "YOUR_API_KEY",
    authDomain: "YOUR_PROJECT.firebaseapp.com",
    projectId: "YOUR_PROJECT_ID",
    storageBucket: "YOUR_PROJECT.appspot.com",
    messagingSenderId: "YOUR_SENDER_ID",
    appId: "YOUR_APP_ID"
};
```
 3. Firestore Rules
Set up security rules for your Firestore database:
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /users/{userId} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
    match /wishlists/{userId} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
  }
}
```

 📁 File Structure (Single File)
Since this is a single HTML file application, all code is contained in one file:
- `index.html` - Complete application with HTML, CSS, and JavaScript

🚀 Usage

 Running the Application
1. Save the code as `EcoTravel.html`
2. Update Firebase configuration with your project details
3. Open in any modern web browser

 User Flow
1. Browse Destinations - View eco-travel options without login
2. Create Account - Click "Login/Sign Up" to register
3. Save Favorites - Click "Add to Wishlist" on any destination
4. Subscribe - Join newsletter for updates

 🛠️ Technical Implementation

 Firebase Integration Details
- Authentication State Observer - Real-time user state tracking
-  Firestore Data Models - Structured user and wishlist data
- Error Handling - Comprehensive auth and database error management

 Key Functions
- `initApp()` - Initializes Firebase and UI
- `updateAuthUI()` - Updates UI based on auth state
- `renderDestinations()` - Dynamically generates destination cards
- `handleWishlistToggle()` - Manages user wishlist interactions
- `showAlert()` - Displays user feedback messages

 Data Models
```javascript
// Destination Object
{
    id: number,
    name: string,
    image: string,
    description: string,
    rating: number,
    reviews: number,
    badge: string,
    }

// User Document in Firestore
{
    name: string,
    email: string,
    createdAt: timestamp,
    newsletterSubscribed: boolean
}

// Wishlist Document
{
    destinations: array<number>,
    updatedAt: timestamp
}
```
📱 Responsive Breakpoints
Mobile: < 576px

Tablet: 576px - 768px

Desktop: > 768px

🎯 Future Enhancements
Social Login - Google/Facebook authentication

Booking System - Integrated trip booking

User Reviews - Destination reviews and ratings

Admin Dashboard - Content management system

Payment Integration - Stripe/Paypal for bookings

🐛 Known Issues
Firebase config needs to be updated for production

Wishlist data is stored locally on page refresh (Firestore integration needed)

No password reset functionality implemented

📄 License
This project is open-source and available under the MIT License.

🙏 Acknowledgments
Images from Unsplash

Icons from Font Awesome

Firebase by Google

Color palette inspired by eco-design principles

📞 Support
For issues or questions, please open an issue in the GitHub repository or contact the development team.

Note: This is a front-end demonstration project. For production use, additional security measures, backend validation, and proper error handling should be implemented.

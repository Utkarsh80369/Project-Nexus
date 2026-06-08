# Project-Nexus: Scalable Full-Stack Rental Platform



**Live Demo:** [https://project-nexus-hqak.onrender.com/listings](https://project-nexus-hqak.onrender.com/listings)
*(Note: Free tier hosting may have initial cold start delays)*

---

## 🌐 Overview

Project-Nexus is a comprehensive full-stack web application designed as a feature-rich rental platform. It demonstrates robust backend architecture, performant database interactions, and a dynamic user interface. Built with Node.js, Express.js, and MongoDB, it showcases key SDE skills including performance optimization, scalability patterns, API integration, and security best practices.

---

## ✨ Key Features & Technical Highlights

* **⚡ Optimized Performance:** Implemented **server-side caching** (`node-cache`) for frequently accessed listing details, drastically reducing database load and improving response times. Includes effective **cache invalidation** on data changes (updates, deletes, reviews).
* **📈 Scalable Architecture:** Engineered **server-side pagination** on the main listings and search results pages using MongoDB's `.skip()` and `.limit()`, ensuring efficient **O(1)** memory usage regardless of the number of listings.
* **🌍 Advanced Geospatial Search:** Developed a "**Find Near Me**" feature allowing users to discover listings within a specific radius, leveraging MongoDB's **`2dsphere` geospatial index** and the `$near` operator for efficient **O(log N)** proximity queries. Integrates with the browser's Geolocation API.
* **🔍 Enhanced Search UX:** Built an instant **autocomplete** search bar for listing titles and locations using optimized, case-insensitive **database regex queries** (`/^prefix/i`), triggered via a **debounced** front-end API call.
* **🔐 Secure Authentication & Authorization:** Implemented robust user signup/login using **Passport.js** (Local Strategy), session management (express-session, connect-mongo), password hashing (`bcrypt`), and route protection middleware. Includes ownership checks for editing/deleting listings and reviews.
* **🔄 Full CRUD Operations:** Complete RESTful API endpoints for creating, reading, updating, and deleting listings and reviews, adhering to MVC principles.
* **☁️ Cloud Image Uploads:** Integrated **Cloudinary API** via `multer` for seamless image uploading and cloud storage.
* **🗺️ Interactive Maps:** Displayed listing locations on interactive maps using **LocationIQ API** (or alternative) and Leaflet.js.
* **🛡️ Security Headers & Sanitization:** Enhanced security using `helmet` for HTTP headers and `express-mongo-sanitize` to prevent NoSQL injection attacks.
* **✅ Data Validation:** Implemented server-side validation using **Joi** schemas via middleware to ensure data integrity before database operations.
* **📱 Responsive UI:** Front-end designed with EJS templating and Bootstrap for responsiveness across various devices.
* **⚙️ Robust Backend:** Utilizes Express Router for modular routing, custom error handling middleware (`ExpressError`), and async utilities (`wrapAsync`).

---

## 🛠️ Tech Stack

* **Backend:** Node.js, Express.js
* **Database:** MongoDB (with Mongoose ORM)
* **Frontend:** EJS (Templating), HTML5, CSS3, JavaScript, Bootstrap
* **Authentication:** Passport.js (Local Strategy), Express Session, Connect-Mongo
* **Caching:** `node-cache`
* **File Uploads:** Multer, Cloudinary API
* **Maps/Geocoding:** LocationIQ API (or alternative like Mapbox/Google), Leaflet.js
* **Validation:** Joi
* **Security:** Helmet, Express-Mongo-Sanitize, Bcrypt
* **Tools:** Git, GitHub, VS Code, Postman/Hoppscotch

---

## 🚀 Getting Started

Follow these instructions to set up and run the project locally.

### Prerequisites

* Node.js (v18 or later recommended)
* npm (usually comes with Node.js)
* MongoDB (local installation or a cloud instance like MongoDB Atlas)

### Installation & Setup

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/Utkarsh80369/Project-Nexus](https://github.com/Utkarsh80369/Project-Nexus)
    cd Project-Nexus
    ```

2.  **Install dependencies:**
    ```bash
    npm install
    ```

3.  **Set up Environment Variables:**
    * Create a `.env` file in the root directory.
    * Copy the contents of `.env.example` into `.env`.
    * Fill in the required values (Database URL, Cloudinary credentials, Session Secret, Map API Key).
        ```dotenv
        # Example .env content (DO NOT COMMIT YOUR ACTUAL .env FILE!)
        CLOUDINARY_CLOUD_NAME=your_cloud_name
        CLOUDINARY_API_KEY=your_api_key
        CLOUDINARY_API_SECRET=your_api_secret
        LOCATIONIQ_KEY=pk.your_locationiq_api_key
        ATLASDB_URL=your_mongodb_connection_string
        SECRET=a_strong_random_secret_for_sessions
        ```
    * **Important:** Ensure your `.gitignore` file includes `.env`.

4.  **Run the application:**
    * For development (with automatic restarts):
        ```bash
        nodemon app.js
        ```
    * For production mode (usually):
        ```bash
        node app.js
        ```

5.  **Access the application:** Open your browser and navigate to `http://localhost:8080` (or the port specified in your `app.js`).

---

## 📖 Usage

1.  **Register/Login:** Create a new user account or log in with existing credentials.
2.  **Browse Listings:** Explore listings on the homepage (uses pagination).
3.  **Search:** Use the search bar (with autocomplete) to find listings by title or location.
4.  **Find Near Me:** Click the "Near Me" icon in the filter bar (allow location access when prompted) to see listings within 20km.
5.  **View Listing:** Click on a listing card to see details (uses caching after first load), reviews, and map location.
6.  **Create Listing:** Logged-in users can create new listings via the "Create Listing" link, including image uploads.
7.  **Add Review:** Logged-in users can add reviews (rating + comment) to listings.
8.  **Edit/Delete:** Users can edit or delete listings and reviews they own.

---

## 🙏 Acknowledgments

* Inspired by Airbnb's UI and core features.
* Utilizes various open-source libraries and APIs.

---
⭐ If you find this project useful or interesting, please consider starring the repository!

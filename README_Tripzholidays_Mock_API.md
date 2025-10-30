# 🌍 Tripzholidays Mock API

This repository contains the **Tripzholidays mock backend**, built for frontend development and API integration testing.  
It uses [`json-server`](https://github.com/typicode/json-server) and a single `db.json` file to simulate real-world REST API responses.

---

## 🚀 How to Run

### 1️⃣ Install json-server
```bash
npm install -g json-server
```

### 2️⃣ Start the mock server
```bash
npx json-server --watch tripzholidays_db.json --port 4000
```

### 3️⃣ API will run at:
```
http://localhost:4000
```

---

## 📁 Data Structure Overview

The `db.json` file contains 4 top-level entities:

| Key | Description |
|-----|--------------|
| **countries** | List of all operating countries and regions |
| **packages** | Travel packages linked to each country |
| **blogs** | Blog posts, travel stories, and destination guides |
| **feedbacks** | Customer reviews linked to specific packages |

---

## 🌎 Endpoints

### 🇨🇭 1. Countries

**Get all countries**
```
GET /countries
```

**Get single country by slug**
```
GET /countries?slug=japan
```

**Response example**
```json
{
  "id": 8,
  "name": "Japan",
  "slug": "japan",
  "title": "Explore The Land of Rising Sun",
  "description": "From ancient temples to neon cities, Japan blends old and new in perfect harmony — where every sunrise feels like a promise renewed.",
  "featured": true,
  "image_url": "https://res.cloudinary.com/yourcloud/image/upload/v1/countries/japan.jpg",
  "country_type": "Asia"
}
```

---

### 🧳 2. Packages

**Get all packages**
```
GET /packages
```

**Get packages by country**
```
GET /packages?country_slug=japan
```

**Get featured packages**
```
GET /packages?featured=true
```

**Get a package by slug**
```
GET /packages?slug=japan-package-1
```

**Response example**
```json
{
  "id": "pkg_japan_1",
  "slug": "japan-package-1",
  "title": "Exclusive Japan Experience 1",
  "duration": "7D/6N",
  "descriptive_duration": "Explore Japan in 7 amazing days with guided tours and local culture.",
  "trip_highlights": "Discover the essence of Japan through guided tours, cultural experiences, and breathtaking landscapes that define its charm...",
  "trip_features": ["Travel Included", "Food Included", "Stay Included", "Sightseeing Included"],
  "featured": true
}
```

---

### 📰 3. Blogs

**Get all blogs**
```
GET /blogs
```

**Get blog by slug**
```
GET /blogs?slug=japan-blog-1
```

**Get featured blogs**
```
GET /blogs?featured=true
```

**Get blogs by place**
```
GET /blogs?place=Japan
```

**Response example**
```json
{
  "id": "blog_008",
  "slug": "japan-sakura-and-temples",
  "title": "Sakura Season & Timeless Temples — Japan Highlights",
  "place": "Japan",
  "date": "2025-03-28",
  "tags": ["japan", "sakura", "temples"],
  "excerpt": "Japan’s cherry blossom season paints the country in soft shades of pink and white...",
  "body_md": "# Discover Japan..."
}
```

---

### 💬 4. Feedbacks

**Get all feedbacks**
```
GET /feedbacks
```

**Get feedbacks for a specific package**
```
GET /feedbacks?package_id=pkg_japan_1
```

**Response example**
```json
{
  "id": "fb_001",
  "package_id": "pkg_japan_1",
  "user_name": "Amit",
  "rating": 4.8,
  "comment": "Amazing experience! Highly recommended.",
  "date": "2024-05-11"
}
```

---

## 🧠 API Relationships

| Entity | Linked To | Relation |
|---------|------------|-----------|
| **Packages** | Countries | Each package belongs to a country (via `country_slug`) |
| **Blogs** | Packages | Each blog may reference multiple packages (`package_slugs`) |
| **Feedbacks** | Packages | Each feedback belongs to a single package (`package_id`) |

---

## 🧩 Suggested Frontend Integration

**Environment Config Example**
```js
const API_BASE_URL = process.env.REACT_APP_API_URL || "http://localhost:4000";
```

**Fetch Example (React)**
```js
useEffect(() => {
  fetch(`${API_BASE_URL}/packages?featured=true`)
    .then(res => res.json())
    .then(setPackages);
}, []);
```

---

## 🛠️ Author Notes

This mock API was generated automatically for **Tripzholidays**.  
It helps developers build and test frontend components without requiring a live backend.

> Includes:
> - 9 countries  
> - 36 travel packages  
> - 15 travel blogs  
> - 200 feedbacks  

All image URLs are **Cloudinary-ready placeholders** and can be replaced with production media anytime.

---

🧡 *Built with love by Tripzholidays Team*

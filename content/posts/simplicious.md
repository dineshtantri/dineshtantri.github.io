---
title: "Bookmarking Tool - Vibe Coding"
date: 2024-12-24
draft: false
---

Over the past year or so that I have been playing around with Replit, it has been truly empowering. I have been able to build and deploy mini applications for my own use in days. The Replit AI agent for slightly involved back and forth and the AI assistant for simpler tasks have been great by and large. As long as you can write your requirements well and refine them and debug patiently, Replit does the trick. I'm unable to comment on the code quality though. My friend Ritesh Nayak had recently written a post about his experience from developer perspective.

![screenshot](/static/images/1735043628793.png)

Back in the day, I used Delicious quite a bit for social bookmarking until they shut down. I have always wanted a clutter free service that I can use for my personal knowledge management. I was able to build a simple clone of Delicious in couple of hours complete with the following features:

---

## **Bookmark Management**

**Add new bookmarks with:**

* URL

* Title

* Description (optional)

* Tags

* Privacy setting (public/private)

* Edit existing bookmarks

* Delete bookmarks

* Toggle bookmark privacy

* Export bookmarks to JSON format

---

## **Tag System**

* Add multiple tags to bookmarks
* Tag suggestions based on previously used tags
* Filter bookmarks by tags
* Tag cloud visualization

---

## **Search & Organization**

* Search bookmarks by title, URL, or description
* Filter bookmarks by tags
* Sort bookmarks by creation date

---

## **User Interface**

* Clean, modern interface using Tailwind CSS
* Responsive design that works on mobile and desktop
* Navigation bar with quick access to profile and logout
* Modal dialogs for adding/editing bookmarks
* Tag suggestions while typing

---

## **Browser Integration**

* Chrome extension for quick bookmarking
* Extension popup with:

  * Title auto-fill from current page

---

## **Other things**

* RESTful API architecture
* PostgreSQL database for data persistence
* Real-time tag suggestions
* Efficient data querying and filtering
* Secure password hashing
* Authentication required for all private operations
* Session management

---


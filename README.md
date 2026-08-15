# 🍔Javaeats Lite Project

**Javaeats Lite** is a comprehensive, multi-tier food-ordering and tracking system designed to streamline the user experience from discovery to delivery. Built to connect hungry customers with their favorite restaurants, the platform supports browsing, customization, and order tracking.


## 📑 Table of Contents

- [Key Features](#key-features)
  - [1. Meal Discovery & Exploration](#1-meal-discovery--exploration)
  - [2. Restaurant & Menu Interaction](#2-restaurant--menu-interaction)
  - [3. Efficient Cart & Order Management](#3-efficient-cart--order-management)
  - [4. Checkout & Fulfillment](#4-checkout--fulfillment)
  - [5. Order Lifecycle](#5-order-lifecycle)
  - [6. User Registration and Login](#6-user-registration-and-login)
- [Core Engineering Challenges](#core-engineering-challenges)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Local Setup](#local-setup)
  - [Build & Run](#build--run)
- [How to Tweak This Project for Your Own Uses](#how-to-tweak-this-project-for-your-own-uses)
- [Find a Bug?](#find-a-bug)
- [Known Issues (Work in Progress)](#known-issues-work-in-progress)
- [Like this project?](#like-this-project)


## ✨ Key Features

### 1. Meal Discovery & Exploration
Empowers users to find their preferred meals efficiently by browsing detailed restaurant profiles and categorized menus. Users can make informed decisions by viewing item contents, prices, and portions.

#### Key functionalities
- **Advanced Sorting**
  - Sort by Rating: show highest-rated restaurants first.
  - Sort by Recommendation: highlight platform-curated or popular picks.
  - Sort by Name: alphabetical listing (A–Z).
  - Sort by Fast Delivery: prioritize restaurants with shortest travel time.

- **Multi-Layered Search**
  - Global Search: Find specific restaurants or meals across the entire platform.
  - Menu Search: Search for exact items within a selected restaurant's menu.

---

### 2. Restaurant & Menu Interaction
Dynamic interfaces that allow customers to deeply engage with restaurant offerings, browse menus, select items and customize their orders.

#### Key functionalities

##### Restaurant Profile
- Favorites: save preferred restaurants for quick future access.
- Share: generate external links to share restaurant details.
- Delivery Info: display delivery costs, Estimated Time of Arrival (ETA), and delivery types.
- Delivery Validation: validate delivery feasibility against the restaurant's operational radius before ability to select restaurant.

##### Dynamic Menu
- Categorization: browse items by category (e.g. Top picks, Offers, Desserts, Hot Deals!, Appetizers, Entrees, Drinks).
- Meal Customization:
  - Add items to the cart.
  - Increase/ decrease item quantity.
  - Add special notes for kitchen staff (e.g., "extra sauce").

---

### 3. Efficient Cart & Order Management
A robust cart system ensuring the ability of cart customization and accurate order placement while minimizing errors and misunderstandings before checkout.

#### Key functionalities

- Item Control: easily adjust quantities, modify sizes or remove items easily.
- State Persistence: Cart contents reliably persist across user sessions and devices.
- Price Transparency: Detailed breakdown of Subtotal, Discounts/Promotions, Delivery Fee, Service Fee, Taxes, and the Final Total.
- Pre-Checkout and Cart Review: A final confirmation screen to verify order details, fees, and delivery info.

---

### 4. Checkout & Fulfillment
A frictionless transaction process handling everything from payment preferences to final drop-off instructions.

#### Address & Payment
- Address Management: select saved addresses or add new addresses.
- Payment Methods: support multiple payment options (cards, in-app payments, cash on delivery where applicable) and securely add used payment methods.

#### Delivery Preferences
- Express Delivery: optional toggle for expedited delivery where available.
- Rider Support: tipping functionality for riders.
- Delivery Instructions: free-text drop-off specifics for the rider.

---

### 5. Order Lifecycle
- **Place Order** : execute the final purchase and receive confirmation message along with an estimated delivery or pickup time.
- **Stop / Cancel Order** :
  - Cancellation is allowed based on system constraints and current workflow milestones.
  - Automatic Cancellation restrictions apply once preparation begins or the order is out for delivery, with clear UI messaging explaining the reasons why cancellation is disallowed.
    
---

### 6. User Registration and Login
Delivers a personalized and secure experience for every user.

#### Key functionalities
- Secure account creation and authentication.
- Comprehensive profile and preference management.
- Order history tracking.
- personalized meal recommendations.


## ⚙️ Core Engineering Challenges

### Usability
Designing a seamless, intuitive UI/UX that allows users to effortlessly transition from discovering new restaurants to finalizing their checkout, minimizing friction at every step.

### Availability
Ensuring the REST API and backend infrastructure remain highly available and resilient, efficiently handling concurrent traffic to seamlessly connect a large volume of customers with a wide range of restaurants.

### Security
Implementing robust system architecture to protect user data. This includes secure password hashing, secure session management, strict input validation to prevent injection attacks, and role-based access controls.


## 🚀 Getting Started
### Prerequisites
To run Javaeats Lite locally, ensure you have the following installed:

- Java 17+
- Spring Boot (via Maven or Gradle)
- MySQL
- Docker (Optional, for containerized database and app deployment)

### Local Setup
1. Clone the repository:
   
```bash
git clone https://github.com/yourusername/javaeats-lite.git
cd javaeats-lite
```

2. Configure the Database:
Update your application.properties or application.yml file with your local MySQL credentials:
```
spring.datasource.url=jdbc:mysql://localhost:3306/javaeats_db
spring.datasource.username=root
spring.datasource.password=your_password
```

3. Build and Run
```bash
./mvnw clean install
./mvnw spring-boot:run
```
   
## 💡 How to Tweak This Project for Your Own Uses

Since this is an example project, I encourage you to clone and rename this repository to use for your own purposes. It is a great starter boilerplate for building modern, scalable e-commerce solutions — feel free to adapt the data models, UI, and integrations (payments, mapping, notifications) to match your needs. Consider adding CI, automated tests, and deployment scripts when you adapt this for production use.

## 🐛 Find a Bug?

If you find an issue or would like to suggest an improvement, please open an issue in the repository using the Issues tab. If you'd like to submit a fix, open a Pull Request and reference the related issue in your PR description so we can track and review it easily.

## 🚧 Known Issues (Work in Progress)

This project is still under active development. Some areas — including parts of the user interface and portions of the business logic — remain work in progress. Expect intermittent breaking changes while features are being implemented and refined. Contributions are welcome; please check open issues before starting significant work to avoid duplication.

## ☕ Like this project?

If you find this project helpful and would like to support it, consider buying me a coffee: [buy me a coffee!](https://buymeacoffee.com/zeinab.ibrahim?new=1)

# Food Tracking System

A comprehensive food-ordering and tracking application designed to streamline the user experience from discovery to delivery.

---

## Table of Contents
- [1. Discovery & Exploration](#1-discovery--exploration)
- [2. Restaurant & Menu Interaction](#2-restaurant--menu-interaction)
- [3. Cart & Order Management](#3-cart--order-management)
- [4. Checkout & Fulfillment](#4-checkout--fulfillment)
- [Order Lifecycle](#order-lifecycle)
- [Notes](#notes)

---

## 1. Discovery & Exploration
Focus: Help users find their preferred meals efficiently.

### Key functionalities
- **Sorting**
  - Sort by Rating — show highest-rated restaurants first.
  - Sort by Recommendation — platform-curated or popular picks.
  - Sort by Name — alphabetical listing (A–Z).
  - Sort by Fast Delivery — prioritize restaurants with shortest travel time.

- **Multi-Layered Search**
  - Global Search — find restaurants or specific meals across the platform.
  - Menu Search — search for specific items within a selected restaurant's menu.

---

## 2. Restaurant & Menu Interaction
Focus: Engage with restaurants and select items.

### Key functionalities

#### Restaurant Profile
- Favorites — save restaurants for quick future access.
- Share — generate links to share restaurant details externally.
- Delivery Info — show delivery costs, Estimated Time of Arrival (ETA), and delivery types.
- Delivery Validation — validate delivery feasibility against the restaurant's delivery radius before ability to select restaurant.


#### Dynamic Menu
- Categorization — browse items by category (e.g. Top picks, Offers, Desserts, Hot Deals!, Appetizers, Entrees, Drinks).
- Meal Customization:
  - Add items to the cart.
  - Increase / decrease item quantity.
  - Add special notes for kitchen staff (e.g., "extra sauce").
  - Show available modifiers, option groups, and constraints (required/optional).

---

## 3. Cart & Order Management
Focus: Manage the user's current selection.

### Key functionalities

#### Cart Overview
- Item Control — adjust quantities or remove items easily.
- Persistence — ensure cart contents persist across sessions and devices (e.g., server-side cart tied to user account or persistent local storage for guests).

#### Price Transparency
- Show detailed breakdown:
  - Subtotal
  - Discounts / Promotions
  - Delivery Fee
  - Service Fee
  - Taxes
  - Total

#### Pre-Checkout
- Confirmation — provide a final review of order details, fees, and delivery info before proceeding.

---

## 4. Checkout & Fulfillment
Focus: Complete the transaction and handle delivery preferences.

### Address & Payment
- Address Management — select saved addresses or add new addresses.
- Payment Methods — support multiple payment options (cards, in-app payments, cash on delivery where applicable).

### Delivery Preferences
- Express Delivery — optional toggle for expedited delivery where available.
- Rider Support — tipping functionality for riders.
- Delivery Instructions — free-text drop-off specifics for the rider.

---

## Order Lifecycle
- **Place Order** — execute the final purchase.
- **Stop / Cancel Order**
  - Allow cancellation subject to system constraints and current order status.
  - Restrict cancellation after certain workflow milestones (e.g., once the restaurant has accepted and begun preparation or when the order is out for delivery).
  - Provide clear UI states and reasons when cancellation is disallowed.



# Entity Relationship Diagram (ERD)

This diagram illustrates the complete database schema for the JavaEats Lite food delivery application, showing all entities, their attributes, and the relationships between them.

```mermaid
erDiagram
    direction LR

    %% Customer and saved data
    USER ||--o{ ADDRESS : "has"
    USER ||--o{ ORDER : "places"
    USER ||--o{ RESTAURANT_FAVORITE : "saves"
    USER ||--o| CART : "owns"
    USER ||--o{ SAVED_PAYMENT_METHOD : "stores"

    %% Restaurant catalog
    RESTAURANT ||--o{ MENU_ITEM : "offers"
    RESTAURANT ||--o{ RESTAURANT_FAVORITE : "is saved by"
    RESTAURANT ||--o{ RESTAURANT_DELIVERY_OPTION : "supports"
    CATEGORY ||--o{ MENU_ITEM : "groups"
    MENU_ITEM ||--o{ MODIFIER_GROUP : "defines"
    MODIFIER_GROUP ||--o{ MODIFIER_OPTION : "offers"
    MENU_ITEM ||--o{ PROMOTION : "has"

    %% Cart
    CART ||--o{ CART_ITEM : "contains"
    MENU_ITEM ||--o{ CART_ITEM : "is added to"
    CART_ITEM ||--o{ CART_ITEM_SELECTION : "contains"
    MODIFIER_OPTION ||--o{ CART_ITEM_SELECTION : "is selected in"

    %% Delivery configuration
    DELIVERY_OPTION ||--o{ RESTAURANT_DELIVERY_OPTION : "is configured as"
    RESTAURANT_DELIVERY_OPTION ||--o{ ORDER : "is selected for"

    %% Orders and fulfillment
    RESTAURANT ||--o{ ORDER : "receives"
    ADDRESS ||--o{ ORDER : "is preferred for"
    RIDER o|--o{ ORDER : "may deliver"
    ORDER ||--|{ ORDER_ITEM : "contains"
    MENU_ITEM ||--o{ ORDER_ITEM : "is purchased as"
    ORDER ||--|| PAYMENT : "has"

    %% Entities
    USER {
        int user_id PK
        string email
        string password_hash
        string first_name
        string last_name
        string phone
    }

    ADDRESS {
        int address_id PK
        int user_id FK
        string street_details
        decimal latitude
        decimal longitude
    }

    RESTAURANT {
        int restaurant_id PK
        string name
        decimal rating
        decimal delivery_radius
        decimal latitude
        decimal longitude
        int average_prep_time_mins
    }

    RESTAURANT_FAVORITE {
        int favorite_id PK
        int user_id FK
        int restaurant_id FK
        datetime created_at
    }

    CATEGORY {
        int category_id PK
        string name
    }

    MENU_ITEM {
        int item_id PK
        int restaurant_id FK
        int category_id FK
        string name
        decimal base_price
    }

    PROMOTION {
        int promotion_id PK
        int item_id FK
        decimal discount_percentage
        datetime start_time
        datetime end_time
    }

    MODIFIER_GROUP {
        int group_id PK
        int item_id FK
        string name
        int min_selections
        int max_selections
    }

    MODIFIER_OPTION {
        int option_id PK
        int group_id FK
        string name
        decimal extra_price
    }

    CART {
        int cart_id PK
        int user_id FK
        string session_id
    }

    CART_ITEM {
        int cart_item_id PK
        int cart_id FK
        int item_id FK
        int quantity
        string special_notes
    }

    CART_ITEM_SELECTION {
        int selection_id PK
        int cart_item_id FK
        int option_id FK
        decimal recorded_price
    }

    SAVED_PAYMENT_METHOD {
        int saved_method_id PK
        int user_id FK
        string gateway_customer_token
        string card_brand
        string last_four_digits
    }

    DELIVERY_OPTION {
        int option_id PK
        string name "Standard, Express, or Pickup"
    }

    RESTAURANT_DELIVERY_OPTION {
        int config_id PK
        int restaurant_id FK
        int option_id FK
        decimal additional_fee
        int time_modifier_mins
    }

    RIDER {
        int rider_id PK
        string first_name
        string phone_number
        string vehicle_type
        string current_status
        decimal current_latitude
        decimal current_longitude
    }

    ORDER {
        int order_id PK
        int user_id FK
        int restaurant_id FK
        int rider_id FK "Nullable for pickup orders"
        int address_id FK "Preferred saved address"
        int config_id FK
        string status
        decimal subtotal
        decimal delivery_fee
        decimal total_amount
        string delivery_instructions
        decimal rider_tip
        datetime expected_delivery_time
        datetime created_at
        datetime picked_up_at
        datetime delivered_at
    }

    ORDER_ITEM {
        int order_item_id PK
        int order_id FK
        int item_id FK
        int quantity
        decimal price_at_purchase
        string selected_modifiers
        string special_notes
    }

    PAYMENT {
        int payment_id PK
        int order_id FK
        string payment_method
        string gateway_transaction_id
        string transaction_status
    }
```

## Key Design Features

- **User Management**: Stores customer profiles, saved addresses, payment methods, and favorites
- **Restaurant Catalog**: Manages restaurant information, menus, categories, modifiers, and promotions
- **Shopping Cart**: Allows users to build orders with customizable menu items and modifiers
- **Order Processing**: Tracks orders from placement through delivery, including status and pricing
- **Delivery System**: Supports multiple delivery options and rider assignment for order fulfillment
- **Payment Integration**: Records payment transactions with support for saved payment methods

# Use Case: View and Modify Cart

**Actor:** Customer  
**Goal:** The customer can view items in their cart, adjust quantities, customize meal options, add special requests, apply vouchers, and view an updated payment summary.  
**Preconditions:** The customer is authenticated, and a cart has been previously created containing at least one meal from a specific restaurant.

### Main Flow
1. The customer selects the **Cart** icon.
2. The system displays the restaurant's name, the items currently in the cart (showing name, price, and quantity), and a list of suggested similar meals from the same restaurant.
3. The system displays the payment summary, including the subtotal, delivery fee, service fee, and total amount.
4. The customer can modify the cart by performing any of the following actions:
   * **Inline Modifications:** Adjusting item quantities (incrementing/decrementing) or deleting items directly from the main cart screen.
   * **Item Customization Popup:** Selecting an individual item to open its details window, allowing them to modify specific choices (e.g., changing sizes, selecting sauces) or adjust the quantity before saving.
   * **Adding Suggestions:** Selecting a suggested meal to add it directly to the cart.
   * **Special Requests:** Adding specific notes or instructions for the restaurant regarding the meal.
   * **Applying Vouchers:** Entering a voucher code to claim a discount.
5. The system dynamically updates the item details, quantities, and the overall payment summary to reflect the customer's changes.
6. The customer selects the option to proceed to checkout.

### Alternative Flows

* **Alternative Flow A: Cart becomes empty**
  1. In Step 4, the customer deletes all items from the cart.
  2. The system clears the payment summary and displays an "Empty Cart" status screen with a button to return to browsing.

* **Alternative Flow B: Invalid Voucher Code**
  1. In Step 4, the customer applies an invalid, expired, or inapplicable voucher code.
  2. The system displays an error message (e.g., *"Invalid Voucher Code"*) and leaves the payment summary unchanged.

## Flowchart
<img width="1202" height="1061" alt="food system diagrams drawio" src="https://github.com/user-attachments/assets/c396f0f0-bd27-4a54-9957-558072de78ad" />


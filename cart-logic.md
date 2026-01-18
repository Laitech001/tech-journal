## my first e-commerce cart logic code
# initialize cart
let cart = JSON.parse(localStorage.getItem('cart')) || [];
the above code load cart from localStroage, and if there's none, it start an empty array.

# Add to Cart
function addToCart(productId) {
  const existingProduct = cart.find(item => item.id === productId);
  
  if (existingProduct) {
    existingProduct.quantity += 1; // Increment quantity if product exists
  } else {
    cart.push({ id: productId, quantity: 1 }); // Add new product
  }

  localStorage.setItem('cart', JSON.stringify(cart)); // Save to localStorage
}
the above add to cart function check if the product is already in cart, update the quantity or add new product, and always sync with localStorage.

# Update cart quantity / Remove Item
To increase or decrease quantity, find the item in cart and update .quantity
To remove, flilter out the product in cart and saved updated cart back to localStoraage

# Render Cart
function renderCart() {
  cartContainer.innerHTML = ''; // Clear previous items
  cart.forEach(cartItem => {
    const product = products.find(p => p.id === cartItem.id);
    if (!product) return;

    // Display product + quantity
    cartContainer.innerHTML += `
      <div class="cart-item">
        <p>${product.name}</p>
        <p>Quantity: ${cartItem.quantity}</p>
      </div>
    `;
  });
  
  if (cart.length === 0) {
    cartContainer.innerHTML = '<p>Your cart is empty</p>';
  }
}
the above code always caode after cart update, its dynamically shows all products and quantity, it handle empty cart display.

# sync with Home page / Cart count
Whenever cart changes, update cart icon or badge:
function updateCartCount() {
  cartCountElement.textContent = cart.reduce((sum, item) => sum + item.quantity, 0);
}
the above function ensure user see real-time update across page.

# LocalStorage Persistence
Cart stays saved even if user refreshes or leaves page.
On page load, always fetch from localStorage.

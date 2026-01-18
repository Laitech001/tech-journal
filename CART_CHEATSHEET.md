// 1. Load cart from localStorage or start empty
let cart = JSON.parse(localStorage.getItem('cart')) || [];

// 2. Add/update product in cart
function addToCart(id){ let p = cart.find(x=>x.id===id); p ? p.quantity++ : cart.push({id,quantity:1}); localStorage.setItem('cart',JSON.stringify(cart)); }

// 3. Remove product or update quantity by filtering/updating cart and resaving to localStorage

// 4. Render cart dynamically: loop cart, match product info, display quantity, show "empty" if none

// 5. Sync cart count/badge: sum quantities to update header/home page

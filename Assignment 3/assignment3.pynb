# Product Class
class Product:
    def __init__(self, name, price):
        self.name = name
        self.price = price

# User Class
class User:
    def __init__(self, name, is_premium=False):
        self.name = name
        self.is_premium = is_premium  

# ShoppingCart Class
class ShoppingCart:
    def __init__(self, user):
        self.user = user
        self.cart = {}  

    def add_product(self, product, quantity=1):
        """Adds a product to the cart"""
        self.cart[product.name] = self.cart.get(product.name, 0) + quantity
        print(f"Added {quantity} x {product.name} to cart.")

    def remove_product(self, product_name):
        """Removes a product if it exists"""
        if product_name in self.cart:
            del self.cart[product_name]
            print(f"Removed {product_name} from cart.")
        else:
            print(f"{product_name} is not in the cart.")

    def calculate_total(self, products):
        """Calculates total cost with 10% discount for premium users"""
        total = sum(products[name].price * qty for name, qty in self.cart.items())
        if self.user.is_premium:
            total *= 0.9  
        return total

    def generate_invoice(self, products):
        """Prints the invoice"""
        print(f"\nInvoice for {self.user.name} ({'Premium' if self.user.is_premium else 'Regular'} User)")
        if not self.cart:
            print("Cart is empty.")
            return
        for name, qty in self.cart.items():
            print(f"{qty} x {name} @ ${products[name].price} each")
        print(f"Total: ${self.calculate_total(products):.2f}")

# Example Usage
products = {
    "Laptop": Product("Laptop", 1200),
    "Phone": Product("Phone", 800),
    "Headphones": Product("Headphones", 150),
}

user = User("Alice", is_premium=True)
cart = ShoppingCart(user)

cart.add_product(products["Laptop"], 1)
cart.add_product(products["Phone"], 2)
cart.add_product(products["Headphones"], 1)
cart.generate_invoice(products)

cart.remove_product("Phone")
cart.generate_invoice(products)
 
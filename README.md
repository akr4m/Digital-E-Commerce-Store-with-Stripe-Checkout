## Digital E-Commerce Store with Stripe Checkout

Demo Project for A Digital E-Commerce Store with Stripe Checkout

### Controllers

- [CartController](https://github.com/akr4m/Digital-E-Commerce-Store-with-Stripe-Checkout/blob/main/App/Http/Controllers/CartController)
- [HomeController](https://github.com/akr4m/Digital-E-Commerce-Store-with-Stripe-Checkout/blob/main/App/Http/Controllers/HomeController)
- [OrderController](https://github.com/akr4m/Digital-E-Commerce-Store-with-Stripe-Checkout/blob/main/App/Http/Controllers/OrderController)
- [ProductController](https://github.com/akr4m/Digital-E-Commerce-Store-with-Stripe-Checkout/blob/main/App/Http/Controllers/ProductController)
- [WebhookController](https://github.com/akr4m/Digital-E-Commerce-Store-with-Stripe-Checkout/blob/main/App/Http/Controllers/WebhookController)
- [CheckoutController](https://github.com/akr4m/Digital-E-Commerce-Store-with-Stripe-Checkout/blob/main/App/Http/Controllers/CheckoutController)
- [CartProductController](https://github.com/akr4m/Digital-E-Commerce-Store-with-Stripe-Checkout/blob/main/App/Http/Controllers/CartProductController)
- [ProductDownloadController](https://github.com/akr4m/Digital-E-Commerce-Store-with-Stripe-Checkout/blob/main/App/Http/Controllers/ProductDownloadController)

### Web Routes

```php
<?php
use Illuminate\Support\Facades\Route;
use App\Http\Controllers\CartController;
use App\Http\Controllers\HomeController;
use App\Http\Controllers\OrderController;
use App\Http\Controllers\ProductController;
use App\Http\Controllers\WebhookController;
use App\Http\Controllers\CheckoutController;
use App\Http\Controllers\CartProductController;
use App\Http\Controllers\ProductDownloadController;

Route::get('/', HomeController::class)->name('home');

Route::get('/products/{product:slug}', [ProductController::class, 'show'])
->name('products.show');

Route::get('/products/downloads/{product:slug}', [ProductDownloadController::class, 'show'])
->name('products.downloads.show');

Route::post('/cart/products', [CartProductController::class, 'store'])
->name('cart.products.store');

Route::delete('/cart/products/{product:slug}', [CartProductController::class, 'destroy'])
->name('cart.products.destroy');

Route::get('/cart', [CartController::class, 'index'])
->name('cart.index');

Route::get('/checkout', [CheckoutController::class, 'index'])
->name('checkout.index');

Route::get('/orders', [OrderController::class, 'index'])
->name('orders.index');

Route::post('/stripe/webhook', [WebhookController::class, 'handleWebhook']);


require  __DIR__.'/auth.php';
```

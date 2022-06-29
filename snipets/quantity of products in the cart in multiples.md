Quantity of products in the cart in multiples
---
Add code to head (script tag)


If the basket is to contain a number of products, e.g. only in even quantities.

```php

function digitalnoir_minimum_order_check() {

	$cart_content = WC()->cart->cart_contents;
	$qty = 0;
	if(is_array($cart_content)){
		foreach($cart_content as $product){

			$qty += $product['quantity'];
			
		}
	}

    if (  $qty % 2 != 0 ) {
		return false;
	}
	 
	return true;

}
``` 

With the following snippet, we will warn the customer that he has to add something to the cart.

``` php
add_action( 'woocommerce_before_cart_table' , 'digitalnoir_minimum_order_message' );
function digitalnoir_minimum_order_message(){

	$is_valid = digitalnoir_minimum_order_check();
	if(!$is_valid){
		echo '<div class="woocommerce-error alert alert_warning" role="alert">

		<div class="alert_icon">&#9786;</div>

		<div class="alert_wrapper">
			V kartóne máte ešte jedno miesto voľné (všetky kartóny sú násobky 2 fliaš)	</div>

		<a class="pokracovat-v-nakupe" href="https://www.otcoviaadcery.sk/obchod">Pokračovať v nákupe</a>

	</div>
';
	remove_action( 'woocommerce_proceed_to_checkout', 'woocommerce_button_proceed_to_checkout', 20 );} }

``` 
Thanks for the order
---

``` php

add_action( 'woocommerce_thankyou', 'bbloomer_add_content_thankyou' ); 
function bbloomer_add_content_thankyou() { 
echo '<h2 class="h2thanks">Ďakujeme. Vaša objednávka bola prijatá, začíname na nej pracovať.</h2>'; 
}
``` 
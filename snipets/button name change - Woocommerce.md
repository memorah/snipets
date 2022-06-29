Button name change - Woocommerce
---
Change the name of the button from ADD TO CART for a simple product, e.g. to BUY, I will use the following snippet.

``` php

// To change add to cart text on single product page
add_filter( 'woocommerce_product_single_add_to_cart_text', 'woocommerce_custom_single_add_to_cart_text' ); 
function woocommerce_custom_single_add_to_cart_text() {
    return __( 'Kúpiť', 'woocommerce' ); 
}
``` 
Change the name of the button from SELECT OPTIONS for a variable product, e.g. to BUY, I will use the following snippet.

``` php

/// To change add to cart text on product archives(Collection) page
add_filter( 'woocommerce_product_add_to_cart_text', 'woocommerce_custom_product_add_to_cart_text' );  
function woocommerce_custom_product_add_to_cart_text() {
    return __( 'Kúpiť', 'woocommerce' );
}
``` 
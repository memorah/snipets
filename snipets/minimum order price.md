Minimum order price
---

``` php

//** Set minimum order amount. **/

function sm_wc_minimum_order_amount() {
    $minimum_order_amount = 40; // change this to your minimum order amount
 
       if ( WC()->cart->subtotal < $minimum_order_amount ) { if ( is_cart() ) { wc_print_notice( sprintf( __( 'Na dokončenie objednávky musíte mať minimálnu hodnotu objednávky %s. Súčasná celková cena objednávky je %s.<a class="spat-do-obchodu" href="#">späť do obchodu</a>', 'store' ), wc_price( $minimum_order_amount ), wc_price( WC()->cart->subtotal ) ), 'error'
            );
        } else {
            wc_add_notice(
                sprintf( __( 'Na dokončenie objednávky musíte mať minimálnu hodnotu objednávky %s. Súčasná celková cena objednávky je %s.<a class="spat-do-obchodu" href="#">späť do obchodu</a>', 'store' ), wc_price( $minimum_order_amount ), wc_price( WC()->cart->subtotal ) ), 'error'
            );
        }
    }
 
}
 
add_action( 'woocommerce_checkout_process', 'sm_wc_minimum_order_amount' );
add_action( 'woocommerce_before_cart', 'sm_wc_minimum_order_amount' );
``` 
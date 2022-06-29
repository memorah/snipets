Change the name of the CHECK AND ORDER button
---



```php
function woocommerce_button_proceed_to_checkout() { ?>
    <a href="<?php echo esc_url( wc_get_checkout_url() ); ?>" class="checkout-button button alt wc-forward">
    <?php esc_html_e( 'Pokladňa', 'woocommerce' ); ?>
    </a>
    <?php
   }
``` 

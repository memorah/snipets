Change of the name of the ORDER WITH PAYMENT OBLIGATION button
---



```php
add_filter( 'woocommerce_order_button_text', 'misha_custom_button_text' );
 
function misha_custom_button_text( $button_text ) {
   return 'Zaplatiť'; // new text is here 
}
``` 

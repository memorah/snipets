Remove the CHECKOUT button
---
If the minimum order quantity is set and this condition is not met, the customer will not be able to continue the purchase (the CHECKOUT button will be removed).

```php

add_action ('wp_head', function () { ?>
<script>jQuery( document.body ).on( 'updated_cart_totals', function(){
    if (jQuery('.woocommerce-error').length > 0) {
        jQuery('.wc-proceed-to-checkout').css('display','none');
    } else {
       jQuery('.wc-proceed-to-checkout').css('display','block');
    }
});
</script>
<?php } );
``` 

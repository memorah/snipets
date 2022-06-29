Inactive "Check and order" button
---

If the condition of, for example, the minimum price of the basket, the number of products, etc. is not met. this script will prevent the customer from continuing the order.

```js
/<script>
	
	jQuery(document).ready(function(){
		
    if (jQuery('.woocommerce-error').length > 0) {
        jQuery('.wc-proceed-to-checkout').css({"opacity":"0.5","pointerEvents":"none"});
    } else {
       jQuery('.wc-proceed-to-checkout').css({"opacity":"1","pointerEvents":"auto"});
    }
});

</script>
``` 
Hiding the VAT rate in woocommerce emails
---

```php
add_filter( 'woocommerce_get_formatted_order_total', 'change_emails_formatted_order_total', 10, 2 );
function change_emails_formatted_order_total( $formatted_total, $order ) {
    // Remove from order total the formatted taxes displayed on emails notifications only
    return is_wc_endpoint_url() ? $formatted_total : wc_price( $order->get_total(), array( 'currency' => $order->get_currency() ) ) . ' ' . __("(vrátane DPH)", "woocommerce");

}
``` 

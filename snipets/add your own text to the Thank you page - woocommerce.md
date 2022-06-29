Add your own text to the Thank you page - woocommerce
---


```php
add_filter('woocommerce_thankyou_order_received_text', 'woo_change_order_received_text', 10, 2 );
function woo_change_order_received_text( $str, $order ) {
    $new_str = $str . ' <p>Rezervujte si svoje miesto v <b>reštaurácií</b> už dnes!</p> <p><a class="et_pb_button et_pb_button_0 et_pb_bg_layout_light rezervacia-restauracie-btn" href="https://www.fragolinoristorante.sk/#rezervacie">Rezervovať</a></p>';
    return $new_str;
}
```
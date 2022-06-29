Adding btn ADD TO CART and QUANTITY field on the store page - DIVI
---

```php
//Setting up Woocommerce "Add to Cart" icon button and adding the quantity field.

//Add-to-Cart Button
add_action( 'woocommerce_after_shop_loop_item', 'woocommerce_template_loop_add_to_cart', 20 );

//Change the Add to Cart text to basket Icon
add_filter( 'woocommerce_product_add_to_cart_text', 'woocommerce_custom_product_add_to_cart_text' );  
function woocommerce_custom_product_add_to_cart_text() {
    return __( 'Pridať do košíka', 'woocommerce' );
}

//Changes basked icon to tick when product is already in the cart
function change_button_text( $product_id, $button_text ) {
    foreach( WC()->cart->get_cart() as $item ) {
        if( $product_id === $item['product_id'] ) {
            return __('Pridať do košíka', 'woocommerce');
        }
    }
    return $button_text;
}
add_filter( 'woocommerce_product_add_to_cart_text', 'change_ajax_add_to_cart_button_text', 10, 2 );
function change_ajax_add_to_cart_button_text( $button_text, $product ) {
    if ( $product->is_type('simple') ) {
        $button_text = change_button_text( $product->get_id(), $button_text );
    }
    return $button_text;
}

//Quantity Field

add_filter( 'woocommerce_loop_add_to_cart_link', 'quantity_inputs_for_woocommerce_loop_add_to_cart_link', 10, 2 );

function quantity_inputs_for_woocommerce_loop_add_to_cart_link( $html, $product ) {
	if ( is_user_logged_in() && $product && $product->is_type( 'simple' ) && $product->is_purchasable() && $product->is_in_stock() && ! $product->is_sold_individually() ) {
		$html = '<form action="' . esc_url( $product->add_to_cart_url() ) . '" class="cart" method="post" enctype="multipart/form-data">';
		$html .= woocommerce_quantity_input( array(), $product, false );
		$html .= '<button type="submit" class="button alt">' . esc_html( $product->add_to_cart_text() ) . '</button>';
		$html .= '</form>';
	}
	return $html;
}
```
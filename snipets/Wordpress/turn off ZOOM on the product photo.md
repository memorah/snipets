Turn off ZOOM on the product photo
---

``` php

add_action( 'after_setup_theme', 'remove_wc_zoom_theme_support', 100 );
function remove_wc_zoom_theme_support() { 
remove_theme_support( 'wc-product-gallery-zoom' );
}

``` 
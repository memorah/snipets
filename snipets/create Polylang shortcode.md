Create Polylang shortcode
---


```php
/* POLYLANG SHORTCODE */

function custom_polylang_langswitcher() {
	$output = '';
	if ( function_exists( 'pll_the_languages' ) ) {
		$args   = [
			'show_flags' => 0, // zobrazenie vlajok
			'show_names' => 1, // zobrazenie nazvu jazyka
			'echo'       => 0,
			'hide_current'      => 1, // skrytie aktivneho jazyka
		];
		$output = '<ul class="polylang_langswitcher">'.pll_the_languages( $args ). '</ul>';
	}

	return $output;
}

add_shortcode( 'polylang_langswitcher', 'custom_polylang_langswitcher' );
?>
``` 
Shortcode:
``` 
[polylang_langswitcher]
``` 
or php
```php
.<?php echo do_shortcode('[polylang_langswitcher]'); ?>
```
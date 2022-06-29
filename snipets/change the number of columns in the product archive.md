Change the number of columns in the product archive
---

By default, Woocommerce puts products into 4 columns. We will use the following snippet for the change.

```php
/**
 * Change number or products per row to 3
 */
add_filter('loop_shop_columns', 'loop_columns', 999);
if (!function_exists('loop_columns')) {
	function loop_columns() {
		return 3; // 3 products per row
	}
}
``` 
It may happen that this breaks layout a bit with this change. The following css hgelps (we determine the class according to the number of columns).

```css
.products.columns-3 {
	display: flex;
	flex-wrap: wrap;
	align-content: flex-center;
}
```
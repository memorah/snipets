Offset from the top at anchor links
---

```js
<script>
	(function($) {
window.addEventListener('DOMContentLoaded', function(ev){
	if (window.location.hash) {
		var origHash = window.location.hash;
		window.location.hash = '';

		$(function() {
			window.setTimeout(function() {
				window.location.hash = origHash;
			}, 600);
		});
	}
});

window.addEventListener('hashchange', scrollToAnchor);

function scrollToAnchor(ev){
	ev.preventDefault();

	if (!window.location.hash) {
		return false;
	}

	var anchorTarget = $(window.location.hash);

	if (!anchorTarget.length) {
		return false;
	}

	// Let the browser finish the current process, before scrolling up/down.
	$(function() {
		window.setTimeout(function(){
			var offset = parseInt(jQuery('html').css('margin-top')) +
				parseInt(jQuery('header').first().css('height')) +
				100; // vyska menu v px
			var anchorTop = anchorTarget.offset().top;
			anchorTop -= offset;

			$( 'html, body' ).animate({ scrollTop: anchorTop });
		}, 250);
	});

	return false;
}
})(window.jQuery);
</script>
```
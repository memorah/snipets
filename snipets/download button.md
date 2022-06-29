Download button
---

```js

jQuery(document).ready(function() {
  var downloadButton = jQuery('.download-button');
     
  downloadButton.each(function(index) {
    jQuery(this).attr('download', '');
  });

``` 
just add class=”download-button”

```html
.<a class="download-button" href="https://www.example.com/song.mp3">Download</a>
```
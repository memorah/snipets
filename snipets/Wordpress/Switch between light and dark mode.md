Switch between light and dark mode
---
Add code to head (script tag)

```js

	(function setTheme(themeName) {
		localStorage.setItem('theme', themeName);
		document.documentElement.className = themeName;
	})
	(function toggleTheme() {
		if (localStorage.getItem('theme') === 'theme-light') {
			setTheme('theme-dark');
		} else {
			setTheme('theme-light');
		}
	})
	(function() {
		if (localStorage.getItem('theme') === 'theme-dark') {
			setTheme('theme-dark');
		} else {
			setTheme('theme-light');
		}
	})(); 
``` 

switch buttons html

``` html
<div class="switch-btn">
 <span id="switch-light" onclick="toggleTheme()">dark mode</span>
 <span id="switch-dark" onclick="toggleTheme()">light mode</span>
</div>
 ``` 

customize by css
``` css
.theme-light {
	background: #fff;
}
.theme-dark {
	background: #000;
}
.theme-light h1 {
	color: #000;
}
.theme-dark h1 {
	color: #fff;
}
``` 
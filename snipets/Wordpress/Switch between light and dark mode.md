Add code to: <head>.. </head>


<script>
       // function to set a given theme/color-scheme
function setTheme(themeName) {
    localStorage.setItem('theme', themeName);
    document.documentElement.className = themeName;
}
// function to toggle between light and dark theme
function toggleTheme() {
   if (localStorage.getItem('theme') === 'theme-light'){
       setTheme('theme-dark');
   } else {
       setTheme('theme-light');
   }
}
// Immediately invoked function to set the theme on initial load
(function () {
   if (localStorage.getItem('theme') === 'theme-dark') {
       setTheme('theme-dark');
   } else {
       setTheme('theme-light');
   }
})();
    </script>
 

switch buttons html


<div class="switch-btn">
 <span id="switch-light" onclick="toggleTheme()">dark mode</span>
 <span id="switch-dark" onclick="toggleTheme()">light mode</span>
</div>
 

customize by css

<style>
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
<style>
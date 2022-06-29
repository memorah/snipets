Drop-down mobile submenu - DIVI
---
Add code to head (script tag)

```js
jQuery(function($) {
       
function setup_collapsible_submenus() {
     
var FirstLevel = $('.et_mobile_menu .first-level > a');
   
FirstLevel.off('click').click(function() {
$(this).attr('href', '#');  
$(this).parent().children().children().toggleClass('reveal-items');
$(this).toggleClass('icon-switch');
});
   
 
}
       
$(window).load(function() {
setTimeout(function() {
setup_collapsible_submenus();
}, 700);
});
  
})(jQuery);
``` 

Add classes to the items in the menu. The highest will receive a first-level class. The item that falls under it gets a second-level class. 

dashboard / appearance / menus / css classes (optional)

customize by css
``` css

.et_mobile_menu .first-level > a {
font-weight: 400;
  position:relative;
}
.et_mobile_menu .first-level > a:after {
font-family: 'ETmodules';
content: '\4c';
font-weight: 300;
position: absolute;
font-size: 16px;
top: 8px;
right: 10px;
}
.et_mobile_menu .first-level > .icon-switch:after{
content: '\4d';
}
.second-level {
display: none;
}
.reveal-items {
display: block;
}


``` 
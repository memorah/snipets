---
Switch between light and dark mode
---
create a languages ​​folder in CHILD THEME via FTP and a builder in it.
After downloading the file divi-preklad.zip, just unzip the archive and upload the files to language> builder

<div align="center">
  <img src="<div align="center">
  <img src="https://github.com/memorah/memorah/blob/e6c441e876089f72031b4e48a56cd4031f373d82/fm-banner.png" width="100%" alt="Banner">
</div>" width="100%" alt="Banner">
</div>

create a new snippet and insert the following code
``` php

function mr_divi_lang_function() {
    //load_child_theme_textdomain( 'Divi', get_stylesheet_directory() . '/languages/theme' );
    //load_child_theme_textdomain( 'et-core', get_stylesheet_directory() . '/languages/core' );
    load_child_theme_textdomain( 'et_builder', get_stylesheet_directory() . '/languages/builder' );
}
add_action( 'after_setup_theme', 'mr_divi_lang_function' );
``` 
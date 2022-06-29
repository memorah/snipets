Switch between light and dark mode
---
create a languages ​​folder in CHILD THEME via FTP and a builder in it.
After downloading the file divi-preklad.zip, just unzip the archive and upload the files to language> builder


  <img align="center" src="https://github.com/memorah/snipets/blob/02faef669cea8c6e7b26697f5c02caf969b14bbd/src/Divi translation img 1.jpeg" width="100%" alt="Banner">


<a href="https://github.com/memorah/snipets/blob/02faef669cea8c6e7b26697f5c02caf969b14bbd/src/divi-preklad.zip">divi-preklad.zip
</a>

create a new snippet and insert the following code

``` php

function mr_divi_lang_function() {
    //load_child_theme_textdomain( 'Divi', get_stylesheet_directory() . '/languages/theme' );
    //load_child_theme_textdomain( 'et-core', get_stylesheet_directory() . '/languages/core' );
    load_child_theme_textdomain( 'et_builder', get_stylesheet_directory() . '/languages/builder' );
}
add_action( 'after_setup_theme', 'mr_divi_lang_function' );
``` 
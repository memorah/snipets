
String translation
---
```php
/add_filter('gettext', 'translate_wplama');
add_filter('ngettext', 'translate_wplama');
function translate_wplama($translated) {
    $translated = str_ireplace('Přidat do košíku', 'Koupit', $translated);
    $translated = str_ireplace('Aktualizovat košík', 'Přepočítat košík', $translated);
    $translated = str_ireplace('Pokračovat v nákupu', 'ZPĚT KE ZBOŽÍ', $translated);
    $translated = str_ireplace('Přejít k pokladně', 'Pokračovat v objednávce', $translated);
    
    return $translated;
}
``` 

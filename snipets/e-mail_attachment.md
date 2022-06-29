Email attachment for Woocommerce
---
modify the path to the file (email attachment)

``` php

add_filter( 'woocommerce_email_attachments', 'bbloomer_attach_pdf_to_emails', 10, 4 );
 
function bbloomer_attach_pdf_to_emails( $attachments, $email_id, $order, $email ) {
    $email_ids = array( 'customer_completed_order' );
    if ( in_array ( $email_id, $email_ids ) ) {
        $upload_dir = wp_upload_dir();
        $attachments[] = $upload_dir['basedir'] . "/folder/subfolder/attachment.pdf";
    }
    return $attachments;
}
``` 
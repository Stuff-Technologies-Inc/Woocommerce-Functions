### Remove tabs through a function, ex "Additional Information"

    /**
     * Remove product data tabs
     */
    add_filter( 'woocommerce_product_tabs', 'woo_remove_product_tabs', 98 );

    function woo_remove_product_tabs( $tabs ) {

        unset( $tabs['additional_information'] );  	// Remove the additional information tab

        return $tabs;
    }

This should add a prefix to order numbers, allowing it to be easier to track. 
 
    add_filter( 'woocommerce_order_number', 'change_woocommerce_order_number' );

    function change_woocommerce_order_number( $order_id ) {
        $prefix = 'US-';
        $new_order_id = $prefix . $order_id;
        return $new_order_id;
    }

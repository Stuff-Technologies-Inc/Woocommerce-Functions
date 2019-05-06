This should add a prefix to order numbers, allowing it to be easier to track. 
 
    add_filter( 'woocommerce_order_number', 'change_woocommerce_order_number', 1, 2);

    function change_woocommerce_order_number( $order_id, $order ) {
        $prefix = 'US-';
        // You can use either one of $order->id (or) $order_id
        // Both will work
        return $prefix . $order->id;
    }

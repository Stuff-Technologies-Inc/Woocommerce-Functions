## This function adds the BTCPay meta data stored from the woocommerce plugin into your customer's order details page. This can be useful for showing customers they did not pay the full amount, or for the customers own records. 

    /**
     * Display BTCPay custom meta data fields on the customers order details page
     */
    add_action( 'woocommerce_order_details_after_order_table', 'btcpay_field_display_customer_order_meta', 10, 1 );

    function btcpay_field_display_customer_order_meta($order){
        echo '<h2>BITCOIN PAYMENT DETAILS:</h2>';
      echo '<table class="woocommerce-table woocommerce-table--order-details shop_table order_details">';
      echo '<tr>';
      echo '<th scope="row"><strong>'.__('BTC Invoice Link').':</strong></th>';
      echo '<td><a href="'. get_post_meta( $order->get_id(), 'BTCPay_redirect', true ) . '"> Invoice ID: '  . get_post_meta( $order->get_id(), 'BTCPay_id', true ) . '</a>';
      echo '</tr>';
      echo '<tr>';
      echo '<th scope="row"><strong>'.__('BTC Address').':</strong></th>';
      echo '<td>' . get_post_meta( $order->get_id(), 'BTCPay_BTCaddress', true );
      echo '</tr>';
      echo '<tr>';
      echo '<th scope="row"><strong>'.__('BTC Amount Total').':</strong></th>';
      echo '<td>' . get_post_meta( $order->get_id(), 'BTCPay_btcPrice', true );
      echo '</tr>';
      echo '<tr>';
      echo '<th scope="row"><strong>'.__('BTC Amount Paid').':</strong></th>';
      echo '<td>' . get_post_meta( $order->get_id(), 'BTCPay_btcPaid', true );
      echo '</tr>';
      echo '<tr>';
      echo '<th scope="row"><strong>'.__('BTC Exchange Rate').':</strong></th>';
      echo '<td>' . get_woocommerce_currency_symbol() . get_post_meta( $order->get_id(), 'BTCPay_formatted_rate', true ) . ' ' . get_woocommerce_currency();
      echo '</tr>';
      echo '</table>';
    }

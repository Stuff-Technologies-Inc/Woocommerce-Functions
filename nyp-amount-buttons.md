## This add's shortcodes for buttons to be added that input the amount determined

    function amount_button_shortcode( $atts ) {
      $a = shortcode_atts( array(
        'amount' => '',
        'name' => 'Other'
      ), $atts );
       return '<button type="button" value="' . $a['amount'] . '" onclick="enterPrice(this.value)">' . $a['name'] . '</button>';
    }
    add_shortcode( 'amount_button', 'amount_button_shortcode' );  

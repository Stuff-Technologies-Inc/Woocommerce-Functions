## This renames the title field from nyp to the value set in your settings. 

    /**
     * Modify NYP print input.
     * 
     * @param  string $html
     * @param  int $product_id
     * @param  string $prefix
     * @return string - The modified input html.
     */
    function kia_filter_nyp_input( $html, $product_id, $prefix ) {
      $new_title_attr = esc_attr( stripslashes ( get_option( 'woocommerce_nyp_label_text', __( 'Name Your Price', 'wc_name_your_price' ) ) ) );
      return str_replace( 'title="nyp"', sprintf( 'title="%s"', $new_title_attr ), $html );
    }
    add_filter( 'woocommerce_get_price_input', 'kia_filter_nyp_input', 10, 3 );

### Display a price range for variable priced products

    /**
     * Display NYP prices as a range.
     * @param  string $price
     * @param  WC_Product obj $product
     * @return string - The modified price string.
     */
    function nyp_price_range( $price, $product ){

      $min = WC_Name_Your_Price_Helpers::get_minimum_price( $product );
      $max = WC_Name_Your_Price_Helpers::get_maximum_price( $product );

      if( $min && $max ) {
        $price = wc_format_price_range( $min, $max );
      } else if( $min ) {
        $price = wc_price( $min );
      }
      return $price;
    }
    add_filter( 'woocommerce_nyp_html', 'nyp_price_range', 10, 2 );

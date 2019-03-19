### This creates a [member] shortcode to display to members only. Replaced by EFU on WPBakery

    /**
     * Create a "member" shortcode to hide stuff when not logged in. 
     */
    add_shortcode( 'member', 'member_check_shortcode' );

    function member_check_shortcode( $atts, $content = null ) {
       if ( is_user_logged_in() && !is_null( $content ) && !is_feed() )
        return $content;
      return '';
    }

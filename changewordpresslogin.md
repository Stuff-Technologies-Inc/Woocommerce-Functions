# This changes the Wordpress login to match branding.

    /* Login Page Editing */
    function my_login_logo() { ?>
        <style type="text/css">
            #login h1 a, .login h1 a {
                background-image: url(https://coincards.ca/wp-content/uploads/2018/12/cclogo.png);
          height:94px;
          width:220px;
          background-size: 220px 94px;
          background-repeat: no-repeat;
              padding-bottom: 30px;
            }
        </style>
    <?php }
    add_action( 'login_enqueue_scripts', 'my_login_logo' );

    function my_login_logo_url() {
        return home_url();
    }
    add_filter( 'login_headerurl', 'my_login_logo_url' );

    function my_login_logo_url_title() {
        return 'Coincards.ca';
    }
    add_filter( 'login_headertitle', 'my_login_logo_url_title' );


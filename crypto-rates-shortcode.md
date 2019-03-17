# Creates a [crypto_rates] shortcode that can be used to show the rates for BTC, LTC, Dogecoin, Dash

    function cryptorates_shortcode() {

      $serverurl = 'https://btcpay.stufftech.io';
      $storeID = '5zYqKPNBLuCMhSzkPocgMELjW5L5rwPmk8JgxzV4BBCL';
      $localcurrency = 'CAD';

      $introtext = '<p style="color:#ffc313;text-transform:uppercase;"><span style="color:white"> ';
      echo $introtext;

      //BTC Bitcoin

      //Set Crypto Ticket (BTC = Bitcoin, LTC = Litecoin, DOGE = Dogecoin, DASH = Dash, etc...)
      $cryptocode = "BTC";

      $json_output = file_get_contents($serverurl . '/api/rates?currencyPairs=' . $cryptocode . '_' . $localcurrency . '&storeId=' . $storeID);
      $obj_result = JSON_decode($json_output, true);

      foreach($obj_result as $row) {
        if($row['code'] == $localcurrency){
          echo '<img src="https://s2.coinmarketcap.com/static/img/coins/16x16/1.png" title="Bitcoin" alt="Bitcoin" scale="0">' . " = $";
          $currencyrate = $row['rate'];
          $currencyrate = number_format($currencyrate, 2, '.', '');
          echo $currencyrate . ' ' . $localcurrency . ' | ';
          break;
        }
      }


      //LTC Litecoin
      $cryptocode = "LTC";

      $json_output = file_get_contents($serverurl . '/api/rates?currencyPairs=' . $cryptocode . '_' . $localcurrency . '&storeId=' . $storeID);
      $obj_result = JSON_decode($json_output, true);

      foreach($obj_result as $row) {
        if($row['code'] == $localcurrency){
          echo '<img src="https://s2.coinmarketcap.com/static/img/coins/16x16/2.png" title="Litecoin" alt="Litecoin" scale="0"> = $';
          $currencyrate = $row['rate'];
          $currencyrate = number_format($currencyrate, 2, '.', '');
          echo $currencyrate . ' ' . $localcurrency . ' | ';
          break;
        }
      }

      //DOGE Dogecoin
      $cryptocode = "DOGE";

      $json_output = file_get_contents($serverurl . '/api/rates?currencyPairs=' . $cryptocode . '_' . $localcurrency . '&storeId=' . $storeID);
      $obj_result = JSON_decode($json_output, true);

      foreach($obj_result as $row) {
        if($row['code'] == $localcurrency){
          echo '<img src="https://s2.coinmarketcap.com/static/img/coins/16x16/74.png" title="Dogecoin" alt="Dogecoin" scale="0"> = $';
          $currencyrate = $row['rate'];
          $currencyrate = number_format($currencyrate, 4, '.', '');
          echo $currencyrate . ' ' . $localcurrency . ' | ';
          break;
        }
      }

      //DASH Dash
      $cryptocode = "DASH";

      $json_output = file_get_contents($serverurl . '/api/rates?currencyPairs=' . $cryptocode . '_' . $localcurrency . '&storeId=' . $storeID);
      $obj_result = JSON_decode($json_output, true);

      foreach($obj_result as $row) {
        if($row['code'] == $localcurrency){
          echo '<img src="https://s2.coinmarketcap.com/static/img/coins/16x16/131.png" title="Dash" alt="Dash" scale="0"> = $';
          $currencyrate = $row['rate'];
          $currencyrate = number_format($currencyrate, 2, '.', '');
          echo $currencyrate . ' ' . $localcurrency;
          break;
        }
      }
    }
    add_shortcode( 'crypto_rates', 'cryptorates_shortcode' );

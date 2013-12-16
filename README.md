check_btcpool
=============

Nagios plugin to monitor your hashrate on a number of bitcoin and litecoin mining pools.
Current supportes btcguild, coinhuntr, coinotron & bitcoin.cz mining pools. 

Usage
=====
/usr/local/nagios/plugins/check_btcpool -p coinotron -c5 -w 20 -a 53B21DE51AEA4C0B86D7AF2B038BB412
/usr/local/nagios/plugins/check_btcpool -p bitcoin.cz -c500 -w 1000 -a 394472-8aed2a17ae0f5339e9b98866210c2aa3


Nagios Example Config
======================
define command{
  command_name    check_btcpool
  command_line    $USER1$/check_btcpool $ARG1$
}


define service{
  use                 generic-service
  host_name            coinotron
  service_description Hashrate of my account 
  check_command       check_btc!-p coinotron -c5 -w 20 -a 53BXXXXXXXXXXXXXXXXXXXXXXXXXX
} 

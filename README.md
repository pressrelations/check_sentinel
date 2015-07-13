Nagios checks for Redis Sentinel
==============
* config for nrpe client:

  ```
  command[check_sentinel]=/usr/local/nagios/libexec/check_sentinel -H 127.0.0.1 -p 26379
  command[check_sentinel_master]=/usr/local/nagios/libexec/check_sentinel_master -H 127.0.0.1 -p 26379 -m <redismaster-name>
  command[check_sentinel_master_health]=/usr/local/nagios/libexec/check_sentinel_master_health -H 127.0.0.1 -p 26379 -m <redismaster-name> -w 1,1 -c 1,1
  ```

* notes:
  * turn off timeout args.
  * Taken from https://gist.github.com/chrisboulton/11337032
  * Credit to @chrisboulton

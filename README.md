mod_gzip
========

A modified ngx_http_gzip_filter_module.

The original module within nginx has an issue so called: First-packet-latency problem which means the gzip module will not send data until the whole response recieved while proxying a large http response.

This module added a new configure item to change the deflating policy to solve the problem:

gzip_flush_mode { NO_FLUSH | SYNC_FLUSH }

* NO_FLUSH: Original policy, module will not send data until the whole response recieved
* SYNC_FLUSH: New policy, module will send data quite sooner

INSTALL
=======
Just replace the original file in NGINX source and compile.

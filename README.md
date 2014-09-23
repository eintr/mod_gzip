mod_gzip
========

A modified ngx_http_gzip_filter_module.

The original module within nginx has an issue so called: First-packet-latency problem which means the gzip module will not send data until the whole response recieved while proxying a large http response.

This module added a new configure item to change the deflating policy to solve the problem.


INSTALL
=======
Just replace the original file in NGINX source and compile.

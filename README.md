# Web servers performance
Web servers simple performance tests

These test results are just indicative.

Nodejs, DartVM and .Net Core are easiest to setup and start with from scratch, Vert.x is hardest but have significant advantage in performance.

= **Nodejs** =
wrk -t12 -c400 -d30s http://127.0.0.1:1337/  
Running 30s test @ http://127.0.0.1:1337/  
  12 threads and 400 connections  
  Thread Stats   Avg      Stdev     Max   +/- Stdev  
    Latency    60.92ms    5.52ms 342.94ms   84.09%  
    Req/Sec   541.31    140.82     1.20k    74.26%  
  193666 requests in 30.09s, 36.02MB read  
Requests/sec:   6435.40  
Transfer/sec:      1.20MB  

= **Dart VM** =
wrk -t12 -c400 -d30s http://127.0.0.1:4040/
Running 30s test @ http://127.0.0.1:4040/
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    56.86ms   82.82ms   1.89s    98.69%
    Req/Sec   665.99    145.75     2.11k    85.40%
  235368 requests in 30.06s, 46.24MB read
Requests/sec:   7830.96
Transfer/sec:      1.54MB

= **.Net Core** =
wrk -t12 -c400 -d30s http://127.0.0.1:5000/
Running 30s test @ http://127.0.0.1:5000/
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    33.62ms   12.31ms 115.76ms   86.00%
    Req/Sec     1.00k   262.78     1.57k    63.17%
  358136 requests in 30.06s, 95.63MB read
Requests/sec:  11913.82
Transfer/sec:      3.18MB

= **Vert.x JVM** =
wrk -t12 -c400 -d30s http://127.0.0.1:8080/
Running 30s test @ http://127.0.0.1:8080/
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    19.83ms    4.68ms 234.04ms   80.37%
    Req/Sec     1.67k   299.02     3.91k    60.26%
  600606 requests in 30.10s, 64.72MB read
Requests/sec:  19955.19
Transfer/sec:      2.15MB

= **Go** =
wrk -t12 -c400 -d30s http://127.0.0.1:8080/
Running 30s test @ http://127.0.0.1:8080/
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   242.99ms  366.87ms   2.00s    83.74%
    Req/Sec     2.14k     3.02k   12.65k    84.41%
  661892 requests in 30.08s, 85.22MB read
  Socket errors: connect 0, read 0, write 0, timeout 316
Requests/sec:  22003.89
Transfer/sec:      2.83MB


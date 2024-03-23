# webstaurantstore
# Performance Report for a load test of Outlet product pages

Test Requirements:

Using JMeter, generate a performance report for a load test of Outlet product pages. The load test should run with a maximum of 5 RPM for a duration of 15 minutes, using a randomized sampling of product pages. The report should provide an assessment of the performance of these pages along with an explanation of the included metrics.
You may obtain sample pages using the following url, which lists all available Outlet products under the heading “WebstaurantStore Scratch and Dent Outlet.” Clicking on any of the items will load the product page you will be testing.
https://www.webstaurantstore.com/outlet.html.

Test Results Summary:

The average (AVG) page load response times for outlet pages is 11.3 seconds (sec) while product pages at 290 milliseconds (ms) 
The p95 response times (95th percentile) for outlet pages is at 12 sec while product pages at 570 ms.
The response times (Avg and p95) for ‘Launch product page’ are under acceptable thresholds while ‘Launch outlet page’ are slightly higher. As per the industry standards, <=4 sec is an acceptable threshold for many web site users. 

Detailed Assessment:

Page load time is an important metric to assess the total time a server takes to respond to all the requests in a page. However, this metric may result in incorrect measurements when the page loading involves multiple resources like images, scripts and stylesheets that are continuously loading or not fully-loaded. Here in the ‘Launch outlet page’ that could be the case as it is heavy in resources such as multiple images, scripts and stylesheets. A good alternative here is to consider ‘perceived performance’ metrics such as Time to Interact (TTI), Largest Contentful Paint (LCP) over the actual server response times. 
Google Lighthouse profiling (Chrome Developer Tools) can discover most of the client side performance metrics/perceived performance for the ‘Launch Outlet Page’. A sample test was run using Lighthouse to provide those details.
  
Performance Tuning Recommendations:

‘Launch Outlet Page’ can be optimized for improving the overall page load times and other perceived performance metrics. 
Optimization of the critical rendering path (CRP) of the outlet.html page may yield foundational improvements. Some of the strategies of CRP optimizations is DOM construction, properly sizing the images, bundling/minifying the scripts and stylesheets, and lazy loading of low priority/3rd party resources.

Metric Explanation for JMeter reports:

Columns in Statistics Section:
Label Name: name of the sampler in the JMeter test.
Number of Samples: the total number of requests made.
Average, Min, Max, Median, 90th, 95th and 95th percentile: These indicate the various response times, respectively, providing a clear perspective on overall application performance.
Throughput: Number of requests per unit of time that your application can handle.
Number of failed requests and Error %: This presents the total number of failed requests and their rate as compared to the total requests, signaling issues if the value is high.
Network - Received and Sent: The amount of data being transferred in both directions, represented as KB/sec.


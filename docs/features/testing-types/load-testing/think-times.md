---
title: Think Times
page_title: Think Times in Test Studio Load Test
description: "Think Times in Test Studio Load Test. Think Times simulate delays between requests in your User Profile"
position: 9
---
# Think Times

Think Times simulate delays between requests in your User Profile. If you recorded new HTTP traffic via <a href="/features/testing-types/load-testing/capturing-traffic" target="_blank">Capture New</a>, Test Studio will automatically detect and record Think Times and add them to the new User Profile. Similarly, if you imported a Fiddler trace, Test Studio will insert Think Times based on the time stamps of the HTTP requests contained in the trace. When you capture traffic from an existing Web Test, Test Studio will execute it as fast as possible and add default Think Times into the recorded HTTP transactions that correspond to the delay between test steps.

Once your recording or import is complete you can optionally insert or modify the existing think times.

1.&nbsp; Click ![clock+][1]. This will add a ![clock][2] in front of every HTTP transaction that doesn't already have a think time.

![Add Think Time][3]

2.&nbsp; Click ![clock][2] next to the HTTP transaction where you would like to add a  think time.

![Add Think Time][4]

3.&nbsp; Click the new **Think Time** step to show the current settings.

![Settings][5]

4.&nbsp; Set the duration you want for this Think Time. The default is 10 seconds. 

5.&nbsp; Set the deviation you want for this Think Time. The deviation specifies the range of random variation from the duration. The default is 3. A deviation of 3 means the think time will randomly vary by up to 3 seconds while the load test is running; that is, it will assume a random distribution of values between 7 seconds and 13 seconds.

**See Also**

- <a href="/knowledge-base/load-testing-kb/think-times" target="_blank">Think Times Knowledge Base article</a>

[1]: /img/features/testing-types/load-testing/think-times/fig1.png
[2]: /img/features/testing-types/load-testing/think-times/fig2.png
[3]: /img/features/testing-types/load-testing/think-times/fig3.png
[4]: /img/features/testing-types/load-testing/think-times/fig4.png
[5]: /img/features/testing-types/load-testing/think-times/fig5.png
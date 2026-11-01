# Test Results
Python version used: 3.12   |   Operating system: Windows |   Date: 01/11/2026

| # | Input                                   | Expected result             | Actual result               | Pass/Fail |
|---|-------|-----------------|---------------|-----------|
| 1 | https://www.example.com/login           | No listed warning signs     |No listed warning signs      | PASS |
| 2 | http://192.0.2.10/account               | IP address + HTTP           | IP Address + HTTP           | PASS |
| 3 | http://example.com@sample.invalid/login | @ symbol + HTTP             | @ symbol + HTTP             | PASS |
| 4 | https://a.b.c.d.e.example.invalid/path  | Many hostname segments      | Many hostname segments      | PASS |
| 5 | https://xn--example.invalid/            | Punycode-style hostname     |Punycode-style hostname      | PASS |

I have learned that based on certain condition we can check whether the text given URL comes under phishing or not.
Also, what suprised me was that there are 6 main conditions to check even though these 6 are not present that doesn't prove safety.

# EWB Phishing URL Awareness Checker

## Overview
Phishing is a scam where attackers use fake links to trick people into entering passwords or personal details. This Python tool takes a sample URL and checks its text for common warning signs, such as an @ symbol, an IP-address hostname, or an unusually long address. It never opens the URL, so it is safe to use for awareness practice.

## Features
- Detects an @ symbol in the URL
- Flags unusually long URLs (over 100 characters)
- Flags IP-address hostnames
- Flags many hostname segments (5 or more)
- Flags punycode-style hostnames (xn--)
- Flags the HTTP scheme
- Runs until we enter q to quit so that we can enter any number of URL for checking

## Requirements
Python 3.10 or later. No extra packages.

## How to Run
Windows:   python phishing_checker.py
Mac/Linux: python3 phishing_checker.py

## Example Output
EWB Phishing URL Awareness Checker
Text checks only - this program does not open URLs.
Enter a sample URL (or type q to quit): https://www.example.com/login

Result:
- No listed warning sign found.This does not prove safety.

Never enter passwords from unexpected links.
Enter a sample URL (or type q to quit): https://192.0.2.10/account

Result:
- Uses an IP address instead of a familiar domain.

Never enter passwords from unexpected links.

## Testing
| # | Input                                   | Expected                    | Actual                      | Result |
|---|-----------------------------------------|-----------------------------|-----------------------------|--------|
| 1 | https://www.example.com/login           | No warning signs            | No warning signs            | PASS |
| 2 | http://192.0.2.10/account               | IP address + HTTP           | IP Address + HTTP           | PASS |
| 3 | http://example.com@sample.invalid/login | @ symbol + HTTP             | @ symbol + HTTP             | PASS |
| 4 | https://a.b.c.d.e.example.invalid/path  | Many hostname segments      | Many hostname segments      | PASS |
| 5 | https://xn--example.invalid/            | Punycode-style hostname     |Punycode-style hostname      | PASS |


## Screenshots
![Sample run](screenshots/sample_run.png)
<img width="912" height="432" alt="sample_run" src="https://github.com/user-attachments/assets/51464c72-b2a5-432e-b4ac-3880677dfeae" />
![Test results](screenshots/test_results.png)
<img width="956" height="431" alt="test_results" src="https://github.com/user-attachments/assets/b002d8d4-8a3d-4b2c-8c01-4e9254450df6" />

## Improvements
- Loop: check several URLs without restarting, with a quit command - 
I have included this improvement as I wanted to check several URLs without restarting again and this solves it.
I tested it using the example URLs given and it ran perfectly.

## Limitations
This is an educational tool. It only reads URL text. It does not visit
URLs, scan for malware or prove that a URL is safe. No warning signs
found does NOT mean a URL is safe.

## Ethical Use
Use sample strings only. Do not collect credentials. Do not use this
project to deceive anyone or to test websites without permission.

## Author
JYTHRAA TOTA, CSE Student, EWB Courses

# Overview
As a penetration tester, I assessed the application’s client-side handling of browser cookies to determine whether user-controlled data could be abused to trigger DOM-based vulnerabilities. During testing, I identified that a cookie storing the last viewed product was populated using untrusted input and later inserted into the DOM without sanitization. By poisoning this cookie with a crafted payload, I was able to achieve arbitrary JavaScript execution in the victim’s browser. This project demonstrates how unsafe client-side trust in cookie values can lead to high-impact DOM-based XSS.

# Steps Undertaken

Step 1: Reviewed application behaviour to understand how product navigation updates client-side cookies.

Step 2: Identified the lastViewedProduct cookie as being set based on user-controlled URL input.

Step 3: Crafted a malicious product URL to inject a JavaScript payload into the cookie.

Step 4: Triggered execution by loading the homepage where the cookie value is read and rendered into the DOM.

Step 5: Confirmed successful exploitation through execution of attacker-controlled JavaScript.

# Conclusion

This assessment confirmed a high-severity DOM-based XSS vulnerability caused by unsafe client-side cookie handling. The findings highlight the importance of validating and safely rendering all client-controlled data, including cookies, to prevent arbitrary script execution and protect users from account compromise.

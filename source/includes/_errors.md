# Errors


The Aura B2B API uses the following error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is invalid.
401 | Unauthorized -- Your API key is wrong or you do not have the right to access this data.
403 | Forbidden -- You don't have the right to access this data.
404 | Not Found -- The specified request could not be found.
405 | Method Not Allowed -- You tried to access the Api endpoint with an invalid method.
418 | I'm a teapot.
429 | Too Many Requests -- You're requesting too many informations! Slow down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.

# Use Exceptions Rather Than Error Codes

> Back in the distant past there were many languages that didn’t have exceptions. In those languages the techniques for handling and  eporting errors were limited. You either set an error flag or returned an error code that the caller could check.


* The problem with these approaches is that the caller must check for errors immediately after the call. Unfortunately, it’s easy to forget. For this reason it is better to throw an exception when you encounter an error.
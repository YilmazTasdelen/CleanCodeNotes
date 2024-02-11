# Warning of Consequences

> Sometimes it is useful to warn other programmers about certain consequences. For example, here is a comment that explains why a particular test case is turned off:

        // Don't run unless you
        // have some time to kill.
        public void _testWithReallyBigFile()
        {
         writeLinesToFile(10000000);
         response.setBody(testFile);
         response.readyToSend(this);
         String responseString = output.toString();
         assertSubString("Content-Length: 1000000000", responseString);
         assertTrue(bytesSent > 1000000000);
        }
* Nowadays, of course, we’d turn off the test case by using the @Ignore attribute with an appropriate explanatory string. @Ignore("Takes too long to run").
 
Here’s another, more poignant example:
        public static SimpleDateFormat makeStandardHttpDateFormat()
        {
        //SimpleDateFormat is not thread safe,
        //so we need to create each instance independently.
        SimpleDateFormat df = new SimpleDateFormat("EEE, dd MMM yyyy HH:mm:ss z");
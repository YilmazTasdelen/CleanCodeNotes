# Provide Context With Exception

> Each exception that you throw should provide enough context to determine the source and location of an error.

 In Java, you can get a stack trace from any exception; however, a stack
trace can’t tell you the intent of the operation that failed.

Create informative error messages and pass them along with your exceptions. Mention the operation that failed and the type of failure.

If you are logging in your application, pass along enough information to be able to log the error in your catch


# Define Exception Classes in Terms of a Caller’s Needs

There are many ways to classify errors. We can classify them by their source: Did they come from one component or another? Or their type: Are they device failures, network failures, or programming errors? However, when we define exception classes in an application, our most important concern should be how they are caught.

         ACMEPort port = new ACMEPort(12);
         try {
         port.open();
         } catch (DeviceResponseException e) {
          reportPortError(e);
         logger.log("Device response exception", e);
         } catch (ATM1212UnlockedException e) {
         reportPortError(e);
         logger.log("Unlock exception", e);
         } catch (GMXError e) {
         reportPortError(e);
         logger.log("Device response exception");
         } finally {
        …
         }

That statement contains a lot of duplication. We can simplify our code considerably by wrapping the API that we are calling and making sure that it returns a common exception type:

        LocalPort port = new LocalPort(12);
         try {
         port.open();
         } catch (PortDeviceFailure e) {
         reportError(e);
         logger.log(e.getMessage(), e);
         } finally {
         …
         }
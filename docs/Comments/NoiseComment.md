# Noise Comment

> Sometimes you see comments that are nothing but noise. They restate the obvious and provide no new information.

        /** The name. */
        private String name;
        
        /**
         * Default constructor.
         */
        protected AnnualDateRule() {}

No, really? Or how about this:

        /** The day of the month. */
        private int dayOfMonth;


* The first comment in Listing  seems appropriate.2 It explains why the catch block  is being ignored. But the second comment is pure noise. Apparently the programmer was just so frustrated with writing try/catch blocks in this function that he needed to vent.

		private void startSending() {
		try {
			doSending();
		} catch (SocketException e) {
			// normal. someone stopped the request.
		} catch (Exception e) {
			try {
			response.add(ErrorResponder.makeExceptionString(e));
			response.closeAll();
			} catch (Exception e1) {
			// Give me a break!
			}
		}
		}
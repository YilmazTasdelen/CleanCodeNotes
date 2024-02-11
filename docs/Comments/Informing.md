# Nonlocal Informing

* If you must write a comment, then make sure it describes the code it appears near. Don’t offer systemwide information in the context of a local comment. 

* Aside from the fact that it is horribly redundant, it also offers information about the default port. And yet the function has absolutely no control over what that default is. 

* The comment is not describing the function, but some other, far distant part of the system.

		/**
		* Port on which fitnesse would run. Defaults to <b>8082</b>.
		*
		* @param fitnessePort
		*/
		public void setFitnessePort(int fitnessePort) {
		this.fitnessePort = fitnessePort;
		}

# Too Much Information 

* Don’t put interesting historical discussions or irrelevant descriptions of details into your comments. 

# Inobvious Connection

* The connection between a comment and the code it describes should be obvious. If you are going to the trouble to write a comment, then at least you’d like the reader to be able to look at the comment and the code and understand what the comment is talking about.

Consider, for example, this comment drawn from apache commons:
        
        /*
        * start with an array that is big enough to hold all the pixels
        * (plus filter bytes), and an extra 200 bytes for header info
        */
        this.pngBytes = new byte[((this.width + 1) * this.height * 3) + 200];

* The purpose of a comment is to explain code that does not explain itself.
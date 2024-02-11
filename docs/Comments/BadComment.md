# Bad Comments

> Most comments fall into this category. Usually they are crutches or excuses for poor code or justifications for insufficient decisions, amounting to little more than the programmer talking to himself

# Mumbling

        public void loadProperties(){
            try
            {
             String propertiesPath = propertiesLocation + "/" + PROPERTIES_FILE;
             FileInputStream propertiesStream = new FileInputStream(propertiesPath);
             loadedProperties.load(propertiesStream);
            }
            catch(IOException e){
                // No properties files means all defaults are loaded
            }
        }

* What does that comment in the catch block mean? Clearly it meant something to the author, but the meaning does not come through all that well.

# Reduntant Comment

* Listing 4-1 shows a simple function with a header comment that is completely unnecessarly long.The comment probably takes longer to read than the code itself.

        // Utility method that returns when this.closed is true. Throws an exception
        // if the timeout is reached.
        public synchronized void waitForClose(final long timeoutMillis)
        throws Exception
        {
         if(!closed)
           {
            wait(timeoutMillis);
            if(!closed)
                throw new Exception("MockResponseSender could not be closed");
        }
* What purpose does this comment serve? It’s certainly not more informative than the
code. It does not justify the code, or provide intent or rationale. It is not easier to read than
the code
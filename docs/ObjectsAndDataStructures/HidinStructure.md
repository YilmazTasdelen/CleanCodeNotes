# Hiding Structure

What if ctxt, options, and scratchDir are objects with real behavior? 

Then, because objects are supposed to hide their internal structure, we should not be able to navigate through them.

How then would we get the absolute path of the scratch directory?

        ctxt.getAbsolutePathOfScratchDirectoryOption();
        or
        ctx.getScratchDirectoryOption().getAbsolutePath()
        Neither option feels good

If ctxt is an object, we should be telling it to do something; we should not be asking it about its internals. So why did we want the absolute path of the scratch directory? What were we going to do with it? Consider this code from (many lines farther down in) the same module:

        String outFile = outputDir + "/" + className.replace('.', '/') + ".class";
        FileOutputStream fout = new FileOutputStream(outFile);
        BufferedOutputStream bos = new BufferedOutputStream(fout);

So, what if we told the ctxt object to do this?

        BufferedOutputStream bos = ctxt.createScratchFileStream(classFileName);
That seems like a reasonable thing for an object to do! This allows ctxt to hide its internals and prevents the current function from having to violate the Law of Demeter by navigating through objects it shouldn’t know about.
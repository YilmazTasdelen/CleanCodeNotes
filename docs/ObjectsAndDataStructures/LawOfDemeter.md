# Law Of Demeter

* a module should not know about the innards of the objects it manipulates.

* As we saw in the last section, objects hide their data and expose operations. This means that an object should not expose its internal structure through accessors because to do so is to expose, rather than to hide, its internal structure.

* More precisely, the Law of Demeter says that a method f of a class C should only call the methods of these:
    * C
    * An object created by f
    * An object passed as an argument to f
    * An object held in an instance variable of C

* The method should not invoke methods on objects that are returned by any of the allowed functions. In other words, talk to friends, not to strangers.
        final String outputDir = ctxt.getOptions().getScratchDir().getAbsolutePath();

# Train Wrecks

* This kind of code is often called a train wreck because it look like a bunch of coupled train cars. Chains of calls like this are generally considered to be sloppy style and should be avoided. It is usually best to split them up as follows:

        Options opts = ctxt.getOptions();
        File scratchDir = opts.getScratchDir();
        final String outputDir = scratchDir.getAbsolutePath();

* these two snippets of code violations of the Law of Demeter Certainly
the containing module knows that the ctxt object contains options, which contain a scratch directory, which has an absolute path. That’s a lot of knowledge for one function to know. The calling function knows how to navigate through a lot of different objects.

* If they are objects, then their internal structure
should be hidden rather than exposed, and so knowledge of their innards is a clear violation of the Law of Demeter.
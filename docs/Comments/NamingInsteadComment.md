# Don’t Use a Comment When You Can Use a Function or a Variable

* Consider the following stretch of code:

        // does the module from the global list <mod> depend on the
        // subsystem we are part of?
        if (smodule.getDependSubsystems().contains(subSysMod.getSubSystem()))

* This could be rephrased without the comment as

        ArrayList moduleDependees = smodule.getDependSubsystems();
        String ourSubSystem = subSysMod.getSubSystem();
        if (moduleDependees.contains(ourSubSystem))

* The author of the original code may have written the comment first (unlikely) and then written the code to fulfill the comment. However, the author should then have refactored the code, as I did, so that the comment could be removed.
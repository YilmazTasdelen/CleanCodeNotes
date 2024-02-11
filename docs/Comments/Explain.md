# Explain

>  The proper use of comments is to compensate for our failure to express ourself in code. Note that I used the word failure. I meant it.

> Comments are always failures. We must have them because we cannot always figure out how to express ourselves without them, but their use is not a cause for celebration. 

* It is possible to make the point that programmers should be disciplined enough to keep the comments in a high state of repair,  elevance, and accuracy. I agree, they should. But I would rather that energy go toward making the code so clear and expressive that it does not need the comments in the first place.

# Explain Yourself in Code

 Which would you rather see? This:

        // Check to see if the employee is eligible for full benefits
        if ((employee.flags & HOURLY_FLAG) && (employee.age > 65))

Or this?

        if (employee.isEligibleForFullBenefits())

# Legal Comments

Sometimes our corporate coding standards force us to write certain comments for legal reasons. For example, copyright and authorship statements are necessary and reasonable things to put into a comment at the start of each source file.

        // Copyright (C) 2003,2004,2005 by Object Mentor, Inc. All rights reserved.
        // Released under the terms of the GNU General Public License version 2 or later.

# Informative Comments

It is sometimes useful to provide basic information with a comment. For example, consider this comment that explains the return value of an abstract method:

        // Returns an instance of the Responder being tested.
        protected abstract Responder responderInstance();

A comment like this can sometimes be useful, but it is better to use the name of the function to convey the information where possible. For example, in this case the comment could be made redundant by renaming the function: responderBeingTested.

Here’s a case that’s a bit better:

        // format matched kk:mm:ss EEE, MMM dd, yyyy
        Pattern timeMatcher = Pattern.compile(
        "\\d*:\\d*:\\d* \\w*, \\w* \\d*, \\d*");

# Clarification

* There is a substantial risk, of course, that a clarifying comment is incorrect
        assertTrue(a.compareTo(a) == 0); // a == a
        assertTrue(a.compareTo(b) != 0); // a != b
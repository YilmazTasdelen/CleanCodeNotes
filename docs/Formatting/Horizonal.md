# Horizonal Formatting 

> Programmers clearly prefer short lines. You should never have to scroll to the right. But monitors are too wide for that nowadays, and younger programmers can shrink the font so small that they can get 200 characters across the screen. Don’t do that. I personally set my limit
at 120.


# Horizontal Openness and Density

We use horizontal white space to associate things that are strongly related and disassociate things that are more weakly related. Consider the following function:

        private void measureLine(String line) {
            lineCount++;
            int lineSize = line.length();
            totalChars += lineSize;
            lineWidthHistogram.addLine(lineSize, lineCount);
            recordWidestLine(lineSize);
        }

I surrounded the assignment operators with white space to accentuate them. Assignment statements have two distinct and major elements: the left side and the right side. The spaces make that separation obvious.

Unfortunately, most tools for reformatting code are blind to the precedence of operators and impose the same spacing throughout. So subtle spacings like those shown above tend to get lost after you reformat the code. 

# Horizontal Alignment

        private Socket      socket;
        private InputStream input;

 * that this kind of alignment is not useful. The alignment seems to emphasize the wrong things and leads my eye away from the true intent. 
 
* the problem is the length of the lists, not the lack of alignment. The length of the list of declarations in FitNesseExpediter below
suggests that this class should be split up.

        private Socket socket;
        private InputStream input;

# Indentation

* To make hierarchy of scopes visible, we indent the lines of source code in proportion to their position in the hiearchy. Statements at the level of the file, such as most class declarations, are not indented at all. Methods within a class are indented one level to the right of the class.

* Your eye can rapidly discern the structure of the indented file. You can almost instantly spot the variables, constructors, accessors, and methods

# Breaking Indentation

 It is sometimes tempting to break the indentation rule for short if statements, short while loops, or short functions. Whenever I have succumbed to this
temptation, I have almost always gone back and put the indentation back in. So I avoid collapsing scopes down to one line like this:

        public class CommentWidget extends TextWidget
        {
         public static final String REGEXP = "^#[^\r\n]*(?:(?:\r\n)|\n|\r)?";
         public CommentWidget(ParentWidget parent, String text){super(parent, text);}
         public String render() throws Exception {return ""; }
        }
        
I prefer to expand and indent the scopes instead, like this:

        public class CommentWidget extends TextWidget {
         public static final String REGEXP = "^#[^\r\n]*(?:(?:\r\n)|\n|\r)?";

         public CommentWidget(ParentWidget parent, String text) {
         super(parent, text);
        }

         public String render() throws Exception {
          return "";
         }
        }
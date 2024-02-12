# Write Your Try Catch Finally Statement First

> One of the most interesting things about exceptions is that they define a scope within your program. When you execute code in the try portion of a try-catch-finally statement, you are stating that execution can abort at any point and then resume at the catch

* Let’s look at an example. We need to write some code that accesses a file and reads some serialized objects.

We start with a unit test that shows that we’ll get an exception when the file doesn’t exist:

        @Test(expected = StorageException.class)
         public void retrieveSectionShouldThrowOnInvalidFileName() {
          sectionStore.retrieveSection("invalid - file");
         }


The test drives us to create this stub:

        public List<RecordedGrip> retrieveSection(String sectionName) {
         // dummy return until we have a real implementation
         return new ArrayList<RecordedGrip>();
        }

Our test fails because it doesn’t throw an exception. Next, we change our implementation so that it attempts to access an invalid file. This operation throws an exception:

        public List<RecordedGrip> retrieveSection(String sectionName) {
         try {
         FileInputStream stream = new FileInputStream(sectionName)
         } catch (Exception e) {
         throw new StorageException("retrieval error", e);
        }
         return new ArrayList<RecordedGrip>();      
        }

Our test passes now because we’ve caught the exception. At this point, we can refactor. We can narrow the type of the exception we catch to match the type that is actually thrown from the FileInputStream constructor: FileNotFoundException:

        public List<RecordedGrip> retrieveSection(String sectionName) {
         try {
         FileInputStream stream = new FileInputStream(sectionName);
         stream.close();
         } catch (FileNotFoundException e) {
         throw new StorageException("retrieval error”, e);
         }
         return new ArrayList<RecordedGrip>();
        }
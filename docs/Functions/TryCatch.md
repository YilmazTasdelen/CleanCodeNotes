# Extract Try/Catch Blocks
Try/catch blocks are ugly in their own right. They confuse the structure of the code and mix error processing with normal processing. So it is better to extract the bodies of the try and catch blocks out into functions of their own.

        public void delete(Page page) {
            try {
             deletePageAndAllReferences(page);
            }
            catch (Exception e) {
             logError(e);
            }
        }

        private void deletePageAndAllReferences(Page page) throws       Exception {
            deletePage(page);
            registry.deleteReference(page.name);
            configKeys.deleteKey(page.name.makeKey());
            }

        private void logError(Exception e) {
            logger.log(e.getMessage());
        }

In the above, the delete function is all about error processing. It is easy to understand and then ignore. The deletePageAndAllReferences function is all about the processes of fully deleting a page. Error handling can be ignored. This provides a nice separation that
makes the code easier to understand and modify.
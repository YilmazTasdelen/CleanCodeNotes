# Prefer Exceptions to Returning Error Codes 

> Returning error codes from command functions is a subtle violation of command query separation. It promotes commands being used as expressions in the predicates of if statements.

        if (deletePage(page) == E_OK) {
          if (registry.deleteReference(page.name) == E_OK) {
            if (configKeys.deleteKey(page.name.makeKey()) == E_OK) {
              logger.log("page deleted");
            } else {
              logger.log("configKey not deleted");
            }
          } else {
            logger.log("deleteReference from registry failed");
          }
        } else {
          logger.log("delete failed");
          return E_ERROR;
        }

* On the other hand, if you use exceptions instead of returned error codes, then the error processing code can be separated from the happy path code and can be simplified:

                try {
                  deletePage(page);
                  registry.deleteReference(page.name);
                  configKeys.deleteKey(page.name.makeKey());
                } catch (Exception e) {
                  logger.log(e.getMessage());
                }
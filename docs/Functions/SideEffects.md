# Have No Side Effects

Side effects are lies. Your function promises to do one thing, but it also does other hidden things. 

        public class UserValidator {
              private Cryptographer cryptographer;

         public boolean checkPassword(String userName, String password) {
                User user = UserGateway.findByName(userName);
                if (user != User.NULL) {
                  String codedPhrase = user.getPhraseEncodedByPassword();
                  String phrase = cryptographer.decrypt(codedPhrase, password);
                    if ("Valid Password".equals(phrase)) {
                        Session.initialize();
                        return true;
                    }
                }
                return false;
            }
        }

* The side effect is the call to Session.initialize(), of course.

* The checkPassword function, by its name, says that it checks the password. The name does not imply that it initializes the session. 
 
* So a caller who believes what the name of the function says runs the risk of erasing the existing session data when he or she decides to check the validity of the user.

* That is, checkPassword can only be called at certain times (in other words, when it is safe to initialize the session).
# Make Meaningful Distinction

> If names must be different, then they should also mean something different. Imagine finding one class named Customer and another named
CustomerObject. What should you understand as the distinction? Which one will represent
the best path to a customer’s payment history?


* For example

        public static void copyChars(char a1[], char a2[]) {
            for (int i = 0; i < a1.length; i++) {
                a2[i] = a1[i];
            }
        }
* this func. reads much better when source and destination are used for the argument names.

* Dont use Noise words. For example you have ; 
          Product class
          ProductInfo class
          ProductData class
you make the name different without making them anything different.

* the word table, variable,string etc.. should never apper in the name.

*How are the programmers in this project supposed to know which of these functions to call?

         getActiveAccount();
         getActiveAccounts();
         getActiveAccountInfo();

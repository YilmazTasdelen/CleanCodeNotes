# Prefixes

>  You also don’t need to prefix member variables with m_ anymore. Your classes and functions should be small enough that you don’t need them


        public class Part {
            private String m_dsc; // The textual description
            void setName(String name) {
            m_dsc = name;
            }
        }
_________________________________________________

        public class Part {
            String description;
            void setDescription(String description) {
            this.description = description;
            }
        }

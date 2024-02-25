# Reverse-an-Integer
Leetcode Solution to Reversing an Integer
Here is my solution : [Reverse an Integer](https://leetcode.com/problems/reverse-integer/submissions/1185683459)https://leetcode.com/problems/reverse-integer/submissions/1185683459

I know it is not efficient but I worked with the tools that I knew - I scoured the better soltions after and discovered the Integer.min_value and Integer.max_value constants that I could have utilised ... 

```java
class Solution {
    public int reverse(int x) {
            long upperBound = 2147483647L;
        long lowerBound = -2147483648L;
        if (x>=upperBound||x<=lowerBound) return 0;

        if (x < 0) {
            String s = String.valueOf(x);
            String replacement = "";
            s = s.replace("-", "");

            for (int i = s.length()-1; i >= 0; i--){
                replacement += s.charAt(i);
            }

            int firstDigit = replacement.charAt(0) - '0';

            if (replacement.length() > 10) return 0;
            else if (replacement.length() == 10 && firstDigit > 2) return 0;
            try {
                return Integer.parseInt(replacement) * -1;
            } catch (Exception e) {
                return 0;
            }
        }
        else {
            String s = String.valueOf(x);
            String replacement = "";

            for (int i = s.length()-1; i >= 0; i--){
                replacement += s.charAt(i);
            }

            int firstDigit = replacement.charAt(0) - '0';

            if (replacement.length() > 10) return 0;
            else if (replacement.length() == 10 && firstDigit > 2) return 0;
            try {
                return Integer.parseInt(replacement);
            } catch (Exception e) {
                return 0;
                }
            }
        }
    }  
```

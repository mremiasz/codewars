# codewars

Przykładowe moje rozwiązania z niektórych zadań.

[![](https://www.codewars.com/users/micrem/badges/large)](https://www.codewars.com/users/micrem)


Word a10n (abbreviation) https://www.codewars.com/kata/5375f921003bf62192000746
```JAVA
import java.util.regex.*;

public class Abbreviator {

  public String abbreviate(String string) {
    Pattern p = Pattern.compile("([a-zA-Z]{4,})");
    Matcher m = p.matcher(string);
    
    while(m.find())
    {
       String part = m.group();
       String repl = "" + part.charAt(0) + (part.length()-2) + part.charAt(part.length()-1);
       string = string.replaceFirst(part, repl);
    }
    return string;
  }
}
```

Large Factorials https://www.codewars.com/kata/557f6437bf8dcdd135000010
```JAVA
import java.math.BigInteger;
public class Kata
{

  public static String Factorial(int n) {

    BigInteger sum = BigInteger.ONE;
     
    for(int i = 1; i <= n; i++) {
      sum=sum.multiply(BigInteger.valueOf(i));      
    }
    
    return String.valueOf(sum);
  }
}
```

Roman Numerals Encoder https://www.codewars.com/kata/51b62bf6a9c58071c600001b
``` java
import java.util.*;
public class Conversion {

    public String solution(int n) {
      String[] romAry = {"M","CM","D","CD","C","XC","L","XL","X","IX","V","IV","I"};
      int[] digitAry = {1000,900,500,400,100,90,50,40,10,9,5,4,1};
      
      StringBuilder sb = new StringBuilder();

      for (int i = 0; i < romAry.length;) {
        int number = digitAry[i];
        String symbol = romAry[i];
        if (n>=number) {
          sb.append(symbol);
          n-=number;
          ;
        }
        if (n<number) i++;
      }
      return sb.toString();  
    }
}
```

Give me a Diamond https://www.codewars.com/kata/5503013e34137eeeaa001648
```java
class Diamond {
  public static String print(int n) {
    // TODO your code here
    if (n < 0 || n % 2 == 0) return null;
    String shape = "";
    int middle = n/2 + 1;
    for (int i = middle; i <= n*2 - middle; i++) {
      for (int j = 1; j <= n - Math.abs(n - i); j++) {
          if (j <= Math.abs(n - i)) shape += " ";
          else shape += "*";
      }
      shape += "\n";
    }
    return shape;
	}
}
```

Evil Autocorrect Prank https://www.codewars.com/kata/538ae2eb7a4ba8c99b000439
```java
import java.util.regex.*;  
public class Kata {
  public static String autocorrect(String input) {
    // your code here
    //input.replaceAll("\\su\\s","your sister");
    String replace = "your sister";
    Pattern pU = Pattern.compile("\\bu\\b");
    Pattern pYou = Pattern.compile("\\b[Yy]ou\\b");
    Pattern pYouu = Pattern.compile("\\b[Yy]ou+\\b");

    Matcher m1 = pU.matcher(input);
    input = m1.replaceAll(replace);
    
    Matcher m2 = pYou.matcher(input);
    input = m2.replaceAll(replace);
    
    Matcher m3 = pYouu.matcher(input);
    input = m3.replaceAll(replace);

    return input;
  }
}
```

# firstNoneRepeatingCharacter
### Requirements:
Given a string str consisting of small english letters, find and return the first instance of a non-repeating character in it. If there is no such letter, then return '-'

### Example 1:
"aaabcccdeef"   -> 'b'

### Example 2:
"abcbad"  -> 'c'

### Example 3:
"abcabcabc" -> '-'

```java
import java.util.Hashtable;

public class testString {
	public static void main(String[] args) {
		String str = "aaabccdef";
		System.out.println(firstNoneRepeatingCharacter(str));
	}
	
	public static char firstNoneRepeatingCharacter(String str) {
		if(str.length() == 1) {
			return str.charAt(0);
		}else {
			char c;
			Hashtable<Character, Integer> hashTable = new Hashtable<Character, Integer>(str.length());
			for(int i = 0; i < str.length(); i++) {
				c = str.charAt(i);
				if(!hashTable.containsKey(c)) {
					hashTable.put(c, 1);
				}else {
					int temp = hashTable.get(c);
					hashTable.replace(c, temp + 1);
				}
			}
			
			for(int i = 0; i < str.length(); i++) {
				if(hashTable.get(str.charAt(i)) == 1) {
					return str.charAt(i);
				}
			}
			return '-';
		}
	}
}
```

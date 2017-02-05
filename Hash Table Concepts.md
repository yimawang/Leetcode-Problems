# Java HashMap put function:

1. If a key already exists with a value "sam", return would be "sam"
2. If a key did not exist, then return is equal to null.

This mean we could use HashMap.put function more to replace many HashMap.contains.

Leetcode problem: 290) Word Pattern

Solution: 
public class Solution {
    public boolean wordPattern(String pattern, String str) {
        String[] the_string = str.split(" ");
        if(the_string.length!=pattern.length())
            return false;

        HashMap<Character,String> hm = new HashMap<Character,String>();
        HashMap<String,Character> hm2 = new HashMap<String,Character>();
        for(int i=0; i<pattern.length();i++){
            if(hm.containsKey(pattern.charAt(i))){
                if(!hm.get(pattern.charAt(i)).equals(the_string[i]))
                    return false;
            }
            else{
                if(hm2.containsKey(the_string[i])){
                    return false;
                }
                hm2.put(the_string[i], pattern.charAt(i));
                hm.put(pattern.charAt(i), the_string[i]);
            }
        }
        return true;
    }
}

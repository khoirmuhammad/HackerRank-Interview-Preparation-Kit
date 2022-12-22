### Alternating Characters
Link : https://www.hackerrank.com/challenges/alternating-characters/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=strings  

You are given a string containing characters A and B only. Your task is to change it into a string such that there are no matching adjacent characters. To do this, you are allowed to delete zero or more characters in the string.......
```
public static int alternatingCharacters(string s)
    {
        char currentChar = s[0];
        int loop = 0;
        int deletion = 0;
        
        foreach(char c in s)
        {
            if (loop != 0)
            {
                if (currentChar == c)
                {
                    deletion++;
                }
                
                currentChar = c;
            }
            
            loop++;
        }
        
        return deletion;
    }
```

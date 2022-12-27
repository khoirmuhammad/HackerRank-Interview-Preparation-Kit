### Hash Tables: Ransom Note
Harold is a kidnapper who wrote a ransom note, but now he is worried it will be traced back to him through his handwriting. He found a magazine and wants to know if he can cut out whole words from it and use them to create an untraceable replica of his ransom note. The words in his note are case-sensitive and he must use only whole words available in the magazine. He cannot use substrings or concatenation to create the words he needs.

Given the words in the magazine and the words in the ransom note, print Yes if he can replicate his ransom note exactly using whole words from the magazine; otherwise, print No.  

Link: https://www.hackerrank.com/challenges/ctci-ransom-note/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=dictionaries-hashmaps

```
public static void checkMagazine(List<string> magazine, List<string> note)
{
    string result = "Yes";
        
    if (note.Count > magazine.Count)
    {
        result = "No";
    }
    else
    {
        if (note.Count == magazine.Count)
        {
            string strMagazine = String.Join(" ", magazine.OrderBy(o => o).ToList());
            string strNote = String.Join(" ", note.OrderBy(o => o).ToList());
                    
            if (strMagazine != strNote)
            {
                result = "No";
            }
        }
        else
        {
                foreach (string item in note)
                {
                    if (magazine.Contains(item))
                    {
                        magazine.Remove(item);
                    }
                    else
                    {
                        result = "No";
                        break;
                    }
                }
         }
                
       }
        
        Console.WriteLine(result);
}
```
### Two Strings
Given two strings, determine if they share a common substring. A substring may be as small as one character.  
Link : https://www.hackerrank.com/challenges/two-strings/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=dictionaries-hashmaps
```
public static string twoStrings(string s1, string s2)
    {
        string result = "NO";
        
        foreach(char s in s1)
        {
            if (s2.Contains(s))
            {
                result = "YES";
                break;
            }
        }
        
        return result;
    }
```


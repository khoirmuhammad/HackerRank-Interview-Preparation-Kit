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
### Making Anagrams
Link : https://www.hackerrank.com/challenges/ctci-making-anagrams/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=strings

```
public static int makeAnagram(string a, string b)
    {
            #region Remove character which is not in A and B. So, Both A and B only contains simillar character
            string orderStrA = string.Empty;
            string orderStrB = string.Empty;

            int aDeletion = 0;
            int bDeletion = 0;

            foreach (char c in a)
            {
                if (b.IndexOf(c) < 0)
                {
                    int idx = a.IndexOf(c);
                    a = a.Remove(idx, 1);
                    aDeletion++;
                }

            }

            foreach (char c in b)
            {
                if (a.IndexOf(c) < 0)
                {
                    int idx = b.IndexOf(c);
                    b = b.Remove(idx, 1);
                    bDeletion++;
                }

            }

            orderStrA = String.Concat(a.OrderBy(c => c)); //gilmmrsvwxx
            orderStrB = String.Concat(b.OrderBy(c => c)); //gilmmmrrsvwwx
            
            #endregion


            #region take less character between A and B. For example string A has 3 char a, string B has 5 char a then we will remove 2 char a in string B
            int deletion = 0;

            var strA = orderStrA.GroupBy(g => g).Select(s => new
            {
                character = s.Key,
                total = s.Count()
            }).ToList();

            var strB = orderStrB.GroupBy(g => g).Select(s => new
            {
                character = s.Key,
                total = s.Count()
            }).ToList();

            foreach(var item in strA)
            {
                var itemB = strB.FirstOrDefault(f => f.character.Equals(item.character));

                if (itemB != null)
                {
                    deletion += Math.Abs(item.total - itemB.total);
                }
                
            }
            #endregion
            
            return aDeletion + bDeletion + deletion;
    }
```

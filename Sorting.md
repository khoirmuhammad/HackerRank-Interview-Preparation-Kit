### Bubble Sort
Link : https://www.hackerrank.com/challenges/ctci-bubble-sort/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=sorting
```
{
        int totalSwap = 0;

            for(int i = 0; i < a.Count - 1; i++) 
            {
                for(int j = 0; j < a.Count - i - 1; j++)
                {
                    if (a[j] > a[j + 1])
                    {
                        var tempVar = a[j];
                        a[j] = a[j + 1];
                        a[j + 1] = tempVar;

                        totalSwap++;
                    }
                }
            }

            Console.WriteLine($"Array is sorted in {totalSwap} swaps.");
            Console.WriteLine($"First Element: {a[0]}");
            Console.WriteLine($"Last Element: {a[a.Count - 1]}");
    }
```

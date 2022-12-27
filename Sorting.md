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
### Mark and Toys
Mark and Jane are very happy after having their first child. Their son loves toys, so Mark wants to buy some. There are a number of different toys lying in front of him, tagged with their prices. Mark has only a certain amount to spend, and he wants to maximize the number of toys he buys with this money. Given a list of toy prices and an amount to spend, determine the maximum number of gifts he can buy.  
Link : https://www.hackerrank.com/challenges/mark-and-toys/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=sorting
```
public static int maximumToys(List<int> prices, int k)
    {
        int result = 0;
                
        int priceItem = 0;
        foreach(var price in prices.OrderBy(o => o).ToList())
        {
            priceItem = priceItem + price;
            
            if (priceItem <= k)
            {
                result++;
            }
            else
            {
                break;
            }
        }
        
        return result;
    }
```

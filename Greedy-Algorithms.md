### Minimum Absolute Difference in an Array
The absolute difference is the positive difference between two values a and b, is written |a-b| or |b-a| and they are equal. If a = 3 and b = 2, |3-2| = |2-3| = 1. Given an array of integers, find the minimum absolute difference between any two elements in the array.  
Link : https://www.hackerrank.com/challenges/minimum-absolute-difference-in-an-array/problem?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=greedy-algorithms  
```
public static int minimumAbsoluteDifference(List<int> arr)
    {
        int result = 0;
        
        arr = arr.OrderBy(x => x).ToList();

        if (arr.Count > 1)
        {
            result = Math.Abs(arr[arr.Count - 1] - arr[0]);
        }

        for (int i = 0; i < arr.Count - 1; i++)
        {
            int tempResult = Math.Abs(arr[i + 1] - arr[i]);
            if (tempResult < result)
            {
                result = tempResult;
            }
        }
        
        return result;
    }
```

# Day 3 - Best Time to Buy and Sell Stock

## Problem
Find the maximum profit by buying and selling a stock once.

## Approach
- Track minimum price so far
- Calculate profit at each step
- Update maximum profit

## Complexity
- Time: O(n)
- Space: O(1)

## Code
```cpp
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int minPrice = INT_MAX;
        int maxProfit = 0;
        for(int i = 0; i < prices.size(); i++) {
            if(prices[i] < minPrice) {
                minPrice = prices[i];
            } else {
                int profit = prices[i] - minPrice;
                if(profit > maxProfit) {
                    maxProfit = profit;
                }
            }
        }
        return maxProfit;
    }
};
```

## Screenshot

<img width="1898" height="932" alt="image" src="https://github.com/user-attachments/assets/1d1b2d5e-e254-4587-b603-8a448fec92b2" />

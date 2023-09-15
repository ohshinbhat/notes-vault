### Two Sum
prob- need to find 2 nums in an array which add upto target in O(n)
sol- for loop->check if map contains a key = target - nums[i], if does return or add nums[i] to map

### Contains Duplicate
prob - need to check if array contains duplicate elements in O(n)
sol- for loop -> add elements to set, if set size doesnt increase, contains duplicate, return true or false

### Best Time to Buy and Sell Stock
prob- given stock prices array, need to find buy price(lowest) and sell price(highest)
sol- for loop -> find a curr_low by Math.min, find a max_profit by Math.max of (prices[i] - curr_low, max_profit)


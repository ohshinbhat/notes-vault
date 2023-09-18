### Product of Array Except Self


### Maximum Subarray
prob - from given array, we need to find max sum that can produced by subarrays
sol- using Kadane's algorithm, find the curr sum by max of (curr_sum+nums[i], nums[i]), then find max sum by max of curr_max, max_sum

### Minimum in Rotated Sorted Array
prob - sorted array rotated n times, we need to find min O(logn)
sol- using binary search while(i<j) -> if nums[i]<nums[j] then return nums[i] cuz its the lowest of the arr
but if not set mid, if nums[mid] >= nums[i], make i = mid+1 else j=mid
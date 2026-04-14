# CSC220_Sort_Colors

class Solution {
public:
    void sortColors(vector<int>& nums) {

        int zerocount = 0;
        int onecount = 0;
        int twocount = 0;

        for(int i = 0; i < nums.size(); i++) {
            if(nums[i] == 0) zerocount++;
            if(nums[i] == 1) onecount++;
            if(nums[i] == 2) twocount++;
        }
        
        int index = 0;

        while(zerocount > 0) {
            nums[index++] = 0;
            zerocount--;
        }
        while(onecount > 0) {
            nums[index++] = 1;
            onecount--;
        }
        while(twocount > 0) {
            nums[index++] = 2;
            twocount--;
        }
    }
};

The problem gives us three different numbers: 0, 1, and 2. These numbers represent the colors and they're given to us in an array. Our approach to the problem was to do a count sort. We first initialized three different counters for each number (zerocount, onecount, twocount). Then we iterated through the array and counted how many instances of each integer appeared. After we had that, we changed the original nums array. We started at index 0 and began replacing the numbers in the original array (i.e, if original array was [1, 0], it would rewrite the "1" to a 0), and then we did that for each number in order of zero, one, two. This wouldn't change the size of the array since all the counts add up to the size of the array.

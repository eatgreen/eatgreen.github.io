#24/02/2017
##problem add numbers
尽量减少不必要的赋值和判断。基本思路，取l1和l2中的元素相加，大于10则进位（用／和%来处理）。返回一个listnode指针，这个指针需要new一个listnode，长度至少满足l1和l2以及进位的需要。

##overflow detection
Addition overflow:
If a+b<=R-1, a$b=a+b
As a and b are unsigned, a$b is more or equal to than both a and b.

If a+b>=R a$b=a+b-R
as R is more than both a and b, a-R and b-R are negative
So, a+b-R<a and a+b-R<b
Therefore, a$b is less than both a and b.

Multiplication overflow: if a*b>max, then a>max/b (max is R-1 if unsigned and R/2-1 if signed).

##container with most water
首先取首尾的元素，较小的高度乘以宽度（此时最大）即为面积
两边向中间step，方向从较小的高度那一边开始，重新上一个步骤

#25/02/2017
##remove duplicated from sorted array
设置两个指针，一个在最初，一个在第一个的下一个。
验证如果第二个的值等于第一个，第二个加一；否则，第二个所指的值赋给第一个的下一个
下一个循环从第一个加一，也就是上次改变了的值开始，知道第二个遍历为止。
特别注意处理1个元素和0个元素的情况

##search insert position
This problem is a bit different from the binary search. Instead of searching for the exact value, here we determine the index of the boundaries of the values.
1. If the target value is presented in the array, the problem ends when l>r, since we donot test the equality of the nums[m] and target, when they equal, r is moved left, eventually r is smaller than l and this l is the sought index.
2. If the target value is not presented in the array, the problem ends the same. when target donot exist, we have the middile value smaller/larger than target, l/r is set to equal to each other.

##Palindrome Number/回文数
the first notion is to unpack the digit into an array, then do the search but this requires the extra space.
the second notion after checking the discussion is by not to unpack them into a new array, but on the fly. such as unpack the last digit, then next time construct it as a new accumalated value. at the same time x is reduced each unpacking, make sure x>unpack to avoid overflow. If the number is Palindrome, the unpacked value should equal the reduced x.

#26/02/2017
##merging two lists
my idea is to compare two pointers on the two lists, and put the smaller one to the new list. But most of the time is spent on how to detect ana manage the end of each list.
reference code, use l1 and l2 as pointers directly, if l1->val is smaller than l2->val, give l1 to l, move l1 to the right pointer. also move l pointer.

1. instead of new, we can use assign values to pointer directly.
2. 当我们赋值一个list pointer to another pointer, the list is automatically copied. this is more efficient than assign values.

##Remove Element
learning from the reference. from i=0->nums.size(), if found copy, count++, else copy the value to the location sliding by the number of recurrence. 我一开始想的是，探测到相等的值，则所有右边的值往左移一位。但更好的想法是，出现一次就记一次数，一个遍历的index,往左移动计数器个位置。

##Pow(x, n)
using recursive to code.
~~1. negative exponent needs to be considered. 2. overflow~~
my idea is to compute x*Pow(x,n-1)
a better one is to compute Pow(x*x,n/2) for even number and x*Pow(x*x,n/2) for odd number. 

# 05/03/2017
## 2sum
首先排序，首尾两个pointer,若其和大于目标值，back--,若其和小于目标值,front++

## 3sum
关键是去除重复

## letter of combination
create a string map of number to string
use digits[i] - '0' to get number out of string digits
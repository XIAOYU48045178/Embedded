`来源 leetcode 仅学习`

`数组`
--

`1. 两数之和`

`给定一个整数数组 nums 和一个整数目标值 target 请你在该数组中找出 和 为目标值 target  的那两个整数 并返回它们的数组下标 可以假设每种输入只会对应一个答案并且你不能使用两次相同的元素可以按任意顺序返回答案` 

`示例`

```
输入：nums = [2,7,11,15], target = 9
输出：[0,1]
解释：因为 nums[0] + nums[1] == 9  返回 [0, 1]  

输入：nums = [3,2,4], target = 6
输出：[1,2]

输入：nums = [3,3], target = 6
输出：[0,1]
```

`提示`

```
2 <= nums.length <= 104
-109 <= nums[i] <= 109
-109 <= target <= 109
只会存在一个有效答案
```

暴力枚举

最容易想到的方法是枚举数组中的每一个数 x 寻找数组中是否存在 target - x 

当我们使用遍历整个数组的方式寻找 target - x 时 需要注意到每一个位于 x 之前的元素都已经和 x 匹配过 因此不需要再进行匹配 而每一个元素不能被使用两次 所以我们只需要在 x 后面的元素中寻找 target - x 

```c
int* twoSum(int* nums, int numsSize, int target, int* returnSize) {
    for (int i = 0; i < numsSize; ++i) {
        for (int j = i + 1; j < numsSize; ++j) {
            if (nums[i] + nums[j] == target) {
                int* ret = malloc(sizeof(int) * 2);
                ret[0] = i, ret[1] = j;
                *returnSize = 2;
                return ret;
            }
        }
    }
    *returnSize = 0;
    return NULL;
}
```

`复杂度分析`

`时间复杂度：O(N^2) 其中 N 是数组中的元素数量 最坏情况下数组中任意两个数都要被匹配一次`

`空间复杂度：O(1)` 


`哈希表`

注意到方法一的时间复杂度较高的原因是寻找 target - x 的时间复杂度过高 因此 我们需要一种更优秀的方法 能够快速寻找数组中是否存在目标元素 如果存在 我们需要找出它的索引 

使用哈希表 可以将寻找 target - x 的时间复杂度降低到从 O(N) 降低到 O(1) 

这样我们创建一个哈希表 对于每一个 x 我们首先查询哈希表中是否存在 target - x 然后将 x 插入到哈希表中 即可保证不会让 x 和自己匹配 

```c
#include "uthash.h" 

struct hashTable {
    int key;
    int val;
    UT_hash_handle hh;
};

struct hashTable* hashtable;

struct hashTable* find(int ikey) {
    struct hashTable* tmp;
    HASH_FIND_INT(hashtable, &ikey, tmp);
    return tmp;
}

void insert(int ikey, int ival) {
    struct hashTable* it = find(ikey);
    if (it == NULL) {
        struct hashTable* tmp = malloc(sizeof(struct hashTable));
        tmp->key = ikey, tmp->val = ival;
        HASH_ADD_INT(hashtable, key, tmp);
    } else {
        it->val = ival;
    }
}

int* twoSum(int* nums, int numsSize, int target, int* returnSize) {
    hashtable = NULL;
    for (int i = 0; i < numsSize; i++) {
        struct hashTable* it = find(target - nums[i]);
        if (it != NULL) {
            int* ret = malloc(sizeof(int) * 2);
            ret[0] = it->val, ret[1] = i;
            *returnSize = 2;
            return ret;
        }
        insert(nums[i], i);
    }
    *returnSize = 0;
    return NULL;
}
```

复杂度分析

时间复杂度：O(N) 其中 N 是数组中的元素数量 对于每一个元素 x 我们可以 O(1) 地寻找 target - x 

空间复杂度：O(N) 其中 N 是数组中的元素数量 主要为哈希表的开销 

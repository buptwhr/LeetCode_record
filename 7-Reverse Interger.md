# 7 Reverse Interger
```C++
class Solution {
public:
    int reverse(int x) {
        long xx = x;
        bool isNeg = false;
        if(xx<0){
            isNeg = true;
            xx = -xx;
        } 
        long ret = 0;
        while(xx>0){
            ret = ret * 10 + xx%10;
            xx = xx/10;
        }
        if(isNeg)
            ret = -ret;
        if(ret>INT_MAX || ret<INT_MIN)
            return 0;
        return ret;       
    }
};
```
To consider the condition that the inversed interger is bigger than INT_MAX, which will cause overflow.

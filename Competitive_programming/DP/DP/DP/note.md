## LCS
### State Transition Equation
``` cpp
if(s1[i-1]==s2[j-1]){
    dp[i][j]=dp[i-1][j-1]+1
}
else{
    dp[i][j]=max(dp[i-1][j],dp[i][j-1])
}
```
### Find LCS string
``` cpp
string res = "";
    int i = s1.length(), j = s2.length();
    while (i > 0 && j > 0) {
        if (s1[i - 1] == s2[j - 1]) {
            res += s1[i - 1];
            i--; j--;
        } else if (dp[i - 1][j] > dp[i][j - 1]) {
            i--;
        } else {
            j--;
        }
    }
    reverse(res.begin(), res.end());
```

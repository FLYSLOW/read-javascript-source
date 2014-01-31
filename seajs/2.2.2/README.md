# Note
## Parse id to uri（also `seajs.resolve`）
1. Parse alias
2. Parse paths
3. Parse vars
4. Normalize, 移除尾部的`#`,尝试添加`.js`后缀
5. Add base
6. Parse map, like redirect
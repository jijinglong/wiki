# Git

## Revert

```
git revert HEAD                   撤销前1次, 并创建新提交
git revert HEAD^                  撤销前前2次，并创建新提交
git revert HEAD~2                 撤销倒数第3次，并创建新提交 (从0开始计数)
git revert master~5..master~2  撤销倒数第6(not included)次到第3(included)次，并创建新提交
git revert -n master~5..master~2  撤销倒数第6(not included)次到第3(included)次，但是不创建提交
git revert fa042ce57              撤销指定的版本
```
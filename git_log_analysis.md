* 參考資料
  * https://willschenk.com/howto/2020/gitlog_in_sqlite/
  * https://git-scm.com/docs/pretty-formats
* 取得格式化的資訊
```
git log --pretty=format:"|%h|%ae|%an|%aI|%s" --numstat -w --after="2023-05-18" --before="2023-05-19"
```

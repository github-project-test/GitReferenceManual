# 查看提交历史 Viewing the Commit History

## **查看提交历史**

```
Mac-Pro: jasper$ git log
```

### 常用命令参数
| Command      |    functions |
| :-------- | --------:|
| -p  | 用来显示每次提交的内容差异 |
| -number(-2)    |   最近几次提交 |
| --stat      |    每次提交的简略的统计信息 |
| --pretty=(oneline|format)      |    指定使用不同于默认格式的方式展示提交历史 |
| --since      |    按时间显示 |
|  --until      |    显示条数 |

#####**git log --pretty=format:"%h %s" --graph**
```
* 2d3acf9 ignore errors from SIGCHLD on trap
*  5e3ee11 Merge branch 'master' of git://github.com/dustin/grit
|\
| * 420eac9 Added a method for getting the current branch.
* | 30e367c timeout code and tests
* | 5a09431 add timeout protection to grit
* | e1193f8 support for heads with slashes in them
|/
* d6016bc require time for xmlschema
*  11d191e Merge branch 'defunkt' into local
```




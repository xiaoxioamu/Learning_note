### shell脚本将命令的结果赋值给变量的2种写法
1. variable=`command`
2. variable=$(command)

```bash
Line_num=$(wc -l test.txt|grep -o [0-9]*)
Line_num=`wc -l test.txt|grep -o [0-9]*`

```

### sed
删除多行
`sed -i '58;64;93d' test_file.txt`

## 提取文本信息使用的awk，grep和sed指令

~~~
awk '{print $1}' input.txt > output.txt     #提取第一列信息，并重新定向
grep -o -E 'NP_|XP_[^|]+' file.txt          #匹配NP_或XP_开头的信息，二抓一
grep -o -E 'NP_[^|]+|XP_[^|]+' file.txt     匹配NP_和XP_开头的信息，两个都抓
paste file1.txt file2.txt > merged.txt      #两个文件合并成一个
grep -o -E '\|ref\|[^|]+' file.txt          #匹配ref后面的内容
sed 's/([^)]*)//g' file.txt > newfile.txt    #s/：表示开始进行替换操作；([^)])：表示一个以左括号 "(" 开头，右括号 ")" 结尾的字符串，中间包含任意数量的非右括号字符，其中 () 表示一个分组，[^)] 表示一个否定字符组，表示匹配除右括号以外的任意字符， 表示匹配 0 或多个此类字符。//：表示将匹配到的字符串替换为空字符串，即删除。g：表示替换所有匹配到的字符串，而不是只替换第一个
sed 's/|ref|//g' file.txt > newfile.txt      #删除所有的|ref|
ssconvert input.txt output.xlsx              #将txt转换成xlsx格式
~~~

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

## 拥有9w多条ref id，如何获取蛋白质的名称
~~~
while read ref_id; do
    xml=$(curl "https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=protein&id=$ref_id&rettype=fasta&retmode=xml")  #curl命令从NCBI的Entrez数据库中获取一个蛋白质序列的FASTA格式和XML格式
    name=$(echo "$xml" | sed -n '/<GBSeq_definition>/,/<\/GBSeq_definition>/p' | sed 's/<GBSeq_definition>\(.*\)<\/GBSeq_definition>/\1/')   #在从NCBI Entrez获取到的XML格式数据中，提取出GBSeq_definition节点的文本内容，即蛋白质的名称，并将其赋值给变量name.
    echo "$name" >> protein_names.txt
done < ref_ids.txt
~~~

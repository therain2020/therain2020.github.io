
有什么用：
- 正则表达式可以校验字符串是否满足一定的规则，并用来校验数据格式的合法性。
- 在一段文本中查找满足要求的内容

是什么：
- 只匹配一个字符的时候
ps：&& 表示取交集，单个&则仅代表可以匹配这个符号 
> 字符类（只匹配一个字符）
[abc]			只能是a，b或c
[^abc]		除了a，b，c之外的任何字符
[a-zA-z]		a到z A到Z，包括（范围）
[a-d[m-p]]		a到d，或m到p
[a-z&&[def]]	a-z和def的交集，为d，e，f
[a-z&&[^bc]]	a-z和除了bc之外的任何字符的交集，等价于[ad-z]
[a-z&&[^m-p]] 	a-z和除了m-p之外的任何字符的交集，等价于[a-lq-z]]


ps：Java中 反斜杠（\）是转义字符 能够改变后面那个字符原本的含义，两个\\可以得到一个转义后的\
> 预定义字符（只匹配一个字符）
.			任何字符
\d			一个数字[0-9]
\D			非数字[^0-9]
\s			一个空白字符串[\t\n\x0B\f\r]
\S			非空白字符[^\s]
\w			（单词字符）英文、数字、下划线[a-zA-Z_0-9]
\W			一个非单词字符[^\w]
 
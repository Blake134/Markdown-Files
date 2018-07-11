---
title: 实验项目3 子实验2:生成词法分析程序(JFlex)
tags: 吴榕华,20152100094,计算机科学与技术（软件技术方向）
grammar_cjkRuby: true
---


## Oberon-0语言的词汇表

|          | INTEGER, BOOLEAN, CONST, WHILE, IF, DO, ELSEIF, THEN, ELSE, BEGIN, END              |
| -------- | ----------------------------------------------------------------------------------- |
|          | MODULE, TYPE, PROCEDURE, RECORD, ARRAY, OF, DIV, MOD, OR, VAR, READ, WRITE, WRITELN |
|          | ., +, -                                                                             |
|          | -, \*, &, =, >, >=, <=, <, #, :=                                                     |
| 结合符号 | ,, :, ;                                                                             |


|保留字  | 单目运算符 | 双目运算符|结合符号|分隔符号|
|------------- | -------------|-------------|-------------|-------------|
|MODULE|.						|	+			|[]					|,|
|BEGIN|~						| -					|()					|:|
|END|+							|*					|					|;|
|CONST|-						|DIV			|
|TYPE|								|MOD		|
|VAR|								|&				|
|PROCEDURE|					|OR			|
|RECORD|						|=			|
|ARRAY|							|>				|
|OF|							|>=					|
|WHILE|							|<=				|
|DO|								|<				|
|IF|								|#				|
|THEN|							|:=				|
|ELSEIF|
|ELSE|

上表按照其功能还有参加的运算数的个数。

## Oberon-0语言词法规则的正则定义式
Number -> (0|\[1-9])(0-9)*
Identifier -> \[a-zA-Z](\[a-zA-Z]|0-9)*
Comment -> "(\*" (\[^\*] | "\*"+\[^\)])* "\*)"
Separator -> ";"|","
Keyword -> MODULE | BEGIN | END | CONST | TYPE | VAR | PROCEDURE | RECORD | ARRAY | OF | WHILE | DO | IF | THEN | ELSEIF | ELSE
Operator -> . | + | - | * | DIV | MOD | = | # | > | >= | < | <= | ~ | OR | & | ; | : | , | :=

## 关于Oberon-0 语言与其他高级语言的词 法规 则之异同比较
### 注释
不支持嵌套注释像C++/C的/\*\*/，Oberon-0语言的就是(\*\*)。没有//那种注释单行
### 计算
仅支持整除不支持别的除法运算。像C/C++和Java里面的除法还会根据表达式一步步再区别其数据类型精度等。
### 判断和循环
用的是Then来连接,End来表示结束。而像是C/C++/Java则是，首先优先{}分隔，然后的优先级是最近优先匹配的方法来匹配。

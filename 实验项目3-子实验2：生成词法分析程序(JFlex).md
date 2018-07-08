---
title: 实验项目3 子实验2:生成词法分析程序(JFlex)
tags: 吴榕华,20152100094,计算机科学与技术（软件技术方向）
grammar_cjkRuby: true
---


## Oberon-0语言的词汇表

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
module = "MODULE" identifier ";" declarations 
identifier = 
Number = (0|\[1-9])(0-9)*
Identifier = \[a-zA-Z](\[a-zA-Z]|0-9)*
Comment = "(\*" (\[^\*] | "\*"+\[^\)])* "\*)"
Separator = ";"|","
Keyword = MODULE | BEGIN | END | CONST | TYPE | VAR | PROCEDURE | RECORD | ARRAY | OF | WHILE | DO | IF | THEN | ELSEIF | ELSE
Operator = . | + | - | * | DIV | MOD | = | # | > | >= | < | <= | ~ | OR | & | ; | : | , | :=

## 
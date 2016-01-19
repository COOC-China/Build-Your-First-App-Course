# 课后练习


{%mcq ans="o1" %}
{%title%}创建工程时的“Application Name”指的是？
{%o1%}应用程序的名字
{%o2%}包名
{%o3%}不知道
{%hint%}参考1.1第2点
{%message%}恭喜你回答正确，可以开始下一章节的学习了
{%endmcq%}

```
{% exercise %}
Define a variable `x` equal to 10.
{% initial %}
var x =
{% solution %}
var x = 10;
{% validation %}
assert(x == 10);
{% context %}
// This is context code available everywhere
// The user will be able to call magicFunc in his code
function magicFunc() {
    return 3;
}
{% endexercise %}
```
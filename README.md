# 마크다운 사용 정리

# HEADER
"#" 의 갯수에 따라 헤더가 정리됨
# h1
## h2
### h3
#### h4
##### h5
###### h6

# BlockQuote
">" 를 사용하여 블럭인용문자 사용가능
> 블록 1
> > 블록2
> > > 블록3

# 수평선
여러 가지 방법으로 작성 가능함
# <hr/>
"#" 헤더를 이용한 수평선으로 굵기 조절도 가능

<hr/>

* * *

***
***************************
- - -
-----------------------------

# 코드 블럭
(```) 을 앞뒤로 사용하여 작성 가능
```c#
public class test{
  test = new test();
}
```
`<pre><code> 코드 내용 </code></pre> 으로 사용도 가능`

<pre>
<code>
```java          
  //이렇게 "```java" 처럼 언어를 선언하여 문법강조가 가능
public class BootSpringBootApplication {
  public static void main(String[] args) {
    System.out.println("Hello, Honeymon");
  }
}
```
</code>
</pre>


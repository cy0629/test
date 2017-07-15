## scss
### scss转css的四种格式
    nested：嵌套缩进的css代码，它是默认值  
    expanded：没有缩进的、扩展的css代码  
    compact：简洁格式的css代码  
    compressed：压缩后的css代码  
### sass的使用
1.变量 sass的变量必须是$开头，后面紧跟变量名

    //  scss样式  
    $globalColor:red;
    .nav{
      color: $globalColor;
    }
    .class{
      background-color: $globalColor;
    }   
    //   css样式
    .nav{
      color: red;
    }
    .class{
      background-color: red;
    }    
    
2.变量的嵌套  
  

```
$globalColor:red;
    $border:1px soild $globalColor;
    .nav{
      color: $globalColor;
    }
    .class{
      background-color: $globalColor;
    }
```
  
3. 嵌套规则  
（1）普通嵌套 
  

```
#header{
    .nav{
      background: red;
      .logo{
        position: absolute;
      }
      a{color: red;
        &:hover{
          color: blue;
        } 
      }
    }
    p{
      color: blue;
    }
}
//scss-style

#header .nav {
  background: red;
}
#header .nav .logo {
  position: absolute;
}
#header .nav a {
  color: red;
}
#header .nav a:hover {
  color: y;
}
#header p {
  color: blue;
}
//css-style
```

（2）群组选择器

```
footer{
  h1,h2,h3{
    color: blue;
  }
}
//scss-style

footer h1, footer h2, footer h3 {
  color: blue;
}
//css-style
```
（3）属性组合

```
.nav{
  border: {
    style: solid;
    width: 1px;
    color: blue;
  }
}
//scss--style
.nav {
  border-style: solid;
  border-width: 1px;
  border-color: blue;
}
//css-style
```
4.sass的导入

```
@import "header";

.main{
  color: red;
}

@import "footer";
-----------------------------
.header{
  background-color: red;
}
.header{
  nav{
    background-color: blue;
  }
}
-----------------------------
.footer{
  background-color: blue;
}
//scss

.header {
  background-color: red;
}

.header nav {
  background-color: blue;
}

.main {
  color: red;
}

.footer {
  background-color: blue;
}
//css
```
5.默认变量值  
    
    变量值后面可以加！defult表示默认变量。
    有其他变量时则使用其他变量，没有则使用默认变量。
    
```
@import "header";
$global:red;
.header{
  background: $global;
}
--------------------
$global:yellow;

//sass

.header {
  background: yellow;
}
//css 

```
6.混合器（mixin）  

```
@mixin border-radius{
  -moz-border-radius: 3px;
  -webkit-border-radius: 2px;
  border-radius: 2px;
}
.header{
    &-nav{
      @include border-radius;
    }
  @include border-radius;
}
//scss

.header {
  -moz-border-radius: 3px;
  -webkit-border-radius: 2px;
  border-radius: 2px;
}
.header-nav {
  -moz-border-radius: 3px;
  -webkit-border-radius: 2px;
  border-radius: 2px;
}
//css
```

    混合器的传参
    

```
@mixin links-colors($normal,$hover,$visited,$active){
  color: $normal;
  &:hover{
    color: $hover;
  }
  &:visited{
    color: $visited;
  }
  &:active{
    color: $active;
  }

}
.header{
    &-nav{
      @include border-radius;
    }
  @include links-colors(red,blue,green,yellow)
}
-------------------------------

.header:hover {
  color: blue;
}
.header:visited {
  color: green;
}
.header:active {
  color: yellow;
}
```
7.继承（extend）

    继承 和混合器的不同在于：继承不能传参，且是写死的，继承下的子元素的css样式不能被继承。

```
.center{
  margin:0 auto;
  &-text{
    color: yellow;
  };
}
.main{
  color: blue;
  @extend .center;
}
//scss

.center, .main {
  margin: 0 auto;
}
.center-text {
  color: yellow;
}

.main {
  color: blue;
}
//css

由例子可以看出 main只继承了center的margin属性，下面的text属性没有被继承。
```
8.占位符（palceholder）

    占位符和继承的用法差不多，但占位符是用%开头来写，并且使用占位符来继承时，%后的在css中不会被显示出来

```
%center{
  margin:0 auto;
}
.main{
  @extend %center;
}
//scss

.main {
  margin: 0;
}
//css
```
    





# 名前空間持ってない系識別子？に名前空間を与える

## やりたいこと

<stdio.h> みたいなグローバルに直接配置する系の関数を名前空間に叩き込みたい
(まぁ<stdio.h>は<cstdio>使えばいいんだけど)

## どうやるん？

```cpp
// header.cpp
namespace givens{
#include <stdio.h>
}
```

```cpp
// user.cpp
#include "head.cpp"

int main(void){
  givens::printf("Hello World!"); // これは成功する
  printf("Hello World!"); // これはコメントアウトしないとそもそもコンパイルエラー
  return 0;
}
```

## 注意
gcc 8.1.0 (mingw) では確認したけどこれが正しい挙動なのかは知らん

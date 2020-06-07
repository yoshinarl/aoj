## 1_A
x の 3乗を返す問題

### まず標準入出力の方法がわからない
iostream を include する必要があるらしい ( [第 3 章 iostream ライブラリ \(C\+\+ ライブラリ・リファレンス\)](https://docs.oracle.com/cd/E19957-01/805-7889/6j7duaiiq/index.html) )

#### 入力

```cpp
int x;
cin >> x;
```

#### 出力

```cpp
std::cout << "Hello World";
```

なお、 `std::endl`を使うことで改行を出力できる。
また、 `<<` はつなげて書くことができるぽいので

```cpp
std::cout << "Hello World" << std::endl;
```

とすれば最後に改行できる。文字列じゃなくて変数を返すときなんかに便利そう

```cpp
// 文字列は \n でもよい
std::cout << "Hello World\n" << std::endl;

// 変数は \n よりも endl が自然？
int x = 0;
std::cout << x << std::endl;
```

### using namespace std; ってなに

解説のコードとか読んでると先頭に

```cpp
#include <iostream>
using namespace std;
```

ってのが多い。なにそれ。
namespace はそのままの意味で、名前空間を用意して名前の衝突を防ぐものらしい。
で、 `std::cin` とか `std::cout` ってのは `std` という namespace 配下にいるぽい。これを毎回 `std::` とするのは面倒なので、 `using` とすることで省略できるようになるとのこと。
プロダクトコードで書くときはめっちゃ気をつけないとヤバそうだけど、競プロだと省略できるように書くのが通例ぽいかな。

## 1_C

### 空白で文字列分割して入力ってどうやるの？

```
a と b が１つの空白で区切られて与えられます。
```

`scanf` つかうらしい

```cpp
int a, b;
scanf("%d %d", &a, &b); 
```
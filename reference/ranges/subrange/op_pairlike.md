# operator PairLike
* ranges[meta header]
* std::ranges[meta namespace]
* subrange[meta class]
* function[meta id-type]
* cpp20[meta cpp]

```cpp
template<not-same-as<subrange> PairLike>
  requires pair-like-convertible-from<PairLike, const I&, const S&>
constexpr operator PairLike() const;
```
* not-same-as[italic][link /reference/concepts/same_as.md]
* pair-like-convertible-from[italic][link ../subrange.md]

## 概要
pair-like (大きさ2のtuple-like) な型への変換演算子。

## 効果
```cpp
return PairLike(begin_, end_);
```

ただし、`begin_`、`end_`は`subrange`が内部で保持するイテレータと番兵。

## 例
```cpp example
#include <ranges>
#include <cassert>

int main()
{
  constexpr int a[] = {1, 2};
  const std::ranges::subrange sub(a);
  const std::pair<const int*, const int*> p = sub;
  assert(p.first == a);
  assert(p.second == a + 2);
}
```

### 出力
```
```

## バージョン
### 言語
- C++20

### 処理系
- [Clang](/implementation.md#clang): 13.0.0
- [GCC](/implementation.md#gcc): 10.1.0
- [ICC](/implementation.md#icc): ?
- [Visual C++](/implementation.md#visual_cpp): 2019 Update 10

## 参照
- [N4861 24 Ranges library](https://timsong-cpp.github.io/cppwp/n4861/ranges)
- [C++20 ranges](https://techbookfest.org/product/5134506308665344)

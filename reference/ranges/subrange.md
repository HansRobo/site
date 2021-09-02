# subrange
* ranges[meta header]
* std::ranges[meta namespace]
* class template[meta id-type]
* cpp20[meta cpp]

```cpp
namespace std::ranges {
  template<input_or_output_iterator I, sentinel_for<I> S = I, subrange_kind K = sized_sentinel_for<S, I> ? subrange_kind::sized : subrange_kind::unsized>
  requires (K == subrange_kind::sized || !sized_sentinel_for<S, I>)
  class subrange : public view_interface<subrange<I, S, K>> { …… };
}
```
* input_or_output_iterator[link /reference/iterator/input_or_output_iterator.md]
* sized_sentinel_for[link /reference/iterator/sized_sentinel_for.md]
* sentinel_for[link /reference/iterator/sentinel_for.md]
* subrange_kind[link subrange_kind.md]
* view_interface[link view_interface.md]

## 概要
`subrange`は、イテレータ`i`と番兵`s`が表す範囲`[i, s)`を範囲として扱うクラステンプレート。

`subrange`は[`borrowed_range`](borrowed_range.md)、[`view`](view.md)のモデルであり、また、大きさ2のtuple-likeな型である。第0要素はイテレータ、第1要素は番兵。

## テンプレートパラメータ制約
[`subrange_kind`](subrange_kind.md)` K`が`sized`である。または、イテレータ`I`と番兵`S`が[`sized_sentinel_for`](/reference/iterator/sized_sentinel_for.md)を満たさない。

## メンバ関数

| 名前                                           | 説明                             | 対応バージョン |
|------------------------------------------------|----------------------------------|----------------|
| [`(constructor)`](subrange/op_constructor.md.nolink)  | コンストラクタ                   | C++20          |
| [`operator PairLike`](subrange/op_pairlike.md.nolink) | pair-likeな型に変換する          | C++20          |
| [`begin`](subrange/begin.md.nolink)                   | 先頭を指すイテレータを取得する   | C++20          |
| [`end`](subrange/end.md.nolink)                       | 番兵を取得する                   | C++20          |
| [`empty`](subrange/empty.md.nolink)                   | 範囲が空かどうかを判定する       | C++20          |
| [`size`](subrange/size.md.nolink)                     | 要素数を取得する                 | C++20          |
| [`next`](subrange/next.md.nolink)                     | イテレータを前進させる           | C++20          |
| [`prev`](subrange/prev.md.nolink)                     | イテレータを後退させる           | C++20          |
| [`advance`](subrange/advance.md.nolink)               | 部分範囲を前進させる             | C++20          |

## 継承しているメンバ関数

| 名前                                         | 説明                             | 対応バージョン |
|----------------------------------------------|----------------------------------|----------------|
| [`operator bool`](view_interface/op_bool.md) | 範囲が空でないかどうかを判定する | C++20          |
| [`data`](view_interface/data.md)             | 配列の先頭へのポインタを取得する | C++20          |
| [`front`](view_interface/front.md)           | 先頭要素への参照を取得する       | C++20          |
| [`back`](view_interface/back.md)             | 末尾要素への参照を取得する       | C++20          |
| [`operator[]`](view_interface/op_at.md)      | 要素へアクセスする               | C++20          |

## 推論補助

| 名前                                                  | 説明                         | 対応バージョン |
|-------------------------------------------------------|------------------------------|----------------|
| [`(deduction_guide)`](subrange/op_deduction_guide.md.nolink) | クラステンプレートの推論補助 | C++20          |

## カスタマイゼーション

| 名前                                                  | 説明                         | 対応バージョン |
|-------------------------------------------------------|------------------------------|----------------|
| [`enable_borrowed_range`](subrange/enable_borrowed_range.md.nolink) | `enable_borrowed_range`の特殊化 (variable template) | C++20          |

## タプルインターフェース

| 名前                                         | 説明                               | 対応バージョン |
|----------------------------------------------|------------------------------------|----------------|
| [`tuple_size`](subrange/tuple_size.md.nolink)       | 静的な要素数取得(class template)   | C++20          |
| [`tuple_element`](subrange/tuple_element.md.nolink) | 静的な要素の型取得(class template) | C++20          |
| [`get`](subrange/get.md.nolink)                     | 要素を取得する(function template)  | C++20          |

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
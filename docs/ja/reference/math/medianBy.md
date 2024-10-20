# medianBy

`getValue` 関数を各要素に適用して、要素の配列の中央値を計算する関数です。

空の配列に対しては `NaN` を返します。
配列の要素数が奇数の場合、中央の要素を返します。
配列の要素数が偶数の場合、中央の2つの要素の平均を返します。

## インターフェース

```typescript
export function medianBy<T>(items: readonly T[], getValue: (element: T) => number): number;
```

### パラメータ

- `items` (`readonly T[]`): 中央値を計算する配列です。
- `getValue` (`(element: T) => number`): 各要素から数値を選択する関数です。

### 戻り値

(`number`): `getValue` 関数を基準に、配列にあるすべての数値の中央値を返します。

## 例

```typescript
medianBy([{ a: 1 }, { a: 2 }, { a: 3 }, { a: 4 }, { a: 5 }], x => x.a); // 3を返します。
medianBy([{ a: 1 }, { a: 2 }, { a: 3 }, { a: 4 }], x => x.a); // 2.5を返します。
medianBy([], x => x.a); // NaNを返します。
```
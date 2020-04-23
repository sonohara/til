## Golang

### slice の罠
https://qiita.com/seihmd/items/d9bc98a4f4f606ecaef7
https://play.golang.org/p/wZU-tNhRACJ

```golang
a := [3]int{1, 2, 3}
s := a[0:2] // a[0:2:3] と同じ
t := append(s, 4)
t[0] = 5
fmt.Println(a) // [5, 2, 4]
fmt.Println(s) // [5, 2]
fmt.Println(t) // [5, 2, 4]
```

- `s` では `len=2`、`cap=3` なので append すると `s[2] = 4` される
  - cap と len の差から3番目の要素が空いていると判断されるため
- slice は元配列を参照するので `a` も変更される
- よって `a = [5, 2, 4]`
- `s` は `a` の `0:2` を参照しているので `[5, 2]`
- `t` は `a` の `0:3` を参照しているので `[5, 2, 4]`
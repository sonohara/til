### イベントハンドラ
基本
- `v-click:xxx` または `@xxx` を使う

```html
<template>
    <button @click="hoge()">Hoge</button>
</template>

<script>
export default {
    methods: {
        hoge: () {
            // 
        }
    }
}
</script>
```

クリック
```html
<button @click="hoge()"></button>
``` 

ダブルクリック
```html
<button @dbclick="hoge()"></button>
``` 
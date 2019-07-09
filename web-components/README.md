## Web Components

### Web Components とは
https://developer.mozilla.org/ja/docs/Web/Web_Components

> 再利用可能なカスタム要素を作成し、ウェブアプリの中で利用するための、一連のテクノロジー

3つの主要技術から構成され、それらを組み合わせてカスタム要素を作成する
- カスタムエレメント
- Shadow DOM
- HTMLテンプレート

### カスタムエレメント
#### カスタムエレメントとは
- 独自のHTMLエレメント
- JavaScriptAPIで実装する

#### How to
js で要素を実装する
```js
export default class UserAgentElement extends HTMLElement {
  constructor() {
    super();
    // 描画ロジック等を記述する
  }
}
```
- 新しいエレメントを作る場合は `HTMLElement` を継承する
- 既存のエレメントを拡張する場合は、対応するクラスを継承する
  - e.g.
    - `<button>` の場合は `HTMLButtonElement`
    - `<img>` の場合は `HTMLImageElement`
- コンストラクタで必ず親を呼ぶ
- クラス内では `this` がカスタム要素インスタンス自身を指す
  - `this.addEventListner()` 等で参照できる

js で新しいタグを登録する
```js
import MyHoge from './my-hoge.js'
window.customElements.define('my-hoge', MyHoge)
```
- タグ名には必ず `-` を含める必要がある

使う
```html
...
<script src="./my-hoge.js" type="module"></script>
...
<my-hoge></my-hoge>
```
- 普通のタグと同じように使う


### Shadow DOM
#### Shadow DOM とは
- スコープが隔離されたDOM
- 通常のDOMに組み込まれてはいるが、そちらからは見えない（「ホストに対してローカル」）
  - なので `document.querySelectorAll` などで引っかからない
- DOMだけでなくCSSもローカルになる
- Shadow DOM で構築されたツリーを Shadowツリー、Shadowツリーが追加されている要素をShadowホストと呼ぶ

#### Shadow DOMの作成
```js
const header = document.createElement('header);
const shadoeRoot = header.attachShadow({mode: 'open'});
shadowRoot.innerHTML = '<h1>Hello Shadow DOM</h1>'
```
- `element.attachShadow()` でその要素にShadow DOMを追加できる
  - タグによっては追加できない場合もある

#### slot
> スロットはコンポーネント内にあるプレースホルダで、ユーザーはこれに独自のマークアップを入れることができます。... 基本的には、「ユーザーのマックアップをここでレンダリングしてください」と言っているのと同じです。

Shadow DOM を持つ要素はそのままだと子要素を表示しない
```html
<div id="shadow">
    Shadow   // 表示されない
</div>
<script>
    document.querySelector("#shadow").attachShadow({mode:"open"})
</script>
```

Shadow Dom 内に `<slot></slot>` 要素があると、そこに子要素が表示されるようになる（ブラウザで Shadow DOM と Light DOM が合成される）。
```html
<div id="shadow">
    Shadow   // 表示される
</div>
<script>
    const shadowRoot = document.querySelector("#shadow").attachShadow({mode:"open"});
    shadowRoot.innerHTML = `
        <slot></slot>
    `
</script>
```

slot は名前を付けると、明示的に表示するDOMを指定できる。
```html
<div id="shadow">
    <div slot="header">Header</div>
    <div slot="body">Body</div>
    <div slot="footer">Footer</div>
</div>
<script>
    const shadowRoot = document.querySelector("#shadow").attachShadow({mode:"open"});
    shadowRoot.innerHTML = `
        <slot name="header"></slot>
        <slot name="body"></slot>
        <slot name="footer"></slot>
    `
</script>
```

DOMの順番と表示順は一致している必要はない。
```html
// これでもOK
<div slot="footer">Footer</div>
<div slot="header">Header</div>
<div slot="body">Body</div>
```

紐付けは1対1じゃなくてもOK。
ただし、Shadow　DOM 側で名前がかぶっていると最初の要素しか表示されない。
```html
<div id="shadow">
    <div slot="contents">Contents1</div>
    <div slot="contents">Contents2</div>
    <div slot="contents">Contents3</div>
</div>
<script>
    const shadowRoot = document.querySelector("#shadow").attachShadow({mode:"open"});
    shadowRoot.innerHTML = `
        <slot name="contents"></slot>   // Contents1-3が表示される
        <slot name="contents"></slot>   // なにも表示されない
    `
</script>
```


#### style
TODO

## 参考
- https://tech.actindi.net/2019/06/25/093335?utm_source=feed
- https://developers.google.com/web/fundamentals/web-components/customelements?hl=ja
- https://developers.google.com/web/fundamentals/web-components/shadowdom?hl=ja
- https://speakerdeck.com/aggre/realistic-web-components
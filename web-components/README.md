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
TODO

#### style
TODO

## 参考
- https://tech.actindi.net/2019/06/25/093335?utm_source=feed
- https://developers.google.com/web/fundamentals/web-components/customelements?hl=ja
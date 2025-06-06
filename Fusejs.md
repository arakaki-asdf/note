# Fuse.js
← [@root](index.md)

- [Fuse.js](#fusejs)
  - [近似値検索](#近似値検索)


javascriptで書かれた軽量かつ柔軟なライブラリ。<br>
短時間で高度な検索機能を盛り込むことが可能。

Fuse.jsはきわめて拘束な検索を実現します。<br>
大規模なデータセットに対しても、検索は10ミリ秒未満で実行できます。


## 近似値検索
完全一致検索だけでなく、スペルミスや入力ミスが合った際も、<br>
関連するデータを見つける近似値検索を可能にします。<br>
文字の入れ替え、追加・削除があっても適切にマッチングできます。

```js
<script src="https://cdn.jsdelivr.net/npm.fuse.js/dist/fuse.js"></script>

const books = [
  {
    title: "Old Man's War",
    author: {
      firstName: 'John',
      lastName: 'Scalzi'
    }
  },
  {
    title: "The Lock Artist",
    author: {
      firstName: 'Steve',
      lastName: 'Hamilton'
    }
  }
]

const fuse = new Fuse(books, {
  keys: ['title', 'author.firstName']
})

fuse.search('jon');
```
denoでの、立ち上げ方
```
deno task dev 
```

## リポジトリでやりたいこと
- reCAPTCHAの実装(ファイルをまとめて行う)
- 購入計算ロジック・フロントとサーバーでの二重計算ロジック

##　Linter・Formatter
Biome

**参考**
[Biome](https://biomejs.dev/ja/guides/getting-started/)
Denoで行いました。パッケージマネージャは、Deno

## vueファイルのデフォルト値の設定方法
1. コマンドパレットを開く。`(Mac: Cmd + Shift + P)`
2. 「Snippets: Configure User Snippets」を選択
3. 「vue.json」を選択
4. 下記をファイル内に保存

```
{
  "Vue 3 Composition API": {
    "prefix": "vue3",
    "body": [
      "<script setup lang=\"ts\">",
      "</script>",
      "",
      "<template>",
      "  <div class=\"${7:component-name}\">",
      "    $0",
      "  </div>",
      "</template>",
      "",
      "<style scoped lang=\"css\">",
      "</style>"
    ],
    "description": "Vue 3 Composition API with TypeScript"
  }
}
```

## PRの書き方
PRのコメントの書き方

```
Closes #issue-number
```
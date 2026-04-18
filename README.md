## リポジトリでやりたいこと
- PHMの宣伝用

##　Linter・Formatter
Biome

**参考**
[Biome](https://biomejs.dev/ja/guides/getting-started/)
パッケージマネージャは、npm

**起動コマンド**
```bash
npx biome check .         # lint + format チェック
npx biome check --write . # 自動修正
npx biome format .        # フォーマットのみ
npx biome lint .          # lintのみ
```

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

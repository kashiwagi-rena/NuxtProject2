<script setup lang="ts">
</script>

<template>
  <div class="page">
    <h1>生命居住可能領域<br>(ゴルディロックスゾーン・英：ハビタブルゾーン)</h1>
    <p class="subtitle">系外惑星で生命の兆候を探すために</p>

    <section>
      <h2>ハビタブルゾーンとは</h2>
      <p>
        ハビタブルゾーン（生命居住可能領域）とは、惑星の表面に液体の水が存在できる、恒星からの距離の範囲のことです。
        生命が存在するための基本条件として広く用いられています。
      </p>
    </section>

    <section>
      <h2>従来モデルの限界</h2>
      <p>
        古典的なハビタブルゾーンは、二酸化炭素と水蒸気を主要な温室効果気体として想定しています。
        しかし、このモデルはすべての生命を保持できる惑星を網羅しているわけではなく、定義の見直しが求められていました。
      </p>
    </section>

    <section>
      <h2>新しいアプローチ</h2>
      <p>
        Ramses Ramirez博士（東京工業大学 地球生命研究所）が提唱する新モデルでは、
        二酸化炭素とメタン、または二酸化炭素と水素といった異なる大気組成を考慮しています。
        これにより、ハビタブルゾーンの外側境界をさらに拡張することが可能になります。
      </p>
    </section>

    <section>
      <h2>研究の意義</h2>
      <p>
        この研究は、現在および将来の宇宙望遠鏡を用いた系外惑星の生命探査における重要な指標となります。
        より広い範囲の惑星を生命探査の候補として考慮できるようになります。
      </p>
    </section>

    <footer>
      <p>掲載誌：Geosciences（2018年7月28日）</p>
      <a
        href="https://wpi.elsi.jp/ja-JP/news_events/highlights/2018/20180808_rramirez.html"
        target="_blank"
        rel="noopener noreferrer"
      >
        元記事を読む（東京工業大学 地球生命研究所）
      </a>
    </footer>
  </div>
</template>

<style scoped lang="css">
.page {
  min-height: 100vh;
  background: radial-gradient(ellipse at bottom, #1b2735 0%, #090a0f 100%);
  color: #e8f4fd;
  padding: 40px 24px;
  max-width: 800px;
  margin: 0 auto;
}

h1 {
  color: #fdd835;
  text-shadow: 0 0 10px rgba(253, 216, 53, 0.9), 0 0 24px rgba(253, 216, 53, 0.5);
  font-size: 2rem;
  margin-bottom: 8px;
}

.subtitle {
  color: #aad4f5;
  font-size: 1rem;
  margin-bottom: 40px;
}

section {
  margin-bottom: 32px;
}

h2 {
  color: #aad4f5;
  font-size: 1.2rem;
  margin-bottom: 10px;
  text-shadow: 0 0 8px rgba(170, 212, 245, 0.6);
}

p {
  line-height: 1.8;
  color: #cde4f5;
}

footer {
  margin-top: 48px;
  padding-top: 16px;
  border-top: 1px solid rgba(170, 212, 245, 0.2);
  font-size: 0.9rem;
  color: #aad4f5;
  display: flex;
  flex-direction: column;
  gap: 8px;
}

a {
  color: #fdd835;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}
</style>

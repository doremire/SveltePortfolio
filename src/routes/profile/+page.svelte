<script>
  import { onMount } from "svelte";
  import twemoji from "twemoji";

  onMount(() => {
    twemoji.parse(document.body, {
      className: "twemoji-icon",
    });
  });

  let projects = [
    {
      title: "cli-clock",
      description:
        "C言語で書かれたCLI上にアスキーアートでグラフィカルな時計を表示するアプリケーションです。",
      github: "https://github.com/doremire/cli-clock",
    },
    // ... 他のプロジェクトデータ
  ];

  let timelineItems = [
    { year: "2006", content: "爆誕" },
    // {
    //   year: "2018 (当時12歳)",
    //   content:
    //     "YouTubeに動画投稿を開始、同時期にグループ結成、編集を担当",
    // },
    // {
    //   year: "2019 (当時13歳)",
    //   content: "その素早い反射神経を活かした一応はプロのゲーマー",
    // },
    // { year: "2019 (当時13歳)", content: "ライブは配信者の企画をサポート" },
    // { year: "2020 (当時14歳)", content: "個人的にYouTubeに動画投稿を開始" },
    // {
    //   year: "2020 (当時14歳)",
    //   content: "ツイッターのヘッダーを専門とした画像加工を始めた、依頼形式",
    // },
    //  {
    //   year: "2021 (当時15歳)",
    //   content: "ライブは配信者にサムネイルを提供、及び専属",
    // },
    // {
    //   year: "2021 (当時15歳)",
    //   content: "iPhone OSの合法での脱獄を開始、界隈入り",
    // },
    {
      year: "2022 (当時16歳)",
      content:
        "[1月] iPadのWeb ConsoleからHTMLを入門。\n[2月] 大学生からC言語を借りる。\n[3月] 初めてノートパソコンを購入。\n[4月] 簡易掲示板の公開。\n[8月] CSR(クライアントサイドレンダリング)の3Dポートフォリオを公開|Node.js。\n[9月] ノートパソコンの修理、PHP/MySQLを使ったツイッターのクローンを公開。IDEの拡張機能を作成。\n[10月] 免許の取得。\n[11月] 国家試験 | Laravel。",
    },
    {
      year: "2023 (当時17歳)",
      content:
        "[1月] 自宅のLinux Serverを公開二代目ポートフォリオ公開に使用(現在も使用中) | 運用面でリスクヘッジが出来ない為サイバーセキュリティの道へ\n[5月] メインOSをLinuxに変えました/Vimを触り始めました",
    },
  ];

  function convertNewlinesToBreaks(text) {
    return text.replace(/\n/g, "<br>");
  }
</script>

<section class="mb-10 bg-blue-400 p-24 text-center">
  <h1 class="text-5xl text-white font-bold mb-4">Welcome to My Portfolio</h1>
  <p class="text-xl text-white">僕には似合わないポップなデザインです。</p>
</section>

<section class="text-center mb-12">
  <div
    class="rounded-full bg-slate-300 w-28 h-28 mx-auto -mt-24 p-4 mb-4 flex items-center justify-center border-8 border-gray-400"
  >
    <twemoji>
      <span class="text-white text-2xl">🐧</span>
    </twemoji>
  </div>
  <h1 class="text-4xl font-semibold mb-2">Doremire</h1>
  <p class="text-gray-600">Full Stack Developer | Server Admin</p>
</section>

<section class="bg-white p-6 mt-8">
  <div class="container mx-auto">
    <div class="grid grid-cols-3 gap-4">
      <div>
        <twemoji><h3 class="text-xl mb-2">🖌 デザイン</h3></twemoji>
        <p>ロゴの作成などにチャレンジしてみたいです。</p>
      </div>
      <div>
        <twemoji><h3 class="text-xl mb-2">🖥 開発</h3></twemoji>
        <p>作りたいものを作ります。</p>
      </div>
      <div>
        <twemoji><h3 class="text-xl mb-2">🚀 ローンチ</h3></twemoji>
        <p>人の役に立つサービスを作りたいです。</p>
      </div>
    </div>
  </div>
</section>

<section class="mb-12 grid grid-cols-1 md:grid-cols-2 gap-8">
  <div class="bg-white p-6 rounded-lg shadow-md">
    <h2 class="text-2xl font-semibold mb-4">おすすめプロジェクト</h2>
    {#each projects as project}
      <div class="mb-4">
        <h3 class="text-xl font-semibold mb-2">{project.title}</h3>
        <p class="text-gray-600">{project.description}</p>
      </div>
      <a
        href={project.github}
        class="text-blue-400 hover:text-blue-500 underline font-bold"
        target="_blank">GitHubで見る</a
      >
    {/each}
  </div>
  <div class="bg-white p-6 rounded-lg shadow-md">
    <h2 class="text-2xl font-semibold mb-4">私について</h2>
    <p class="text-gray-600">
      私は情熱的な開発者です、常に思考して日々アイディアをノートに書き留めています。私の目標は、私のレベルと理想のギャップを埋めることです。
    </p>
    <p class="text-gray-600">
      自由な時間には、新しい技術を探求したり、コミュニティの仲間と議論をして楽しんでいます。
    </p>
  </div>
</section>

<div class="p-8 md:mx-36">
  <h1 class="text-4xl text-gray-700 font-semibold mb-2">Timeline</h1>
  {#each timelineItems as item, index}
    <div class="flex items-stretch">
      <div class="flex flex-col items-center mr-10 relative -mt-4">
        <!-- 上部の線 -->
        {#if index !== 0}
          <div class="w-1 flex-grow bg-gray-300 absolute top-0 bottom-1/2" />
        {/if}
        <!-- 点 -->
        <div
          class="h-4 w-4 z-10 bg-blue-500 rounded-full absolute top-1/2 transform -translate-y-1/2"
        />
        <!-- 下部の線 -->
        {#if index !== timelineItems.length - 1}
          <div class="w-1 flex-grow bg-gray-300 absolute top-1/2 bottom-0" />
        {/if}
      </div>
      <div class="flex-grow p-4 bg-gray-100 shadow rounded-lg mb-4">
        <div class="font-bold mb-2 text-gray-400">{item.year}</div>
        <div class="text-gray-700">
          <b>{@html convertNewlinesToBreaks(item.content)}</b>
        </div>
      </div>
    </div>
  {/each}
</div>

<div class="container mx-auto p-8">
  <section
    class="bg-purple-500 text-white p-10 text-center rounded-md shadow-lg"
  >
    <h2 class="text-3xl font-bold mb-4">👀 興味を持たれた方は</h2>
    <p class="mb-6">
      🔍
      私のスキルや経験をさらに詳しく知りたい方は、スキルページやコンタクトフォームをご覧ください
      💌
    </p>
    <a href="/skills" class="bg-white text-purple-500 py-2 px-6 rounded-full"
      >🚀 スキルを見る</a
    >
  </section>
</div>

<main class="container mx-auto p-8">
  <section class="text-center">
    <h2 class="text-2xl font-semibold mb-4">お問い合わせ</h2>
    <p class="text-gray-600">お気軽にご連絡ください！</p>
    <a
      href="/contact"
      class="mt-4 inline-block bg-blue-500 text-white px-6 py-2 rounded-full hover:bg-blue-600"
      >お問い合わせする</a
    >
  </section>
</main>

<style global lang="postcss">
  @tailwind base;
  @tailwind utilities;
  /* @tailwind components; */
  :global(.twemoji-icon) {
    width: 30px;
    height: 30px;
    display: inline-block;
  }
</style>

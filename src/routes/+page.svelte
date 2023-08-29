<script>
  let portfolioHistory = [
    { year: "2020", event: "プロジェクトAの開始" },
    { year: "2021", event: "プロジェクトBの完了" },
    // ... 他のポートフォリオの歴史データ
  ];

  let mutualLinks = [
    // { title: "256さん", url: "" },
    // { title: "るみさん", url: "" },
    // { title: "ATKさん", url: "" },
    // { title: "Amex", url: "" },
    // { title: "他の人", url: "" },

    // ... 他の相互リンクデータ
  ];

  let teams = [{ name: "Yetly", role: "メンバー" }];
  let timelineItems = [
    { year: "2022", content: "ポートフォリオ制作" },
    { year: "2022", content: "デザインの改善" },
    { year: "2023", content: "サーバー構築/セルフホスト" },
    { year: "2023", content: "大幅なデザインの変更" },
    { year: "2023", content: "WEBアプリケーションの提供を開始" },
  ];
</script>

<!-- ヒーローセクション -->
<section class="bg-blue-200 p-10">
  <h2 class="text-4xl font-bold mb-4">ポートフォリオの歴史</h2>
  <div class="p-8 md:mx-36">
    {#each timelineItems as item, index}
      <div class="flex items-center">
        <div class="flex flex-col items-center mr-10 h-32 relative">
          <!-- 上部の線 -->
          {#if index !== 0}
            <div class="w-1 bg-gray-300 absolute top-0 bottom-1/2" />
          {/if}
          <!-- 点 -->
          <div
            class="h-4 w-4 z-10 bg-blue-500 rounded-full absolute top-1/2 transform -translate-y-1/2"
          />
          <!-- 下部の線 -->
          {#if index !== timelineItems.length - 1}
            <div class="w-1 bg-gray-300 absolute top-1/2 bottom-0" />
          {/if}
        </div>
        <div class="flex-grow p-4 bg-white shadow rounded-lg">
          <div class="font-bold mb-2 text-gray-400">{item.year}</div>
          <div class="text-gray-700"><b>{item.content}</b></div>
        </div>
      </div>
    {/each}
  </div>

  <!-- タイムライン -->
  <div class="p-10 text-left">
    <div class="mb-6">
      <h3 class="text-xl font-bold mb-2">2020: テキスト</h3>
      <p>最初のプロジェクト開始。</p>
    </div>
    <div class="mb-6">
      <h3 class="text-xl font-bold mb-2">2021: テキスト</h3>
      <p>他プロジェクトでの協力を開始。</p>
    </div>
    <div>
      <h3 class="text-xl font-bold mb-2">2022: テキスト</h3>
      <p>テキスト</p>
    </div>
  </div>

  <!-- 画像のスライダー -->
  <section class="p-10">
    <h1 class="text-4xl text-gray-700 font-semibold mb-2">snap shot</h1>

    <div class="flex overflow-x-scroll">
      <img
        class="w-64 h-48 mx-2 rounded-md shadow-lg"
        src="https://via.placeholder.com/256x192?text=Project+A"
        alt="Project A"
      />
      <img
        class="w-64 h-48 mx-2 rounded-md shadow-lg"
        src="https://via.placeholder.com/256x192?text=Project+B"
        alt="Project B"
      />
      <img
        class="w-64 h-48 mx-2 rounded-md shadow-lg"
        src="https://via.placeholder.com/256x192?text=Project+C"
        alt="Project C"
      />
      <img
        class="w-64 h-48 mx-2 rounded-md shadow-lg"
        src="https://via.placeholder.com/256x192?text=Project+A"
        alt="Project A"
      />
      <img
        class="w-64 h-48 mx-2 rounded-md shadow-lg"
        src="https://via.placeholder.com/256x192?text=Project+B"
        alt="Project B"
      />
      <img
        class="w-64 h-48 mx-2 rounded-md shadow-lg"
        src="https://via.placeholder.com/256x192?text=Project+C"
        alt="Project C"
      />
    </div>
  </section>
</section>

<!-- 使用技術のアイコン表示 -->
<section class="p-10 grid grid-cols-3 gap-4">
  <!-- Python -->
  <div class="flex flex-col items-center">
    <img
      src="https://cdn.simpleicons.org/python"
      alt="Python"
      width="48"
      height="48"
    />
    <p>Python</p>
  </div>

  <!-- React -->
  <div class="flex flex-col items-center">
    <img
      src="https://cdn.simpleicons.org/react"
      alt="React"
      width="48"
      height="48"
    />
    <p>React</p>
  </div>
</section>

<main class="container mx-auto p-8">
  <section class="text-center">
    <h1 class="text-4xl font-bold mb-4">👋 Welcome to My Portfolio</h1>
    <p class="text-gray-600">Passionate Developer | Tech Enthusiast</p>
  </section>

  <!-- CTA -->
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

  <section class="bg-gray-100 p-6 mt-8">
    <div class="container mx-auto">
      <h2 class="text-3xl mb-6">所属チーム・グループ</h2>
      <ul class="space-y-4">
        {#each teams as team}
          <li class="flex items-center space-x-2">
            <span class="text-purple-600">{team.name}</span>
            <span class="text-gray-600">({team.role})</span>
          </li>
        {/each}
      </ul>
    </div>
  </section>

  <section class="bg-gray-100 p-6 mt-8">
    <div class="container mx-auto">
      <h2 class="text-3xl mb-6">相互リンク</h2>
      <ul class="space-y-4">
        {#each mutualLinks as link}
          <li class="flex items-center">
            <svg
              class="w-6 h-6 text-blue-600 mr-2"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M5 13l4 4L19 7"
              />
            </svg>
            <a
              href={link.url}
              class="text-blue-600 hover:underline"
              target="_blank"
              rel="noopener noreferrer"
            >
              {link.title}
            </a>
          </li>
        {/each}
      </ul>
    </div>
  </section>
</main>

<!-- <img height="32" width="32" src="https://cdn.simpleicons.org/zenn/cbd5e1" /> -->

<style global lang="postcss">
  @tailwind base;
  @tailwind utilities;
  /* @tailwind components; */
  /* Add this to your styles (if you're not using @apply with Tailwind) */
</style>

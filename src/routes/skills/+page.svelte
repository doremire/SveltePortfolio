<script>
  let skills = [
    // 既存のスキルにカテゴリIDを追加
    {
      name: "HTML (WHATWG)",
      level: 5,
      reason:
        "WHATWG の HTML Living Standardです、W3Cから移管されてから使い始めました。僕がiPadで初めて書いたHTMLを貼っときます。中３の頃に書きました。外部のAPIを利用したメールフォームなどを設置していました。",
      categoryId: "frontend",
      github: "https://github.com/doremire/first-html",
    },
    {
      name: "CSS",
      level: 4,
      reason:
        "厳密に僕が初めて書いた言語です、最近はライブラリで済ますので直で書くことは少なくなりました。Tipsなどをあまり知らないので4で",
      categoryId: "frontend",
    },
    {
      name: "Sass",
      level: 2,
      reason:
        "CSSのプリプロセッサ（CSSメタ言語）です、あまり使いこなせてないです。最近はあまり使いません。",
      categoryId: "frontend",
    },
    {
      name: "JavaScript",
      level: 3,
      reason:
        "知れば知る程奥深い言語です、様々な歴史を持ってます。奥が深すぎて全ては使いこなせてないので3で",
      categoryId: "frontend",
    },
    {
      name: "React",
      level: 2,
      reason: "あまり自信がないです、基本的なことしかできません",
      categoryId: "frontend",
    },
    {
      name: "Svelte",
      level: 2,
      reason:
        "このページもSvelteで開発しています、とても良いライブラリです。(「コンパイラだろ」とのツッコミが来そうですが)",
      github: "https://github.com/doremire/portfolio-v3",
      categoryId: "frontend",
    },
    {
      name: "Three.js",
      level: 2,
      reason:
        "WebGLの3Dライブラリです、初めて作ったポートフォリオに採用しました。経験はありますが、3Dを扱うので数学の知識が必須です。",
      categoryId: "frontend",
    },
    {
      name: "TypeScript",
      level: 3,
      reason: "使いやすい言語です、これも3で",
      categoryId: "frontend",
    },
    {
      name: "Python",
      level: 1,
      reason: "基本的なことしかできません",
      categoryId: "backend",
    },
    {
      name: "PHP",
      level: 3,
      reason: "簡単な掲示板などを作成しました、CVEから目が離せません",
      categoryId: "backend",
    },
    {
      name: "C lang",
      level: 2,
      reason:
        "僕が初めて触った明確なプログラミング言語です。簡単なツールを作成できます。その程度",
      github: "https://github.com/doremire/cli-clock",
      categoryId: "programming",
    },
    {
      name: "MySQL",
      level: 2,
      reason: "不自由なくは使えます",
      categoryId: "database",
    },
    {
      name: "Docker",
      level: 1,
      reason: "あまり知見が無いです。",
      categoryId: "devops",
    },
    {
      name: "Red Hat Enterprise Linux",
      level: 1,
      reason:
        "Red Hatの企業用(エンタープライズ)のサーバーOSです、短期間ですが触る機会がありました。",
      categoryId: "server",
    },
    {
      name: "Ubuntu Server",
      level: 3,
      reason:
        "誰でも使えて安定な動作をするUbuntuのサーバー用のOSです、普段はCLIで使っています。不自由なく使えると言っても差し支えないでしょう。",
      categoryId: "server",
    },
    {
      name: "デザイン",
      level: 2,
      reason: "そもそもデザインセンスがあまり無い、理論でどうにかしています。",
      categoryId: "others",
    },
    {
      name: "サイバーセキュリティ",
      level: 1,
      reason: "これも奥が深いというよりは広義すぎるので、全体評価では1です。",
      categoryId: "others",
    },
    {
      name: "CTF",
      level: 1,
      reason: "弱いです",
      categoryId: "others",
    },
    {
      name: "競技プログラミング",
      level: 0,
      reason: "僕の思考力が試されています。",
      categoryId: "others",
    },
    {
      name: "Linux",
      level: 2,
      reason: "メインPCのOSです。流石にLPICとかは取れないかもしれません。",
      categoryId: "others",
    },
  ];

  let categories = [
    { id: "frontend", name: "フロントエンド" },
    { id: "backend", name: "バックエンド" },
    { id: "programming", name: "プログラミング" },
    { id: "database", name: "データベース" },
    { id: "devops", name: "DevOps/運用" },
    { id: "server", name: "Server" },
    { id: "others", name: "その他" },
  ];

  let levels = [
    {
      level: 1,
      description: "基本的な知識のみ。",
    },
    {
      level: 2,
      description: "その技術を使ったプロジェクトを作った。",
    },
    {
      level: 3,
      description: "複数プロジェクトでの経験。難問も自力で解決可能。",
    },
    {
      level: 4,
      description: "豊富な経験と深い知識。ベストプラクティスに精通。",
    },
    {
      level: 5,
      description: "複数年の経験。難問を容易に解決可能。多くの技を知っている。",
    },
  ];

  let skillsByYear = [
    {
      year: 2022,
      skills: [
        {
          name: "HTML/CSS",
          reason: "入門時代",
        },
        {
          name: "C",
          reason: "簡単なプログラムの作成",
        },
        {
          name: "JavaScript",
          reason: "小規模なアプリケーションの実装を行った。",
        },
        // ... 他のスキル
      ],
    },
    {
      year: 2023,
      skills: [
        {
          name: "Server",
          reason: "Linux Serverを構築",
        },
        // ... 他のスキル
      ],
    },
    // ... 他の年
  ];
</script>

<section class="bg-gray-900 text-gray-300 py-16">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <header class="text-center mb-16">
      <h1 class="text-5xl font-bold">技術スキル</h1>
      <p class="text-xl mt-4">私のスキルセットとそのレベルをご覧ください。</p>
      <p class="text-xl mt-4 opacity-10 font-bold">
        (嘘なく厳しく自己採点します)
      </p>
    </header>

    <div class="grid grid-cols-1 lg:grid-cols-3 gap-12">
      <aside class="lg:col-span-1 bg-gray-800 p-6 rounded-lg">
        <h2
          class="text-4xl font-semibold mb-10 text-indigo-500 border-b pb-4 mt-5"
        >
          スキルレベル説明
        </h2>
        <ul>
          {#each levels as level}
            <li class="mb-4 flex items-center">
              <span
                class="px-3 py-1 rounded-full bg-indigo-600 text-white font-bold mr-2"
                >{level.level}</span
              >
              <span>{level.description}</span>
            </li>
          {/each}
        </ul>
        <h2
          class="text-4xl font-semibold mb-10 text-indigo-500 border-b pb-4 mt-10 border-gray-500"
        />
        <ul>
          <div class="container mx-auto my-10 p-5">
            <h1 class="text-4xl font-semibold mb-5">スキルタイムライン</h1>
            <div class="relative">
              <div
                class="absolute left-1/4 top-0 h-full border-l-2 border-gray-400"
              />
              {#each skillsByYear as yearData}
                <div class="mb-8 flex items-center">
                  <div class="flex-shrink-0 w-1/4 pr-4 text-right">
                    <span class="font-bold">{yearData.year}</span>
                  </div>
                  <div class="flex-shrink-0 w-full pl-4 pr-7">
                    <ul>
                      {#each yearData.skills as skill}
                        <li class="mb-2">{skill.name} - {skill.reason}</li>
                      {/each}
                    </ul>
                  </div>
                </div>
              {/each}
            </div>
          </div>
        </ul>
      </aside>

      <div class="lg:col-span-2">
        {#each categories as category}
          <div class="mb-12 bg-gray-800 p-6 rounded-lg shadow-md">
            <h3 class="text-3xl font-semibold mb-5 text-indigo-500">
              {category.name}
            </h3>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
              {#each skills.filter((skill) => skill.categoryId === category.id) as skill}
                <div class="bg-gray-700 p-4 rounded-lg">
                  <h4 class="text-2xl font-semibold mb-2 text-indigo-400">
                    {skill.name}
                  </h4>
                  <div class="flex items-center mb-2">
                    <span class="mr-2">レベル:</span>
                    <span class="text-yellow-400 font-bold">{skill.level}</span>
                  </div>
                  <p class="text-sm mb-2">根拠: {skill.reason}</p>
                  {#if skill.github}
                    <!-- GitHubプロジェクトが存在する場合に表示 -->
                    <a
                      href={skill.github}
                      class="text-blue-400 hover:text-blue-500 underline"
                      target="_blank">GitHubで見る</a
                    >
                  {/if}
                </div>
              {/each}
            </div>
          </div>
        {/each}
      </div>
    </div>
  </div>
</section>

<style global lang="postcss">
  @tailwind base;
  @tailwind utilities;
  /* @tailwind components; */
</style>

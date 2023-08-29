<script>
  let skills = [
    // 既存のスキルにカテゴリIDを追加
    {
      name: "JavaScript",
      level: 5,
      reason: "多数のフロントエンド・バックエンドプロジェクトを実装。",
      github: "https://github.com/yourusername/js-project-example",
      categoryId: "frontend",
    },
    {
      name: "React",
      level: 4,
      reason: "小規模なアプリケーションの実装を行った。",
      github: "https://github.com/yourusername/react-project-example",
      categoryId: "frontend",
    },
    {
      name: "Node.js",
      level: 4,
      reason: "APIサーバーやツールの開発に4年間使用。",
      github: "https://github.com/yourusername/nodejs-project-example",
      categoryId: "backend",
    },
    {
      name: "Python",
      level: 3,
      reason: "データ解析やスクリプト作成に使用。2年の経験。",
      github: "https://github.com/yourusername/python-project-example",
      categoryId: "backend",
    },
    {
      name: "Vue.js",
      level: 3,
      reason: "複数の小規模から中規模のアプリケーションを作成。2年の経験。",
      github: "https://github.com/yourusername/vue-project-example",
      categoryId: "frontend",
    },
    {
      name: "Svelte",
      level: 2,
      reason: "いくつかのプロジェクトで試験的に使用。1年未満の経験。",
      github: "https://github.com/yourusername/svelte-project-example",
      categoryId: "frontend",
    },
    {
      name: "GraphQL",
      level: 3,
      reason: "API開発とクライアントの統合に使用。1.5年の経験。",
      github: "https://github.com/yourusername/graphql-project-example",
      categoryId: "backend",
    },
    {
      name: "Docker",
      level: 4,
      reason:
        "アプリケーションのコンテナ化やCI/CDのパイプラインで使用。3年の経験。",
      github: "https://github.com/yourusername/docker-project-example",
      categoryId: "devops",
    },
    {
      name: "TypeScript",
      level: 4,
      reason: "型安全を求める多数のプロジェクトで使用。3年の経験。",
      github: "https://github.com/yourusername/typescript-project-example",
      categoryId: "frontend",
    },
    {
      name: "MongoDB",
      level: 3,
      reason:
        "NoSQLデータベースとして、複数のアプリケーションで使用。2年の経験。",
      github: "https://github.com/yourusername/mongodb-project-example",
      categoryId: "database",
    },
  ];

  let categories = [
    { id: "frontend", name: "フロントエンド" },
    { id: "backend", name: "バックエンド" },
    { id: "database", name: "データベース" },
    { id: "devops", name: "DevOps/運用" },
    { id: "architecture", name: "アーキテクチャ" },
  ];

  let levels = [
    {
      level: 1,
      description: "初級: 基本的な知識のみ。プロジェクトでの使用経験なし。",
    },
    {
      level: 2,
      description:
        "中級: プロジェクトでの使用経験あり。サポートが必要な場合も。",
    },
    {
      level: 3,
      description: "上級: 複数プロジェクトでの経験。難問も自力で解決可能。",
    },
    {
      level: 4,
      description: "専門家: 豊富な経験と深い知識。ベストプラクティスに精通。",
    },
    {
      level: 5,
      description: "マスター: 複数年の経験。活発な開発。",
    },
  ];

  let skillsByYear = [
    {
      year: 2020,
      skills: [
        {
          name: "JavaScript",
          level: 5,
          reason: "多数のフロントエンド・バックエンドプロジェクトを実装。",
        },
        {
          name: "React",
          level: 4,
          reason: "小規模なアプリケーションの実装を行った。",
        },
        // ... 他のスキル
      ],
    },
    {
      year: 2020,
      skills: [
        {
          name: "JavaScript",
          level: 5,
          reason: "多数のフロントエンド・バックエンドプロジェクトを実装。",
          
        },
        // ... 他のスキル
      ],
    },
    {
      year: 2021,
      skills: [
        // ... スキルの詳細
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
                  <a
                    href={skill.github}
                    class="text-blue-400 hover:text-blue-500 underline"
                    target="_blank">GitHubで見る</a
                  >
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

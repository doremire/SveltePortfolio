<script>
  import { onMount } from "svelte";
  import twemoji from "twemoji";

  onMount(() => {
    twemoji.parse(document.body, { size: 32 });
  });

  let isMenuOpen = false;

  onMount(() => {
    // メニューが開かれたときにクリックイベントを追加
    // @ts-ignore
    document.addEventListener("click", closeMenuOnClickOutside);
  });

  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }

  /**
   * @param {{ target: { closest: (arg0: string) => any; }; }} event
   */
  function closeMenuOnClickOutside(event) {
    // メニューが開かれており、クリックがヘッダー外部で行われた場合はメニューを閉じる
    if (isMenuOpen && !event.target.closest(".menu")) {
      isMenuOpen = false;
    }
  }
</script>

<div class="container">
  <!-- 全てのページでヘッダーを表示する -->

  <header class="bg-blue-400 py-4">
    <nav class="container flex items-center justify-between mx-5">
      <div class="text-white text-lg font-semibold">My Portfolio</div>
      <div class="menu sm:hidden">
        <button
          class="text-white focus:outline-none"
          on:click={toggleMenu}
          aria-expanded={isMenuOpen}
          aria-controls="menu-list"
        >
          <span class="sr-only">メニューを開く</span>
          <svg
            class="w-6 h-6"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            />
          </svg>
        </button>
        {#if isMenuOpen}
          <ul
            id="menu-list"
            class="absolute bg-white top-10 right-0 z-10 p-4 shadow"
          >
            <li>
              <a href="/" class="text-gray-700 hover:text-pink-400 transition"
                >ホーム</a
              >
            </li>
            <li>
              <a
                href="/profile"
                class="text-gray-700 hover:text-pink-400 transition"
                >プロフィール</a
              >
            </li>
            <li>
              <a
                href="/skills"
                class="text-gray-700 hover:text-pink-400 transition">スキル</a
              >
            </li>
            <li>
              <a
                href="/contact"
                class="text-gray-700 hover:text-pink-400 transition"
                >お問い合わせ</a
              >
            </li>
          </ul>
        {/if}
      </div>
      <ul class="hidden sm:flex space-x-4">
        <li>
          <a href="/" class="text-white hover:text-pink-400 transition"
            >ホーム</a
          >
        </li>
        <li>
          <a href="/profile" class="text-white hover:text-pink-400 transition"
            >プロフィール</a
          >
        </li>
        <li>
          <a href="/skills" class="text-white hover:text-pink-400 transition"
            >スキル</a
          >
        </li>
        <li>
          <a href="/contact" class="text-white hover:text-pink-400 transition"
            >お問い合わせ</a
          >
        </li>
      </ul>
    </nav>
  </header>

  <style global lang="postcss">
    @tailwind base;
    @tailwind utilities;
  </style>

  <style lang="postcss">
    .menu {
      @apply relative;
    }
  </style>

  <!-- それぞれのページ内容をここに入れ込む -->
  <slot />

  <!-- 全てのページでfooterを表示する -->
  <div class="flex space-x-4 float-right mr-10">
    <a
      href="https://example.com/link1"
      class="flex w-20 h-20 bg-blue-200 rounded-lg"
    >
      <img
        class="m-auto"
        height="32"
        width="32"
        src="https://cdn.simpleicons.org/zenn/fff"
      />
    </a>

    <a
      href="https://example.com/link2"
      class="flex w-20 h-20 bg-blue-300 rounded-lg"
    >
      <img
        class="m-auto"
        height="32"
        width="32"
        src="https://cdn.simpleicons.org/qiita/fff"
      />
    </a>

    <a
      href="https://example.com/link3"
      class="flex w-20 h-20 bg-blue-400 rounded-lg"
    >
      <img
        class="m-auto"
        height="32"
        width="32"
        src="https://cdn.simpleicons.org/x/fff"
      />
    </a>
  </div>

  <footer class="bg-blue-400 p-6 mt-12">
    <div class="container mx-auto text-center">
      <div class="mt-4">
        <twemoji>
          <p class="text-white">連絡先: contact@doremire-server.com</p>
        </twemoji>
        <p class="text-white">&copy; 2023 by Doremire</p>
      </div>
    </div>
  </footer>
</div>

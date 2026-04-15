<script lang="ts">
  import Login from './Login.svelte';
  import Register from './Register.svelte';
  import { link } from 'svelte-spa-router';

  let menuOpen = false;
</script>

<nav
  class="bg-white py-4 font-bold lg:py-1 xl:py-2 2xl:py-3 px-4 lg:px-16 lg:mt-4 z-20 relative lg:absolute md:top-0 md:left-0 md:w-full"
>
  <div class="flex">
    <img
      class="w-12 h-12 lg:w-16 lg:h-16 absolute top-1/2 -translate-y-1/2 left-4 xl:scale-[1.3] xl:left-8 2xl:scale-[1.5]"
      src="assets/Tibi Logo_menü bal@2x.png"
      alt="Tibi logo"
    />
    <img
      class="w-12 lg:w-16 absolute top-1/2 -translate-y-1/2 left-24 xl:scale-[1.3] xl:left-32 2xl:scale-[1.5]"
      src="assets/Roshen logo_menü_bal@2x.png"
      alt="Roshen logo"
    />
  </div>
  <div class="flex justify-end items-center">
    <ul class="hidden lg:flex justify-end items-center gap-5">
      <li>
        <a href="/" use:link class="hover:underline xl:text-[1.35rem] 2xl:text-2xl"
          >NYEREMÉNYJÁTÉK</a
        >
      </li>
      <li>
        <a href="/nyertesek" use:link class="hover:underline xl:text-[1.35rem] 2xl:text-2xl"
          >NYERTESEK</a
        >
      </li>
      <li>
        <a href="/szabalyzat" use:link class="hover:underline xl:text-[1.35rem] 2xl:text-2xl"
          >SZABÁLYZAT</a
        >
      </li>
      <li>
        <a href="/faq" use:link class="hover:underline xl:text-[1.35rem] 2xl:text-2xl">FAQ</a>
      </li>
      <Register />

      <Login />
    </ul>

    <!-- Hamburger Menu -->
    <div class="lg:hidden flex items-center">
      <button
        id="menu-toggle"
        class="focus:outline-none cursor-pointer"
        aria-label="Toggle menu"
        on:click={() => (menuOpen = !menuOpen)}
      >
        <svg
          class="w-8 h-8"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h16m-7 6h7"
          ></path>
        </svg>
      </button>
    </div>
  </div>

  <!-- Mobile Menu -->
  <div id="mobile-menu" class="lg:hidden mt-2" class:hidden={!menuOpen}>
    <ul class="flex flex-col items-end gap-2">
      <li>
        <a href="/" use:link class="hover:underline">NYEREMÉNYJÁTÉK</a>
      </li>
      <li>
        <a href="/nyertesek" use:link class="hover:underline">NYERTESEK</a>
      </li>
      <li>
        <a href="/szabalyzat" use:link class="hover:underline">SZABÁLYZAT</a>
      </li>
      <li>
        <a href="/faq" use:link class="hover:underline">FAQ</a>
      </li>
      <Register />

      <Login />
    </ul>
  </div>
</nav>

<script>
  import { goto } from "$app/navigation";
  import { page as Page } from "$app/stores";
  import { createEventDispatcher, onMount } from "svelte";

  /**
   * @type {any}
   */
  export let showTopBar;
  /**
   * @type {boolean}
   */
  export let isShowMenu;

  $: container = "";
  $: button = "";

  const pages = [
    { page: "Coming Soon!", link: "/backup" },
    { page: "Coming Soon!", link: "/" },
    { page: "Coming Soon!", link: "/" },
    { page: "Coming Soon!", link: "/" },
  ];

  const action = (e) => {
    // hide sidebar if clicked outside
    if (button && button !== e.target && !button.contains(e.target))
      if (container && container !== e.target && !container.contains(e.target))
        isShowMenu = false;
  };

  onMount(() => {
    document.addEventListener("click", action, true);
    return () => document.removeEventListener("click", action, true);
  });
</script>

<section
  class="transition-all duration-500 ease-in-out {showTopBar
    ? 'translate-y-1/5'
    : '-translate-y-full'} border border-white transform drop-shadow-xl drop-shadow-[0_35px_35px_rgba(0,0,0,0.25)]  bg-[#0a192f] text-[var(--primary-green)]  flex items-start  w-screen justify-between px-8 pt-8 pb-4 fixed top-0 z-50"
>
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <div
    on:click|preventDefault={() => {
      goto("/");
    }}
    class="cursor-pointer mt-[-16px]"
  >
    <svg
      class=" h-12 w-12 text-[var(--primary-green)] hover:text-green-500"
      xmlns="http://www.w3.org/2000/svg"
      fill="none"
      viewBox="0 0 24 24"
      stroke="currentColor"
      stroke-width="2"
    >
      <path
        stroke-linecap="round"
        stroke-linejoin="round"
        d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z"
      />
    </svg>
  </div>

  <div class="hidden md:flex gap-8">
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    {#each pages as page}
      <div
        class="underline no-underline cursor-pointer"
        on:click|preventDefault={() => {
          goto(`${page.link}`);
        }}
      >
        {page.page}
      </div>
    {/each}
  </div>

  <!-- Mobile view -->
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <div
    bind:this={button}
    on:click|preventDefault={() => {
      isShowMenu = !isShowMenu;
    }}
    class="block md:hidden"
  >
    Menu
  </div>

  {#if isShowMenu}
    <div
      id="mobile-menu"
      class="transition-all duration-500 ease-in-out translate-y-[80px] z-40 bg-[#0a192f] absolute inset-0 flex flex-col w-screen"
    >
      {#each pages as page}
        <a
          bind:this={container}
          on:click|preventDefault={() => {
            isShowMenu = !isShowMenu;
          }}
          class="p-4 {$Page?.url?.pathname.includes(`${page.link}`)
            ? ' text-white'
            : 'bg-[var(--primary-green)] text-[#0a192f]'} bg-[#0a192f] hover:text-white "
          href={page.link}>{page.page}</a
        >
      {/each}
    </div>
  {/if}
</section>

<script>
  import { browser } from "$app/environment";
  import "../app.css";
  import Footer from "../components/NavBar/Footer.svelte";
  import TopBar from "../components/NavBar/TopBar.svelte";

  $: showTopBar = true;
  $: isShowMenu = false;
  $: prevScrollPos = 0;
  $: if (browser) {
    prevScrollPos = window.scrollY;
  }

  const hideTopBar = () => {
    let currentScrollPos = window.scrollY;

    prevScrollPos > currentScrollPos
      ? (showTopBar = true)
      : [isShowMenu ? (showTopBar = true) : (showTopBar = false)];
    prevScrollPos = currentScrollPos;
  };
</script>

<svelte:window on:scroll={hideTopBar} />

<div class="overflow-x-hidden">
  <TopBar bind:isShowMenu bind:showTopBar />
  <slot />
  <Footer />
</div>

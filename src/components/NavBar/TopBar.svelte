<script>
  import { goto } from "$app/navigation";
</script>

<section class="bg-[#0a192f] text-[var(--primary-green)]  flex  w-screen justify-between p-8 z-40 fixed inset-0 sticky">
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <div
    on:click|preventDefault={() => {
      goto("/");
    }}
    class="cursor-pointer w-1/4 border"
  >
    DashBoard
  </div>

  <div class="hidden md:flex gap-8">
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div
      on:click|preventDefault={() => {
        goto("/backup");
      }}
    >
      Comming Soon!
    </div>
    <div>Comming Soon!</div>
    <div>Comming Soon!</div>
    <div>Comming Soon!</div>
  </div>

  <!-- Mobile view -->
  <div class="block md:hidden">
    Menu
  </div>
</section>

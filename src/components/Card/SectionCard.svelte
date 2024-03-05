<script>
  import { goto } from "$app/navigation";

  export let clazz = "";
  export let overClass = "";
</script>

<section
  class={overClass
    ? overClass
    : `flex h-fit w-screen justify-between px-8 md:px-16 py-20 max-w-[1300px] ${clazz}`}
>
  <slot />
</section>

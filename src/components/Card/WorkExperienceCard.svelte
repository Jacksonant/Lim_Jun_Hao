<script lang="ts">
  export let payload = {
    title: "",
    companyName: "",
    companyLink: "",
    period: "",
    contents: [],
  };
</script>

<div class="border-[1px] border-[#374151] cursor-pointer rounded-md py-10 px-6">
  <h3 class="text-[var(--secondary-gray)] text-lg font-normal mb-2">
    <span>
      {payload?.title} @
      <!-- svelte-ignore a11y-invalid-attribute -->
      <a
        target="_blank"
        rel="noopener noreferrer"
        class="text-[var(--primary-green)] no-underline underline"
        href={payload.companyLink}>{payload?.companyName}</a
      >
    </span>
  </h3>

  <p class="font-light mb-4">{payload?.period}</p>

  <ul class="list-inside space-y-4">
    {#each payload?.contents as content}
      <li>
        {content}
      </li>
    {/each}
  </ul>
</div>

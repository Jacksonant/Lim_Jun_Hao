<script lang="ts">
  import { GlobeAlt, Icon } from "svelte-hero-icons";

  export let project = {
    level: "",
    name: "",
    description: "",
    technologies: [""],
    img: "",
    alt: "",
    githubLink: "",
    deployedLink: "",
  };
</script>

<div class="relative cursor-pointer rounded-md transition ease-in-out delay-150 hover:-translate-y-1 hover:scale-110 duration-300 hover:shadow-lg hover:shadow-white	">
  <div class="  py-10 px-10 md:px-12">
    <p class="highlight">{project.level} Project</p>
    <h3 class="text-xl font-semibold mb-4 text-[var(--secondary-gray)]">
      {project.name}
    </h3>
    <p class="py-5">
      {project.description}
    </p>

    <ul class="my-2 flex flex-wrap wrap text-sm font-light gap-2">
      {#each project.technologies as technology}
        <li class="list-none">{technology}</li>
      {/each}
    </ul>

    <div class="flex items-center mt-5 gap-4">
      {#if project.githubLink.length > 0}
        <a
          class="h-5 w-5 z-10  text-[var(--secondary-gray)] "
          href={project.githubLink}
          target="_blank"
          rel="noreferrer"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            role="img"
            viewBox="0 0 24 24"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
            class="w-5 h-5 hover:text-[var(--primary-green)] transition-all duration-150"
          >
            <path
              d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"
            />
          </svg>
        </a>
      {/if}

      <a
        class="h-6 w-6 z-10 flex items-center text-[var(--secondary-gray)] "
        href={project.deployedLink}
        target="_blank"
        rel="noreferrer"
      >
        <!-- <svg
          width="84"
          height="65"
          viewBox="0 0 84 65"
          fill="none"
          stroke="currentColor"
          stroke-width="6"
          stroke-linecap="round"
          stroke-linejoin="round"
          xmlns="http://www.w3.org/2000/svg"
          class="w-5 h-5 hover:text-[var(--primary-green)] transition-all duration-150"
          ><path d="M37.5274 0L75.0548 65H0L37.5274 0Z" fill="nones" /></svg
        > -->
        <Icon src={GlobeAlt} class="w-full h-full" />
      </a>
    </div>
  </div>

  <div class="absolute inset-0 opacity-10">
    <img
      class="object-cover bg-white w-full h-full"
      src={project.img}
      alt={project.alt}
    />
  </div>
</div>

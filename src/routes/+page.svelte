<script lang="ts">
  import { projects } from "../stores/projects.json";
  import { works } from "../stores/works.json";

  import { page } from "$app/stores";
  import SectionCard from "../components/Card/SectionCard.svelte";
  import WorkExperienceCard from "../components/Card/WorkExperienceCard.svelte";
  import ProjectCard from "../components/Card/ProjectCard.svelte";
  import Whatsapp from "../components/Custom/Whatsapp.svelte";

</script>

<svelte:head>
	<title>
		{`Lim Jun Hao | Dashboard`}
	</title>
</svelte:head>

<SectionCard>
  <section class="mt-20 flex flex-col h-fit w-full md:w-[60%]">
    <h4 class="text-[var(--primary-green)] mb-6 highlight">Hi, my name is</h4>
    <h2 class=" text-[var(--secondary-gray)] text-4xl font-semibold">
      Lim Jun Hao
    </h2>

    <h3 class="mt-4 text-3xl font-semibold">I love building things</h3>

    <section class=" mt-4 md:hidden block flex flex-col w-full max-w-xl h-[280px]">
      <!-- svelte-ignore a11y-img-redundant-alt -->
      <img class="h-full" src="/default-image.jpeg" alt="default-image" />
    </section>

    <p class=" mt-5 text-lg max-w-xl">
      As an engineering graduate, my heart yearns to explore fields beyond my
      own, to discover the wonders that lie beyond the horizons of my expertise.
      My thirst for knowledge, coupled with an innate passion for creating
      things, led me to the captivating world of web development, where I was
      able to unleash my coding skills and bring my visions to life.
    </p>

    <p class=" mt-5 text-lg max-w-xl">
      My journey in Web 2.0 development began when I joined Sigma School, where
      I delved into the intricacies of web development and honed my skills
      through the Fundamental courses. As I progressed, I realized that my true
      passion lies in coding, and I took on freelance projects to challenge
      myself and refine my craft.
    </p>

    <p class=" mt-5 text-lg max-w-xl">
      Now, as I stand on the precipice of my future, I am committed to becoming
      a well-rounded IT professional, one who not only possesses the technical
      knowledge and skills necessary to excel in the industry but also has the
      passion and drive to make a difference in the world. With each passing
      day, I am one step closer to achieving my dreams, and I am eager to see
      what the future holds.
    </p>

    <div class=" mt-20">
      <a
        on:click={() => {
          const contactSection = document.getElementById("contact");
          contactSection.scrollIntoView({ behavior: "smooth" });
        }}
        class="scroll-smooth border border-[var(--primary-green)] text-[var(--primary-green)] hover:text-[#0a192f] hover:bg-[var(--primary-green)] px-7 py-5 rounded-md no-underline transition-all duration-500 ease-in-out"
        href={"Javascript:void(0)"}>Contact me!</a
      >
    </div>
  </section>
  <section
    class="mt-20 hidden md:flex flex-col w-[40%] lg:w-[50%] items-end md:h-[280px] xl:h-[480px]"
  >
    <!-- svelte-ignore a11y-img-redundant-alt -->
    <img class="h-full" src="/default-image.jpeg" alt="default-image" />
  </section>
</SectionCard>

<SectionCard>
  <section class=" flex flex-col h-fit w-full md:w-[60%]">
    <h2 class="text-[var(--secondary-gray)] text-4xl font-semibold">
      Technology Stack
    </h2>

    <p class=" mt-5 text-lg max-w-xl">
      Though my knowledge in the tech stack may be scant, it doth not deter me
      from embarking on new projects and continuously learning. Furthermore, I
      am zealous to quickly acquire new skills. Below are my current
      competencies:
    </p>

    <p class=" mt-5 text-md max-w-xl">Native (Very familiar with)</p>
    <ul
      class="marker:text-[var(--primary-green)] grid grid-cols-2 gap-y-2 list-disc list-inside text-xs my-2"
    >
      <li>Javascript</li>
      <li>Typescript</li>
      <li>Sveltekit</li>
      <li>Tailwind</li>
      <li>GraphQL</li>
      <li>Retool</li>
      <li>Supabase</li>
    </ul>

    <p class=" mt-5 text-md max-w-xl">
      Intermediate (Have intermediate experience but not using on a daily basis)
    </p>
    <ul
      class="marker:text-[var(--primary-green)] grid grid-cols-2 gap-y-2 list-disc list-inside text-xs my-2"
    >
      <li>Vue js</li>
      <li>React js</li>
      <li>Bootstrap</li>
      <li>Firebase</li>
      <li>C/ C++</li>
    </ul>

    <p class=" mt-5 text-md max-w-xl">
      Honestly not good enough (Have had some experience, but currently not good
      enough)
    </p>
    <ul
      class="marker:text-[var(--primary-green)] grid grid-cols-2 gap-y-2 list-disc list-inside text-xs my-2"
    >
      <li>Postgresql</li>
      <li>GCP</li>
      <li>SST</li>
      <li>AWS</li>
      <li>Docker</li>
      <li>Kubernetes</li>
      <li>Python</li>
    </ul>
  </section>
  <section
    class=" hidden md:flex flex-col w-[40%] items-end md:h-[280px] xl:h-[480px]"
  >
    <!-- svelte-ignore a11y-img-redundant-alt -->
    <img class="h-full" src="/default-image.jpeg" alt="default-image" />
  </section>
</SectionCard>

<SectionCard>
  <section class=" flex flex-col w-full h-fit">
    <h2 class="text-[var(--secondary-gray)] text-4xl font-semibold">
      IT Work Experiences
    </h2>

    <div class=" grid grid-cols-1 md:grid-cols-2 gap-8 mt-10">
      {#each works as work}
        <WorkExperienceCard bind:payload={work} />
      {/each}
      <!-- <WorkExperienceCard {payload} /> -->
    </div>
  </section>
</SectionCard>

<SectionCard>
  <section class=" flex flex-col w-full h-fit">
    <h2 class="text-[var(--secondary-gray)] text-4xl font-semibold">
      Some Things I've Built
    </h2>

    <div class="mt-8 grid grid-cols-1 gap-8 md:grid-cols-2 lg:grid-cols-3 space-y-0">
      {#each projects as project}
        <ProjectCard bind:project />
      {/each}
    </div>
  </section>
</SectionCard>

<SectionCard clazz="hidden">
  <section class=" flex flex-col w-full h-fit">
    <h2 class="text-[var(--secondary-gray)] text-4xl font-semibold">
      IT Education
    </h2>

    <div
      class="border border-blue-300 shadow rounded-md p-4 mt-10 w-full md:w-1/2"
    >
      <div class="animate-pulse flex space-x-4">
        <div class="rounded-full bg-slate-200 h-10 w-10" />
        <div class="flex-1 space-y-6 py-1">
          <div class="h-2 bg-slate-200 rounded" />
          <div class="space-y-3">
            <div class="grid grid-cols-3 gap-4">
              <div class="h-2 bg-slate-200 rounded col-span-2" />
              <div class="h-2 bg-slate-200 rounded col-span-1" />
            </div>
            <div class="h-2 bg-slate-200 rounded" />
          </div>
        </div>
      </div>
    </div>
  </section>
</SectionCard>

<SectionCard>
  <section id="contact" class=" flex flex-col justify-center">
    <h2
      class="flex items-center text-[var(--secondary-gray)] text-2xl lg:text-4xl font-semibold"
    >
      What's Next?
    </h2>

    <div class="mt-24 flex flex-col justify-center">
      <div class="flex flex-col">
        <h3
          class="flex items-center text-[var(--secondary-gray)] text-4xl xl:text-6xl font-semibold mb-10"
        >
          Get In Touch
        </h3>
        <p class="flex items-center text-md xl:text-xl font-semibold mb-10">
          I'm always on the lookout for new opportunities or project ideas to
          collaborate on. So if you have any questions or simply want to say hi,
          please feel free to reach out to me anytime!
        </p>
      </div>

      <div class="mt-20">
        <a
          class="flex justify-center gap-4 max-w-[270px] border border-[var(--primary-green)] text-[var(--primary-green)] hover:text-[#0a192f] hover:bg-[var(--primary-green)] px-7 py-5 rounded-md no-underline transition-all duration-500 ease-in-out"
          target="_blank"
          rel="noreferrer"
          href="https://wa.me/601118589401?text=Hi,%20coming%20from%20your%20personal%20website!"
          ><svg
            class="w-6 h-6"
            fill="currentColor"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 448 512"
          >
            <path
              d="M380.9 97.1C339 55.1 283.2 32 223.9 32c-122.4 0-222 99.6-222 222 0 39.1 10.2 77.3 29.6 111L0 480l117.7-30.9c32.4 17.7 68.9 27 106.1 27h.1c122.3 0 224.1-99.6 224.1-222 0-59.3-25.2-115-67.1-157zm-157 341.6c-33.2 0-65.7-8.9-94-25.7l-6.7-4-69.8 18.3L72 359.2l-4.4-7c-18.5-29.4-28.2-63.3-28.2-98.2 0-101.7 82.8-184.5 184.6-184.5 49.3 0 95.6 19.2 130.4 54.1 34.8 34.9 56.2 81.2 56.1 130.5 0 101.8-84.9 184.6-186.6 184.6zm101.2-138.2c-5.5-2.8-32.8-16.2-37.9-18-5.1-1.9-8.8-2.8-12.5 2.8-3.7 5.6-14.3 18-17.6 21.8-3.2 3.7-6.5 4.2-12 1.4-32.6-16.3-54-29.1-75.5-66-5.7-9.8 5.7-9.1 16.3-30.3 1.8-3.7.9-6.9-.5-9.7-1.4-2.8-12.5-30.1-17.1-41.2-4.5-10.8-9.1-9.3-12.5-9.5-3.2-.2-6.9-.2-10.6-.2-3.7 0-9.7 1.4-14.8 6.9-5.1 5.6-19.4 19-19.4 46.3 0 27.3 19.9 53.7 22.6 57.4 2.8 3.7 39.1 59.7 94.8 83.8 35.2 15.2 49 16.5 66.6 13.9 10.7-1.6 32.8-13.4 37.4-26.4 4.6-13 4.6-24.1 3.2-26.4-1.3-2.5-5-3.9-10.5-6.6z"
            />
          </svg> Hello me on Whatsapp</a
        >
      </div>
    </div>
  </section>
</SectionCard>

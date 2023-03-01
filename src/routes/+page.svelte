<script lang="ts">
  import IntroCard from "../components/Card/IntroCard.svelte";
  import SectionCard from "../components/Card/SectionCard.svelte";
  import WorkExperienceCard from "../components/Card/WorkExperienceCard.svelte";

  const payload = {
    title: "Software Developer",
    companyName: "Epic Startups",
    companyLink: "https://www.epicstartups.co/",
    period: "Sept 2022 - Present",
    contents: ["Content 1", "Content 2", "Content 3"],
  };
</script>

<SectionCard>
  <section class="border flex flex-col h-fit">
    <h4 class="text-[var(--primary-green)] mb-6 highlight">Hi, my name is</h4>
    <h2 class=" text-[var(--secondary-gray)] text-4xl font-semibold">Lim Jun Hao</h2>
    <h3 class="mt-4 text-3xl font-semibold">I love building things</h3>

    <p class=" mt-5 text-lg max-w-lg">
      As an engineering graduate, my heart yearns to explore fields beyond my
      own, to discover the wonders that lie beyond the horizons of my expertise.
      My thirst for knowledge, coupled with an innate passion for creating
      things, led me to the captivating world of web development, where I was
      able to unleash my coding skills and bring my visions to life.
    </p>

    <p class=" mt-5 text-lg max-w-lg">
      My journey in Web 2.0 development began when I joined Sigma School, where
      I delved into the intricacies of web development and honed my skills
      through the Fundamental courses. As I progressed, I realized that my true
      passion lies in coding, and I took on freelance projects to challenge
      myself and refine my craft.
    </p>

    <p class=" mt-5 text-lg max-w-lg">
      Now, as I stand on the precipice of my future, I am committed to becoming
      a well-rounded IT professional, one who not only possesses the technical
      knowledge and skills necessary to excel in the industry but also has the
      passion and drive to make a difference in the world. With each passing
      day, I am one step closer to achieving my dreams, and I am eager to see
      what the future holds.
    </p>

    <div class=" mt-20">
      <a
        class="border border-[var(--primary-green)] text-[var(--primary-green)] px-7 py-5 rounded-md no-underline hover:transition-all hover:duration-150 hover:ease-in-out"
        href="/portfoliowebsite/#contact">Contact me!</a
      >
    </div>
  </section>
  <section class="border flex flex-col w-[40%] h-[480px]">
    <!-- svelte-ignore a11y-img-redundant-alt -->
    <img class="h-full" src="/default-image.jpeg" alt="default-image" />
  </section>
</SectionCard>

<SectionCard>
  <section class="border flex flex-col h-fit">
    <h2 class=" text-secondary-gray text-4xl font-semibold">
      Technology Stack
    </h2>

    <p class=" mt-5 text-lg max-w-lg">
      Though my knowledge in the tech stack may be scant, it doth not deter me
      from embarking on new projects and continuously learning. Furthermore, I
      am zealous to quickly acquire new skills. Below are my current
      competencies:
    </p>

    <p class=" mt-5 text-md max-w-lg">Native (Very familiar with)</p>
    <ul class="grid grid-cols-2 gap-y-2 list-disc list-inside text-xs my-2">
      <li>Javascript</li>
      <li>Typescript</li>
      <li>Svelte</li>
      <li>Node.js</li>
      <li>Tailwind</li>
      <li>GraphQL</li>
      <li>Retool</li>
      <li>Supabase</li>
    </ul>

    <p class=" mt-5 text-md max-w-lg">
      Intermediate (Have intermediate experience but not using on a daily basis)
    </p>
    <ul class="grid grid-cols-2 gap-y-2 list-disc list-inside text-xs my-2">
      <li>Vue js</li>
      <li>React js</li>
      <li>Bootstrap</li>
      <li>Postgresql</li>
      <li>GCP</li>
      <li>SST</li>
      <li>Figma</li>
      <li>Firebase</li>
      <li>C/ C++</li>
    </ul>

    <p class=" mt-5 text-md max-w-lg">
      Honestly not good enough (Have had some experience, but currently not good
      enough)
    </p>
    <ul class="grid grid-cols-2 gap-y-2 list-disc list-inside text-xs my-2">
      <li>AWS</li>
      <li>Docker</li>
      <li>Kubernetes</li>
      <li>Python</li>
    </ul>
  </section>
  <section class="border flex flex-col w-[40%] h-[480px]">
    <!-- svelte-ignore a11y-img-redundant-alt -->
    <img class="h-full" src="/default-image.jpeg" alt="default-image" />
  </section>
</SectionCard>

<SectionCard>
  <section class="border flex flex-col w-full h-fit">
    <h2 class="text-[var(--secondary-gray)] text-4xl font-semibold">
      IT Work Experiences
    </h2>

    <div class=" grid grid-cols-1 md:grid-cols-2 gap-8 mt-10">
      <WorkExperienceCard {payload} />
      <WorkExperienceCard {payload} />
    </div>
  </section>
</SectionCard>

<SectionCard>
  <section class="border flex flex-col w-full h-fit">
    <h2 class="text-[var(--secondary-gray)] text-4xl font-semibold">
      Some Things I've Built
    </h2>

    <div class="grid grid-cols-1 gap-8 md:grid-cols-2 lg:grid-cols-3 space-x-8">
      <div class="relative cursor-pointer rounded-md mt-10">
        <div class="py-10 px-10 md:px-12">
          <p class="highlight">Featured Project</p>
          <h3 class="text-xl font-semibold mb-4 text-[var(--secondary-gray)]">WhatsApp Sender</h3>
          <p class="py-5">
            WhatsApp messages bulk sender using Python and Selenium.
          </p>

          <ul class="flex flex-wrap wrap text-sm font-light gap-2">
            <li class="list-none">Python</li>
            <li class="list-none">Selenium</li>
            <li class="list-none">WhatsApp</li>
            <li class="list-none">Automation</li>
          </ul>

          <div class="flex items-center mt-5">
            <a
              href="https://github.com/joinsigma/portfolio-website/blob/main/styles/experience.css"
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
                <title>GitHub</title>
                <path
                  d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"
                />
              </svg>
            </a>
          </div>
        </div>

        <div class="proj__image">
          <img
            src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTITASIQstp1IZatUNyRuB3I4jAuh1dDQV0gg&usqp=CAU"
            alt="whatsapp"
          />
        </div>
      </div>

      <div class="project__card">
        <div class="proj__container">
          <p class="highlight">Featured Project</p>
          <h3 class="proj__title">WhatsApp Sender</h3>
          <p class="proj__description">
            WhatsApp messages bulk sender using Python and Selenium.
          </p>

          <ul class="proj__tech">
            <li>Python</li>
            <li>Selenium</li>
            <li>WhatsApp</li>
            <li>Automation</li>
          </ul>

          <div class="proj__links">
            <a
              href="https://github.com/joinsigma/portfolio-website/blob/main/styles/experience.css"
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
                <title>GitHub</title>
                <path
                  d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"
                />
              </svg>
            </a>
          </div>
        </div>

        <div class="proj__image">
          <img
            src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTITASIQstp1IZatUNyRuB3I4jAuh1dDQV0gg&usqp=CAU"
            alt="whatsapp"
          />
        </div>
      </div>
    </div>
  </section>
</SectionCard>

<script context="module">
  export const prerender = true;
</script>

<script lang="ts">
  import { testimonials } from "$lib/contents/home/index";
  import {
    features,
    otherFeatures,
    secondaryFeatures as cards,
  } from "$lib/contents/home/features";

  import Features from "$lib/components/features.svelte";
  import ChooseProject from "$lib/components/index/choose-project.svelte";
  import Hero from "$lib/components/index/hero.svelte";
  import SectionScreenshot from "$lib/components/index/section-ides.svelte";
  import Testimonials from "$lib/components/index/testimonials.svelte";
  import GetStarted from "$lib/components/index/get-started/index.svelte";
  import OpenGraph from "$lib/components/open-graph.svelte";
  import Section from "$lib/components/section.svelte";
  import HomepageResources from "$lib/components/homepage-resources.svelte";
  import AnimatedLogos from "$lib/components/animated-logos.svelte";
  import Titles from "$lib/components/index/titles.svelte";
  import Newsletter from "$lib/components/forms/newsletter.svelte";
  import CommunityCallout from "$lib/components/index/community-callout.svelte";
  import IntegrateDontDictate from "$lib/components/index/integrate-dont-dictate.svelte";
</script>

<OpenGraph
  data={{
    description:
      "Gitpod is a cloud development environment for teams to efficiently and securely develop software. Improve your team's developer experience by coding in a CDE.",
    title: "Gitpod: Always ready to code.",
    keywords:
      "cloud dev environment, cde, remote development, open-source, integration, coding, developer experience, automation",
  }}
/>

<svelte:head>
  <!-- Preloading the IDE screenshots so that the IDE switcher works swiftly -->
  <link rel="preload" as="image" href="/images/index/vscode-desktop.webp" />
  <link rel="preload" as="image" href="/images/index/vscode-browser.webp" />
  <link rel="preload" as="image" href="/images/index/Intellij.webp" />
  <link rel="preload" as="image" href="/images/index/goland.webp" />
  <link rel="preload" as="image" href="/images/index/pycharm.webp" />
  <link rel="preload" as="image" href="/images/index/phpstorm.webp" />
  <link rel="preload" as="image" href="/images/index/rubymine.webp" />
  <link rel="preload" as="image" href="/images/index/vim.webp" />
  <link rel="preload" as="image" href="/images/index/webstorm.webp" />
  <link rel="preload" as="image" href="/images/index/rider.webp" />
</svelte:head>

<Hero />
<AnimatedLogos />
<Titles />
<SectionScreenshot />
<ChooseProject />
<div id="choose-project-observer-target-bottom">
  <Features {features} />
</div>
<IntegrateDontDictate class="py-small" />
<Features features={otherFeatures} />
<Section>
  <HomepageResources {cards} />
</Section>
<Testimonials
  title="Trusted by the best developer teams"
  text="Gitpod empowers teams to be always ready to code."
  class="-mb-20"
  {testimonials}
/>
<CommunityCallout />
<GetStarted />
<Newsletter />

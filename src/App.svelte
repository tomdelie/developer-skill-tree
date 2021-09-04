<script lang="ts">
  import { onMount } from 'svelte';

  import Label from './components/Label.svelte';
  import SourceControl from './components/Groups/SourceControl.svelte';
  import HTML from './components/Groups/HTML.svelte';
  import CSS from './components/Groups/CSS.svelte';
  import JavaScript from './components/Groups/JavaScript.svelte';
  import PHP from './components/Groups/PHP.svelte';
  import Python from './components/Groups/Python.svelte';
  import Java from './components/Groups/Java.svelte';
  import Mobile from './components/Groups/Mobile.svelte';
  import Database from './components/Groups/Database.svelte';
  import CloudProvider from './components/Groups/CloudProvider.svelte';
  import Automation from './components/Groups/Automation.svelte';

  let outer;
  let inner;
  let centered = true;
  let lastScrollLeft;

  const handleResize = () => {
    const scrollLeftValue = (inner.offsetWidth - outer.offsetWidth)/2;
    outer.scrollLeft = scrollLeftValue;
    lastScrollLeft = scrollLeftValue;

    centered = true;
  };

  const handleScroll = (event) => {
    if (event.target.scrollLeft < lastScrollLeft - 10 || event.target.scrollLeft > lastScrollLeft + 10) {
      centered = false;
    }
  };
  
  onMount(async () => {
    window.addEventListener('resize', handleResize);
    outer.addEventListener('scroll', handleScroll);
    setTimeout(() => handleResize(), 500);
  });
</script>

<header>
  <div class="flex justify-between items-center px-4 sm:px-8 py-4 text-center border-b" style="background-color: #140E30; border-color: #251e47; box-shadow: 2px 0 10px 1px #120b32;">
    <div class="hidden sm:block"></div>
    <h1 class="text-xl font-semibold text-white uppercase">Full Stack <span class="text-yellow-400">Developer</span> Skill Tree</h1>
    <a class="ml-2" href="https://github.com/tomdelie/developer-skill-tree" target="_blank">
      <img src="/images/icons/control/github.svg" alt="GitHub" width="30" />
    </a>
  </div>
</header>
<main>
  {#if !centered}
    <button class="fixed bottom-6 right-6 z-50 white bg-white bg-white p-2 h-10 w-10 rounded-full shadow" title="Horizontally align tree" on:click={handleResize}>
      <img src="/images/icons/center_focus.svg" width="30" alt="Center focus" />
    </button>
  {/if}

  <section bind:this={outer} class="flex w-full overflow-x-scroll">
    <div bind:this={inner} class="flex flex-col items-center">
      <Label title="Full Stack" links={[false, true, false]} />
      <div class="flex items-center justify-between">
        <SourceControl name="Source Control" icon="control/control.svg" />
        <HTML name="HTML" icon="html/html.svg" links={[true, false, true, true]} />
        <CSS name="CSS" icon="css/css.svg" />
      </div>
      <Label title="" links={[true, true, true]} linkWidth="w-750" />
      <div class="flex items-center justify-between">
        <JavaScript name="JavaScript" icon="javascript/javascript.svg" links={[false, true, true, false]} linkHeight={8.5} />
        <PHP name="PHP" icon="php/php.svg" links={[false, true, true, false]} linkHeight={8.5} />
        <Python name="Python" icon="python/python.svg" links={[false, true, true, false]} linkHeight={8.5} />
        <Java name="Java" icon="java/java.svg" links={[false, true, true, false]} linkHeight={8.5} />
        <Mobile name="Mobile" icon="mobile/mobile.svg" links={[false, true, true, false]} linkHeight={8.5} />
      </div>
      <Label title="" links={[true, true, true]} linkWidth="w-750" />
      <Database name="Database" icon="database/database.svg" links={[false, false, true, false]} />
      <Label title="Deployment" links={[true, false, true]} />
      <div class="flex items-center justify-between">
        <CloudProvider name="Cloud Provider" icon="provider/provider.svg" links={[false, true, false, false]} />
        <Automation name="Automation" icon="automation/automation.svg" links={[false, true, false, false]} />
      </div>
    </div>
  </section>
</main>
<footer style="color: hsla(238, 24%, 76%, 1); background: rgb(56, 47, 102);" class="mt-16 px-8 py-12 flex flex-col md:flex-row justify-between items-center md:items-center text-sm">
  <div class="flex flex-col items-center md:items-start">
    <span>Just a quick project to learn some <a href="https://svelte.dev/" target="_blank" class="underline hover:text-yellow-400 transition duration-200">Svelte</a></span>
    <span>Made by <a href="https://tomdelie.com/" target="_blank" class="underline hover:text-yellow-400 transition duration-200">Tom Délié</a></span>
  </div>
  <div class="flex flex-col items-center md:items-start">
    <span>Color palette from <a href="https://mobalytics.gg/" target="_blank" class="underline hover:text-yellow-400 transition duration-200">mobalytics.gg</a></span>
  </div>
</footer>

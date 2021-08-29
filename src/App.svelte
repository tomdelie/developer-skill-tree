<script lang="ts">
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
</script>

<main class="absolute top-0 left-0">
  <div class="flex flex-col items-center justify-center -mb-16 mt-16">
    <h1 class="text-3xl font-semibold text-white uppercase">Full Stack <span class="text-yellow-400">Developer</span> Skill Tree</h1>
    <span class="" style="color: hsla(238, 24%, 76%, 1)">Quick project to learn <a href="https://svelte.dev/" target="_blank" class="underline hover:text-yellow-400 transition duration-200">Svelte</a></span>
  </div>
  <section class="p-16 flex flex-col items-center justify-center">
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
  </section>
</main>

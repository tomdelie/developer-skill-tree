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

<main class="flex items-center justify-center">
  <section class="p-16 flex flex-col items-center justify-center">
    <Label title="Full Stack" />
    <div class="flex items-center justify-between">
      <SourceControl name="Source Control" icon="control/control.svg" />
      <HTML name="HTML" icon="html/html.svg" />
      <CSS name="CSS" icon="css/css.svg" />
    </div>
    <div class="flex items-center justify-between">
      <JavaScript name="JavaScript" icon="javascript/javascript.svg" />
      <PHP name="PHP" icon="php/php.svg" />
      <Python name="Python" icon="python/python.svg" />
      <Java name="Java" icon="java/java.svg" />
      <Mobile name="Mobile" icon="mobile/mobile.svg" />
    </div>
    <Database name="Database" icon="database/database.svg" />
    <Label title="Deployment" />
    <div class="flex items-center justify-between">
      <CloudProvider name="Cloud Provider" icon="provider/provider.svg" />
      <Automation name="Automation" icon="automation/automation.svg" />
    </div>
  </section>
</main>

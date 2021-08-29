<script lang="ts">
  import Group from '../Group.svelte';
  import Technology from "../Technology.svelte";
  
  export let name: string = "";
  export let icon: string;
  export let links: boolean[] = [false, false, false, false];
  export let linkHeight: number = 9.37;
</script>

<Group {name} {icon} {links} {linkHeight}>
  <Technology
    moreClass="absolute"
    position="top"
    active={true}
    name="Vue.js"
    icon="javascript/vuejs.svg"
    repository="vuejs/vue"
  />

  <Technology
    moreClass="absolute"
    position="top-right"
    active={false}
    name="Angular"
    icon="javascript/angular.svg"
    repository="angular/angular"
  />

  <Technology
    moreClass="absolute"
    position="right"
    active={true}
    name="React"
    icon="javascript/react.svg"
    repository="facebook/react"
  />

  <Technology
    moreClass="absolute"
    position="bottom-right"
    active={true}
    name="Svelte"
    icon="javascript/svelte.svg"
    repository="sveltejs/svelte"
  />

  <Technology
    moreClass="absolute"
    position="bottom"
    active={true}
    name="Express"
    icon="javascript/express.svg"
    repository="expressjs/express"
  />

  <Technology
    moreClass="absolute"
    position="bottom-left"
    active={true}
    name="HAPI"
    icon="javascript/hapi.png"
    repository="hapijs/hapi"
  />

  <Technology
    moreClass="absolute"
    position="left"
    active={true}
    name="TypeScript"
    icon="javascript/typescript.svg"
    repository="microsoft/typescript"
  />

  <Technology
    moreClass="absolute"
    position="top-left"
    active={false}
    name="Strapi"
    icon="javascript/strapi.svg"
    repository="strapi/strapi"
  />
</Group>
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
    name="HTML5"
    icon="html/html5.svg"
  />
</Group>

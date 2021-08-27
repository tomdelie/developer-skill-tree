<script lang="ts">
  import Group from '../Group.svelte';
  import Technology from "../Technology.svelte";
  
  export let name: string = "";
  export let icon: string;
</script>

<Group {name} {icon}>
  <Technology
  moreClass="absolute"
  position="top"
  active={true}
  name="HTML5"
  icon="html/html5.svg"
/>
</Group>

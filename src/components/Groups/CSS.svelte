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
    name="CSS3"
    icon="css/css3.svg"
  />
  <Technology
    moreClass="absolute"
    position="top-right"
    active={true}
    name="SASS"
    icon="css/sass.svg"
    repository="sass/sass"
  />
  <Technology
    moreClass="absolute"
    position="right"
    active={true}
    name="TailwindCSS"
    icon="css/tailwindcss.svg"
    repository="tailwindlabs/tailwindcss"
  />
  <Technology
    moreClass="absolute"
    position="bottom-right"
    active={true}
    name="Materialize"
    icon="css/materialize.svg"
    repository="Dogfalo/materialize"
  />
  <Technology
    moreClass="absolute"
    position="bottom"
    active={true}
    name="Bootstrap"
    icon="css/bootstrap.svg"
    repository="twbs/bootstrap"
  />
  <Technology
    moreClass="absolute"
    position="bottom-left"
    active={false}
    name="Bulma"
    icon="css/bulma.svg"
    repository="jgthms/bulma"
  />
  <Technology
    moreClass="absolute"
    position="left"
    active={true}
    name="PostCSS"
    icon="css/postcss.svg"
    repository="postcss/postcss"
  />
  <Technology
    moreClass="absolute"
    position="top-left"
    active={false}
    name="LESS"
    icon="css/less.svg"
    repository="less/less.js"
  />
</Group>
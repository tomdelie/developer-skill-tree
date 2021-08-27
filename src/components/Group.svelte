<script lang="ts">
  export let name: string = "";
  export let icon: string;
</script>

<div class="group m-16 flex items-center justify-center relative">
  <img
    src="/images/icons/{icon}"
    alt={name}
    width="150"
    class="absolute"
    style="opacity: .05; padding: 1rem;"
  />
  <h2 class="w-32 text-center">{name.toUpperCase()}</h2>
  <slot />
</div>

<style>
  .group {
    box-shadow: 0px 2px 10px rgb(21 11 37 / 50%);
    /* color: #b3b4d0; */
    font-size: 1em;
    color: white;
    font-weight: 600;
    width: 250px;
    height: 250px;
    background-color: #2c274f;
    border-radius: 100000rem;
    border: 1px solid #382f66;
  }
</style>

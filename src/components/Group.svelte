<script lang="ts">
  export let name: string = "";
  export let icon: string;

  export let links: boolean[] = [false, false, false, false];
  export let linkHeight: number = 9.37;

  const leftLink: boolean = links[0];
  const topLink: boolean = links[1];
  const bottomLink: boolean = links[2];
  const rightLink: boolean = links[3];
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

  {#if leftLink}
    <div class="left-link absolute h-1 w-32 bg-purple-custom" />
  {/if}

  {#if topLink}
    <div
      class="top-link absolute h-32 w-1 bg-purple-custom"
      style="height: {linkHeight}rem"
    />
  {/if}

  {#if bottomLink}
    <div
      class="bottom-link absolute h-32 w-1 bg-purple-custom"
      style="height: {linkHeight}rem"
    />
  {/if}

  {#if rightLink}
    <div class="right-link absolute h-1 w-32 bg-purple-custom" />
  {/if}
</div>

<style>
  .top-link {
    top: 0;
    transform: translateY(calc(-100% - 1px));
  }

  .bottom-link {
    bottom: 0;
    transform: translateY(calc(100% + 1px));
  }

  .right-link {
    right: 0;
    transform: translateX(calc(100% + 1px));
  }

  .left-link {
    left: 0;
    transform: translateX(calc(-100% - 1px));
  }

  .group {
    box-shadow: 0px 2px 10px rgb(21 11 37 / 50%);
    color: white;
    font-weight: 600;
    width: 250px;
    height: 250px;
    background-color: #2c274f;
    border-radius: 100000rem;
    border: 1px solid #382f66;
  }
</style>

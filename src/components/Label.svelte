<script lang="ts">
  export let title: string;

  export let links: boolean[] = [false, false, false];
  export let linkWidth: string = 'w-32';

  const leftLink: boolean = links[0];
  const bottomLink: boolean = links[1];
  const rightLink: boolean = links[2];
</script>

<div class="m-16 relative {title === '' ? 'w-4 h-4 border border-purple-custom bg-purple-custom' : 'min-w-32 px-4 py-2 h-10 start font-semibold flex items-center justify-center rounded-sm'}">
  {#if title !== ''}
    <span>{ title }</span>
  {/if}

  {#if bottomLink}
    <div class="bottom-link absolute h-32 w-1 bg-purple-custom" />
  {/if}

  {#if rightLink}
    <div class="right-link absolute h-1 {linkWidth} bg-purple-custom" />
  {/if}

  {#if leftLink}
    <div class="left-link absolute h-1 {linkWidth} bg-purple-custom" />
  {/if}
</div>

<style>
  .w-750 {
    width: 750px;
  }

  .bottom-link {
    bottom: 0;
    transform: translateX(-50%) translateY(calc(100% + 1px));
    left: 50%;
  }

  .left-link {
    left: 0;
    top: 50%;
    transform: translateX(calc(-100% - 1px)) translateY(-50%);
  }

  .right-link {
    right: 0;
    top: 50%;
    transform: translateX(calc(100% + 1px)) translateY(-50%);
  }

  .start {
    box-shadow: 0px 2px 10px rgb(21 11 37 / 50%);
    color: white;
    background-color: #2c274f;
    border: 1px solid #382f66;
  }
</style>

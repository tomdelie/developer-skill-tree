<script lang="ts">
  import { onMount } from 'svelte';
  import tippy from 'tippy.js';

  export let active: boolean = false;
  export let name: string;
  export let moreClass: string;
  export let icon: string;

  export let top: number | undefined = undefined;
  export let left: number | undefined = undefined;
  export let right: number | undefined = undefined;
  export let bottom: number | undefined = undefined;

  let styleTop = `top: ${top}px;`;
  let styleLeft = `left: ${left}px;`;
  let styleRight = `right: ${right}px;`;
  let styleBottom = `bottom: ${bottom}px;`;

  let tippyTrigger;

  onMount(() => {
    tippy(tippyTrigger, {
      allowHTML: true,
      theme: 'custom-dark',
      arrow: true,
      content: `
        <div>
          <div class="flex items-center mb-2">
            <img src="/images/icons/${icon}" class="filter drop-shadow" width="36" alt="${name}" />
            <h1 class="text-lg ml-4 uppercase" style="color: #bd9e59;">${name}</h1>
          </div>
          <span class="text-gray-300">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</span>
        </div>`,
      trigger: 'click',
    });
  });
</script>

<div bind:this="{tippyTrigger}" class="{moreClass} circle-container flex items-center justify-center"
  style="
    { top ? styleTop : "" }
    { left ? styleLeft : "" }
    { right ? styleRight : "" }
    { bottom ? styleBottom : "" }
  "
>
  <div class="circle filter drop-shadow-xl shadow-md flex items-center justify-center {active ? 'circle-active' : ''}">
    <img src="/images/icons/{icon}" class="filter drop-shadow" width="20" alt="{name}" />
  </div>
</div>

<style>
  .top {
    position: absolute;
    top: 0.25rem;
    transform: translateX(-50%);
    left: 50%;
  }

  .bottom {
    position: absolute;
    bottom: 0.25rem;
    transform: translateX(-50%);
    left: 50%;
  }

  .top-left {
    position: absolute;
    margin-top: calc(32px/2 + 0.5rem);
    margin-left: calc(32px/2 + 0.5rem);
  }

  .left {
    position: absolute;
    left: 0.25rem;
    top: 50%;
    transform: translateY(-50%);
  }

  .bottom-left {
    position: absolute;
    left: 0rem;
    bottom: 0rem;
    margin-bottom: calc(32px/2 + 0.5rem);
    margin-left: calc(32px/2 + 0.5rem);
  }

  .top-right {
    margin-top: calc(32px/2 + 0.5rem);
    margin-left: calc(-32px/2 - 0.5rem);
    position: absolute;
    right: 0rem;
    top: 0rem;
  }

  .right {
    position: absolute;
    right: 0.25rem;
    top: 50%;
    transform: translateY(-50%);
  }

  .bottom-right {
    margin-bottom: calc(32px/2 + 0.5rem);
    margin-left: calc(-32px/2 - 0.5rem);
    position: absolute;
    right: 0rem;
    bottom: 0rem;
  }

  .circle-container {
    width: 60px;
    height: 60px;
    border-radius: 999rem;
    border: 2px solid transparent;
    transition: 0.2s all ease;
  }

  .circle-active {
    border: 4px solid rgba(242, 191, 67, 1) !important;
  }

  .circle {
    color: black;
    border: 4px solid #b3b4d0;
    border-radius: 999rem;
    width: 44px;
    height: 44px;
    transition: 0.5s all ease;
  }

  .circle-container:hover {
    border: 2px solid rgba(242, 191, 67, 0.7);
    transition: 0.5s all ease;
    cursor: pointer;
  }

  .circle-container:hover .circle {
    border: 4px solid rgba(242, 191, 67, 1);
    transition: 0.5s all ease;
  }

  .circle > div {
    border: 1px solid rgba(0, 0, 0, 1);
    height: 100%;
    width: 100%;
    border-radius: 999rem;
  }
</style>
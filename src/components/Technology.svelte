<script lang="ts">
  import { onMount } from "svelte";
  import tippy from "tippy.js";

  const TECH_BORDER = 2;
  const TECH_RADIUS = 30;
  const RADIUS: number = 125;
  const offset: number = RADIUS - (TECH_RADIUS + TECH_BORDER / 2);
  const X_PI4: number = offset + RADIUS * Math.cos(Math.PI / 4);
  const Y_PI4: number = offset - RADIUS * Math.sin(Math.PI / 4);
  const X_3PI4: number = offset + RADIUS * Math.cos((3 * Math.PI) / 4);
  const Y_3PI4: number = offset - RADIUS * Math.sin((3 * Math.PI) / 4);

  export let name: string;
  export let moreClass: string;
  export let icon: string;
  export let position: string;
  export let active: boolean = false;
  export let repository: string | undefined = undefined;
  const user = repository ? repository.split("/")[0] : undefined;
  const repo = repository ? repository.split("/")[1] : undefined;
  export let top: number | undefined = undefined;
  export let left: number | undefined = undefined;
  export let right: number | undefined = undefined;
  export let bottom: number | undefined = undefined;

  if (position === "top-left") {
    top = Y_3PI4;
    left = X_3PI4;
  }

  if (position === "top-right") {
    top = Y_PI4;
    left = X_PI4;
  }

  if (position === "bottom-left") {
    bottom = Y_3PI4;
    left = X_3PI4;
  }

  if (position === "bottom-right") {
    left = X_PI4;
    bottom = Y_PI4;
  }

  let styleTop = `top: ${top}px;`;
  let styleLeft = `left: ${left}px;`;
  let styleRight = `right: ${right}px;`;
  let styleBottom = `bottom: ${bottom}px;`;

  let tippyTrigger;

  onMount(() => {
    tippy(tippyTrigger, {
      allowHTML: true,
      theme: "custom-dark",
      interactive: true,
      arrow: false,
      appendTo: document.body,
      content: `
        <div class="flex items-center">
          <div class="flex items-center">
            <img src="/images/icons/${icon}" class="filter drop-shadow" width="24" alt="${name}" />
            <h1 class="ml-4 text-white font-semibold uppercase">${name}</h1>
          </div>
          ${
            user && repo
              ? `<iframe class="ml-10" src="https://ghbtns.com/github-btn.html?user=${user}&repo=${repo}&type=star&count=true" frameborder="0" scrolling="0" width="110" height="20" title="GitHub"></iframe>`
              : ""
          }
        </div>`,
    });
  });
</script>

<div
  bind:this={tippyTrigger}
  class="{moreClass} {position} circle-container flex items-center justify-center"
  style="
    {top ? styleTop : ''}
    {left ? styleLeft : ''}
    {right ? styleRight : ''}
    {bottom ? styleBottom : ''}
  "
>
  <div
    class="circle filter drop-shadow-xl shadow-md flex items-center justify-center {active
      ? 'circle-active'
      : ''}"
  >
    <img
      src="/images/icons/{icon}"
      class="filter drop-shadow"
      width="20"
      alt={name}
    />
  </div>
</div>

<style>
  :global(.top) {
    position: absolute;
    top: 0.25rem;
    transform: translateX(-50%);
    left: 50%;
  }

  :global(.bottom) {
    position: absolute;
    bottom: 0.25rem;
    transform: translateX(-50%);
    left: 50%;
  }

  :global(.top-left) {
    position: absolute;
    margin-top: calc(32px / 2 + 0.5rem);
    margin-left: calc(32px / 2 + 0.5rem);
  }

  :global(.left) {
    position: absolute;
    left: 0.25rem;
    top: 50%;
    transform: translateY(-50%);
  }

  :global(.bottom-left) {
    position: absolute;
    left: 0rem;
    bottom: 0rem;
    margin-bottom: calc(32px / 2 + 0.5rem);
    margin-left: calc(32px / 2 + 0.5rem);
  }

  :global(.top-right) {
    margin-top: calc(32px / 2 + 0.5rem);
    margin-left: calc(-32px / 2 - 0.5rem);
    position: absolute;
    right: 0rem;
    top: 0rem;
  }

  :global(.right) {
    position: absolute;
    right: 0.25rem;
    top: 50%;
    transform: translateY(-50%);
  }

  :global(.bottom-right) {
    margin-bottom: calc(32px / 2 + 0.5rem);
    margin-left: calc(-32px / 2 - 0.5rem);
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

<script lang="ts">
  import Technology from "./Technology.svelte";
  export let name: string = "";
  export let icon: string;

  const techBorder = 2;
  const techRadius = 30;

  export let radius: number = 125;
  const offset: number = radius - (techRadius + techBorder / 2);


  export let x_PI4: number = offset + radius * Math.cos(Math.PI / 4);
  export let y_PI4: number = offset - radius * Math.sin(Math.PI / 4);

  export let x_3PI4: number = offset + radius * Math.cos((3 * Math.PI) / 4);
  export let y_3PI4: number = offset - radius * Math.sin((3 * Math.PI) / 4);
</script>

<div class="group flex items-center justify-center relative">
  <img
    src="/images/icons/{icon}"
    alt={name}
    class="absolute"
    style="opacity: .05; padding: 1rem;"
  />
  <span>{name.toUpperCase()}</span>

  <Technology
    moreClass="absolute top"
    active={false}
    name="falcon"
    icon="falcon.svg"
  />

  <Technology
    moreClass="absolute bottom"
    active={false}
    name="tornado"
    icon="tornado.png"
  />

  <Technology
    moreClass="absolute top-left"
    active={false}
    name="aiohttp"
    icon="aiohttp.svg"
    top={y_3PI4}
    left={x_3PI4}
  />

  <Technology
    moreClass="absolute left"
    active={false}
    name="fastapi"
    icon="fastapi.svg"
  />

  <Technology
    moreClass="absolute bottom-left"
    active={false}
    name="bottle"
    icon="bottle-x100.png"
    bottom={y_3PI4}
    left={x_3PI4}
  />

  <Technology
    moreClass="absolute top-right"
    active={false}
    name="flask"
    icon="flask.svg"
    top={y_PI4}
    left={x_PI4}
  />

  <Technology
    moreClass="absolute right"
    active={true}
    name="django"
    icon="django.svg"
  />

  <Technology
    moreClass="absolute bottom-right"
    active={false}
    name="dash"
    icon="dash.svg"
    left={x_PI4}
    bottom={y_PI4}
  />
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

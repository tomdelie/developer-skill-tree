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
    active={false}
    name="falcon"
    icon="python/falcon.svg"
    repository="falconry/falcon"
  />

  <Technology
    moreClass="absolute"
    position="bottom"
    active={false}
    name="tornado"
    icon="python/tornado.png"
    repository="tornadoweb/tornado"
  />

  <Technology
    moreClass="absolute"
    position="top-left"
    active={false}
    name="aiohttp"
    icon="python/aiohttp.svg"
    repository="aio-libs/aiohttp"
  />

  <Technology
    moreClass="absolute"
    position="left"
    active={false}
    name="fastapi"
    icon="python/fastapi.svg"
    repository="tiangolo/fastapi"
  />

  <Technology
    moreClass="absolute"
    position="bottom-left"
    active={false}
    name="bottle"
    icon="python/bottle-x100.png"
    repository="bottlepy/bottle"
  />

  <Technology
    moreClass="absolute"
    position="top-right"
    active={false}
    name="flask"
    icon="python/flask.svg"
    repository="pallets/flask"
  />

  <Technology
    moreClass="absolute"
    position="right"
    active={true}
    name="django"
    icon="python/django.svg"
    repository="django/django"
  />

  <Technology
    moreClass="absolute"
    position="bottom-right"
    active={false}
    name="dash"
    icon="python/dash.svg"
    repository="plotly/dash"
  />
</Group>

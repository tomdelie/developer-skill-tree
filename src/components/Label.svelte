<script lang="ts">
  export let title: string;
</script>

<div class="m-16 min-w-32 px-4 py-2 h-10 start font-semibold flex items-center justify-center relative rounded-sm">
  <span>{ title }</span>
</div>

<style >
  .start {
    box-shadow: 0px 2px 10px rgb(21 11 37 / 50%);
    color: white;
    background-color: #2c274f;
    border: 1px solid #382f66;
  }
</style>

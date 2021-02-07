<script>
  export let haserror = false;
  export let txt = ""
</script>

<style type="text/scss">
  .Alert {
    color: white;
    padding: 20px;
    display: none;
  }
  .haserror {
    display: block;
    background-color: red;
  }
</style>

<div class="Alert" class:haserror={!haserror}>
  <slot />
</div>

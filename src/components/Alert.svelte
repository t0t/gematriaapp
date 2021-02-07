<script>
  export let haserror = false
  console.log(`haserror es: ${haserror}`)
</script>

<style type="text/scss">
  .Alert {
    color: white;
    background-color: red;
    padding: 20px;
    display: none;
  }
  .haserror {
      display: block;
  }
</style>

<div class="Alert" class:haserror={haserror}>
  <slot />
</div>

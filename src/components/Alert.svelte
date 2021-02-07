<script>
  export let haserror = false
</script>

<style type="text/scss">
  .Alert {
    color: var(--black);
    padding: 20px;
    display: none;
    /* transition: all 1s linear; */
    position: relative;
  }
  .haserror {
    display: block;
    background-color: var(--destacado_light);
    animation-name: show_error;
    animation-duration: .3s;
    animation-fill-mode: backwards;
    animation-iteration-count: 1;
  }

  @keyframes show_error {
    0% {
      transform: translateY(0px);
      opacity: 0;
    }
    50% {
      transform: translateY(10px);
      opacity: 1;
    }
  }
</style>

<div class="Alert" class:haserror={!haserror}>
  <slot />
</div>

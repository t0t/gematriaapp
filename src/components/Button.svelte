<script>
  export let variante = 'primary';
  export let bordered = false;
</script>

<style type="text/scss">
  button {
    font-size: 2em;
    padding: var(--basepadding);
    background-color: var(--black);
    color: var(--secondary);
  }
  button:hover {
    cursor: pointer;
    background-color: var(--secondary);
    color: var(--black);
  }
  .primary {
    color: var(--black);
    border-top-right-radius: var(--basepadding);
    border-bottom-right-radius: var(--basepadding);
    background-color: var(--white);
  }
  .secondary {
    color: var(--white);
    background-color: var(--black);
  }
  .bordered {
    border: none;
  }
</style>

<button class={variante} class:bordered={bordered}>
  <slot />
</button>

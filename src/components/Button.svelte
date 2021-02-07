<script>
  export let variante = 'primary';
  export let bordered = false;
</script>

<style type="text/scss">
  button {
    font-size: 1.5em;
    padding: var(--basepadding);
    border: none;
    margin-left: -3px;
  }
  button:hover {
    cursor: pointer;
    background-color: var(--secondary);
    color: var(--black);
  }
  .primary {
    border-top-right-radius: var(--basepadding);
    border-bottom-right-radius: var(--basepadding);
    background-color: var(--black);
    color: var(--secondary);
  }
  .secondary {
    color: var(--white);
    background-color: var(--black);
  }
  .bordered {
    border: 1px solid black;
  }
</style>

<button class={variante} class:bordered={bordered}>
  <slot />
</button>

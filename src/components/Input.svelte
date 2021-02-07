<script>
export let value = "";
export let placeholder = "Introduce texto";
const onInput = e => (value = e.target.value);
</script>

<style type="text/scss">
  input {
    font-size: 2em;
    padding: var(--basepadding);
    border: none;
  }
  input {
    border-top-left-radius: var(--basepadding);
    border-bottom-left-radius: var(--basepadding);
  }
</style>

<input 
{value}
{placeholder}
type="" 
name="" 
on:input={onInput}
/>
<script>
  export let value = ''
  export let placeholder = 'p.e.: "בראשית"'
  const onInput = (e) => (value = e.target.value)
</script>

<style type="text/scss">
  *:focus {
    outline: none;
  }
  input {
    font-size: 2em;
    padding: var(--basepadding);
    border: none;
    transition: ease-in-out 5s ease-in-out;
    &:focus-within {
      background-color: var(--secondary);
      color: var(--black);
      &::placeholder {
        color: transparent;
      }
    }
    /* &::placeholder {
        color: blue;
    } */
  }
  input {
    border-top-left-radius: var(--basepadding);
    border-bottom-left-radius: var(--basepadding);
  }
</style>

<input {value} {placeholder} type="" name="" on:input={onInput} />

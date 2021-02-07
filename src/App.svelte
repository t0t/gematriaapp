<script>
  import Button from './components/Button.svelte'
  import Input from './components/Input.svelte';
  import Alert from './components/Alert.svelte';

  let gematria = new Map([
    ['\u05D0', 1], //'alef', '‎א'
    ['\u05D1', 2], //'bet', 'ב‎'
    ['\u05D2', 3], //'guimel', 'ג‎'
    ['\u05D3', 4], //'dalet', 'ד‎'
    ['\u05D4', 5], //'he', 'ה‎'
    ['\u05D5', 6], //'vav', 'ו‎'
    ['\u05D6', 7], //'tzain', 'ז‎'
    ['\u05D7', 8], //'jet', 'ח‎'
    ['\u05D8', 9], //'tet', 'ט‎'
    ['\u05D9', 10], //'yod', 'י‎'
    ['\u05DB', 20], //'kaf', 'כ'
    ['\u05DC', 30], //'lamed', 'ל‎'
    ['\u05DE', 40], //'mem', 'מ'
    ['\u05DF', 50], //'nun', 'נ'
    ['\u05E1', 60], //'samej', 'ס‎'
    ['\u05E2', 70], //'ayin', 'ע‎'
    ['\u05E4', 80], //'pe', 'פ'
    ['\u05E6', 90], //'tzadic', 'צ'
    ['\u05E7', 100], //'kof', 'ק‎'
    ['\u05E8', 200], //'resh', 'ר‎'
    ['\u05E9', 300], //'shin', 'ש‎'
    ['\u05EA', 400], //'tav', 'ת‎'
    ['\u05DA', 500], //'kaf_sofit', 'ך‎'
    ['\u05DD', 600], //'mem_sofit', 'ם‎'
    ['\u05DF', 700], //'nun_sofit', 'ן‎'
    ['\u05E3', 800], //'pe_sofit', 'ף‎'
    ['\u05E5', 900], //'tzadi_sofit', 'ץ‎'
  ])
  let valorinput = "";
  let haserror = false;
  let errormessage = ""
  let counter = 0
  let arrayASumar = []
  let splited = []

  function handleSubmit() {
    counter = 0;
    valorinput = valorinput;
    splited = valorinput.split('');
    errormessage = ""
    for (const s of splited) {
      if (s == '\u05D0') {
        counter += 1
      } else if (s == '\u05D1') {
        counter += 2
      } else if (s == '\u05D2') {
        counter += 3
      } else if (s == '\u05D3') {
        counter += 4
      } else if (s == '\u05D4') {
        counter += 5
      } else if (s == '\u05D5') {
        counter += 6
      } else if (s == '\u05D6') {
        counter += 7
      } else if (s == '\u05D7') {
        counter += 8
      } else if (s == '\u05D8') {
        counter += 9
      } else if (s == '\u05D9') {
        counter += 10
      } else if (s == '\u05DB') {
        counter += 20
      } else if (s == '\u05DC') {
        counter += 30
      } else if (s == '\u05DE') {
        counter += 40
      } else if (s == '\u05DF') {
        counter += 50
      } else if (s == '\u05E1') {
        counter += 60
      } else if (s == '\u05E2') {
        counter += 70
      } else if (s == '\u05E4') {
        counter += 80
      } else if (s == '\u05E6') {
        counter += 90
      } else if (s == '\u05E7') {
        counter += 100
      } else if (s == '\u05E8') {
        counter += 200
      } else if (s == '\u05E9') {
        counter += 300
      } else if (s == '\u05EA') {
        counter += 400
      } else if (s == '\u05DA') {
        counter += 500
      } else if (s == '\u05DD') {
        counter += 600
      } else if (s == '\u05DF') {
        counter += 700
      } else if (s == '\u05E3') {
        counter += 800
      } else if (s == '\u05E5') {
        counter += 900
      } else {
        haserror = true
        if (haserror = true) {
          errormessage= "Revisa tu texto. Recuerda que sólo admite carácteres hebreos"
        } else {
          haserror = false
          errormessage = ""
        }
      }
    }
    
    return counter;
  };
</script>

<style type="text/scss">
  $color: #04ff00;
  $font_size: 2em;
  $base_size: 2em;

  h1 {
    font-size: $font_size;
    padding: var(--basepadding);
  }
  h2 {
    line-height: normal;
    font-size: $font_size * 4;
    font-weight: bold;
    padding-bottom: var(--basepadding);
  }
  small {
    color: var(--white);
    display: block;
    font-size: 1em;
    margin: var(--basepadding);
    /* color: var(--white); */
  }
  :global(html) {
    background-color: var(--primary);
    /* height: 100vh; */
    font-size: 15px;
  }
  main {
    line-height: 1.5;
    display: grid;
    grid-template-columns: 1fr;
    align-items: center;
    text-align: center;
    color: $color;
    font-family: 'Montserrat', sans-serif;
  }
  .formulario {
    margin-right: $base_size;
    margin-bottom: $base_size;
    margin-left: $base_size;
  }
  form {
    display: grid;
    /* grid-template-columns: 1fr 1fr; */
    grid-template-rows: 1fr 1fr;
    grid-template-areas: 
    "i b"
    "l l"
    ;
    input { grid-area: "i"; border: 1px solid red;}
    button { grid-area: "b";}
    label { grid-area: "l"; grid-column: 1 / -1; margin-top: $base_size;}
  }

  a {
    text-decoration: none;
    color: var(--secondary);
  }
  h3 {
    color: var(--secondary);
    font-size: 1.5em;
    margin-bottom: $base_size;
  }

  :root {
    --primary: #333;
    --secondary: rgb(155, 155, 155);
    --black: rgb(0, 0, 0);
    --white: rgb(222, 222, 222);
    --fullwidth: 100%;
    --basepadding: 20px;
  }
/* $: haserror = false */
</style>

<main>
  <header>
    <h1>Gematria App</h1>
    <h3>Lo que valen las palabras hebreas</h3>
  </header>
  <section>
    <h2>{counter}</h2>
    <div class="formulario">
      <form 
      name="myForm"
      on:submit|preventDefault={handleSubmit}>
        <Input bind:value={valorinput}/>
        <Button variante="primary">Calcular!</Button>
        <label>בראשית ברא אלהים את השמים ואת הארץ (Génesis, 1)</label>
      </form>
      {#if (haserror == true)}
      <Alert {haserror}> {errormessage} </Alert>
      {/if}
    </div>
  </section>
  <section>
    <small>
      Creado en JS, Html, Sass con Svelte por
      <a href="http://sergiofores.es" target="_blank">Sergio Forés</a><br>
      <a href="https://tanach.us/Server.txt?Genesis*&content=Consonants" target="_blank">Codex de Leningrado</a>
    </small>
  </section>
</main>

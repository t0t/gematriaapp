<script>
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
  console.log(gematria)

  let txtmedido = ''
  let counter = 0
  let arrayASumar = []
  let splited = []

  function handleSubmit() {
    counter = 0
    txtmedido = txtmedido
    splited = txtmedido.split('')
    for (const s of splited) {
      if (s == '\u05D0') {
        counter += 1
      } else if (s == '\u05D1') { counter += 2
      } else if (s == '\u05D2') { counter += 3
      } else if (s == '\u05D3') { counter += 4
      } else if (s == '\u05D4') { counter += 5
      } else if (s == '\u05D5') { counter += 6
      } else if (s == '\u05D6') { counter += 7
      } else if (s == '\u05D7') { counter += 8
      } else if (s == '\u05D8') { counter += 9
      } else if (s == '\u05D9') { counter += 10
      } else if (s == '\u05DB') { counter += 20
      } else if (s == '\u05DC') { counter += 30
      } else if (s == '\u05DE') { counter += 40
      } else if (s == '\u05DF') { counter += 50
      } else if (s == '\u05E1') { counter += 60
      } else if (s == '\u05E2') { counter += 70
      } else if (s == '\u05E4') { counter += 80
      } else if (s == '\u05E6') { counter += 90
      } else if (s == '\u05E7') { counter += 100
      } else if (s == '\u05E8') { counter += 200
      } else if (s == '\u05E9') { counter += 300
      } else if (s == '\u05EA') { counter += 400
      } else if (s == '\u05DA') { counter += 500
      } else if (s == '\u05DD') { counter += 600
      } else if (s == '\u05DF') { counter += 700
      } else if (s == '\u05E3') { counter += 800
      } else if (s == '\u05E5') { counter += 900
      } 
    }
    return counter
  }
$: txtmedido = handleSubmit()
</script>

<style type="text/scss">
  $color: #04ff00;
  $font_size: 2em;

h1 {
    font-size: $font_size;
    padding: var(--basepadding);
  }
  h2 {
    font-size: $font_size*4;
    font-weight: normal;
    padding-bottom: var(--basepadding);
  }
  h1,
  small {
    color: var(--white);
    /* color: var(--primary); */
  }
  small {
    display: block;
    font-size: 1em;
    margin: var(--basepadding);
    /* color: var(--white); */
  }
  :global(html) {
    background-color: var(--primary);
    height: 100vh;
    font-size: 15px;
  }
  main {
    margin: var(--basepadding);
    padding: var(--basepadding);
    display: grid;
    grid-template-columns: 1fr;
    align-items: center;
    text-align: center;
    color: $color;
    font-family: 'Montserrat', sans-serif;
  }
  .formulario {
    /* display: grid;
    grid-template-columns: 1fr 1fr; */
    margin-bottom: var(--basepadding);
  }
  input,
  button {
    font-size: 2em;
    padding: var(--basepadding);
    border: none;
  }
  input {
    border-top-left-radius: var(--basepadding);
    border-bottom-left-radius: var(--basepadding);
  }
  button {
    border-top-right-radius: var(--basepadding);
    border-bottom-right-radius: var(--basepadding);
    background-color: var(--black);
    color: var(--secondary);
  }
  button:hover {
    cursor: pointer;
    background-color: var(--secondary);
    color: var(--black);
    
  }
  a {
    text-decoration: none;
    color: var(--secondary);
  }
  
  :root {
    --primary: #333;
    --secondary: rgb(155, 155, 155);
    --black: rgb(0, 0, 0);
    --white: rgb(222, 222, 222);
    --fullwidth: 100%;
    --basepadding: 20px;
}
</style>

<main>
  <header>
    <h1>Gematria App</h1>
  </header>
  <section>
    <h2>{counter}</h2>
    <div class="formulario">
      <form on:submit|preventDefault={handleSubmit}>
        <input  
        placeholder="p.e.: ששש‎" 
        bind:value={txtmedido}
        />
        <button on:click|preventDefault={handleSubmit}>Go!</button>
      </form>
    </div>
    <small>Copia/Pega o escribe letras hebreas: (p.e.: "בְּרֵאשִׁ֖ית בָּרָ֣א אֱלֹהִ֑ים אֵ֥ת הַשָּׁמַ֖יִם וְאֵ֥ת הָאָֽרֶץ")</small>
  </section>
  <section>
    <small>By <a href="http://sergiofores.es">Sergio Forés</a></small>
  </section>
</main>

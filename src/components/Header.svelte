<script>
  import logoPrefeitura from '$svg/capa_prefeitura.png'; 
  import logoPretoHorizontal from '$svg/logo_preto_horizontal.png'; 
</script>

<header>
  <div class="headerWrapper">
    <div class="wordmark">
      <a href="https://dados.rio/" target="_blank" aria-label="Escritório de dados">
        <img src={logoPretoHorizontal} alt="Logo Prefeitura" />
      </a>
    </div>
    <p class="hed-text">O Rio nunca teve<br> tanta gente<br>trabalhando</p>
    <p id="produzido_por">
      Desenvolvido pelo <br><a href="https://www.dados.rio"  target="_blank">Escritório de Dados da<br> Prefeitura do Rio de Janeiro </a> 
    </p>
  </div>
</header>

<style>
 .headerWrapper {
    position: relative;
    text-align: center; /* Centraliza o texto */
  }

  .title {
    font-size: 2em; /* Tamanho da fonte para dispositivos grandes */
  }

  .subtitle {
    font-size: 1.5em; /* Tamanho da fonte para dispositivos grandes */
  }


.topLeftImage {
  max-width: 12em;
  margin: 0 auto;
 position: absolute;
 padding: 1em 1em;
 top: 0;
}
.hed-text {
    font-family: var(--dubois-wide);
    text-transform: uppercase;
    font-size: 3.5rem !important;
    margin: 0 auto;
    padding: 0 2rem;
    line-height: 1;
    max-width: 40rem;
    margin-top: 5rem;
    text-align: left;
    /* margin-top:-50px  */
  }

  #produzido_por {
    padding-top: 4rem;
    padding-bottom: 6rem;
    margin: 0 auto;
    line-height: 1.4rem;
    max-width: 36rem;
    text-align: left;
  }
  .wordmark {
    max-width: 13em;
    margin: 0 auto;
  
    padding: 1em 0;
  }

  .wordmark a {
    border: none;
    color: var(--color-fg);
  }

  .wordmark a:hover {
    background-color: transparent;
  }

  :global(.wordmark svg path) {
    fill: var(--color-off-black);
    stroke: none;
  }

  @media only screen and (max-width: 600px) {
    .title {
      font-size: 1.5em; /* Tamanho da fonte para dispositivos pequenos */
    }

    .subtitle {
      font-size: 1.2em; /* Tamanho da fonte para dispositivos pequenos */
    }

    .topLeftImage{
      display: none;
    }
    .hed-text {
    font-family: var(--dubois-wide);
    text-transform: uppercase;
    font-size: 2.4rem !important;
    margin: 0 auto;
    padding: 0 2rem;
    line-height: 1;
    max-width: 40rem;
    margin-top: 5rem;
    text-align: left;
    /* margin-top:-50px  */
  }

  #produzido_por {
    padding: 4rem 2rem;
    margin: 0 auto;
    line-height: 1.3rem;
    max-width: 40rem;
    text-align: left;
  }
  }
</style>

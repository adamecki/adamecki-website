<script>
  let progress = 0;
  window.onload = function() {
    window.setTimeout(loadMainDiv, 3000);
  }
  function loadMainDiv() {
    progress = 1;
  }

  let page = 0;
  function mainPage() {
    page = 0;
  }
  function newsPage() {
    page = 1;
  }
  function aboutPage() {
    page = 2;
  }
  function contactPage() {
    page = 3;
  }
</script>

<style>
  @font-face{
    font-family: Ubuntu;
    src: url(./fonts/Ubuntu/Ubuntu-Regular.ttf);
  }
  @font-face{
    font-family: UbuntuLight;
    src: url(./fonts/Ubuntu/Ubuntu-Light.ttf);
  }
  @font-face{
    font-family: UbuntuBold;
    src: url(./fonts/Ubuntu/Ubuntu-Bold.ttf);
  }

  @keyframes menuLoadAnimation{
    0%{
      opacity: 0;
      transform: translate(0, 100%);
    }
    25%{
      opacity: 0;
      transform: translate(0, 100%);
    }
    100%{
      transform: translate(0, 0);
      opacity: 1;
    }
  }
  @keyframes mainLoadAnimation{
    0%{
      opacity: 0;
    }
    100%{
      opacity: 1;
    }
  }
  @keyframes elementLoadAnimation{
    0%{
      transform: translate(0, 100%);
    }
    100%{
      transform: translate(0, 0);
    }
  }

  .header1 {
    animation: menuLoadAnimation 1s cubic-bezier(0.77, 0, 0.175, 1);
    width: 100%;
    margin-top: 50px;
    cursor: default;
    font-family: UbuntuLight;
    font-size: 30px;
    text-align: center;
    word-spacing: 20px;
    color: white;
  }
  .header1 a{
    background: linear-gradient(to left, transparent 50%, white 50%);
    background-repeat: no-repeat;
    background-size: 200% 2px;
    background-position: bottom right;
    font-family: UbuntuBold;
    text-decoration: none;
    color: white;
    transition: all 200ms cubic-bezier(0.77, 0, 0.175, 1);
    display: inline-block;
    transform: translate(0, 100%);
    cursor: pointer;
  }
  .header1 a:hover{
    background-position: bottom left;
  }

  .container{
    animation: mainLoadAnimation 300ms ease;
    height: auto;
    margin-top: 50px;
    margin-left: 1%;
    margin-right: 1%;
    margin-bottom: 25px;
    padding: 15px;
    border-radius: 5px;
    background-color: rgb(45, 45, 55);
    color: white;
    font-family: Ubuntu;
  }
  .container a{
    background: linear-gradient(to left, transparent 50%, lightblue 50%);
    background-repeat: no-repeat;
    background-size: 200% 2px;
    background-position: bottom right;
    text-decoration: none;
    color: lightblue;
    transition: all 200ms cubic-bezier(0.77, 0, 0.175, 1);
  }
  .container a:hover{
    background-position: bottom left;
  }
  .container h1{
    text-align: center;
  }
  
  .pcontainer{
    overflow: hidden;
  }
  .footnote{
    cursor: default;
  }

  .glowna{
    animation: elementLoadAnimation 1s cubic-bezier(0.77, 0, 0.175, 1) forwards;
    animation-delay: 0.75s;
  }
  .akt{
    animation: elementLoadAnimation 1s cubic-bezier(0.77, 0, 0.175, 1) forwards;
    animation-delay: 1s;
  }
  .about{
    animation: elementLoadAnimation 1s cubic-bezier(0.77, 0, 0.175, 1) forwards;
    animation-delay: 1.25s;
  }
  .social{
    animation: elementLoadAnimation 1s cubic-bezier(0.77, 0, 0.175, 1) forwards;
    animation-delay: 1.5s;
  }
</style>

<html lang="pl">
  <body>
    <div class="header1">
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <!-- svelte-ignore a11y-missing-attribute -->
      <p class="pcontainer">
        adamecki
        <a on:click={mainPage} class="glowna">główna</a>
        <a on:click={newsPage} class="akt">aktualności</a>
        <a on:click={aboutPage} class="about" style="word-spacing: 1px;">o mnie</a>
        <a on:click={contactPage} class="social">kontakt</a>
      </p>
    </div>

    {#if progress == 1}
      <div class="container">
        {#if page == 0}
          <h1>główna</h1>
          <p>dolor sit amet</p>
          <p>dolor sit amet</p>
          <p>dolor sit amet</p>
          <p>dolor sit amet</p>
          <p>dolor sit amet</p>
          <p>dolor sit amet</p>
        {/if}
        {#if page == 1}
          <h1>aktualności</h1>
          <p>dolor sit amet</p>
          <p>dolor sit amet</p>
        {/if}
        {#if page == 2}
          <h1>o mnie</h1>
          <p>dolor sit amet</p>
        {/if}
        {#if page == 3}
          <h1>kontakt</h1>
          <p>dolor sit amet</p>
        {/if}
      </div>

      <!-- stopka -->
      <div class="container" style="height: auto; margin-top: 10px; padding-bottom: 30px;">
        <div class="footnote" style="float: left;">
          <b>2023 Adamecki</b>
        </div>
        <div class="footnote" style="float: right;">
          <a href="#0">Discord</a>
          |
          <a href="#0">GitHub</a>
        </div>
      </div>
    {/if}
  </body>
</html>
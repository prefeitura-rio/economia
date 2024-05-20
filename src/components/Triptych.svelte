<script>
  import Block from "$components/Block.svelte";
  import ImageRaw from "$components/ImageRaw.svelte";
  import inView from "$actions/inView.js";
  import { onMount } from "svelte";
  import { selectAll, easeLinear } from "d3";

  let visiblePhoto = false;
  let photos;

  function showPhotos() {
    photos
      .transition()
      .delay((d, i) => i * 250)
      .duration(500)
      .ease(easeLinear)
      .style("opacity", 1);
  }

  onMount(() => {
    photos = selectAll(".trip-wrapper .border-2");
  });

  export let text;
  let playing1 = false;
  let playing2 = false;
  let playing3 = false;
  let video1;
  let video2;
  let video3;

  function togglePlay(video, playing) {
    if (video.paused) {
      video.play();
      return true;
    } else {
      video.pause();
      return false;
    }
  }
</script>

<div class="trip-wrapper" use:inView on:enter={() => showPhotos()}>
  <div id="package" class="relative">
    <div class="video-container border-2 border-black" id="madera-triptych">
      <video bind:this={video1} width="300" height="auto" on:click={() => playing1 = togglePlay(video1, playing1)} poster="assets/img/intro/thumb1.jpg">
        <source src="https://storage.googleapis.com/datario-public/dataviz-videos/ALEXANDRE%20RIBEIRO.mp4" type="video/mp4" />
      </video>
      <div class="play-button" on:click|stopPropagation={() => playing1 = togglePlay(video1, playing1)} style="visibility: {playing1 ? 'hidden' : 'visible'}"><img width="80px" src="assets/img/intro/play.png"></div>
    </div>
    <div class="video-container border-2 border-black" id="gardena1-triptych">
      <video bind:this={video2} width="300" height="auto" on:click={() => playing2 = togglePlay(video2, playing2)} poster="assets/img/intro/thumb2.jpg">
        <source src="https://storage.googleapis.com/datario-public/dataviz-videos/ANA%20KARINE.mp4" type="video/mp4" />
      </video>
      <div class="play-button" on:click|stopPropagation={() => playing2 = togglePlay(video2, playing2)} style="visibility: {playing2 ? 'hidden' : 'visible'}"><img width="80px" src="assets/img/intro/play.png"></div>
    </div>
    <div class="video-container border-2 border-black" id="gardena2-triptych">
      <video bind:this={video3} width="300" height="auto" on:click={() => playing3 = togglePlay(video3, playing3)} poster="assets/img/intro/thumb3.jpg">
        <source src="https://storage.googleapis.com/datario-public/dataviz-videos/EVERTON%20FERREIRA.mp4" type="video/mp4" />
      </video>
      <div class="play-button" on:click|stopPropagation={() => playing3 = togglePlay(video3, playing3)} style="visibility: {playing3 ? 'hidden' : 'visible'}"><img width="80px" src="assets/img/intro/play.png"></div>
    </div>
  </div>
  <Block>
    <p class="mt-2 text-label">{@html text ?? ""}</p>
  </Block>
</div>


<style>
  .video-container {
    position: relative;
    width: 300px; /* Adjust to match video width */
    height: auto; /* Adjust to match video height */
  }

  .play-button {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-size: 50px;
    color: white;
    cursor: pointer;
    transition: 0.5s;
  }

  .trip-wrapper {
    height: calc(120vw * 1.25);
    /* padding: 1rem 1rem 0rem 1rem; */
    max-width: 60rem;
    max-height: 60rem;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
  }

  .trip-wrapper .border-2 {
    opacity: 0;
  }

  .relative {
    position: relative;
    height: 100%;
    width: 100%;
  }

  .text-label {
    font-family: var(--dubois);
    text-transform: uppercase;
    color: var(--color-off-white);
    font-size: 14px;
    margin-bottom: 4rem;
  }

  .border-2 {
    position: absolute;
  }

  #madera-triptych {
    top: 0;
    left: 0;
  }

  #gardena1-triptych {
    top: 37%;
    right: -3.5%;
  }

  #gardena2-triptych {
    top: 17%;
    left: 35%;
  }


  @media only screen and (min-width: 700px) {
    .trip-wrapper {
      height: calc(100vw * 1.25);
      padding: 2rem 2rem 0rem 2rem;
    }

  }

  @media only screen and (min-width: 900px) {
    .trip-wrapper {
      height: calc(100vw * 1.25);
    }
  }

  @media only screen and (max-width: 620px) {
    .trip-wrapper {
      margin-top: -5rem;
      max-width: 100%;
      height: calc(250vw * 1.9);
      max-height: calc(250vw * 1.9);
    }

    .text-label {
      margin-top: -240px;
      text-align: center;
    }

    #package {
      padding-top: 425px;
      height: 3000px !important;
      overflow: hidden;
    }
    #madera-triptych {
      /* transform: scale(1.5); */
      /* transform: rotate(0deg); */
      width: 80%;
      top: 1rem;
      left: 2.3rem;
    }

    #gardena1-triptych {
      /* transform: scale(1.7); */
      /* transform: rotate(-8deg); */
      width: 80%;
      top: 34rem;
      left: 2.3rem;
    }

    #gardena2-triptych {
      /* transform: rotate(8deg); */
      width: 80%;
      /* transform: scale(1.6); */
      top: 67rem;
      left: 2.3rem;
    }
  }
</style>

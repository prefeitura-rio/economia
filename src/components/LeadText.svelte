<script>
  // import { beforeUpdate } from "svelte";

  // import Block from "$components/Block.svelte";

  export let id;
  export let text;
  export let subhead;
  // export let type;
  // export let stepIndex
  export let className = "";
  // export let year

  const grafs = text.split("\n");
  let w;

  const positioningClasses = {
    "madera-mom": {
      position: "col-start-1 col-span-6",
      positionMobile: "col-start-1 col-span-12"
    },
    "madera-ggp": {
      position: "col-start-2 col-span-6",
      positionMobile: "col-start-1 col-span-12"
    },
    "cimeira3": {
      position: "col-start-4 col-span-4",
      positionMobile: "col-start-1 col-span-12"
    },
    "cimeira1": {
      position: "col-start-7 col-span-6",
      positionMobile: "col-start-1 col-span-12"
    },
    "cimeira2": {
      position: "col-start-7 col-span-6",
      positionMobile: "col-start-1 col-span-12"
    },
    "cimeira33": {
      position: "col-start-7 col-span-6",
      positionMobile: "col-start-1 col-span-12"
    },
    "madera-farm": {
      position: "col-start-2 col-span-6",
      positionMobile: "col-start-1 col-span-12"
    },
    "gardena-mom-and-me": {
      position: "col-start-6 col-span-6",
      positionMobile: "col-start-1 col-span-12"
    },
    "gardena-air": {
      position: "col-start-6 col-span-6",
      positionMobile: "col-start-1 col-span-12"
    },
    "gardena-preschool": {
      position: "col-start-6 col-span-6",
      positionMobile: "col-start-1 col-span-12"
    },
    "fremont": {
      position: "col-start-2 col-span-5",
      positionMobile: "col-start-1 col-span-12"
    },
    "2acervo": {
      position: "col-start-2 col-span-5",
      positionMobile: "col-start-1 col-span-12"
    },
    "3acervo": {
      position: "col-start-2 col-span-5",
      positionMobile: "col-start-1 col-span-5"
    },
    "fremont-2": {
      position: "col-start-2 col-span-5",
      positionMobile: "col-start-1 col-span-12"
    },
    "fremont-income": {
      position: "col-start-2 col-span-5",
      positionMobile: "col-start-1 col-span-12"
    }
  };

  // beforeUpdate(() => {
  //   console.info("LeadText", stepIndex)
  // })
</script>

<svelte:window bind:innerWidth={w} />

<div class={`${className} grid grid-cols-12 gap-3 w-full max-w-5xl`}>
  {#if w > 900}
    <div class={`${positioningClasses[id].position} p-4`}>
      {#if subhead}
        <p class={`subhed subhed-${subhead.split(",")[0]} text-label mt-6 mb-2 text-3xl`}>
          {subhead}
        </p>
      {/if}
      {#each grafs as graf}
        <p class="mb-4 text-lg text-label">{@html graf}</p>
      {/each}
    </div>
  {:else}
    <div class={`${positioningClasses[id].positionMobile} p-4`}>
      {#if subhead}
        <p class={`subhed subhed-${subhead.split(",")[0]} text-label mt-6 mb-2 text-3xl`}>
          {subhead}
        </p>
      {/if}
      {#each grafs as graf}
        <p class="mb-4 text-lg text-label">{@html graf}</p>
      {/each}
    </div>
  {/if}
</div>

<style>
  .h-screen {
    padding: 1rem;
    width: 100%;
    grid-auto-rows: minmax(min-content, max-content);
  }

  .h-screen div {
    border: 2px solid var(--color-off-black);
    background-color: white;
    padding: 2rem 2rem 1rem 2rem;
    
    max-width: 25rem;
    margin: 0 auto;
  }

  .subhed.text-label {
    font-family: var(--dubois-wide);
    text-transform: uppercase;
    font-size: 24px;
    margin: 0;
  }

  .subhed-Madera::before,
  .subhed-Gardena::before,
  .subhed-Fremont::before {
    display: inline-block;
    width: 1rem;
    height: 1rem;
    border-radius: 50%;
    content: "";
    border: 1px solid var(--color-off-black);
    position: relative;
    margin-right: 0.25rem;
    left: 0rem;
    top: 0rem;
  }

  .subhed-Madera::before {
    background-color: var(--color-db-pink);
  }
  .subhed-Gardena::before {
    background-color: var(--color-db-yellow);
  }
  .subhed-Fremont::before {
    background-color: var(--color-db-green);
  }

  @media only screen and (min-width: 700px) {
    .h-screen {
      padding: 1rem 1rem 1rem 12rem;
    }
  }
</style>

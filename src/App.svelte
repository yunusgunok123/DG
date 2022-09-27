<script lang="ts">
  import { Button, MaterialApp } from "svelte-materialify";
  import { fly } from "svelte/transition";
  import Preload from "./lib/Preload.svelte";
  import Slide1 from "./lib/Slide1.svelte";
  import Slide2 from "./lib/Slide2.svelte";
  import Slide3 from "./lib/Slide3.svelte";
  import Slide4 from "./lib/Slide4.svelte";
  import Slide5 from "./lib/Slide5.svelte";
  import Slide6 from "./lib/Slide6.svelte";
  import Slide7 from "./lib/Slide7.svelte";

  const slides = [Slide1, Slide2, Slide3, Slide4, Slide5, Slide6, Slide7];

  let isDark = true;
  let slideNumber = 0;

  let direction = true;

  async function load(): Promise<Config> {
    const res = await fetch("/config.json");
    const db = await res.json();
    const config = db[window.location.search.slice(1)];
    return (
      config || {
        name: "Yunus",
        id: "hu-JryC9aC0",
        message: "Sevilmiyorsun!",
        file: "ben.jpg",
      }
    );
  }
</script>

{#await load()}
  <div>Lütfen Bekle</div>
{:then config}
  <Preload file={config.file} />
  <MaterialApp theme={isDark ? "dark" : "light"}>
    <div class="topbar">
      <div class="right">
        <Button fab on:click={() => (isDark = !isDark)}
          >{isDark ? "🌞" : "🌑"}</Button
        >
      </div>
    </div>

    <div class="stack f-h">
      <div class={slideNumber != 0 ? "hidden" : ""}>
        <Slide1 id={config.id} />
      </div>
      {#each slides as slide, index}
        {#if index != 0 && slideNumber == index}
          <div
            in:fly={{ duration: 1000, x: direction ? 500 : -500 }}
            out:fly={{ duration: 1000, x: direction ? -500 : 500 }}
          >
            <svelte:component this={slide} {config} />
          </div>
        {/if}
      {/each}
    </div>

    <div class="bottombar">
      <div class="left">
        {#if slideNumber != 0}
          <Button
            fab
            on:click={() => (
              (direction = false), setTimeout(() => (slideNumber -= 1), 50)
            )}>⫷</Button
          >
        {/if}
      </div>
      <div class="right">
        {#if slideNumber != slides.length - 1}
          <Button
            fab
            on:click={() => (
              (direction = true), setTimeout(() => (slideNumber += 1), 50)
            )}>⫸</Button
          >
        {/if}
      </div>
    </div>
  </MaterialApp>
{/await}

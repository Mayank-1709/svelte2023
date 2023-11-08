<script>
  import statsData from "../lib/Statsdata.json";
  import { blockData } from "../lib/Data.json";
  import { iconData } from "../lib/Data.json";
  import DropdownMenu from "../lib/DropdownMenu.svelte";
</script>

<!-- The main content of the webpage -->
<div class="main-page-content">
  <DropdownMenu />
  <!-- Hero video section -->
  <div class="hero-video">
    <video controls autoplay muted loop poster="../images/poster-image.jpg">
      <source src="../videos/cr7-hero-video.mp4" type="video/mp4" />
      Your browser does not support the video tag.
    </video>
    <h2>Magnificient Ronaldo</h2>
    <!-- Title for the hero video -->
  </div>

  <!-- Grid container for career highlights -->
  <div class="grid-container">
    <!-- Display three empty blocks with dynamic content -->
    {#each [1, 2, 3] as i}
      <div class="block block{i}" />
    {/each}

    <!-- Display career highlight information from 'blockData' -->
    {#each blockData as data, index (index)}
      <div class="block block${index + 4}">
        <p>{data}</p>
      </div>
    {/each}
  </div>

  <!-- Container for displaying numerical statistics -->
  <div class="number-container">
    <h2>NUMEROS</h2>
    <!-- Title for the statistics section -->

    <!-- Iterate through 'statsData' to display statistics -->
    {#each statsData as item}
      {#if item.number !== undefined}
        <div class="stats">
          <h2>{item.number}</h2>
          <h4>{item.label}</h4>
        </div>
      {:else}
        <!-- Display an empty statistics block if item.number is empty -->
        <div class="stats" />
      {/if}
    {/each}

    <!-- Iterate through 'iconData' to display icons -->
    {#each iconData as item}
      <div class="stats">
        <!-- Display an icon based on CSS class from 'iconData' -->
        <i class={item} />
      </div>
    {/each}
  </div>
</div>

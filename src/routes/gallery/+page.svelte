<script>
  import { onMount } from "svelte";
  import careerData from "../../lib/Careerdata.json";
  import familyMembers from "../../lib/Familymembers.json";
  import DropdownMenu from "../../lib/DropdownMenu.svelte";

  let urls = [];
  const BASE_URL = `https://api.unsplash.com`;
  const CLIENT_ID = `udhKpbCA3oTftT1_unc7veA5kDEvPVBcEkHVjM7rN7E`;

  // Fetch data when the component is mounted
  onMount(async () => {
    // Fetch photos related to soccer from the Unsplash API
    const response = await fetch(
      `${BASE_URL}/search/photos?query=soccer&per_page=20&client_id=${CLIENT_ID}`
    );
    const data = await response.json();

    // Generating 4 random numbres between 0 and 20(exclusive) to select 4 image urls from 20 fetched from API
    const randomIndices = [];
    while (randomIndices.length < 4) {
      const randomIndex = Math.floor(Math.random() * 20);
      if (!randomIndices.includes(randomIndex)) {
        randomIndices.push(randomIndex);
      }
    }

    const football = [];

    // Extract 4 regular photo URLs from the API response
    randomIndices.forEach((index) => {
      football.push(data.results[index].urls.regular);
    });

    // Create a temporary URL array with the initial video
    const tempUrls = ["../videos/Video_1.mp4"];

    // Filenames for video gallery
    const videoFilenames = [
      "../videos/Video_2.mp4",
      "../videos/Video_3.mp4",
      "../videos/Video_4.mp4",
      "../videos/Video_5.mp4",
    ];

    // Combine photo and video URLs for the gallery
    for (let i = 0; i < football.length; i++) {
      tempUrls.push(football[i]);
      tempUrls.push(videoFilenames[i]);
    }

    urls = tempUrls;
  });

  // Function to handle video hover events (play on hover, pause on leave)
  const handleVideoHover = (event) => {
    if (event.type === "mouseenter") {
      event.target.play();
    } else if (event.type === "mouseleave") {
      event.target.pause();
    }
  };
</script>

<!-- The main content of the webpage -->
<div class="main-page-content">

  <DropdownMenu />
  <!-- Career highlights section -->
  <div class="photo-container-career-highlights">
    <div class="headings">
      <h2>CAREER HIGHLIGHTS</h2>
      <!-- Title for the section -->
    </div>
    {#each careerData as data, index (index)}
      <div class="photo{index + 1}">
        <p>{data}</p>
        <!-- Display each career highlight with corresponding index -->
      </div>
    {/each}
  </div>

  <!-- Personal life section -->
  <div class="photo-container-personal-life">
    <div class="headings">
      <h2>PERSONAL LIFE</h2>
      <!-- Title for the section -->
    </div>
    <div class="gallery">
      {#each familyMembers as member, index (index)}
        {#if (index + 1) % 2 !== 0}
          <!-- Display family member photo and description based on index % 2-->
          <div class="personal-life-photo {member.photoClass}" />
          <div class="description">
            <p>{member.description}</p>
          </div>
        {:else}
          <!-- Display family member description and photo -->
          <div class="description">
            <p>{member.description}</p>
          </div>
          <div class="personal-life-photo {member.photoClass}" />
        {/if}
      {/each}
    </div>
  </div>

  <!-- Video gallery section -->
  <div class="video-container">
    <div class="headings">
      <h2>VIDEO GALLERY</h2>
      <!-- Title for the section -->
    </div>
    <div class="video-gallery">
      {#each urls as url, index (index)}
        {#if url.match(".mp4")}
          <div class="video-goals">
            <!-- Display video with controls and autoplay behavior -->
            <video
              on:mouseenter={handleVideoHover}
              on:mouseleave={handleVideoHover}
              controls
              muted
              loop
            >
              <source src={url} type="video/mp4" />
              Your browser does not support the video tag.
            </video>
          </div>
        {:else}
          <!-- Create a div for images -->
          <div
            class="image-container image{index}"
            style="background-image: url({url})"
          />
        {/if}
      {/each}
    </div>
  </div>
</div>

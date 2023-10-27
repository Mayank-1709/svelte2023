<script>
    const blockData = [
      "A Galáctico Unveiled: Cristiano Ronaldo's Historic Move to Real Madrid",
      "Ronaldo's Triumph: Leading Portugal to Euro 2016 Glory",
      "CR7's Five-Star Legacy: Ballon d'Or Dominance",
    ];

    const statsData = [
        { number: "850", label: "GOALS" },
        { number: "", label: "" }, 
        { number: "1204", label: "MATCHES" },
        { number: "", label: "" },
        { number: "86", label: "TOTAL AWARDS" },
        { icon: "fa-solid fa-futbol style-icon" },
        { icon: "fa-solid fa-trophy style-icon" },
        { icon: "fa-solid fa-award style-icon" }
    ];
</script>

<div class="main-page-content">
    <div class="hero-video">
        <video autoplay muted loop poster="../images/poster-image.jpg"> 
            <source src="../videos/cr7-hero-video.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
        <h2>Magnificient Ronaldo</h2>
    </div>

    <div class="grid-container">
        {#each [1, 2, 3] as i}
            <div class="block block{i}"></div>
        {/each}
        
        {#each blockData as data, index (index)}
            <div class="block block${index+4}">
                <p>{data}</p>
            </div>
        {/each}
    </div>

    <div class="number-container">
        <h2>NUMEROS</h2> 
        {#each statsData as item}
            {#if item.number !== undefined}
                <div class="stats">
                    <h2> {item.number} </h2>
                    <h4> {item.label} </h4>
                </div>
            {:else}
            <div class="stats"></div>
            {/if}
            {#if item.icon !== undefined}
            <div class="stats">
                <i class="{item.icon}"></i>
            </div>
        {/if}
    {/each}  
    </div>
</div>



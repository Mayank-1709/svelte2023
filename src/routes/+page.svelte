<script>
    const blockData = [
      "A Galáctico Unveiled: Cristiano Ronaldo's Historic Move to Real Madrid",
      "Ronaldo's Triumph: Leading Portugal to Euro 2016 Glory",
      "CR7's Five-Star Legacy: Ballon d'Or Dominance",
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
        <div class="block block1"></div> 
        <div class="block block2"></div> 
        <div class="block block3"></div>    
        {#each blockData as data, index (index)}
            <div class = "block block${index+4}">
                <p>{data}</p>
            </div>
        {/each}
    </div>
    <div class="number-container">
        <h2>NUMEROS</h2>
        <div class="stats">
            <h2>850</h2>
            <h4>GOALS</h4>
        </div>
        <div class="stats"></div>
        <div class="stats">
            <h2>1204</h2>
            <h4>MATCHES</h4>
        </div>
        <div class="stats"></div>
        <div class="stats">
            <h2>86</h2>
            <h4>TOTAL AWARDS</h4>
        </div>
        <div class="stats">
            <i class="fa-solid fa-futbol style-icon"></i>
        </div>
        <div class="stats">
            <i class="fa-solid fa-trophy style-icon"></i> 
        </div>
        <div class="stats">
            <i class="fa-solid fa-award style-icon"></i>
        </div>
    </div>
</div>



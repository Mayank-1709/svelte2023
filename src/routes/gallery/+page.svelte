<script>
    const careerData = [
        "Ronaldo's football journey started at Sporting Lisbon.",
        "In the iconic red jersey, Ronaldo soared to stardom.",
        "Real Madrid witnessed Ronaldo's Galactico era.",
        "Juventus saw Ronaldo's Serie A dominance.",
        "Ronaldo's journey continues with AL-Nassr in Saudi Arabia.",
        "Leading Portugal to victory, Ronaldo's captaincy shines."
    ];

    let familyMembers = [
        {
            name: "José Dinis Aveiro",
            description: `Cristiano Ronaldo's late father, José Dinis Aveiro, played a significant role in his life.
                          Despite his passing in 2005, Cristiano often pays tribute to his father's memory,
                          crediting him with inspiring his football journey.`,
            photoClass: "photo_1",
        },

        {
            name: "Maria Dolores dos Santos Aveiro",
            description: `Maria Dolores dos Santos Aveiro is Cristiano Ronaldo's beloved mother. 
                          Her unwavering support and guidance have been pivotal in shaping Cristiano's career and life.
                          He holds a deep affection for her.`,
            photoClass: "photo_2",              
        },

        {
            name: "Georgina Rodríguez",
            description: `Georgina Rodríguez is Cristiano Ronaldo's partner and the mother of one of his children, Alana Martina.
                          They share a close bond and often share glimpses of their life together on social media.`,
            photoClass: "photo_3",
        },

        {
            name: "Cristiano Ronaldo's Children",
            description: `Cristiano Ronaldo is a doting father to five children. Cristiano Jr., Mateo, Eva Maria, Alana Martina and Bella bring immense joy to his life.
                          His social media often features heartwarming moments with his kids.`,
            photoClass: "photo_4",
        },

        {
            name: "Fitness",
            description: `Cristiano Ronaldo's dedication to fitness is legendary. His rigorous workout routines, diet, 
                          and commitment to staying in peak physical condition have made him an inspiration for fitness enthusiasts worldwide. `,
            photoClass: "photo_5",
        }
    ];

    const videoFilenames = [
        "../videos/Video_1.mp4",
        " ",
        "../videos/Video_2.mp4",
        " ",
        "../videos/Video_3.mp4",
        " ",
        "../videos/Video_4.mp4",
        " ",
        "../videos/Video_5.mp4"
    ];
</script>

<div class="main-page-content"> 
   <div class="photo-container-career-highlights">
        <div class="headings">
            <h2>CAREER HIGHLIGHTS</h2>
        </div>
        {#each careerData as data, index(index)}
            <div class="photo{index+1}">
                <p>{data}</p>
            </div>
        {/each}
   </div> 

   <div class="photo-container-personal-life">
        <div class="headings">
            <h2>PERSONAL LIFE</h2>
        </div>
        <div class="gallery">
            {#each familyMembers as member, index (index)}
                {#if (index+1) % 2 !== 0}
                    <div class="personal-life-photo {member.photoClass}"></div>
                    <div class="description">
                        <p>{member.description}</p>
                    </div>
                {:else}
                    <div class="description">
                        <p>{member.description}</p>
                    </div>
                    <div class="personal-life-photo {member.photoClass}"></div>
                {/if}
            {/each}
        </div>
   </div>

   <div class="video-container">
        <div class="headings">
            <h2>VIDEO GALLERY</h2>
        </div>
        <div class="video-gallery">
            <div class="video-goals">
                <video autoplay muted loop> 
                    <source src="../videos/Video_1.mp4" type="video/mp4">
                    Your browser does not support the video tag.
                </video>
            </div>
            <div class="video-goals"></div>
            <div class="video-goals">
                <video autoplay muted loop> 
                    <source src="../videos/Video_2.mp4" type="video/mp4">
                    Your browser does not support the video tag.
                </video>
            </div>
            <div class="video-goals"></div>
            <div class="video-goals">
                <video autoplay muted loop> 
                    <source src="../videos/Video_3.mp4" type="video/mp4">
                    Your browser does not support the video tag.
                </video>
            </div>
            <div class="video-goals"></div>
            <div class="video-goals">
                <video autoplay muted loop> 
                    <source src="../videos/Video_4.mp4" type="video/mp4">
                    Your browser does not support the video tag.
                </video>
            </div>
            <div class="video-goals"></div>
            <div class="video-goals">
                <video autoplay muted loop> 
                    <source src="../videos/Video_5.mp4" type="video/mp4">
                    Your browser does not support the video tag.
                </video>
            </div>
        </div>  
   </div>
</div>

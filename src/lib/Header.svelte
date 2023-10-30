<script>
    import Nav from '$lib/Nav.svelte' // Import the 'Nav' component from a Svelte module
</script>
<header class="main-header" id="fixed-header">
    <div class=sub-main-header>
        <div class="site-title-container">
            <div>The</div> <!-- The first part of the site title -->
            <div>Ronaldo</div> <!-- The second part of the site title -->
            <div>Realm</div> <!-- The third part of the site title -->
        </div>
        <div>
            <div class="football-animation">
                <!-- Animated football icon with spinning effect -->
            <i class="fa-solid fa-futbol style-icon fa-spin" style="font-size:7em" ></i>
            </div>
        </div>
        <div class="logo"></div> <!-- Div containing the logo of the website -->
        <div class="nav-container"><Nav /></div> <!-- Navigation container using the 'Nav' component -->
    </div>
</header>


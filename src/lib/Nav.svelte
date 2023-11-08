<script>
    let selectedNavItem = "Home";

    function selectNavItem(item) {
      selectedNavItem = item;
    }
</script>
<!-- Navigation container for the header -->
<nav class="nav-header"> 
     <!-- Unordered list for the navigation menu -->
    <ul class="nav-menu"> 
        <li><a href="/" on:click={() => selectNavItem("Home")} class:selected={selectedNavItem === "Home"}>Home</a></li>
        <li><a href="/gallery" on:click={() => selectNavItem("Gallery")} class:selected={selectedNavItem === "Gallery"}>Gallery</a></li>
        <li><a href="/stats" on:click={() => selectNavItem("Stats")} class:selected={selectedNavItem === "Stats"}>Stats</a></li>
    </ul>
</nav>

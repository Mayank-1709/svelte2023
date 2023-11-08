<script>
  import Nav from "$lib/Nav.svelte";
</script>

<header class="main-header">
  <div class="sub-main-header">
    <div class="site-title-container">
      <div>The</div>
      <div>Ronaldo</div>
      <div>Realm</div>
    </div>
    <div>
      <div class="football-animation">
        <!-- Animated football icon with spinning effect -->
        <i
          class="fa-solid fa-futbol style-icon fa-spin"
          style="font-size:7em"
        />
      </div>
    </div>
    <div class="logo" />
    <!-- Div containing the logo of the website -->
    <div class="nav-container"><Nav /></div>
    <!-- Navigation container using the 'Nav' component -->
  </div>
</header>

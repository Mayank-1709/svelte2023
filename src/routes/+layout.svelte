<!-- Import Svelte components 'Header' and 'Footer' from the specified paths -->
<script>
  import Header from "$lib/Header.svelte";
  import Footer from "$lib/Footer.svelte";
</script>

<svelte:head>
  <!-- Link to the main CSS stylesheet for styling the page -->
  <link rel="stylesheet" href="css/main.css" />

  <!-- Link to the Font Awesome CSS for using icons -->
  <link
    rel="stylesheet"
    href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css"
  />
</svelte:head>

<!-- Include the 'Header' component for the top section of the page -->
<Header />

<slot />
<!-- page content -->

<!-- Include the 'Footer' component for the bottom section of the page -->
<Footer />

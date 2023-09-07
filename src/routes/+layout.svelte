<script>
    import Header from '$lib/Header.svelte' 
    import Footer from '$lib/Footer.svelte' 
</script>

<svelte:head>
    <link rel="stylesheet" href="css/main.css" />
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css" />
</svelte:head>

<Header />

<slot /> <!-- page content -->

<Footer />
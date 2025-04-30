<script>
  import Footer from "$lib/components/footer/footer.svelte";
  import Header from "$lib/components/header/header.svelte";
</script>

<Header />
<!-- mobile header -->

<main>
  <slot />
</main>
<Footer />

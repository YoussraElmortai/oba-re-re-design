<script>
  // components
  import Carousel from "$lib/components/carousel/carousel.svelte";
  import Hero from "$lib/components/hero/hero.svelte";
  import News from "$lib/components/news/news.svelte";
  import Sticky from "$lib/components/sticky/sticky.svelte";
</script>

<section class="hero">
  <Hero />
  <a href="/" class="button"
    >Onze lidmaatschappen <img src="/assets/arrow.svg" /></a
  >
</section>

<section>
  <h2>Onze nieuwste boeken</h2>
  <Carousel />
  <a href="/" class="button"
    >Bekijk onze boekentips <img src="/assets/arrow.svg" /></a
  >
</section>

<section>
  <h2>Het laatste nieuws</h2>

  <News />
  <a href="/" class="button"
    >Meer nieuws van de OBA <img src="/assets/arrow.svg" /></a
  >
</section>

<section>
  <h2>beleef met oba</h2>
  <Sticky />
  <a href="/" class="button"
    >Volledig culturele agenda <img src="/assets/arrow.svg" /></a
  >
</section>

<style>
</style>

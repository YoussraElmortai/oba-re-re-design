<script>
  import { onMount } from 'svelte';

onMount(() => {
    document.addEventListener("DOMContentLoaded", () => {
  const cards = document.querySelectorAll(".card");
  let prevCardHeight = 0;

  cards.forEach((card, index) => {
    if (index > 0) {
      card.style.top = `${prevCardHeight}px`;
      prevCardHeight += card.clientHeight; 
    }
  });
});
});
</script>

<section>
  <h2>Onze nieuwste boeken</h2>
  <!-- carousel -->
</section>

<section>
  <h2>Het laatste nieuws</h2>
</section>

<section class="sticky">
  <h2>beleef met oba</h2>
  <div class="sticky_container">
    <div class="card">Card 1</div>
    <div class="card">Card 2</div>
    <div class="card">Card 3</div>
  </div>
</section>

<style>
  .sticky {
    min-height: fit-content; 
    position: relative;
  }

  .sticky_container {
    position: relative;
    display: flex;
    flex-flow: column;
    gap: 2rem;
    align-items: center;
  }

  .card {
    position: sticky;
    top: 0;
    height: 70vh;
    width: 100%;
    background: #ccc;
    display: flex;
    font-size: 3rem;
    border-radius: 0.5rem;
  }
  .card:nth-child(1) {
    background: #777;
  }
  .card:nth-child(2) {
    background: #555;
  }
  .card:nth-child(3) {
    background: #333;
  }
</style>

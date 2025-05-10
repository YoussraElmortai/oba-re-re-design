<script>
    import { onMount } from "svelte";

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

<div class="sticky_container">
  <article class="card">
    <img src="/assets/senioren-lezen-samen.jpg" alt="" />
    <div class="content">
      <h3>Samen lezen voor senioren</h3>
      <p>
        Samen genieten we van mooie romanfragmenten, pakkende verhalen
        en gedichten. De teksten brengen gesprekken op gang en halen
        persoonlijke herinneringen naar boven. Iedereen kan meedoen en
        voorbereiding is niet nodig!
      </p>
      <ul class="details">
        <li>donderdag 3 april</li>
        <li>10.00 tot 12.00</li>
        <li>OBA Olympisch Kwartier</li>
        <li>toegang gratis | vrije inloop</li>
      </ul>
    </div>
  </article>

  <article class="card">
    <img src="/assets/debat.jpeg" alt="" />
    <div class="content">
      <h3>Boeklezing | Nu de wereld niet meer kijkt</h3>
      <p>
        Samen met Stichting Global South Lens organiseren we een
        boeiende middag met journalist en schrijver Eduard Cousin over
        zijn boeken Nu de wereld niet meer kijkt en Alexandrië. In
        zijn boeken beschrijft Cousin onder meer de vervlogen hoop bij
        veel Egyptenaren na de Arabische Lente, een periode die
        aanvankelijk vol optimisme was maar al snel teleurstelling
        bracht.
      </p>
      <ul class="details">
        <li>Zaterdag 5 april 2025</li>
        <li>16:00 tot 17:30</li>
        <li>OBA Slotermeer</li>
        <li>toegang gratis | aanmelden vereist</li>
      </ul>
    </div>
  </article>

  <article class="card">
    <img src="/assets/voorlezen.jpeg" alt="" />
    <div class="content">
      <h3>Voorlezen en Knutselen 4+</h3>
      <p>
        Voorlezen & Knutselen is een activiteit speciaal voor de
        kleinste creatievelingen. Iedere twee weken nodigen wij
        kinderen van 4 jaar en ouder uit om te genieten van een
        vrolijk verhaal en creatief aan de slag te gaan. Het is een
        moment van plezier, leren en nieuwe ontdekkingen waar de
        kinderen hun fantasie de vrije loop kunnen laten.
      </p>
      <ul class="details">
        <li>Donderdag 10 april 2025</li>
        <li>15:30 tot 16:30</li>
        <li>OBA Duivendrecht</li>
        <li>toegang gratis | vrije inloop</li>
      </ul>
    </div>
  </article>
</div>

<style>
  .sticky_container {
    position: relative;
    display: flex;
    flex-flow: column;
    gap: 2rem;
    margin-bottom: 2rem;
  }

  .card {
    position: sticky;
    top: 0;
    height: fit-content;
    width: 100%;
    background: #f5f5f5;
    display: flex;
    border-radius: 0.5rem;
    flex-flow: column;
    gap: 2rem;
    padding: 1.5rem;

    @media (min-width: 770px) {
      display: grid;
      grid-template-columns: 1fr 1.2fr;
    }

    &:nth-of-type(2n) {
      background: #dfdfdf;
    }

    &:nth-of-type(3n) {
      background: #d0d0d0;
    }

    & img {
      width: auto;
      height: 50%;
      object-fit: cover;
      border-radius: 0.5rem;

      @media (min-width: 770px) {
        width: 100%;
        height: 100%;
      }
    }

    & .content {
      display: flex;
      flex-flow: column;
    }

    & ul {
      list-style: " ";
    }
  }
</style>

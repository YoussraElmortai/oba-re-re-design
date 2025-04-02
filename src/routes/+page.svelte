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

<section>
  <h2>Onze nieuwste boeken</h2>
  <ul>
    <li>
      <img
        src="https://leibniz.zbkb.nl/assets/id/PPN%3A436719541?aid=ob-oba-lokaal-waas&sid=14&dts=1743610608606&sig=c654736f76693c3d4d298d77057b84190c5780cdaa6ac7e3b712ab6ed82407cf&width=100"
        alt=""
      />
      <a href="/">Laat me binnen</a>
      <span class="author">Manon Uphoff</span>
    </li>

    <li>
      <img
        src="https://leibniz.zbkb.nl/assets/id/PPN%3A44175127X?aid=ob-oba-lokaal-waas&sid=14&dts=1743610574120&sig=30745bc28a13c68c33c1586fda7e670da0d0e555cbfb425c5686ccfd99db9685&width=100"
        alt=""
      />
      <a href="/">The women</a>
      <span class="author">Kristin Hannah</span>
    </li>

    <li>
      <img
        src="https://leibniz.zbkb.nl/assets/id/PPN%3A443080828?aid=ob-oba-lokaal-waas&sid=14&dts=1743610574120&sig=d65df853721fa89d6778c6d2d8fbb272b7599da68a740e99bae7a2f91e6dfedf&width=100"
        alt=""
      />
      <a href="/">Eekhoorn en de verbrgen schat</a>
      <span class="author">Coralie Bickford-Smith</span>
    </li>

    <li>
      <img
        src="https://leibniz.zbkb.nl/assets/id/PPN%3A444199365?aid=ob-oba-lokaal-waas&sid=14&dts=1743610574120&sig=9dd7328493e7fcd83ec08fabede40939d7ab01a8882743812ef236b39beecc2a&width=100"
        alt=""
      />
      <a href="/">Togo</a>
      <span class="author">Fiona Rempt</span>
    </li>
  </ul>
  <a href="/" class="button"
    >Bekijk onze boekentips <img src="/assets/arrow.svg" /></a
  >
</section>

<section>
  <h2>Het laatste nieuws</h2>
  <div class="news_container">
    <article class="news">
      <img
        class="news_image"
        src="https://www.oba.nl/dam/nieuws/obaopschoolmbozuid-opening.jpg.rendition.384.614.jpeg"
        alt=""
      />
      <div class="news_content">
        <h3>
          OBA opent eerste mbo-schoolbibliotheek op MBO College Zuid
        </h3>
        <p>
          Gisteren openden we op MBO College Zuid de eerste OBA
          Schoolbibliotheek voor mbo-studenten. Deze samenwerking
          tussen het ROC van Amsterdam (ROCvA)
        </p>
        <a class="inline_link" href="/"
          >lees meer <img src="/assets/arrow.svg" /></a
        >
      </div>
    </article>

    <article class="news">
      <img
        class="news_image"
        src="https://www.oba.nl/dam/nieuws/obaopschoolmbozuid-opening.jpg.rendition.384.614.jpeg"
        alt=""
      />
      <div class="news_content">
        <h3>
          OBA opent eerste mbo-schoolbibliotheek op MBO College Zuid
        </h3>
        <p>
          Gisteren openden we op MBO College Zuid de eerste OBA
          Schoolbibliotheek voor mbo-studenten. Deze samenwerking
          tussen het ROC van Amsterdam (ROCvA)
        </p>
        <a class="inline_link" href="/"
          >lees meer <img src="/assets/arrow.svg" /></a
        >
      </div>
    </article>

    <article class="news">
      <img
        class="news_image"
        src="https://www.oba.nl/dam/nieuws/obaopschoolmbozuid-opening.jpg.rendition.384.614.jpeg"
        alt=""
      />
      <div class="news_content">
        <h3>
          OBA opent eerste mbo-schoolbibliotheek op MBO College Zuid
        </h3>
        <p>
          Gisteren openden we op MBO College Zuid de eerste OBA
          Schoolbibliotheek voor mbo-studenten. Deze samenwerking
          tussen het ROC van Amsterdam (ROCvA)
        </p>
        <a class="inline_link" href="/"
          >lees meer <img src="/assets/arrow.svg" /></a
        >
      </div>
    </article>
  </div>

  <a href="/" class="button"
    >Meer nieuws van de OBA <img src="/assets/arrow.svg" /></a
  >
</section>

<section>
  <h2>beleef met oba</h2>
  <div class="sticky_container">
    <article class="card">
      <img src="/assets/senioren-lezen-samen.jpg" alt="" />
      <div class="content">
        <h3>Samen lezen voor senioren</h3>
        <p>
          Samen genieten we van mooie romanfragmenten, pakkende
          verhalen en gedichten. De teksten brengen gesprekken op gang
          en halen persoonlijke herinneringen naar boven. Iedereen kan
          meedoen en voorbereiding is niet nodig!
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
          boeiende middag met journalist en schrijver Eduard Cousin
          over zijn boeken Nu de wereld niet meer kijkt en Alexandrië.
          In zijn boeken beschrijft Cousin onder meer de vervlogen
          hoop bij veel Egyptenaren na de Arabische Lente, een periode
          die aanvankelijk vol optimisme was maar al snel
          teleurstelling bracht.
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
  <a href="/" class="button"
    >Volledige culturele agenda <img src="/assets/arrow.svg" /></a
  >
</section>

<style>
  .news_container {
    height: fit-content;
    display: flex;
    flex-flow: row wrap;
    gap: 2rem;
    margin-bottom: 2.5rem;
  }

  .news {
    display: flex;
    flex-flow: column;
    gap: 1rem;
    width: 20rem;
    height: 30rem;

    & .news_image {
      height: 15rem;
      object-fit: cover;
      border-radius: 0.5rem;
    }
  }

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
    height: 70vh;
    width: 100%;
    background: #f5f5f5;
    display: flex;
    border-radius: 0.5rem;
    flex-flow: column;
    gap: 2rem;
    padding: 0.5rem;

    @media (min-width: 770px) {
      display: grid;
      grid-template-columns: 1fr 1.2fr;
      width: 60%;
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

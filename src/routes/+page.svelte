<section class="carousel">
  <h2>Onze nieuwste boeken</h2>
  <section class="card_list">
    <article class="card">
      <header class="card_header">
        <h2>Book title</h2>
      </header>
    </article>
    <article class="card">
      <header class="card_header">
        <h2>Book title</h2>
      </header>
    </article>
    <article class="card">
      <header class="card_header">
        <h2>Book title</h2>
      </header>
    </article>
    <article class="card">
      <header class="card_header">
        <h2>Book title</h2>
      </header>
    </article>
    <article class="card">
      <header class="card_header">
        <h2>Book title</h2>
      </header>
    </article>
  </section>
</section>

<section class="news">
  <h2>Het laatse nieuws</h2>
  <div class="news_wrapper">
    <article class="news_card">
      <header class="news_heading">
        <img
          src="https://www.oba.nl/content/dam/noord-holland/amsterdam/nieuws/ouderkerk-feestelijke-opening.jpg.rendition.120.192.jpeg"
          alt=""
        />
        <h3>Feestelijke opening OBA ouderkerk</h3>
      </header>
      <p>
        OBA Ouderkerk gaat weer open na een grondige verbouwing. We
        hebben een moderne bibliotheek gecreëerd die weer jaren mee
        kan.
      </p>
    </article>
    <article class="news_card">
      <header class="news_heading">
        <img
          src="https://www.oba.nl/content/dam/noord-holland/amsterdam/nieuws/ouderkerk-feestelijke-opening.jpg.rendition.120.192.jpeg"
          alt=""
        />
        <h3>Feestelijke opening OBA ouderkerk</h3>
      </header>
      <p>
        OBA Ouderkerk gaat weer open na een grondige verbouwing. We
        hebben een moderne bibliotheek gecreëerd die weer jaren mee
        kan.
      </p>
    </article>
    <article class="news_card">
      <header class="news_heading">
        <img
          src="https://www.oba.nl/content/dam/noord-holland/amsterdam/nieuws/ouderkerk-feestelijke-opening.jpg.rendition.120.192.jpeg"
          alt=""
        />
        <h3>Feestelijke opening OBA ouderkerk</h3>
      </header>
      <p>
        OBA Ouderkerk gaat weer open na een grondige verbouwing. We
        hebben een moderne bibliotheek gecreëerd die weer jaren mee
        kan.
      </p>
    </article>
  </div>
</section>

<style scoped>
  .carousel {
    padding: 2rem;
  }
  .card_list {
    display: flex;
    gap: 1rem;
  }

  .card {
    display: flex;
    position: relative;
    flex-flow: column;
    height: 350px;
    width: 400px;
    min-width: 250px;
    padding: 1.5rem;
    background: grey;
    border-radius: 0.5rem;

    &:hover {
      bottom: 20px;
    }
  }

  .news {
    padding: 2rem;
  }
</style>

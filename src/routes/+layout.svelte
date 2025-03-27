<header>
  <a href="/"
    ><img
      src="https://www.oba.nl/content/dam/logo/oba-logo.png"
      alt="logo"
    /></a
  >
  <ul>
    <li><a href="/">inloggen<img src="/assets/login.svg" /></a></li>
  </ul>
</header>

<nav>
  <ul>
    <li><a href="/">agenda <img src="/assets/calendar.svg" /></a></li>
    <li><a href="/">collectie<img src="/assets/books.svg" /></a></li>
    <li><a href="/">jeugd<img src="/assets/kid.svg" /></a></li>
    <li><a href="/">educatie<img src="/assets/school.svg" /></a></li>
  </ul>
  <div class="magic_line"></div>
</nav>
<main>
  <slot />
</main>

<footer>
  <div class="break" />
  <div class="footer_content">
    <h4>Service</h4>
    <ul>
      <li><a href="/">lidmaatchappen</a></li>
      <li><a href="/">nieuws</a></li>
      <li><a href="/">veelgestelde vragen</a></li>
      <li><a href="/">vestigingen</a></li>
      <li><a href="/">oba school</a></li>
      <li><a href="/">oba next</a></li>
      <li><a href="/">contact</a></li>
    </ul>
  </div>

  <div class="footer_content">
    <h4>zakelijk</h4>
    <ul>
      <li><a href="/">over ons</a></li>
      <li><a href="/">vacatures</a></li>
      <li><a href="/">voor de pers</a></li>
      <li><a href="/">oba congres</a></li>
      <li><a href="/">steun ons</a></li>
    </ul>
  </div>

  <div class="footer_content">
    <ul>
      <li>
        <a aria-label="instagram" href="/"
          ><img
            aria-hidden="true"
            src="/assets/instagram.svg"
            alt=""
          /></a
        >
      </li>
      <li>
        <a aria-label="bluesky" href="/"
          ><img
            aria-hidden="true"
            src="/assets/bluesky.svg"
            alt=""
          /></a
        >
      </li>
      <li>
        <a aria-label="twitter" href="/"
          ><img
            aria-hidden="true"
            src="/assets/twitter.svg"
            alt=""
          /></a
        >
      </li>
      <li>
        <a aria-label="facebook" href="/"
          ><img
            aria-hidden="true"
            src="/assets/facebook.svg"
            alt=""
          /></a
        >
      </li>
      <li>
        <a aria-label="linkedin" href="/"
          ><img
            aria-hidden="true"
            src="/assets/linkedin.svg"
            alt=""
          /></a
        >
      </li>
    </ul>
  </div>

  <div class="footer_content">
    <ul>
      <li><a href="/">privacystatement</a></li>
      <li><a href="/">disclaimer</a></li>
    </ul>
  </div>
</footer>

<style>
  header {
    display: flex;
    flex-flow: row;
    justify-content: space-between;
    align-items: center;
    padding: 2rem 2rem 0;
    font-weight: bold;

    & img {
      height: 2rem;
      width: auto;
    }

    & ul {
      list-style: "";
      display: flex;
      gap: 1rem;

      & a {
        padding-bottom: 0.2rem;
        display: flex;
        align-items: center;
        gap: 0.5rem;
      }
    }
  }

  nav {
    padding: 1.5rem 2rem;
    font-weight: bold;
    & ul {
      list-style: " ";
      display: flex;
      flex-flow: row;
      gap: 1rem;
    }

    & a {
      padding-bottom: 0.2rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }
  }

  .magic_line {
    width: 4rem;
    height: 2px;
    background-color: red;
  }

  footer {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
    padding: 2rem;
    & ul {
      list-style: " ";
      display: flex;
      flex-flow: column;
      gap: 0.5rem;
      font-weight: bold;
    }

    & .footer_content:nth-last-child(2) {
      & ul:first-of-type {
        flex-flow: row;
        align-items: center;
      }
    }
  }

  .break {
    grid-column: span 2;
    width: 100%;
    height: 1px;
    background-color: black;
  }

  .footer_content {
    display: flex;
    flex-flow: column;
    gap: 1rem;
  }
</style>

<header>
  <a href="/"
    ><img
      src="https://www.oba.nl/content/dam/logo/oba-logo.png"
      alt="logo"
    /></a
  >
  <ul>
    <li><a href="/">inloggen</a></li>
    <li><a href="/">english</a></li>
  </ul>
</header>

<nav>
  <ul>
    <li><a href="/">agenda</a></li>
    <li><a href="/">collectie</a></li>
    <li><a href="/">jeugd</a></li>
    <li><a href="/">educatie</a></li>
  </ul>
</nav>
<main>
  <slot />
</main>

<footer>
  <div>
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

  <div>
    <h4>zakelijk</h4>
    <ul>
      <li><a href="/">over ons</a></li>
      <li><a href="/">vacatures</a></li>
      <li><a href="/">voor de pers</a></li>
      <li><a href="/">oba congres</a></li>
      <li><a href="/">steun ons</a></li>
    </ul>
  </div>

  <div>
    <ul>
      <li><a href="/">instagram</a></li>
      <li><a href="/">bluesky</a></li>
      <li><a href="/">twitter</a></li>
      <li><a href="/">facebook</a></li>
      <li><a href="/">linkedin</a></li>
    </ul>
  </div>

  <div>
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
        &:hover {
          border-bottom: solid 2.5px red;
        }
      }
    }
  }

  nav {
    padding: 1.5rem 2rem;
    font-weight: bold;
    & ul {
      list-style: " ";
      display: flex;
      gap: 1rem;
    }

    & a {
      padding-bottom: 0.2rem;
      &:hover {
        border-bottom: solid 2.5px red;
      }
    }
  }

  footer {
    & ul {
      list-style: " ";
      display: flex;
      flex-flow: column;
      gap: 0.5rem;
      font-weight: bold;
    }
  }
</style>

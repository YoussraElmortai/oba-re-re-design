<script>
  import { onMount } from "svelte";

  let magicLine;
  let navItems = [];

  onMount(() => {
    navItems = document.querySelectorAll("[list-item]");
    magicLine = document.querySelector(".magic_line");

    if (navItems.length > 0) {
      navItems[0].classList.add("active");
      updateMagicLine(navItems[0]);
    }

    navItems.forEach((item) => {
      item.addEventListener("mouseenter", handleMouseEnter);
      item.addEventListener("mouseleave", handleMouseLeave);
      item.addEventListener("click", handleClick);
    });

    return () => {
      navItems.forEach((item) => {
        item.removeEventListener("mouseenter", handleMouseEnter);
        item.removeEventListener("mouseleave", handleMouseLeave);
        item.removeEventListener("click", handleClick);
      });
    };
  });

  function handleMouseEnter(e) {
    updateMagicLine(e.currentTarget);
  }

  function handleMouseLeave() {
    const activeItem = document.querySelector("[list-item].active");
    if (activeItem) {
      updateMagicLine(activeItem);
    }
  }

  function handleClick(e) {
    navItems.forEach((i) => i.classList.remove("active"));
    e.currentTarget.classList.add("active");
    updateMagicLine(e.currentTarget);
  }

  function updateMagicLine(element) {
    if (!magicLine) return;

    const itemRect = element.getBoundingClientRect();
    const navRect = element.closest("nav").getBoundingClientRect();

    magicLine.style.width = `${itemRect.width}px`;
    magicLine.style.left = `${itemRect.left - navRect.left}px`;
  }
</script>

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
    <li list-item>
      <a href="/">home <img src="/assets/calendar.svg" /></a>
    </li>
    <li list-item>
      <a href="/agenda">agenda <img src="/assets/calendar.svg" /></a>
    </li>
    <li list-item>
      <a href="/collectie">collectie<img src="/assets/books.svg" /></a>
    </li>
    <li list-item>
      <a href="/jeugd">jeugd<img src="/assets/kid.svg" /></a>
    </li>
    <li list-item>
      <a href="/educatie">educatie<img src="/assets/school.svg" /></a>
    </li>
  </ul>
  <div class="magic_line"></div>
</nav>

<main>
  <slot />
</main>

<footer>
  <div class="break"></div>
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
      <li><a href="/">privacystatement</a></li>
      <li><a href="/">disclaimer</a></li>
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
    position: relative;
    padding: 1.5rem 2rem;
    font-weight: bold;
    & ul {
      position: relative;
      list-style: " ";
      display: flex;
      flex-flow: row;
      gap: 1.5rem;
    }

    & a {
      padding-bottom: 0.5rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }
  }

  .magic_line {
    position: absolute;
    height: 2px;
    background-color: red;
    transition: all 0.3s ease-out;
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

      & li:hover{
        color: red;
      }
    }

    & .footer_content:nth-last-child(1) {
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

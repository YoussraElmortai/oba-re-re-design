<script>
  import { onMount } from "svelte";

  let magicLine;
  let navItems = [];
  let mobileMenuOpen = false;

  onMount(() => {
    // Only initialize for desktop nav
    const desktopNav = document.querySelector(".desktop-nav");
    if (desktopNav) {
      navItems = desktopNav.querySelectorAll("[list-item]");
      magicLine = desktopNav.querySelector(".magic_line");

      // Set initial magic line styles
      if (magicLine) {
        magicLine.style.opacity = "1";
      }

      if (navItems.length > 0 && magicLine) {
        navItems[0].classList.add("active");
        updateMagicLine(navItems[0]);
      }

      navItems.forEach((item) => {
        item.addEventListener("mouseenter", handleMouseEnter);
        item.addEventListener("mouseleave", handleMouseLeave);
        item.addEventListener("click", handleClick);
      });
    }

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
    mobileMenuOpen = false;
  }

  function updateMagicLine(element) {
    if (!magicLine) return;

    const itemRect = element.getBoundingClientRect();
    const navRect = element.closest("nav").getBoundingClientRect();

    magicLine.style.width = `${itemRect.width}px`;
    magicLine.style.left = `${itemRect.left - navRect.left}px`;
  }

  function toggleMobileMenu() {
    mobileMenuOpen = !mobileMenuOpen;
  }

  function handleClickOutside(event) {
    const mobileNav = document.querySelector(".mobile-nav");
    const menuButton = document.querySelector(".mobile-menu-toggle");

    if (
      mobileMenuOpen &&
      !mobileNav.contains(event.target) &&
      !menuButton.contains(event.target)
    ) {
      mobileMenuOpen = false;
    }
  }
</script>

<svelte:window on:click={handleClickOutside} />

<header>
  <a href="/">
    <img
      class="logo"
      src="https://www.oba.nl/content/dam/logo/oba-logo.png"
      alt="logo"
    />
  </a>

  <div class="mobile-menu-container">
    <button class="mobile-menu-toggle" on:click={toggleMobileMenu}>
      <img
        src="/assets/hamburger.svg"
        alt="hamburger menu"
        class="menu-icon"
      />
    </button>
  </div>

  <ul class="desktop-login">
    <li><a href="/">inloggen<img src="/assets/login.svg" /></a></li>
  </ul>
</header>

<!-- Mobile menu component later -->
<div class="mobile-menu-wrapper" class:open={mobileMenuOpen}>
  <nav class="mobile-nav">
    <ul>
      <li list-item>
        <a href="/">home <img src="/assets/home.svg" /></a>
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
      <li class="login-mobile">
        <a href="/">inloggen<img src="/assets/login.svg" /></a>
      </li>
    </ul>
  </nav>
</div>

<!-- Desktop navigation -->
<nav class="desktop-nav">
  <ul>
    <li list-item>
      <a href="/">home <img src="/assets/home.svg" /></a>
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

<style>
  header {
    display: flex;
    flex-flow: row;
    justify-content: space-between;
    align-items: center;
    padding: 2rem 2rem 0;
    font-weight: bold;
    position: relative;
    z-index: 10;
    background: white;
  }

  .logo {
    height: 4rem;
  }

  header img:not(.menu-icon) {
    height: 2rem;
    width: auto;
  }

  .menu-icon {
    height: 2rem;
    width: auto;
  }

  header ul {
    list-style: none;
    display: flex;
    gap: 1rem;
  }

  header a {
    padding-bottom: 0.2rem;
    display: flex;
    align-items: center;
    gap: 0.5rem;
    text-decoration: none;
    color: inherit;
  }

  nav {
    font-weight: bold;
  }

  nav.desktop-nav {
    position: relative;
    padding: 1.5rem 2rem;
  }

  nav.desktop-nav ul {
    position: relative;
    list-style: none;
    display: flex;
    flex-flow: row;
    gap: 1.5rem;
  }

  nav.desktop-nav a {
    position: relative;
    padding-bottom: 0.5rem;
    display: flex;
    align-items: center;
    gap: 0.5rem;
  }

  .magic_line {
    position: absolute;
    height: 2px;
    background-color: red;
    transition: all 0.5s ease;
    opacity: 0;
  }

  /* Mobile menu styles */
  .mobile-menu-container {
    position: relative;
  }

  .mobile-menu-toggle {
    background: none;
    border: none;
    cursor: pointer;
    padding: 0.5rem;
    display: none;
  }

  .mobile-menu-wrapper {
    position: fixed;
    top: -100%;
    left: 0;
    width: 100%;
    background: white;
    border-radius: 0.5rem;
    box-shadow: 0 4px 6px rgba(46, 44, 44, 0.176);
    z-index: 5;
    transition: top 0.3s ease-out;
    overflow: hidden;
  }

  .mobile-menu-wrapper.open {
    top: 0;
  }

  .mobile-nav {
    width: 100%;
    padding: 1rem 2rem;
    padding-top: 6rem;
    margin: 0 auto;
  }

  .mobile-nav ul {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .mobile-nav a {
    padding: 0.5rem 0;
    display: flex;
    align-items: center;
    gap: 0.5rem;
  }

  .login-mobile {
    display: none;
    border-top: 1px solid #eee;
    margin-top: 1rem;
    padding-top: 1rem;
  }

  .desktop-login {
    display: flex;
  }

  @media (max-width: 768px) {
    .mobile-menu-toggle {
      display: block;
    }

    .desktop-nav {
      display: none;
    }

    .desktop-login {
      display: none;
    }

    .login-mobile {
      display: block;
    }
  }

  @media (min-width: 769px) {
    .mobile-menu-wrapper {
      display: none;
    }
  }
</style>
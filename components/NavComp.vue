<template>
  <div>
    <nav>
      <div class="staging"><p>Staging</p></div>
      <div class="navbar container" :class="showMenu ? 'show-mobile-menu' : ''">
        <div class="logo">
          <img
            src="https://ik.imagekit.io/fawaazfaris/forever-shashi/forever-shashi/forever-shashi-logo.png"
            alt=""
          />
        </div>
        <div>
          <ul>
            <a @click="toggleMenu" href="#hero"><li>Home</li></a>
            <a @click="toggleMenu" href="#about"><li>About</li></a>
            <a @click="toggleMenu" href="#vision"><li>Vision</li></a>
            <a @click="toggleMenu" href="#our-work"><li>Our Work</li></a>
            <a @click="toggleMenu" href="#values"><li>Our Values</li></a>
            <a @click="toggleMenu" href="#join-us"><li>Join Us</li></a>
            <a @click="toggleMenu" href="#contact-us"><li>Contact Us</li></a>
          </ul>
        </div>
      </div>
      <div class="mobile-menu-button" @click="toggleMenu">
        <img
          src="https://ik.imagekit.io/fawaazfaris/forever-shashi/forever-shashi/menu-black.png"
          alt=""
        />
      </div>
    </nav>
  </div>
</template>

<script setup>
let showMenu = ref(false);

function toggleMenu() {
  showMenu.value = !showMenu.value;
}
</script>

<style lang="scss" scoped>
.staging {
  background-color: #191919;
  color: white;
  text-align: center;
  p {
    text-align: center;
    padding: 0.2em;
    text-transform: uppercase;
    margin: 0;
  }
}
nav {
  position: fixed;
  background-color: white;
  z-index: 999;
  width: 100%;
}
.navbar {
  padding: 1em;
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100vw;

  .logo {
    width: 6em;
    height: auto;

    img {
      width: 100%;
      object-fit: contain;
    }
  }

  ul {
    list-style: none;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 1.5em;

    a {
      font-weight: 700;
      text-transform: uppercase;
      font-size: 0.9rem;
      text-decoration: none;
      color: #191919;
      font-family: "Montserrat", sans-serif;
    }
  }
}
.mobile-menu-button {
  display: none;
}

@media (max-width: 35em) {
  .navbar {
    width: 100vw;
    height: 100vh;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 2em;
    position: fixed;
    background-color: white;
    left: -110vw;
    transition: all 0.2s ease-in;

    ul {
      flex-direction: column;
      justify-self: center;
      align-items: center;
      padding: 0;
      gap: 2em;
      a {
        font-size: 1.2rem;
      }
    }
  }
  .mobile-menu-button {
    display: block;
    position: fixed;
    top: 2em;
    right: 2em;
    width: 1.5em;
    height: 1.5em;
    border-radius: 50%;
    border: 5px solid #191919;
    background-color: white;
    padding: 0.5em;

    img {
      width: 100%;
      object-fit: contain;
    }
  }

  .show-mobile-menu {
    left: 0;
  }
}
</style>

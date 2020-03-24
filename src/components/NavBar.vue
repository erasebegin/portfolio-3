<template>
  <div id="nav" class="nav">
    <router-link to="/" class="nav-link home-link"
      ><h4>
        Chris Haupt's
      </h4>
      <h1>
        Portfolio
      </h1></router-link
    >
    <div class="nav-subsection">
      <router-link to="/about" class="nav-link sub-link"
        ><h4>
          About
        </h4></router-link
      >
      <router-link to="/contact" class="nav-link sub-link"
        ><h4>
          Contact
        </h4></router-link
      >
    </div>
  </div>
</template>

<style scoped>
.nav {
  overflow: hidden;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  font-family: "Amatic SC", cursive;
  text-align: center;
  padding: 3em 0;
}

.nav-link {
  text-decoration: none;
  transition: 200ms;
  color: rgb(17, 17, 17);
}

.nav-link:hover {
  transform: scale(1.02, 1.02);
  text-shadow: 2px 1px 4px #ebebeb;
  transition: 200ms;
}

.nav-link:visited {
  color: rgb(17, 17, 17);
}

.nav-subsection {
  display: flex;
  margin: 1em 0;
}

.sub-link {
  border: 1px dashed black;
  border-radius: 50%;
  padding: 1em;
  margin: 1em;
}

.sub-link:hover {
  text-shadow: 1px 1px 2px #ebebeb;
}

h1 {
  font-size: 8rem;
}

h4 {
  font-size: 4rem;
}
</style>

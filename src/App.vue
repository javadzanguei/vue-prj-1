<template>
  <header>
    <h2>Tab Menu</h2>
  </header>

  <main>
    <div class="container">
      <NavTab :tabs="tabs1"></NavTab>
      <NavTab :tabs="tabs2"></NavTab>
    </div>
  </main>
</template>

<style>
@import './assets/base.css';

#app {
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem;

  font-weight: normal;
}

header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

a,
.green {
  text-decoration: none;
  color: hsla(160, 100%, 37%, 1);
  transition: 0.4s;
}

@media (hover: hover) {
  a:hover {
    background-color: hsla(160, 100%, 37%, 0.2);
  }
}

@media (min-width: 1024px) {
  body {
    display: flex;
    place-items: center;
  }

  #app {
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding: 0 2rem;
  }

  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  .logo {
    margin: 0 2rem 0 0;
  }
}
</style>
<script>
import NavTab from "./components/NavTab.vue";
  export default {
    components : {
      NavTab,
    },
    data() {
      return { 
        tabs1 : [
          {
            id : 'home',
            name : 'Home',
            content : 'Home tab content',
          },
          {
            id : 'profile',
            name : 'Profile',
            content : 'Profile tab content',
          },
          {
            id : 'contact',
            name : 'Contact',
            content : 'Contact tab content',
          },
        ],
        tabs2 : [
          {
            id : 'mobile',
            name : 'Mobile',
            content : 'Mobile tab content',
          },
          {
            id : 'laptop',
            name : 'Laptop',
            content : 'Laptop tab content',
          },
        ]
      }
    },
  }
</script>
<template>
  <header>
    <h2>Tab Menu</h2>
  </header>

  <main>
    <div class="container ">
      <ul class="nav nav-tabs" id="myTab" role="tablist">
          <li v-for="(tab, index) in tabs" class="nav-item" role="presentation">
            <button class="nav-link" :class="{'active' : activeTab === index}" id="{{tab.id}}-tab" type="button" @click="changeActiveTab(index)">{{tab.name}}</button>
          </li>
        </ul>
        <div class="tab-content p-3" id="myTabContent">
          <div v-for="(tab, index) in tabs" class="tab-pane fade" :class="{'show active' : activeTab === index}" id="{{tab.id}}" role="tabpanel">{{tab.content}}</div>
        </div>
    </div>
  </main>
</template>

<style>
@import './assets/base.css';

* {
  padding: 5px 7px;
  margin: 7px;
}

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
  export default {
    data() {
      return { 
        activeTab : 0,
        tabs : [
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
        ]
       }
    },
    methods : {
      changeActiveTab(index) {
        this.activeTab = index
      }
    }
  }
</script>
<template>
  <ul class="nav nav-tabs" id="myTab" role="tablist">
    <li v-for="(tab, index) in tabs" class="nav-item" role="presentation">
      <button class="nav-link" :class="{'active' : activeTab === index}" id="{{tab.id}}-tab" type="button" @click="changeActiveTab(index)">{{tab.name}}</button>
    </li>
  </ul>
  <div class="tab-content p-3" id="myTabContent">
    <div v-for="(tab, index) in tabs" class="tab-pane fade" :class="{'show active' : activeTab === index}" id="{{tab.id}}" role="tabpanel">{{tab.content}}</div>
  </div>
</template>

<script>
export default {
  name : "NavTab",
  props : {
    tabs : {
      type : Array,
      required : true,
    },
  },
  data() {
    return {
      activeTab : 0,
    }
  },
  methods : {
    changeActiveTab(index) {
      this.activeTab = index
    }
  }
}
</script>

<style scoped>

</style>
<template>
  <ul>
    <li v-for="tab in tabs" :class="{ 'is-active': tab.isActive }">
      <span @click="selectTab(tab.name)">{{ tab.name }}</span>
    </li>
  </ul>
  <div id="text">
    <p v-if="activeTab == 'Info'">
      Lorem Ipsum is simply dummy text of the printing and typesetting industry.
      Lorem Ipsum has been the industry's standard dummy text ever since the
      1500s, when an unknown printer took a galley of type and scrambled it to
      make a type specimen book. It has survived not only five centuries, but
      also the leap into electronic typesetting, remaining essentially
      unchanged. It was popularised in the 1960s with the release of Letraset
      sheets containing Lorem Ipsum passages, and more recently with desktop
      publishing software like Aldus PageMaker including versions of Lorem
      Ipsum.
    </p>
    <p v-else-if="activeTab == 'Phone'">I AM PHONE INFO</p>
    <p v-else-if="activeTab == 'Email'">I AM Email INFO</p>
    <p v-else-if="activeTab == 'GitHub'">I AM GitHub INFO</p>
    <p v-else-if="activeTab == 'LinkedIn'">I AM LinkedIn INFO</p>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      tabs: [
        { name: "Info", isActive: true },
        { name: "Phone", isActive: false },
        { name: "Email", isActive: false },
        { name: "GitHub", isActive: false },
        { name: "LinkedIn", isActive: false },
      ],
      activeTab: "Info",
    };
  },
  components: {},
  methods: {
    selectTab(selectedTab) {
      this.activeTab = selectedTab;

      this.tabs.forEach((tab) => {
        tab.isActive = tab.name == selectedTab;
      });
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
ul {
  border-bottom: 2px solid gray;
  display: flex;
  justify-content: space-between;
  width: 50%;
  margin: auto;
  padding: 10px 0;
}
#text {
  width: 50%;
  margin: auto;
  padding: 30px 0;
}

li {
  list-style: none;
  padding: 0 40px;
  border-right: 2px solid gray;
  cursor: pointer;
}
ul :last-child {
  border: none;
}
.is-active {
  background-color: cadetblue;
}
</style>

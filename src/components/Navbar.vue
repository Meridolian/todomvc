<template>
  <div class="navbarContainer">
    <div class="title">
      <button class="titleButton">TODO MVC</button>
    </div>

    <div class="routes">
      <button class="route" v-for="route in routes" :key="route.name">{{ route.name }}</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navbar",
  props: {},
  data() {
    return {
      routes: [
        { name: "Settings" },
        { name: "Search" },
        { name: "Todos List" },
      ],
    };
  },
};
</script>

<style scoped>
.navbarContainer {
  width: 100%;
  height: 7.5vh;
  background-color: rgba(0, 0, 0, 0.75);
  color: white;
  border-radius: 10px;
}

button {
  height: 100%;
  width: 100%;
  background-color: rgba(0, 0, 0, 0);
  color: white;
  cursor: pointer;
  border: none;
  border-radius: 10px;
  outline: none !important;
  box-shadow: none !important;
}
button:hover {
  background-color: rgba(255, 255, 255, 0.25);
}

.title {
  height: 100%;
  width: 20%;
  float: left;
}
.titleButton {
  font-size: 35px;
}

.routes {
	float: right;
  height: 100%;
  width: 80%;
}
.route {
  float: right;
  width: 15%;
  font-size: 25px;
}
</style>
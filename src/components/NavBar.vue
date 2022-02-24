<template>
  <div class="container">
    <div class="title-icon-container">
      <div class="icons-titles">
        <i class="fa-solid fa-list-ol fa-xl"></i>
      </div>

      <h2>TodosApp</h2>
    </div>
    <div v-show="homePage" class="search-container">
      <i class="fa-solid fa-magnifying-glass"></i>
      <input type="text" placeholder="Search a Todo..." />
    </div>
    <div class="links-container">
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
    </div>
  </div>
</template>
<script>
export default {
  name: "NavBarComponent",
  computed: {
    homePage() {
      if (this.$route.path === "/") {
        return true;
      } else {
        return false;
      }
    },
  },
};
</script>
<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Ubuntu:wght@300&display=swap");
.container {
  display: flex;
  justify-content: space-between;
  background-color: #ffffff;
  height: 55px;
  width: 100%;
  border-bottom: 1px solid #d8d8d8;
}

.title-icon-container {
  display: flex;
  justify-content: center;
  align-items: center;
}
.title-icon-container h2 {
  font-family: "Ubuntu", sans-serif;
  color: rgb(0, 0, 0);
}
.fa-list-ol {
  color: rgb(255, 255, 255);
  padding: 16px 4px;
  margin: 0px 8px;
  background-color: rgba(32, 107, 196, 255);
  border-radius: 15px 30px 45px;
}

.search-container {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 0.4375rem 0.75rem;
  margin: 10px 8px;
  border: 1px solid #d8d8d8;
  border-radius: 5px;
}

.search-container:hover {
  outline: 3px solid rgba(110, 207, 255, 0.6);
}
.search-container input {
  font-family: "Ubuntu", sans-serif;
  outline: none;
  border: none;
  margin: 0px 10px;
}
.fa-magnifying-glass {
  color: #999ba0;
  cursor: pointer;
}

.fa-magnifying-glass:hover {
  color: #7d7f83;
}

.links-container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0px 7px;
}

.links-container a {
  text-decoration: none;
  font-family: "Ubuntu", sans-serif;
  padding: 5px 10px;
  color: rgb(105, 130, 160);
  font-weight: 600;
}

.links-container a:hover {
  color: rgb(30, 74, 128);
}
</style>

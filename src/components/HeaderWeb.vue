<template>
  <div>
    <nav class="menu">
      <li>EMISORAS</li>
      <li>PODCASTS</li>
      <li>MI LISTA</li>
      <li>BUSQUEDA</li>
    </nav>
  </div>
</template>

<script>
export default {
    name: 'HeaderWeb'
}
</script>

<style scoped>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

.menu {
  background-color: #455a64;
  height: 80px;
  width: 100%;
  display: flex;
  justify-content: space-around;
}

li {
    align-content: center;
    list-style: none;
}

.menu > li:hover {
  background-color: #fff;
  color: #000;
  cursor: pointer;
  height: 100%;
}
</style>

<template>
  <nav class="menu">
    <div class="menu-item menu-left">
      <span class="menu-link">about</span>
      <span class="menu-link">contact</span>
    </div>
    <div class="menu-item menu-center">
      <div class="brand-logo">skeletons</div>
    </div>
    <div class="menu-item menu-right">
      <div class="search-icon">
        <box-icon name='search'></box-icon>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Nav"
}
</script>

<style scoped>
nav {
  width: 100%;
  height: 100px;
  margin: 0 auto;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: flex-start;
  align-items: center;
  text-transform: uppercase;
  font-family: "Monument Extended";
}

.menu-item {
  flex: 1;
}

.menu-left {
  text-align: left;
  margin-left: 4em;
}

.menu-center {
  text-align: center;
}

.menu-right {
  text-align: right;
  margin-right: 4em;
}

.menu-link {
  padding: 0 30px;
}

</style>
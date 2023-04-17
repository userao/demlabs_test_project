<template>
  <div class="status-bar">
    <div v-for="item in statusBarItems" :key="item.id" class="status-bar__item">
      <span>{{ item.title }}</span
      ><span
        :class="{
          'status-bar__item__indicator': true,
          online: item.online,
          offline: !item.online,
        }"
      ></span>
    </div>
  </div>
</template>
  
<script>
export default {
  data: () => ({
    statusBarItems: [
      { title: 'Cellnet', online: true, id: 1 },
      { title: 'Mainnet', online: true, id: 2 },
      { title: 'Somenet', online: true, id: 3 },
      { title: 'Testnet', online: true, id: 4 },
    ],
  }),
}
</script>

<style scoped>
.status-bar {
  display: flex;
  justify-content: space-evenly;
  width: 100%;
  background: #2e3138;
  box-shadow: 5px -5px 10px rgba(8, 7, 13, 0.42), inset 1px 1px 0px #524d64;
  border: solid 1px #49455a;
  border-right: none;
  border-bottom: none;
}

.status-bar__item {
  padding: 0.85rem 0;
  color: #fff;
}

.status-bar__item__indicator {
  margin-left: 0.5rem;
  display: inline-block;
  width: 0.5rem;
  aspect-ratio: 1 / 1;
  border-radius: 50%;
}

.online {
  background: radial-gradient(#fff, #a9e81c 40%);
}

.offline {
  background: radial-gradient(#fff, red 40%);
}
</style>


<template>
  <div class="sidebar flex">
    <div class="logo flex">
      <img src="~/assets/images/Logo.png" />
      <p>CELLFRAME</p>
    </div>
    <ul class="menu-list">
      <li
        v-for="option in menuOptions"
        :key="option.title"
        :data-option="option.title"
        :class="{
          'menu-list__option': true,
          flex: true,
          'active-option': option.title === activeOption,
        }"
        @click="() => handleClick(option.title)"
      >
        <img :src="require(`~/assets/images/${option.iconFileName}.png`)" />
        <p>{{ option.title }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data: () => ({
    activeOption: 'Certificates',
    menuOptions: [
      { title: 'Wallet', iconFileName: 'wallet' },
      { title: 'DEX', iconFileName: 'dex' },
      { title: 'TX explorer', iconFileName: 'tx-explorer' },
      { title: 'Certificates', iconFileName: 'certificates' },
      { title: 'Tokens', iconFileName: 'tokens' },
      { title: 'VPN Client', iconFileName: 'vpn-client' },
      { title: 'VPN Service', iconFileName: 'vpn-service' },
      { title: 'Console', iconFileName: 'console' },
      { title: 'Logs', iconFileName: 'logs' },
      { title: 'Settings', iconFileName: 'settings' },
      { title: 'dApps', iconFileName: 'dapps' },
    ],
  }),
  computed: {
    iconPath() {
      const paths = this.menuOptions.reduce((paths, item) => {
        const path = `~/assets/${item.iconFileName}.png`
        return { ...paths, [item.title]: path }
      }, {})
      return paths
    },
  },
  methods: {
    getIconPath(filename) {
      return `~/assets/wallet.png`
    },
    handleClick(optionName) {
      this.activeOption = optionName
    },
  },
}
</script>

<style scoped>
.sidebar {
  grid-row-start: span 3;
  width: 180px;
  flex-direction: column;
  margin-bottom: 5px;
  border: solid 1px #49455a;
  border-right: none;
  border-bottom: none;
  border-radius: 0 0 1rem 0;
  box-shadow: 5px -5px 10px rgba(8, 7, 13, 0.42), inset 1px 1px 0px #524d64;
}

.logo {
  color: #fff;
  align-items: center;
  gap: 0.5rem;
  padding: 20px 0 20px 24px;
}
.menu-list {
  padding: 0;
  color: #fff;
}
.menu-list__option {
  align-items: center;
  gap: 1rem;
  margin-right: 10px;
  padding: 1.125rem 0 1.125rem 1.5rem;
  list-style: none;
  font-size: 13px;
}

.menu-list__option > p {
  line-height: 1;
}

.active-option {
  border: solid 1px #49455a;
  border-top: none;
  border-radius: 0px 1rem 1rem 0px;
  box-shadow: 1px 1px 0px rgba(107, 102, 126, 0.49),
    inset 3px 3px 5px rgba(8, 7, 13, 0.25);
}
</style>
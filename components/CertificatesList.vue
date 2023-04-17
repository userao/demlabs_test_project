<template>
  <div class="certificates-list">
    <p class="certificates-list__header">Certificates</p>
    <ul class="certificates-list__items">
      <li class="certificates-list__category-name">Public</li>
      <li
        v-for="certificate in publicCertificates"
        :key="certificate.name"
        class="certificates-list__item"
      >
        {{ certificate.name }}
      </li>
    </ul>
    <ul class="certificates-list__items">
      <li class="certificates-list__category-name">Private</li>
      <li
        v-for="certificate in privateCertificates"
        :key="certificate.name"
        class="certificates-list__item"
      >
        {{ certificate.name }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data: () => ({
    certificates: [
      { name: 'Commodo cupidatat ut.', private: true },
      { name: 'Nostrud nulla fugiat.', private: false },
      { name: 'Dolore incididunt adipisicing.', private: true },
      { name: 'Amet sint adipisicing.', private: false },
      { name: 'Ex tempor veniam.', private: false },
      { name: 'Nostrud consectetur et.', private: true },
      { name: 'Quis Lorem dolore.', private: false },
      { name: 'Voluptate veniam pariatur.', private: true },
      { name: 'Magna qui cupidatat.', private: false },
      { name: 'Velit ex reprehenderit.', private: true },
    ],
  }),
  computed: {
    privateCertificates() {
      return this.certificates.filter((certificate) => certificate.private)
    },
    publicCertificates() {
      return this.certificates.filter((certificate) => !certificate.private)
    },
  },
}
</script>

<style scoped>
.certificates-list {
  grid-row-start: span 2;
  width: 95%;
  padding-inline: 1rem;
  place-self: center;
  background: #363a42;
  border-radius: 12px;
  box-shadow: 1px 1px 0px rgba(107, 102, 126, 0.49),
    inset 3px 3px 5px rgba(8, 7, 13, 0.25);
  color: #fff;
}

.certificates-list__header {
  font-weight: 700;
  padding: 12px 0;
}
.certificates-list__items {
  list-style: none;
}

.certificates-list__category-name {
  font-weight: 500;
  font-size: 13px;
  position: relative;
  box-sizing: content-box;
  padding: 8px 0;
  background: #2e3138;
}

.certificates-list__category-name::before,
.certificates-list__category-name::after {
  content: '';
  display: block;
  position: absolute;
  background: #2e3138;
  height: 100%;
  width: 1rem;
  top: 0;
  bottom: 0;
}
.certificates-list__category-name::before {
  left: -1rem;
}
.certificates-list__category-name::after {
  right: -1rem;
}
.certificates-list__item {
  padding: 12px 0;
  line-height: 24px;
  border-bottom: 1px solid #2e3138;
}

.certificates-list li:last-child {
  border-bottom: none;
}
</style>
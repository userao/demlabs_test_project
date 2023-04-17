<template>
  <div class="filters">
    <h5 class="filters__header">Filter</h5>
    <label class="input-group"
      >Public certificates
      <input
        id="show-public-certificates"
        v-model="shownCertificates"
        type="radio"
        value="show-public-certificates"
      />
      <span class="checkmark" />
    </label>
    <label class="input-group"
      >Private certificates
      <input
        id="show-private-certificates"
        v-model="shownCertificates"
        type="radio"
        value="show-private-certificates"
      />
      <span class="checkmark" />
    </label>
    <label class="input-group"
      >Both
      <input
        id="show-both"
        v-model="shownCertificates"
        type="radio"
        value="show-both"
      />
      <span class="checkmark" />
    </label>
  </div>
</template>

<script>
export default {
  data: () => ({
    shownCertificates: 'show-both',
  }),
}
</script>

<style scoped>
.filters {
  color: #fff;
  align-self: center;
  margin-left: 20px;
}

.input-group {
  display: block;
  position: relative;
  margin-bottom: 2rem;
  cursor: pointer;
  padding-left: 2rem;
}

.filters__header {
  font-size: 14px;
  font-weight: 700;
  padding-bottom: 1.5rem;
}

.input-group input {
  cursor: default;
  position: absolute;
  opacity: 0;
  height: 0;
  width: 0;
}

.input-group label {
  cursor: pointer;
}

.checkmark {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  height: 20px;
  width: 20px;
  border-radius: 50%;
  background: #2d3037;
  box-shadow: 2px 2px 5px rgba(8, 7, 13, 0.42),
    inset 1px 1px 3px rgba(77, 85, 99, 0.52);
}

.input-group input:checked ~ .checkmark {
  background: linear-gradient(90deg, #7930de 0%, #7f65ff 100%);
}

.input-group input:checked ~ .checkmark:after {
  background: #363a42;
}

.checkmark:after {
  content: '';
  position: absolute;
  top: 7px;
  left: 7px;
  width: 6px;
  height: 6px;
  background: #717580;
  border-radius: 50%;
}
</style>
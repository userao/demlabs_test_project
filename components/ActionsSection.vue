<template>
  <div class="actions">
    <h5 class="actions__header">Actions</h5>
    <button
      class="button active"
      @mouseenter="handleHover"
      @mouseleave="handleHover"
      @mousedown="handleClick"
      @mouseup="handleClick"
    >
      Create certificate
    </button>
    <button
      class="button active"
      @mouseenter="handleHover"
      @mouseleave="handleHover"
      @mousedown="handleClick"
      @mouseup="handleClick"
    >
      Import certificate
    </button>
    <button class="button disabled" disabled>
      Export private certificate to public
    </button>
    <button class="button disabled" disabled>
      Export certificate to mempool
    </button>
    <button class="button disabled" disabled>Delete certificate</button>
  </div>
</template>

<script>
export default {
  methods: {
    handleClick: (e) => {
      e.target.classList.toggle('clicked')
    },
    handleHover: (e) => {
      e.target.classList.toggle('hover')
    },
  },
}
</script>

<style scoped>
.actions {
  color: white;
  margin-left: 20px;
}

.actions__header {
  font-size: 14px;
  font-weight: 700;
  margin-bottom: 24px;
}

.button {
  width: 90%;
  display: block;
  border: none;
  border-radius: 30px;
  font-size: 14px;
  color: white;
  line-height: 24px;
  margin-bottom: 20px;
  padding: 6px 0;
}

.active {
  background: linear-gradient(230.15deg, #9580ff 0%, #a361ff 92.48%);
  box-shadow: 2px 2px 7px rgba(11, 10, 13, 0.44), inset 1px 1px 4px #f1e7ff;
}

.hover {
  background: linear-gradient(230.15deg, #9580ff 0%, #bd91fc 92.48%);
}

.clicked {
  background: linear-gradient(90deg, #7930de 0%, #7f65ff 100%);
}

.disabled {
  cursor: normal;
  background: #b0aeb9;
  box-shadow: 2px 2px 7px rgba(11, 10, 13, 0.44),
    inset 1px 1px 4px rgba(241, 231, 255, 0.3);
}
</style>
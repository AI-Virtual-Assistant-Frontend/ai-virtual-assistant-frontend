<template>
  <div class="backdrop">
    <div class="popup">
      <header class="popup-header">
        <slot name="header"></slot>
        <button
          type="button"
          class="btn-close"
          @click="close"
        >
          X
        </button>
      </header>

      <section class="popup-body">
        <slot name="body"></slot>
      </section>

      <footer class="popup-footer">
        <slot name="footer"></slot>
        <button
          type="button"
          class="btn-footer"
          @click="close"
        >
          Close
        </button>
      </footer>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Popup',
  methods: {
    close() {
      this.$emit('close');
    }
  }
}
</script>

<style scoped>
.backdrop {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: rgba(0, 0, 0, 0.3);
  display: flex;
  justify-content: center;
  align-items: center;
}

.popup {
  background: #FFFFFF;
  box-shadow: 2px 2px 20px 1px;
  overflow-x: auto;
  display: flex;
  flex-direction: column;
}

.popup-header,
.popup-footer {
  padding: 15px;
  display: flex;
}

.popup-header {
  position: relative;
  border-bottom: 1px solid #eeeeee;
  color: #4AAE9B;
  justify-content: space-between;
}

.popup-footer {
  border-top: 1px solid #eeeeee;
  flex-direction: column;
  justify-content: flex-end;
}

.popup-body {
  position: relative;
  padding: 20px 10px;
}

.btn-close {
  position: absolute;
  top: 0;
  right: 0;
  border: none;
  font-size: 20px;
  padding: 10px;
  cursor: pointer;
  font-weight: bold;
  color: #4AAE9B;
  background: transparent;
}

.btn-footer {
  color: white;
  background: #4AAE9B;
  border: 1px solid #4AAE9B;
  border-radius: 2px;
}
</style>
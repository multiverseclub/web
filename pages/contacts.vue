<template>
  <div class="main-content">
    <div class="contacts">
      <a href="mailto:">multiverse.controlroom@gmail.com</a>

      <br />
      <a href="https://www.instagram.com/multiverseclubit/"
        >@multiverseclubit</a
      >
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.main-content {
  height: 100vh;
  display: flex;
  align-items: center;

  .contacts {
    flex-direction: row;
    margin: auto;
    text-align: center;
  }

  a {
    font-size: 144px;
  }
}
</style>

<template>
  <div>
    <h1 align="center" style="font-size: 50px">
      {{ $t('educationLanding.aboutUsTitle') }}
    </h1><br>

    <div class="container">
      <p class="centered-text">
        {{ $t('educationLanding.aboutUs_desc') }}
      </p>
    </div><br>
  </div>
</template>

<style scoped lang="scss">
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  //height: 10vh; 
  margin: 0;
}
.centered-text {
  text-align: left;
  max-width: 700px;
  font-size: 20px
}
</style>

<script>

</script>
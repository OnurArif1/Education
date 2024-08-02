<template>
  <div>
    <h1 align="center">
      {{ $t('educationLanding.ielts_title') }}
    </h1><br>

    <div class="container">
      <p class="centered-text">
        {{ $t('educationLanding.ielts_subDesc') }}
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
}
</style>

<script>
</script>
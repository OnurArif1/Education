<template>
  <div>
    <h1 align="center">
      {{ $t('educationLanding.general_title') }}
    </h1><br>

    <div class="container">
      <p class="centered-text">
        {{ $t('educationLanding.general_detailDesc') }}
      </p>
    </div><br>

    <div class="container">
      <p class="centered-text">
        {{ $t('educationLanding.general_detailDesc2') }}
      </p>
    </div><br>

    <div class="container">
      <p class="centered-text">
        {{ $t('educationLanding.general_detailDesc3') }}<a href="https://www.leicester.gov.uk">(https://www.leicester.gov.uk)</a>
      </p>
    </div><br>

    <div class="container">
      <p class="centered-text">
        {{ $t('educationLanding.general_detailDesc4') }}<a href="https://leicesterlanguageacademy.co.uk">(https://leicesterlanguageacademy.co.uk)</a>
      </p>
    </div>
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

<template>
  <div>
    <h1 align="center">
      {{ $t('educationLanding.academic_title') }}
    </h1><br>

    <div class="container">
      <p class="centered-text">
        {{ $t('educationLanding.academic_subDesc') }}
      </p>
    </div><br>
    <div class="container">
      <ul class="list-style">
        <li>{{ $t('educationLanding.academic_subDesc2') }}</li>
        <li>{{ $t('educationLanding.academic_subDesc3') }}</li>
        <li>{{ $t('educationLanding.academic_subDesc4') }}</li>
        <li>{{ $t('educationLanding.academic_subDesc5') }}</li>
        <li>{{ $t('educationLanding.academic_subDesc6') }}</li>
      </ul>
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

ul.list-style {
  padding-left: 20px; 
  margin: 0; 
  list-style-type: disc; 
}


ul.list-style li {
  display: list-item; 
}
</style>

<script>
</script>
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

/* Liste stili */
ul.list-style {
  padding-left: 20px; /* Liste işaretlerinin sağında boşluk bırakır */
  margin: 0; /* Liste içi margin'i sıfırla */
  list-style-type: disc; /* Liste işaretlerini belirle */
}

/* Liste elemanlarını alt alta göstermek için */
ul.list-style li {
  display: list-item; /* Varsayılan olarak list-item olur, ama kesinlik kazandırır */
}
</style>

<script>
</script>
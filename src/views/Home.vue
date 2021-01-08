<template>
  <div class="home">
    <Titulo texto="¿Telegram es bueno?" />
    <Telegram />
  </div>
</template>

<script>
// @ is an alias to /src
import Telegram from '../components/LogoTelegram';
import Titulo from '../components/Titulo';
export default {
  name: 'Home',
  components: {
    Titulo,
    Telegram
  }
}
</script>

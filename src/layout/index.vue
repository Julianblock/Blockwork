<template>
    <div>
      <Sidebar />
      <Header />
    </div>
</template>

<script>
import Sidebar from './Sidebar/index.vue';
import Header from './Header/index.vue';

export default {
  name: 'app',
  components: {
    Sidebar,
    Header
  }
}
</script>
<template>
  <q-toolbar>
    <img :src="`./src/assets/logo/logo.png`" class="rounded-circle" />

    <q-toolbar-title> Anna Prata </q-toolbar-title>

    <q-icon name="account_circle" size="2em"></q-icon>
  </q-toolbar>
</template>

<script>
export default {
  name: 'HeaderMenu',
  data() {
    return {};
  },
};
</script>

<style>
.rounded-circle {
  border-radius: 50%;
  width: 40px;
  height: 40px;
  object-fit: cover;
}
</style>

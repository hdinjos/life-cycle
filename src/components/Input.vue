<template>
  <div>
      <label>Nama</label>
      <input v-model="name" type="text"/>
      <label>Alamat</label>
      <input v-model="address" type="password"/>
      <p>{{name}}</p>
      <p>{{address}}</p>
      <Input :name="name"/>
  </div>
</template>

<script>
import Input from '@/components/input';

export default {
    data: () => {
        return {
            name: 'Ferry',
            address: 'Semarang'
        }
    },
    components: {
        Input
    }
}
</script>

<style>

</style>
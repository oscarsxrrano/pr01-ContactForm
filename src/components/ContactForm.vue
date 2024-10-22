<script setup>
  import { ref } from 'vue'

  // variables reactives
  const name = ref('')
  const number = ref('')

  // emit
  const emit = defineEmits(['add-contact'])

  // agregar nuevo ontacto
  const addContact = () => {
    if (name.value && number.value) {
      // hacer un emit al component pare
      emit('add-contact', { name: name.value, number: number.value})

      name.value = ''
      number.value = ''
    }
  }

</script>

<template>
  <div>
    <!--formulari per afegir els contactes-->
    <input v-model="name" placeholder="Escriu el nom..."/>
    <input v-model="number" placeholder="Escriu el número de teléfon..."/>
    <button @click="addContact">Afegir contacte</button>

  </div>
</template>

<style scoped>
  
</style>
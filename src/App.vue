<script setup>
  import { ref } from 'vue'

  const contactName = ref('')
  const contactNumber = ref ('')

  // Afegir contacte
  const addContact = () => {
    if (contactName.value && contactNumber.value) {
      console.log('Nou contacte:', {
        name: contactName.value,
        number: contactNumber.value
      })

      // Limpiar el formulario
      contactName.value = ''
      contactNumber.value = ''
    }
  }
</script>

<template>
  <div>
    <h1>Llibreta de Contactes</h1>

    <!--formulari per afegir els contactes-->
    <input v-model="contactName" placeholder="Escriu el nom..."/>
    <input v-model="contactNumber" placeholder="Escriu el número de teléfon..."/>
    <button @click="addContact">Afegir contacte</button>

  </div>
</template>

<style scoped>
body {
  background-color: rgb(168, 233, 241);
}
</style>

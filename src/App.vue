<script setup>
  // imports vue
  import { ref } from 'vue'
  import ContactForm from './components/ContactForm.vue';
  
  // array contactes
  const contacts = ref([])

  // funcion para añadir el contacto al array
  const addContact = (newContact) => {
    contacts.value.push(newContact)
  }
</script>

<template>
  <div>
    <h1>Llibreta de Contactes</h1>

    <ContactForm @add-contact="addContact"></ContactForm>

    <!--llista de contactes-->
    <ul>
      <li v-for="(contact, index) in contacts" :key="index">
        {{ contact.name }} - <span id="numero">{{ contact.number }}</span>
      </li>
    </ul>
  </div>
</template>

<style scoped>
  #numero {
    color: rgb(75, 161, 133);
  }

  div {
    background-color: blanchedalmond;
  }

</style>

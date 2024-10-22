<script setup>
  // imports vue
  import { ref, computed } from 'vue'
  import ContactForm from './components/ContactForm.vue';
  
  // array contactes
  const contacts = ref([])

  // busqueda relativa
  const buscar = ref('')

  // funcion para añadir el contacto al array
  const addContact = (newContact) => {
    contacts.value.push(newContact)
  }

  // funcion para filtrar por nombre
  const filtrar = computed(() => {
    return contacts.value.filter(contact => 
      contact.name.toLowerCase().includes(buscar.value.toLowerCase())
    )
  })
</script>

<template>
  <div class="divTop">
    <h1>Llibreta de Contactes</h1>


    <!--llamamos al hijo aquí-->
    <ContactForm @add-contact="addContact"></ContactForm>

    <!--busqueda-->
    <input class="inputBuscar"  v-model="buscar" placeholder="Buscar per nom..."/>

    <!--llista de contactes-->
    <ul>
      <li v-for="(contact, index) in filtrar" :key="index">
        {{ contact.name }} - <span id="numero">{{ contact.number }}</span>
      </li>

    </ul>
  </div>
</template>

<style scoped>
  #numero {
    color: rgb(75, 161, 133);
  }

  .divTop {
    background-color: rgb(253, 210, 146);
    padding: 2%;
    border-radius: 5px;
    box-shadow: 5px 5px 5px 5px rgb(63, 51, 32) ;
  }

</style>

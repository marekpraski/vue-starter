<template>
   <div>
       <label>Zaloguj si� e-mailem</label>
       <input type="email" v-model="email">
       <button @click="enter()">Wchodz�</button>
   </div>
</template>

<script>

export default {
 data() {
     return {
         email: ''
     }
 },
 methods: {
     enter() {
         this.$emit('login', this.email);
     }
 }
}
</script>
<template>
<div H1>
	Witaj w systemie zapisów
	<p>{{email}}</p>
	<!--  <div H2>{{email}}</div> -->
	<!--  <div H2>{{password}}</div> -->



	<button @click="logMeIn">Wchodzę</button>
	<div v-if="isAuthenticated">
		Zalogowany jako {{email}} <a  @click="logMeOut()">wyloguj mnie</a>
	</div>
	<div v-else>
		<login-form @login="enter($event)" :button-label="'Wejdź'"></login-form>

	</div>

	<div
		<!--  <div v-if="email.length < 10">Ale masz krótki adres!</div>
<div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
<div v-else>Twój adres e-mail jest stanowczo za długi.</div> -->
	</div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
export default {
components: {LoginForm},
 data() {
	 return {
		 email: '',
		 isAuthenticated: false,
		// password: "krótkie hasło"
	 }
 },
 methods: {
	 alertMyEmail() {
		    alert(this.email);
		  },
	logMeIn() {
			  this.isAuthenticated=true;
			  
		  },
		  logMeOut(){
			 this.isAuthenticated=false;
			 this.email='';
		  },
		  enter() {
			  this.$emit('login',this.email);
		  }
		 
 }
}
</script>

<style>
h1 {
	font-size: 10px
}
</style>

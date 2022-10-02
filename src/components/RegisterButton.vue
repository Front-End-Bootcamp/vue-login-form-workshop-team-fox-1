<script setup>
import { ref } from "vue";

const isRegister = ref({
	fullname: "",
	email: "",
	phone: "",
	password: "",
	passwordconfirm: "",
});

</script>

<template>
	<from @submit.prevent="isRegister" >
		<input type="text" v-model="name" placeholder="Full Name" />
		<input type="email" v-model="email" placeholder="Email" />
		<input type="text" v-model="phone" placeholder="Phone" />
		<input type="password" v-model="password" placeholder="Password" />
		<input type="password" v-model="passwordconfirm" placeholder="Confirm Password" />
		<button submit="register">Register</button>
	</from>
</template>

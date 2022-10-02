<script setup>
import InputFullName from "@/components/Inputs/InputFullName.vue";
import InputMail from "@/components/Inputs/InputMail.vue";
import InputPhone from "@/components/Inputs/InputPhone.vue";
import InputPassword from "@/components/Inputs/InputPassword.vue";
import RegisterButton from "@/components/Buttons/RegisterButton.vue";
import LoginButton from "@/components/Buttons/LoginButton.vue";

import { ref } from "vue";
const isLogin = ref(true);
const fullName = ref("");
const email = ref("");
// const registerInfo = ref({
// 	fullName: null,
// 	email: null,
// 	phone: null,
// 	password: null,
// });
</script>

<template>
	{{ fullName }} {{ email }}
	<form @submit.prevent="isLogin">
		<template v-if="isLogin === true">
			<InputFullName v-model:name="fullName" />
			<InputMail v-model:email="email" />
			<InputPhone />
			<InputPassword />
			<InputPassword />
			<RegisterButton />
		</template>
		<template v-else>
			<InputMail />
			<InputPassword />
			<LoginButton />
		</template>
	</form>
</template>

<script setup>
import { ref } from "vue";

// const props = defineProps(["username", "password"]);

const loginInfos = ref({
	username: null,
	password: null,
});

loginInfos.value.username = localStorage.getItem("username");
loginInfos.value.password = localStorage.getItem("password");

const isLogin = (e) => {
	if (
		e.target[0].value === loginInfos.value.username &&
		e.target[1].value === loginInfos.value.password
	) {
		alert("Giriş Başarılı");
	} else alert("Girdiğiniz bilgileri kontrol edin!");
	e.target[0].value = "";
	e.target[1].value = "";
};
</script>

<template>
	{{ loginInfos.username }}
	{{ loginInfos.password }}

	<form @submit.prevent="isLogin">
		<input type="text" name="username" id="username" placeholder="username" />
		<input type="text" name="password" id="password" placeholder="password" />
		<button class="loginBtn" type="submit">LOGIN</button>
	</form>
</template>

<style scoped>
.loginBtn {
	background: #252eff;
	padding: 0.3rem 1rem;
	text-align: center;
	color: #fafafa;
	border: none;
	border-radius: 12px;
}
</style>

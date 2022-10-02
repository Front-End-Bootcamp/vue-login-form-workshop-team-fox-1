<script setup>
const props = defineProps(['password']);
const emit = defineEmits(['password']);

const passwordHandler = event => {
	console.log('passwordHandler' , /^(?=.*\d)(?=.*[!@#$%^&*])(?=.*[a-z])(?=.*[A-Z]).{8,}$/
	.test(event.target.value))
}

</script>


<template>
	<form>
		<label ></label>
		<input class="from__input" type="password" name="password" id="password"
		placeholder="Password" :value="password" @input="passwordHandler">
	</form>
</template>
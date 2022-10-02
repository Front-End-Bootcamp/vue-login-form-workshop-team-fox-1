<script setup>
import { computed } from "vue";
const props = defineProps(["phone", "label"]);
const emit = defineEmits(["update:phone"]);
const phoneHandler = (event) => {
	emit("update:phone", event.target.value);
};
const isValid = computed(() => {
	return /^(\([0-9]{3}\) |[0-9]{3}-)[0-9]{3}-[0-9]{4}/.test(props.phone);
});
</script>

<template>
	<div class="form__wrapper">
		<label class="form__label">{{ label }}</label> <br />
		<input
			class="form__input"
			type="phone"
			name="phone"
			id="phone"
			:value="phone"
			@input="emailHandler"
			:placeholder="isValid ? '' : 'Boş geçilmez.'"
		/>
		<p v-if="!isValid">Boş geçmeyiniz.</p>
	</div>
</template>

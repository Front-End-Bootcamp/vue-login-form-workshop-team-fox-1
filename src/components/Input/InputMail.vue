<script setup>
import { computed } from "vue";
const props = defineProps(["email", "label"]);
const emit = defineEmits(["update:email"]);

const emailHandler = (event) => {
	emit("update:email", event.target.value);
};

const isValid = computed(() => {
	return /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(props.email);
});
</script>

<template>
	<div class="">
		<label class=""></label> <br />
		<input
			class=""
			type="email"
			name="email"
			id="email"
			:value="email"
			@input="emailHandler"
			:placeholder="isValid ? '' : 'Email'"
		/>
		<p v-if="!isValid">Boş geçmeyiniz.</p>
	</div>
</template>

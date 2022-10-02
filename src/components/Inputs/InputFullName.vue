<script setup>
import { computed } from "vue";
const props = defineProps(["name", "placeholder"]);
const emit = defineEmits(["update:name"]);

const isValid = computed(() => {
	return props.name.length > 1;
});
const nameHandler = (event) => {
	emit("update:name", event.target.value);
};
</script>

<template>
	<div>
		<input
			class="form__input"
			type="text"
			name="name"
			id="name"
			:value="name"
			@input="nameHandler"
			:placeholder="placeholder"
		/>

		<p v-if="!isValid">bos gecilemez</p>
	</div>
</template>

<script setup>
import {ref, computed} from "vue"
import NameComp from './components/Input/NameComp.vue';

const name = ref("")
</script>

<template>
	<NameComp v-model:name="name" placeholder="Full Name" ></NameComp>
</template>

<style scoped>
</style>

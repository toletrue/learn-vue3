<template>
	<label class="form-label" id="child-id">
		{{ label }}
	</label>
	<input v-model="value" v-bind="$attrs" type="text" class="form-control" />
</template>

<script setup>
import { computed } from 'vue';

const props = defineProps(['modelValue', 'label']);
const emit = defineEmits(['update:modelValue']);

const value = computed({
	get() {
		return props.modelValue;
	},
	set(value) {
		emit('update:modelValue', value);
	},
});
</script>

<style lang="scss" scoped></style>

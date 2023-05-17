<template>
	<div class="card">
		<div class="card-header">
			<slot name="header">#Header</slot>
		</div>
		<div class="card-body">
			<slot :child-message="childMessage" hello-message="안녕하세요"
				>#Body</slot
			>
		</div>
		<div class="card-footer text-muted">
			<slot name="footer">#Footer {{ childMessage }}</slot>
		</div>
	</div>
</template>

<script setup>
import { ref } from 'vue';

const childMessage = ref('자식 컴포넌트 메시지');
</script>

<style lang="scss" scoped></style>

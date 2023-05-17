<template>
	<main>
		<div class="container py-4">
			<MyButton class="my-button" id="my-button" @click="sayHello"></MyButton>
			<LabelInput label="이름" data-id="id입니다."></LabelInput>
			<hr />
			<FancyButton>Click!!<span style="color: red">@@@</span></FancyButton>
			<FancyButton></FancyButton>
			<hr />
			<AppCard>
				<!-- <template #[slotArgs]>제목입니다.</template> -->
				<!-- <template #default>내용입니다.</template> -->
				<!-- 암시적으로 Default 슬롯입니다.
				<template #footer>푸터입니다.</template> -->
				<template #default="{ childMessage, helloMessage }">
					Default입니다. {{ message }}
					<br />
					{{ childMessage }}
					<br />
					{{ helloMessage }}
				</template>
			</AppCard>
		</div>
	</main>
</template>

<script setup>
import MyButton from './MyButton.vue';
import LabelInput from './LabelInput.vue';
import FancyButton from './FancyButton.vue';
import AppCard from './AppCard.vue';
import { ref } from 'vue';

const sayHello = () => {
	alert('안녕하세요!');
};

const slotArgs = ref('header');

const message = ref('안녕하세요!!!');
</script>

<style lang="scss" scoped></style>

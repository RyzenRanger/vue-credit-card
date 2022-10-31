<template>
	<vue-flip
		:active-hover = "true"
		width					= "400px"
		height				= "250px"
	>
		<template v-slot:front>
			true
		</template>
		<template v-slot:back >
			false
		</template>
	</vue-flip>
</template>

<script>
import VueFlip from 'vue-flip';

export default {
	name: 'credit-card',

	components: { 'vue-flip': VueFlip },
}
</script>

<style lang = 'scss'>
.front {
	background-color: red;
}

.back {
	background-color: white;
}
</style>

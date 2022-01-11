<template>
	<div>
		<h1>SignUp</h1>
		<SignupForm></SignupForm>
	</div>
</template>
<script>
import SignupForm from "@/components/SignupForm.vue"

export default {
	name: "signup",
	components: {
		SignupForm,
	},
	data() {
		return {
			sampleData: "",
		}
	},
	beforeCreate() {},
	created() {},
	beforeMount() {},
	mounted() {},
	beforeUpdate() {},
	updated() {},
	beforeUnmount() {},
	unmounted() {},
	methods: {},
}
</script>

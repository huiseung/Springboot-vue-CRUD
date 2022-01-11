<template>
	<form @submit.prevent="submitForm">
		<div>
			<label for="username">id: </label>
			<input id="username" type="text" v-model="username" />
		</div>
		<div>
			<label for="password">pw: </label>
			<input id="password" type="password" v-model="password" />
		</div>
		<div>
			<label for="nickname">nickname: </label>
			<input id="nickname" type="text" v-model="nickname" />
		</div>
		<button type="submit">signup</button>
		<p>{{ logMessage }}</p>
	</form>
</template>
<script>
import { registerUser } from "@/api/index"

export default {
	name: "",
	components: {},
	data() {
		return {
			username: "",
			password: "",
			nickname: "",
			logMessage: "",
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
	methods: {
		async submitForm() {
			const userData = {
				username: this.username,
				password: this.password,
				nickname: this.nickname,
			}
			try {
				const { data } = await registerUser(userData)
				console.log(data)
				this.logMessage = `${data.username} 님이 가입되었습니다`
			} catch (error) {
				console.log(error)
				this.logMessage = "error"
			}
			this.initForm()
		},

		initForm() {
			this.username = ""
			this.password = ""
			this.nickname = ""
		},
	},
}
</script>

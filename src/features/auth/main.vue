<template>
	<div>
		<div class="login-wrap">
			<div class="login-html">
				<input id="tab-1" type="radio" v-model="navigation" value="signin" @change="navigate"  name="tab" class="sign-in" checked>
				<label for="tab-1" class="tab">Sign In</label>
				
				<input id="tab-2" type="radio" v-model="navigation" value="signup" @change="navigate"  name="tab" class="sign-up">
				<label for="tab-2" class="tab">Sign Up</label>

				<div class="login-form">

					<sign-in @do-sign-in="doSignIn"/>
					<sign-up @do-sign-up="doSignUp"/>
				</div>
			</div>
		</div>
		<p style="text-align: center">
			<a href="https://github.com/lucianobragaweb/vue-login">See the project repository</a>
		</p>
	</div>
</template>

<script>
	import SignIn from './sign-in'
	import SignUp from './sign-up'

	export default {
		data(){
			return {
				navigation: 'signin'
			}
		},
		components: {
			SignIn,
			SignUp
		},
		methods: {
			doSignIn(obj){
				// simulando uma chamada ajax
				window.console.log(obj)
			},
			doSignUp (obj) {
		        // fingir que há uma chamada AJAX
		        window.console.log(obj)
		      },
			navigate() {
				this.$bus.$emit('navigate', this.navigation)
			}
		}
	}
</script>

<style src="./styles.css"></style>

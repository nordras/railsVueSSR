<style scoped>
 .login-footer {
 background-color: #e6e6e6;
 }
</style>
<template>
 <div class="bg-white rounded text-wktext">
	 <form :action="action" method="post">
		 <div class="rounded-t py-4 px-5 bg-blue">
		 	<span class="text-base text-white text-wktext-bold">Welcome, please login</span>
		 </div>
		 <div class="my-10 mx-8">
			 <input name="authenticity_token" type="hidden" v-bind:value="token">
			 <div class="relative block w-full mb-10 material-input">
				 <input class="block text-lg p-2 w-full border-0 border-b-2 border-grey-dark focus:outline-none" type="text" name="user[email]" required v-model.trim="$v.email.$model">
				 <span class="relative block bar"></span>
				 <label class="block text-lg absolute pointer-events-none">Email</label>
				 <span class="form-text text-danger" v-if="$v.email.$error">Campo inválido.</span>
			 </div>
			 <div class="relative block w-full mb-10 material-input">
				 <input class="block text-lg p-2 w-full border-0 border-b-2 border-grey-dark focus:outline-none" type="password" name="user[password]" required v-model.trim="$v.password.$model">
				 <span class="relative block bar"></span>
				 <label class="block text-lg absolute pointer-events-none">Password</label>
				 <span class="form-text text-danger" v-if="$v.password.$error">Campo inválido.</span>
			 </div>
		 </div>
		 <div class="login-footer rounded-b py-5 px-12">
		 	<input type="submit" value="Log In" class="text-base text-white py-2 px-3 rounded w-full cursor-pointer bg-blue" :disabled="$v.$invalid">
		 </div>
	 </form>
 </div>
</template>
<script>
	import { required, email } from 'vuelidate/lib/validators'
 export default {
  props: ['action', 'token'],
  data() {
   	return {
     	email: "",
     	password: ""
   	}
 	},
  validations: {
    email: {
      required,
      email
    },
    password: {
      required
    }
  }
 }
</script>
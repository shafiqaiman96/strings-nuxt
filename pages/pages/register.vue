<template>
<div>
  <div class="app flex-row align-items-center">
    <div class="container">
      <b-row class="justify-content-center">
        <b-col md="6" sm="8">
          <b-card no-body class="mx-4">
            <b-card-body class="p-4">
              <h1 class="text-center">Join us now!</h1>
              <p class="text-center">Create your account</p><br>
              <b-input-group class="mb-3">
                <b-input-group-prepend>
                  <b-input-group-text><i class="icon-user"></i></b-input-group-text>
                </b-input-group-prepend>
                <input type="text" class="form-control" placeholder="Username">
              </b-input-group>

              <b-input-group class="mb-3">
                <b-input-group-prepend>
                  <b-input-group-text>@</b-input-group-text>
                </b-input-group-prepend>
                <input type="text" class="form-control" placeholder="Email">
              </b-input-group>

              <b-input-group class="mb-3">
                <b-input-group-prepend>
                  <b-input-group-text><i class="icon-lock"></i></b-input-group-text>
                </b-input-group-prepend>
                <input  class="form-control" placeholder="Password" :id='{valid:passwordValidation.valid}' :type="passwordVisible ? 'text' : 'password'" v-model="password">
				<button class="visibility" tabindex='-1' @click='togglePasswordVisibility' :arial-label='passwordVisible ? "Hide password" : "Show password"'>
			<i class="material-icons">{{ passwordVisible ? "hide" : "show" }}</i>
		</button>
			  </b-input-group>

              <b-input-group class="mb-4">
                <b-input-group-prepend>
                  <b-input-group-text><i class="icon-lock"></i></b-input-group-text>
                </b-input-group-prepend>
                <input class="form-control" placeholder="Repeat password"  type="text" v-model.lazy='checkPassword'>
              </b-input-group>


	<!-- <div class="password"><b-input-group-text style="height:35px;  border-radius: 5px 0px 0px 5px;"><i class="icon-lock"></i></b-input-group-text>
		<input :class='{valid:passwordValidation.valid}' :type="passwordVisible ? 'text' : 'password'" v-model="password">
		<button class="visibility" tabindex='-1' @click='togglePasswordVisibility' :arial-label='passwordVisible ? "Hide password" : "Show password"'>
			<i class="material-icons">{{ passwordVisible ? "hide" : "show" }}</i>
		</button>
	</div> -->
	<!-- <div class="password">
	<b-input-group-text style="height:35px;  border-radius: 5px 0px 0px 5px;"><i class="icon-lock"></i></b-input-group-text>
	<input type="password" v-model.lazy='checkPassword'>
	</div> -->

	<transition name="hint" appear>
		<div v-if='passwordValidation.errors.length > 0 && !submitted' class='hints'>
			<h2>Hints</h2>
			<p v-for='error in passwordValidation.errors' v-bind:key="error.id">{{error}}</p>
		</div>
	</transition>
	
	<div class="matches" v-if='notSamePasswords'>
		<p>Passwords don't match.</p>
	</div>
	


              	<b-button variant="success" block @click='resetPasswords' v-if='passwordsFilled && !notSamePasswords && passwordValidation.valid' style="width: 130px; float: right">
		Create Account
	</b-button>
            </b-card-body>
            <!-- <b-card-footer class="p-4">
              <b-row>
                <b-col cols="6">
                  <b-button block class="btn btn-facebook"><span>facebook</span></b-button>
                </b-col>
                <b-col cols="6">
                  <b-button block class="btn btn-twitter" type="button"><span>twitter</span></b-button>
                </b-col>
              </b-row>
            </b-card-footer> -->
          </b-card>
        </b-col>
      </b-row>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'Register',
  layout: 'clean',
  data () {
		return {
			rules: [
				{ message:'One lowercase letter required.', regex:/[a-z]+/ },
				{ message:"One uppercase letter required.",  regex:/[A-Z]+/ },
				{ message:"8 characters minimum.", regex:/.{8,}/ },
				{ message:"One number required", regex:/[0-9]+/ },
				{ message:"One special character required. ~!@#$%^&*()_-", regex:/[~!@#$%^&*()_-]+/ }
			],
			password:'',
			checkPassword:'',
			passwordVisible:false,
			submitted:false
		}
	},
	methods: {
		resetPasswords () {
			this.password = ''
			this.checkPassword = ''
			this.submitted = true
			setTimeout(() => {
				this.submitted = false
			}, 2000)
		},
		togglePasswordVisibility () {
			this.passwordVisible = !this.passwordVisible
		}	
	},
	computed: {
		notSamePasswords () {
			if (this.passwordsFilled) {
				return (this.password !== this.checkPassword)
			} else {
				return false
			}
		},
		passwordsFilled () {
			return (this.password !== '' && this.checkPassword !== '')
		},
		passwordValidation () {
			let errors = []
			for (let condition of this.rules) {
				if (!condition.regex.test(this.password)) {
					errors.push(condition.message)
				}
			}
			if (errors.length === 0) {
				return { valid:true, errors }
			} else {
				return { valid:false, errors }
			}
		}
	}
}
</script>

<style lang="scss" scoped>
$bgColor:#3A81C8;
$color:#D4DEDF;
	
	
body {
	padding:1em;
	background-color:$bgColor;
	color:$color;
}

[v-cloak] {
	opacity:0;
}

#app {
	max-width:600px;
	margin: 0 auto;
}

.hints {
	max-width:600px;
	opacity: 0.8;
	border-radius: 10px;
	padding-bottom:1em;
	padding-left:1em;
	padding-top:5px;
	background:rgb(61, 255, 61);
	margin: 1em 0;
	font-size: .9em;
	color:darken(rgb(0, 0, 0), 50%);
	h2 {
		margin: .5em 0 .2em 0;
	}
	p {
		margin: 0;
		padding-left:1em;
		&::before {
			content:">";
			font-size:.9em;
			margin-right:6px;
			display:inline-block;
		}
	}
}

.visibility {
	all:unset;
	// background:whitesmoke;
	display:inline-block;
	color:$bgColor;
	padding-left: 15px;
	// vertical-align:center;
}

.material-icons {
	font-size: 1em;
}
.password {
	display:flex;
	align-items:center;
	padding-bottom: 15px;
}

input, button {
	padding:6px;
	display: block;
    width: 80%;
    height: calc(1.5em + 0.75rem + 2px);
    padding: 0.375rem 0.75rem;
    font-size: 0.875rem;
    font-weight: 400;
    line-height: 1.5;
    color: #3e515b;
    background-color: #fff;
    background-clip: padding-box;
    border: 1px solid #c2cfd6;
    border-radius: 0;
    transition: border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
}
input + button {
	font-size: .85em;
}
// [type=password], [type=text] {
// 	color:#D4DEDF;
// 	border:1px solid transparent;

// 	margin:6px 10px 6px 0;
// 	&.valid {
// 		border:1px solid whitesmoke;
// 	}
// }
[type=password] {
	// letter-spacing:.2em;
}

.hint {
	&-enter {
		opacity:0;
		transform:translate3d(-20px,0,0);
	}
	&-leave-to {
		opacity:0;
		transform:translate3d(0, 20px, 0);
	}
	&-enter-active {
		transition:300ms;
	}
	&-leave-active {
		transition:400ms;
	}
}
</style>
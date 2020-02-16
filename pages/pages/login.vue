<template>
<div style="background-color: #C5CCCB "><img src="https://strings.my/wp-content/uploads/2019/10/strings-9.png" style="width:200px; float: left; padding: 20px">
  <div class="app flex-row align-items-center">
    <div class="container">
      <b-row class="justify-content-center">
        <b-col md="8">
          <b-card-group>
            <b-card no-body class="p-4">
              <b-card-body>
                <h1 class="text-center">Welcome Back!</h1>
                <p class="text-center">Sign In to your account</p>
                <b-input-group class="mb-3">
                  <b-input-group-prepend><b-input-group-text><i class="icon-user"></i></b-input-group-text></b-input-group-prepend>
                  <input type="text" class="form-control" placeholder="Username">
                </b-input-group>
                <b-input-group class="mb-4">
                  <b-input-group-prepend><b-input-group-text><i class="icon-lock"></i></b-input-group-text></b-input-group-prepend>
                  <input type="password" class="form-control" placeholder="Password">
                </b-input-group>
                <b-row>
                  <b-col cols="6">
                    <b-button variant="success" class="px-4" style="border-radius: 5px"><nuxt-link to="/" style="color: white">Login</nuxt-link></b-button>
                  </b-col>
                  <b-col cols="6" class="text-right">
                    <b-button variant="link" class="px-0" style="color: red">Forgot password?</b-button><br>
                  </b-col>
                </b-row>
              </b-card-body>
            </b-card>
            <b-card no-body class="text-white bg-green py-5 d-md-down-none" style="width:44%">
              <b-card-body class="text-center">
                <div>
                  <h2>Sign up</h2>
                  <p>Strings is supported by the Open Bank Project (OBP) as our partner to provide a proven API platform to banks. Through the use of OBP APIs, we connect financial institutions and Third Party Providers (TPP) to bank ecosystems.</p><br>
                  <b-button variant="orange" class="px-4" style="border-radius: 5px"><nuxt-link to="/pages/register" style="color: white">Register Now!</nuxt-link></b-button>
                </div>
              </b-card-body>
            </b-card>
          </b-card-group>
        </b-col>
      </b-row>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'Login',
  layout: 'clean'
}
</script>

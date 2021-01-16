<template>
  <section class="container-fluid">
        <div class="row justify-content-center">
            <div class="col-lg-4">
                <div class="login-panel bg-white text-left">
                    <h2 class="display-3 font-weight-bold">Login</h2>
                    <p class="font-weight-bold">Welcome back</p>
                    <br>
                    <form action="" @submit="getData" method="post">
                        <div class="form-group">
                            <label class="input-label">Email</label>
                            <input type="email" class="form-control" placeholder="Email" name="email" v-model="gets.email">
                        </div>
                        <div class="form-group">
                            <label class="input-label">Password</label>
                            <input type="password" class="form-control" placeholder="Password" name="password" v-model="gets.password">
                        </div>
                        <br>
                        <div class="form-group d-flex justify-content-center">
                            <button class="btn btn-primary w-25" id="login" type="submit" @click="getData">Login</button>
                        </div>
                    </form>
                    <div class="form-group d-flex justify-content-center">
                      <router-link class="nav-item" to="/userregistration">New User Registration <br> Click here</router-link>
                            <!-- <button class="btn btn-primary w-25" id="New User" to="/userregistration">New User Click here</button> -->
                        </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import Vue from 'vue'
import axios from 'axios'
import VueAxios from 'vue-axios'
Vue.use(VueAxios, axios)
export default {
  name: 'Login',
  data () {
    return {
      gets: {
        email: '',
        password: ''
      },
      url: 'http://10.177.1.51:8083/users/find/'
    }
  },
  methods: {
    getData (e) {
      e.preventDefault()
      this.axios.get(`${this.url}/${this.gets.email}/${this.gets.password}`, this.gets)
        .then((result) => {
          console.warn(this.gets)
        }).catch(error => console.log(error))
    }
  }
}
</script>

<style lang="scss" scoped>
.display-3{
  font-size: 45px;
}
.widget {
    margin: 0;
    height: unset;
}
.login-panel {
    position: relative;
    padding: 60px 0;
    .alert {
        opacity: 0;
        position: absolute;
        width: 100%;
        top: 100px;
        transition: all .5s;
        &.alert-primary {
            background-color: #007BFF;
            color: #fff;
            font-size: 18px;
            border: none;
        }
        .widget {
            position: absolute;
            right: 5px;
            top: 0;
            margin: 10px;
        }
    }
}
</style>

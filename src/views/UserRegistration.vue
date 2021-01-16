<template>
  <section class="container-fluid">
        <div class="row justify-content-center">
            <div class="col-lg-4">
                <div class="login-panel bg-white text-left">
                    <h1 class="display-3 font-weight-bold">New User Registration</h1>
                    <br>
                    <form action="" @submit="postData" method="post">
                      <div class="form-group">
                            <label class="input-label">User Name</label>
                            <input type="text" class="form-control" placeholder="UserName" name="userName" v-model="posts.userName">
                        </div>
                        <div class="form-group">
                            <label class="input-label">Email</label>
                            <input type="email" class="form-control" placeholder="Email" name="email" v-model="posts.email">
                        </div>
                        <div class="form-group">
                            <label class="input-label">Password</label>
                            <input type="password" class="form-control" placeholder="Password" name="password" v-model="posts.password">
                        </div>
                        <div class="form-group">
                            <label class="input-label">Phone Number</label>
                            <input type="long" class="form-control" placeholder="Phone Number" name="mobileNumber" v-model="posts.mobileNumber">
                        </div>
                        <div class="form-group">
                            <label class="input-label">Gender</label>
                            <input type="text" class="form-control" placeholder="Male or Female" name="gender" v-model="posts.gender">
                        </div>
                        <br>
                        <div class="form-group d-flex justify-content-center">
                            <button class="btn btn-primary w-25" id="login" @click="postData"><a v-bind:href="vuelink"></a>Register</button>
                        </div>
                    </form>
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
  name: 'UserRegistration',
  data () {
    return {
      vuelink: '../login',
      posts: {
        userName: '',
        email: '',
        password: '',
        mobileNumber: 0,
        gender: ''
      }
    }
  },
  methods: {
    postData (e) {
      this.axios.post('http://10.177.1.51:8083/users/save', this.posts)
        .this((result) => {
          console.warn(this.posts)
        })
      e.preventDefault()
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

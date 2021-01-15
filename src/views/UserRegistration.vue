<template>
  <section class="container-fluid">
        <div class="row justify-content-center">
            <div class="col-lg-4">
                <div class="login-panel bg-white text-left">
                    <h1 class="display-3 font-weight-bold">New User Registration</h1>
                    <br>
                    <form action="">
                      <div class="form-group">
                            <label class="input-label">User Name</label>
                            <input type="email" class="form-control" placeholder="UserName">
                        </div>
                        <div class="form-group">
                            <label class="input-label">Email</label>
                            <input type="email" class="form-control" placeholder="Email">
                        </div>
                        <div class="form-group">
                            <label class="input-label">Password</label>
                            <input type="email" class="form-control" placeholder="Password">
                        </div>
                        <div class="form-group">
                            <label class= "input-label" for="gender">Gender</label>
                            <br>
                            <select id="gender" name="gender">
                            <option value="Male">Male</option>
                            <option value="Female">Female</option>
                            <option value="Do not Specify">Do not Specify</option>
                            </select>
                        </div>
                        <br>
                        <div class="form-group d-flex justify-content-center">
                            <button class="btn btn-primary w-25" id="login"><a v-bind:href="vuelink"></a>Register</button>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </section>
</template>

<script>

export default {
  data () {
    return {
      vuelink: '../login'
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

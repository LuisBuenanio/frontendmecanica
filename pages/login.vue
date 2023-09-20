<template>
  <div class="account-pages my-5 pt-sm-5">
    <Loader :isLoading="isLoading"></Loader>
            <div class="container">
                <div class="row justify-content-center">
                    <div class="col-md-8 col-lg-6 col-xl-5">
                        <div class="text-center mb-4">
                            <a href="index.html" class="auth-logo mb-5 d-block">
                                <img src="assets/images/logo-dark.png" alt="" height="30" class="logo logo-dark">
                                <img src="assets/images/logo-light.png" alt="" height="30" class="logo logo-light">
                            </a>

                            <h4>Login</h4>
                            <p class="text-muted mb-4">Get your Chatvia account now.</p>

                        </div>

                        <div class="card">
                            <div class="card-body p-4">
                                <div class="p-3">
                                    <div >

                                        <div class="mb-3">
                                            <label class="form-label">Email</label>
                                            <div class="input-group bg-soft-light rounded-3  mb-3">
                                                <span class="input-group-text text-muted" id="basic-addon5">
                                                    <i class="ri-mail-line"></i>
                                                </span>
                                                <input v-model="model.email" type="email" class="form-control form-control-lg bg-soft-light border-light" placeholder="Enter Email" aria-label="Enter Email" aria-describedby="basic-addon5">

                                            </div>
                                        </div>


                                        <div class="mb-4">
                                            <label class="form-label">Password</label>
                                            <div class="input-group bg-soft-light mb-3 rounded-3">
                                                <span class="input-group-text border-light text-muted" id="basic-addon7">
                                                    <i class="ri-lock-2-line"></i>
                                                </span>
                                                <input v-model="model.password" type="password" class="form-control form-control-lg bg-soft-light border-light" placeholder="Enter Password" aria-label="Enter Password" aria-describedby="basic-addon7">

                                            </div>
                                        </div>


                                        <div class="d-grid">
                                            <button @click="Login()" class="btn btn-primary waves-effect waves-light" type="button">Login</button>
                                        </div>

                                        <div class="mt-4 text-center">
                                            <p class="text-muted mb-0">By registering you agree to the Chatvia <a href="#" class="text-primary">Terms of Use</a></p>
                                        </div>

                                    </div>
                                </div>
                            </div>
                        </div>

                        <div class="mt-5 text-center">
                            <p>No tienes una cuenta ? <nuxtLink to="/register" class="fw-medium text-primary"> Registrarme </nuxtLink> </p>
                            <p>© {{new Date().getFullYear()}} Udemy. Crafted with <i class="mdi mdi-heart text-danger"></i> by Themesbrand</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
</template>
<script>
  export default {
    name: 'IndexPage',
    data(){
      return {
        res:[],
        model:{
          email:'',
          password:'',
        },
        isLoading:false
      };
    },
    methods:{
      async Login(){
        this.isLoading = true
        try{
        const res = await this.$api.$post('login-user',this.model)
       if(res.hasOwnProperty('errors')){
        this.$swal.fire({
          icon:'error',
  title: 'No se pudo iniciar sesion!',
  confirmButtonText: 'Ok',

})
       }else{
        let user = res
        localStorage.setItem('userChat',JSON.stringify(user))
        this.$router.push("/")
       }

  }catch(e){
    console.log(e)
    this.$swal.fire({
          icon:'error',
  title: 'Hubo un error!',
  showDenyButton: false,
  showCancelButton: false,
  confirmButtonText: 'Ok',

})
  }finally{
    this.isLoading = false
  }
      }
    },
    mounted(){
      let ls = localStorage.getItem('userChat')
      let user = JSON.parse(ls)
      if(user!=null){
        this.$router.push('/')
      }
      this.$nextTick(async()=>{


      })

    }
  }
  </script>

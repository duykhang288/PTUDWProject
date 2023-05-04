<script>
    import FormloginVue from "../components/Formlogin.vue";
    import toastsVue from "../components/toasts.vue";
    export default {
        components: {
            FormloginVue,
            toastsVue
        },
    };
</script>
<template>
<toastsVue></toastsVue>
   
<div class="container" >
  <div class="container-fluid m-5 p-5 shadow" style="background-color:#e9ecef ; border-radius: 40px ; ">
    <h1 class="text-dark" style="margin-top: 100px ; margin-left: 450px;">ĐĂNG NHẬP</h1>
    <div class="row d-flex justify-content-center align-items-center h-100">
      
      <div class="col-md-8 col-lg-6 col-xl-4 offset-xl-1">
          <FormloginVue></FormloginVue>
      </div>
    </div>
  </div>
</div>  

</template>

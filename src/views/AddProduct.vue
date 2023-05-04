
<script>
import toastjs from "../assets/js/toasts";
import toastsVue from "../components/toasts.vue";
import ProductService from "../services/Product.service";
import HeaderShop from "../components/HeaderShop.vue";
import Productform from "../components/Productform.vue";
export default {
  data(){
    return {
         toasts:{
              title:"Success",
              msg:"Thêm sản phẩm thành công",
              type:"success",
              duration:2000
              },
    }
  },
  components: {
    HeaderShop,
    Productform,
    toastsVue
    },
	methods: {
    toastjs,
        async addproduct(data) {
            try {
                await ProductService.create(data);
                this.toastjs();
                setTimeout(()=>{
                  location.reload();
                },2000);
            }catch(error) {
                console.log(error);
                    this.toasts.title = "Warning",
                    this.toasts.msg="Tài khoản không phải ADMIN",
                    this.toasts.type = "warn",
                    this.toasts.duration=2000
                    this.toastjs();
                }
            },  
	},
};
</script>
<template>
<HeaderShop></HeaderShop>
<toastsVue></toastsVue>
	<div class="page">
		<div>
			<div class="header text-center shadow" style="background-color: #e9ecef; border-radius: 20px; padding: 30px; margin-left:150px;margin-right: 150px;">
            <h2>Thêm Sản Phẩm</h2>
        </div>
        <div class="container shadow mx-auto" style="background-color: #e9ecef; border-radius: 20px; padding: 30px; margin-left:150px;margin-right: 150px; margin-top: 50px; margin-bottom: 50px;" >
			<Productform
				:product="{img:[]}"
        @submit:product="addproduct"
        :resetAfterSubmit="false"
			/>
        </div>
		</div>
	</div>
</template>

<template>
<HeaderShop></HeaderShop>
<toastsVue></toastsVue>
    <div v-if="product" class="page">
		<div class="header text-center shadow" style="background-color: #e9ecef; border-radius: 20px; padding: 30px; margin-left:150px;margin-right: 150px;">
            <h2>Sửa Sản Phẩm</h2>
        </div>
        <div class="container mx-auto p-3" style="background-color: #e9ecef; border-radius: 20px; margin-top: 30px;margin-bottom: 30px;">
            <Productform
			  :product="product"
              @submit:product="updateProduct"
		/>
        </div>
		
	</div>
</template>

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
              msg:"Sửa sản phẩm thành công",
              type:"success",
              duration:2000
              },
        product:null,
    }
  },
	components: {
        HeaderShop,
	    Productform,
        toastsVue
	},
	methods: {
    toastjs,
    async getproduct(id) {
			try {
				this.product = await ProductService.get(id);
			} catch (error) {
				console.log(error);
				this.$router.push({
					name: "notfound",
					params: { pathMatch: this.$route.path.split("/").slice(1) },
					query: this.$route.query,
					hash: this.$route.hash,
				});
			}
		},
        async updateProduct(data) {
            try {
                await ProductService.update(this.product._id,data);
                this.toastjs();
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
    created(){
        this.getproduct(this.$route.params.id);
    }
};
</script>

<script>
    import SliderShop from '@/components/SliderShop.vue'
    import HeaderShop from '@/components/HeaderShop.vue'
    import ProductService from '../services/Product.service'
    import { mapState } from "pinia";
    import { useAuthStore } from "@/stores/Auth.store";
    import toastsVue from '../components/toasts.vue';
    export default {
         data(){
            return {
                Products:[],
            }
        },
        components:{
            HeaderShop,
            SliderShop,
            toastsVue
        },
        computed: {
            ...mapState(useAuthStore,{
                currentUser: "user",
            }),
    },
        methods:{
             async retrieveProduct() {
            try {
                this.Products = await ProductService.getAll();
            } catch (error) {
                console.log(error);
                }
            },          
        },
        mounted() {
        this.retrieveProduct();
        },
    }
</script>
<template>
    <div class="header">
        <HeaderShop></HeaderShop>
      </div>
      <toastsVue></toastsVue>
    <div class="slider">
        <SliderShop></SliderShop>
    </div> 

<div style="margin: 20px 100px;">
    <div class="container-fluid row">
        
    </div>
    <div class="container-fluid row">
		<div class="col-9">
					<div id="carouselExampleControls" class="carousel slide" data-bs-ride="carousel">
					<div class="banner2">
			<div class="carousel-inner">
				<div class="carousel-item active">
				<img src="https://images.fpt.shop/unsafe/fit-in/800x300/filters:quality(90):fill(white)/fptshop.com.vn/Uploads/Originals/2022/4/14/637855722891895145_F-H1_800x300.png" class="d-block w-100" alt="...">
				</div>
				<div class="carousel-item">
				<img src="https://images.fpt.shop/unsafe/fit-in/800x300/filters:quality(90):fill(white)/fptshop.com.vn/Uploads/Originals/2022/4/19/637859639769118655_F-H1_800x300.png" class="d-block w-100" alt="...">
				</div>
				<div class="carousel-item">
				<img src="https://images.fpt.shop/unsafe/fit-in/800x300/filters:quality(90):fill(white)/fptshop.com.vn/Uploads/Originals/2022/4/11/637852645197208865_F-H1_800x300.png" class="d-block w-100" alt="...">
				</div>
			</div>
			<button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleControls" data-bs-slide="prev">
				<span class="carousel-control-prev-icon" aria-hidden="true"></span>
				<span class="visually-hidden">Previous</span>
			</button>
			<button class="carousel-control-next" type="button" data-bs-target="#carouselExampleControls" data-bs-slide="next">
				<span class="carousel-control-next-icon" aria-hidden="true"></span>
				<span class="visually-hidden">Next</span>
			</button>
			</div>
			</div>
		</div>
		<div class="col-3">
			<div class="row" id="sidebarfrist" style="background-image:url('https://i.pinimg.com/736x/e2/a6/c1/e2a6c1ba6bd7287ac3b62030eb5d1489.jpg');border-radius: 10px;
  margin-bottom: 50px;
  padding-bottom: 20px;
  margin-left: 20px;">
                        <h3>Xu Hướng</h3>
                        <div class="container" id="box">
						<button type="button" class="btn btn-sm btn-light"><a class="text-decoration-none" href="">#Camera</a></button>
                            <button type="button" class="btn btn-sm btn-light"><a class="text-decoration-none" href="">#Mànhình</a></button>
                            <button type="button" class="btn btn-sm btn-light"><a class="text-decoration-none" href="">#Pin</a></button>
                            <button type="button" class="btn btn-sm btn-light"><a class="text-decoration-none" href="">#Sạc nhanh</a></button>
                            <button type="button" class="btn btn-sm btn-light"><a class="text-decoration-none" href="">#IOS</a></button>
                            
                        </div>
            </div>
			<div class="row shadow" id="sidebar">
                        <h3>Bán Chạy</h3>
                        <div class="container" id="box">
                        <nav>
                            <div class="nav nav-tabs" id="nav-tab" role="tablist">
                              <button class="nav-link active btn-sm" id="nav-home-tab" data-bs-toggle="tab" data-bs-target="#nav-home" type="button" role="tab" aria-controls="nav-home" aria-selected="true">Ngày</button>
                              <button class="nav-link btn-sm" id="nav-profile-tab" data-bs-toggle="tab" data-bs-target="#nav-profile" type="button" role="tab" aria-controls="nav-profile" aria-selected="false">Tuần</button>
                              <button class="nav-link btn-sm" id="nav-contact-tab" data-bs-toggle="tab" data-bs-target="#nav-contact" type="button" role="tab" aria-controls="nav-contact" aria-selected="false">Năm</button>
                            </div>
                        </nav>
                          <div class="tab-content" id="nav-tabContent">
                            <div class="tab-pane fade show active" id="nav-home" role="tabpanel" aria-labelledby="nav-home-tab">
                                <ul class="list-group list-group-flush" id="sidebarlist">
                                    <li class="list-group-item"> <a class="text-decoration-none" href="">Iphone 13 ProMax </a></li>
                                    <li class="list-group-item"><a class="text-decoration-none" href="">Iphone 13 Pro </a></li>
                                    <li class="list-group-item"><a class="text-decoration-none" href="">Iphone 11 </a></li>
                             
                                  </ul>
                            </div>
                            <div class="tab-pane fade" id="nav-profile" role="tabpanel" aria-labelledby="nav-profile-tab">
                                <ul class="list-group list-group-flush"  id="sidebarlist">
                                    <li class="list-group-item"><a class="text-decoration-none" href="">Iphone 13 ProMax</a></li>
                                    <li class="list-group-item"><a class="text-decoration-none" href="">Iphone 13 </a></li>
                                    <li class="list-group-item"><a class="text-decoration-none" href="">Iphone 13 Pro </a></li>
                                
                                  </ul>
                            </div>
                            <div class="tab-pane fade" id="nav-contact" role="tabpanel" aria-labelledby="nav-contact-tab">
                                <ul class="list-group list-group-flush"  id="sidebarlist">
                                    <li class="list-group-item"><a class="text-decoration-none" href="">Iphone 12 </a></li>
                                    <li class="list-group-item"><a class="text-decoration-none" href="">Iphone 13 Pro Max </a></li>
                                    <li class="list-group-item"><a class="text-decoration-none" href="">Iphone 11 </a></li>
                              
                                  </ul>
                            </div>
                          </div>
                        </div>
                    </div>
		</div>
	</div>
   
    
    <div class="flex-row justify-content-md-center" style="margin:0 100px;">
      <div style="text-align: center; margin: 30px 0; background-color: rgb(231, 231, 231); border-radius: 10px; padding: 30px;" class="heading container-fluid "  >
        <h3>Các sản phẩm mới ra mắt</h3>
        
    </div>
        <div class="row d-sm-flex flex-wrap " id="x">
            <div class="card m-4 shadow" style="width: 18rem; background-color: rgb(244, 244, 244); border-radius: 20px; border: 0px !important;padding: 20px !important;"  v-for="item in Products" v-show="item.categories === 'New'">
                <div class="wrapper-img">
                    <div class="image_slider">
                        <div class="image_item" v-for="img in item.img">
                            <img :src="img" class="card-img-top" alt="..." style="border-radius: 15px;">
                        </div>
                    </div>
                </div>
                <div class="card-body product mx-auto">
                    <h5 class="card-title">{{item.title}}</h5>
                    <h6 class="price text-primary">{{item.price}}VND</h6>
                    <router-link :to="{
                        name: 'details',
                        params: { id: item._id },
                    }"  >
                        <button type="button" class="btn btn-dark mx-auto">Mua Ngay</button>
                    </router-link>
                </div>
            </div>
        </div> 
        <div style="text-align: center; margin: 30px 0; background-color: rgb(231, 231, 231); border-radius: 10px; padding: 30px;" class="heading container-fluid "  >
        <h3>Các sản phẩm bán chạy</h3>
        
    </div>
    <div class="d-sm-flex flex-wrap" id="x">
            <div class="card m-4 shadow" style="width: 18rem; background-color: rgb(244, 244, 244); border-radius: 20px; border: 0px !important;padding: 20px !important;"  v-for="item in Products" v-show="item.categories === 'hot'">
                <div class="wrapper-img">
                    <div class="image_slider">
                        <div class="image_item" v-for="img in item.img">
                            <img :src="img" class="card-img-top" alt="..." style="border-radius: 15px;">
                        </div>
                    </div>
                </div>
                <div class="card-body product mx-auto">
                    <h5 class="card-title">{{item.title}}</h5>
                    <h6 class="price text-primary">{{item.price}}VND</h6>
                    <router-link :to="{
                        name: 'details',
                        params: { id: item._id },
                    }"  >
                        <button type="button" class="btn btn-dark mx-auto">Mua Ngay</button>
                    </router-link>
                </div>
            </div>
        </div> 
    
    </div>   
 
</div>
<div>
</div>
</template>
<style scoped>   
    .wrapper-img{
        width: 100%;
        height: 100%;
        overflow: hidden;
    }
    .image_slider{
       display: flex;
       transition: all .8s ease;
       
    }
    .image_slider:hover{ 
       transform: translateX(-100%);
    }
   .image_item{
       flex: 1 0 100%;
   }
   #banner2 {
    margin-bottom: 20px;
  }
#banner2 img {
    border-radius: 20px;
    
  }
.products {
  list-style-type:none;
}
.price {
  font-weight: bold;
  color: #515457!important;
  padding-bottom:10px;
  font-size: 18px;
}
.btn-custom {
  display: inline-block;
  padding: 7px;
  border-radius: 20px;
  width: 100%;
  text-align: center;
  color: #fff ;
  background-color: #494949 ;
  cursor: pointer;
  outline: none;
  border: none;
  font-size: 16px;
  text-decoration: none;
}
.btn-favorite {
  display: inline-block;
  padding: 7px;
  border: 1px solid rgb(173, 0, 0);
  border-radius: 20px;
  width: 100%;
  text-align: center;
  color: rgb(173, 0, 0) ;
  background-color: #fff ;
  cursor: pointer;
  font-size: 16px;
  text-decoration: none;
}
.btn-favorite:hover {
  color: #fff;
  background-color: rgb(190, 75, 75);
}
.btn-admin {
  display: inline-block;
  padding: 7px;
  border-radius: 10px;
  width: 100%;
  text-align: center;
  color: #fff ;
  background-color: #494949 ;
  cursor: pointer;
  outline: none;
  border: none;
  font-size: 16px;
  text-decoration: none;
}
.btn-admin:hover, .btn-custom:hover {
  color: #fff ;
  background-color:#797979;
}
h5{ 
  height:48px;
}
.checked {
  color: orange;
}
#sidebarfrist {
  background-image: url("https://i.pinimg.com/736x/e2/a6/c1/e2a6c1ba6bd7287ac3b62030eb5d1489.jpg");
  border-radius: 10px;
  margin-bottom: 50px;
  padding-bottom: 20px;
  margin-left: 20px;
}
#sidebarfrist h3 {
  margin: 20px 30px auto auto;
  font-weight: 600;
  color: #ffffff;
}
#box .btn {
  margin: 5px;
}
#sidebar {
  background-color: rgba(245, 245, 245, 0.705);
  border-radius: 10px;
  margin-bottom: 50px;
  padding-bottom: 20px;
  margin-left: 20px;
}
#sidebar h3 {
  margin: 20px 20px auto auto;
  font-weight: 600;
  color: #424242;
}
#sidebar #box {
  border-left: 5px solid #494949;
  padding: 5px 5px 10px 10px;
  text-align: center;
}
#box .nav-tabs .nav-item.show .nav-link, .nav-tabs .nav-link.active {
  /* color: #01152F; */
  color: #fff;
  background-color: #494949;
  font-weight: 600;
}
.list-group-flush .list-group-item {
  border-right: 0;
  border-left: 0;
  border-radius: 0;
  background-color: #F8F8F8;
}
#sidebar a {
  color: black !important;
}
</style>
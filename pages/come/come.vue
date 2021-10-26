<template>
	<view class="home">
		<swiper indicator-dots circular>
			<swiper-item v-for="item in swipers" :key="item.id">
				<image :src="item.image_src"></image>
			</swiper-item>

		</swiper>
		

		
		
		<view class='hot_goods'>
			<view class="tit">宣传栏 </view>			
		</view>
		
		<view class='hot_goods'>
			 <navigator url="/pages/add/add"><button type="primary" >我要发帖</button></navigator>
			
		</view>
		
		<goods-list :goods="goods"></goods-list>
		
		
		
	</view>
</template>

<script>
	import goodsList from '@/components/goods-list/goods-list.vue'
	export default {
		data() {
			return {
				swipers:[],
				goods:[],
				
				
			}
		},
		onLoad(){
			this.Swipers()
			//this.Showtext()
			this.Gethotgoods()
		},
		components:{"goods-list":goodsList},
		onReachBottom() {
			console.log("触底了")
		},
		
		methods: {
			//获取轮播图的数据
			async Swipers(){
				//console.log('lunbotu')
				 const res = await this.$myRequest({
					url:'/api/public/v1/home/swiperdata'
				})
				this.swipers=res.data.message
				
				//console.log(this.swipers)
			},
			Showtext(){
				console.log(vmo)
			},
			//获取商品数据
			async Gethotgoods(){
				const res = await this.$myRequest({
					url:'/api/public/v1/goods/search'
				})
				this.goods=res.data.message.goods
				//console.log(this.goods)
			}

				
			
		}
	}
</script>

<style lang='scss'> 
.home{
	swiper{
		width:700rpx ;
		height:380rpx;
		image{
			height:100%;
			width: 100%;
		}
			
		
	}
}
.hot_goods{
	background-color: #eeeeee;
	overflow: hidden;
	margin-top: 10px;//距离上面远一点
	.tit{
		height:50px;
		line-height: 50px;
		color: $shop-color;
		text-align: center;
		letter-spacing: 20px;
		background-color: white;
		margin: 7rpx 0;
	}
	.goods_list{
		
			padding:0 1rpx;
			display: flex;//平着显示
			flex-wrap: wrap;
			justify-content: space-between;
		.goods_item{
		background: #FFFFFF;
		width:340rpx;
		margin: 10rpx 0;
		padding: 15rpx;
		box-sizing: border-box;
		image{
			//调节图片大小
			width:75%;
			height:175rpx;
			margin:0 auto;
			display: block;
			margin: auto;
			} 
		}
		.price{
			color:$shop-color;
			font-size: 36rpx;
			text:nth-child(2){
				color: #ccc;
				font-size:28rpx;
				margin-left: 17rpx;
				text-decoration: line-through;
			}
			
	
		}
		.name{
			font-size:28rpx;
			line-height: 50rpx;
			padding-bottom: 15rpx;
			padding-top:12rpx ;
		}
	}
	

}
	

</style>

<template>
	<div>
		<!-- 头部 -->
		<mt-header title="爱咋整"></mt-header>
		<router-view></router-view>
		<nav class="mui-bar mui-bar-tab">
				
			<router-link class="mui-tab-item" :to="{name:'home'}">
                <span class="mui-icon mui-icon-search"></span>
                <span class="mui-tab-label">首页</span>
            </router-link>
            <router-link class="mui-tab-item" :to="{name:'member'}">
                <span class="mui-icon mui-icon-search"></span>
                <span class="mui-tab-label">会员</span>
            </router-link>
            <router-link class="mui-tab-item" :to="{name:'shopcart'}">
                <span class="mui-icon mui-icon-search"><span class="mui-badge">9</span></span>
                <span class="mui-tab-label">购物车</span>
            </router-link>
            <router-link class="mui-tab-item" :to="{name:'search'}">
                <span class="mui-icon mui-icon-search"></span>
                <span class="mui-tab-label">查找</span>
            </router-link>
		</nav>
		<!-- 底部 -->
	</div>
</template>
<script>
	export default {
		data(){
			return {
			}
		},created(){
			// 用户登录
			this.$ajax.post('clientLogin',
				{username:'jige',password:"123321"}
			).then(res=>{
					console.log(res)
				
				}).catch(error=> {
			    console.log(error);
			  });
			
		}
	}
</script>
<style></style>
<template>
    <div class="tmpl">
    

        <nav-bar title="明星面对面"></nav-bar>
        <div class="upload ">
            <upload :id="id" :multiple="false" :url.sync="urls"  @select-type="onSelectType"  @select-url="onSelectUrl"  :url="wurl"></upload>
        </div>
    <!-- MUI 图文列表 -->
        
        <button @click="onSub">测试</button>

    </div>
</template>
<script>
export default {
    data(){
        return {
            newsList:[],//新闻列表数据
            id:'operationProjectDatas',
                urls:[],
                wurl:[],
                deviceId:'123',
                clientId:'59f6e1064467027c0c1c786f',
                sex:'0',
                file:""
        }
    },
    created(){
        
    },methods:{
        onSelectType (type) {
            console.log(type)
            
          },onSelectUrl(url){
            
            console.log(url)
            this.file = url[0]

        },onSub(){
            this.$ajax.post('http://test.legle.cc:82/starTestUrl',{clientId:this.clientId,deviceId:this.deviceId,sex:this.sex,file:this.file})
        .then(res=>{
            if(res.data.code == 1){
                let data = res.data.starsData
                console.log(data)
            }
            
        }).catch((err) => {
            console.log(err)
        })
        }
    }
}

</script>
<style scoped>
.mui-media-body p {
    color: #0bb0f5;
}

.news-desc p:nth-child(1) {
    float: left;
}

.news-desc p:nth-child(2) {
    float: right;
}
.upload{
        border: 1px solid #ddd;
        width: 100px;
        height: 100px;
        border-radius: 4px;
        background: url('../../static/img/add_upload.png');
        background-size: contain;
        float:left;
      }
</style>

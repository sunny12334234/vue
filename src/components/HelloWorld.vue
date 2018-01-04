<template>
    <div id="index">
        <header class="mui-bar mui-bar-nav">
            <a class="mui-action-back mui-icon mui-icon-left-nav mui-pull-left"></a>
            <h1 class="mui-title">支付方式</h1>
        </header>
        <div class="mui-content" onclick="alert(1)">
        <input v-focus>
        <p v-demo:foo.a.b="imgSrc"></p>
            <div class="mui-card" >
                <div class="mui-card-header">支付宝免密支付</div>
                <div class="mui-card-content" onclick="alert(2)">
                    <span class="mui-icon mui-icon-plusempty" onclick="alert(3)"></span>
                </div>
                <div class="mui-card-footer"><img :src="baseImg+imgSrc"></div>
            </div>
        </div>
    </div>
</template>


<script>

export default {
    name: 'share',
    data() {
        return {
			baseImg: "http://ovjqyq4zd.bkt.clouddn.com/",
			imgSrc: "alipay.png",
        }
    },
    methods:{
        alipay(){
            mui.toast("本应用已支持支付宝支付")
        }
    },
    directives: {
      focus: {
        // 指令的定义
        inserted: function (el) {
          el.focus()
        }
      },
      demo:{
        bind: function (el, binding, vnode) {
          var s = JSON.stringify
          el.innerHTML =
            'name: '       + s(binding.name) + '<br>' +
            'value: '      + s(binding.value) + '<br>' +
            'expression: ' + s(binding.expression) + '<br>' +
            'argument: '   + s(binding.arg) + '<br>' +
            'modifiers: '  + s(binding.modifiers) + '<br>' +
            'vnode keys: ' + Object.keys(vnode).join(', ')
        }
      }
    }
}
</script>

<style>
#index {
    font-family: "微软雅黑";
}


.mui-bar {
    background: rgb(42, 130, 69);
}

.mui-title {
    color: #fff;
}

.mui-icon-person {
}

.mui-pull-left {

    color: #fff;
}


.mui-card {
    background: rgb(3, 171, 237);
    color: #fff;
    position: relative;
    margin-bottom: 30px;
}


.mui-card .mui-card-footer img {
    width: 80px;
    padding-top: 30px;
}

.mui-card .mui-card-content .mui-icon {
    position: absolute;
    right: 0;
    top: 50%;
    font-size: 100px;
    transform: translateY(-50%);
}
</style>


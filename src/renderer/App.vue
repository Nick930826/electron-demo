<template>
  <div class="home">
    <iframe id="iframe" ref="iframe" src="https://mp.weixin.qq.com"></iframe>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        msg: '牛逼'
      }
    },
    mounted() {
      let iframe = this.$refs.iframe
      
      iframe.onload = function() {
        
        let dom = iframe.contentDocument
        let account = dom.querySelector('input[name="account"]')
        let password = dom.querySelector('input[name="password"]')
        const evt = dom.createEvent('HTMLEvents');
        evt.initEvent('input', false, true);
        account.value = 'xianyou1993@qq.com'
        account.dispatchEvent(evt);
        password.value = 'cxy930826'
        password.dispatchEvent(evt);

        // dom.querySelector('.btn_login') && dom.querySelector('.btn_login').click();
      }
    }
  }
</script>

<style scoped>
.home {
  width: 100%;
  height: 100%;
}
#iframe {
  width: 100%;
  height: 100%;
  border: none;
  margin: 0;
}
</style>
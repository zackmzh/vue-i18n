<template>
  <div class="hello">
    <button @click="changeLangEvent()">change lang</button>
    <span v-text="$t('m.music')"></span>
    {{$t('m.friend')}}
    <span>{{$t('m.download')}}</span>
    
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods: {
    /**
 * 切换语言 
 */ 
   changeLangEvent() {
    
    var r = confirm(this.$t('m.change'));
    
    if (r == true) {
      if(this.lang === 'zh-CN') {
        this.lang = 'en-US';
        this.$i18n.locale = this.lang;
      }else {
        this.lang = 'zh-CN';
        this.$i18n.locale = this.lang;
      }
    } else {
        return ;
    }

    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

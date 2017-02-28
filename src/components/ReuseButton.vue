// 进一步修改src/components/TypeButton.vue
<script>
  import Button from './BaseButton.vue'
  export default{
    name: "type-button",
    //将传递过来的type在props中注册，并进行验证
    created:function(){
      //console.log(this.type)
    },
    props: {
      type: {
        validator: function (typeStr) {
          if (typeof typeStr === 'string') {
            switch (typeStr) {
              case 'babab':
              case 'primary':
              case 'info':
              case 'success':
              case 'warning':
              case 'danger':
                return true;
              default:
                return false;
            }
          } else return false;
        }
      }
    },
    render(createElement){
      return createElement(Button,
        {
          class: [this.type],
          on:{
              //click:this.click
          }
        },
        this.$slots.default
      )
    },
    methods: {
    },
    components: {}
  };
</script>
<style scoped>
</style>
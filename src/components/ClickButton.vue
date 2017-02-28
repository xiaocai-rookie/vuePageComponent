// TypeButton.vue的render函数
<script>
  import Button from './BaseButton.vue'
  export default{
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
          //添加on对象
          on:{
              click:this.click
          }
        },
        this.$slots.default
      )
    },
    //添加
    methods: {
        click(){
            //触发组件中定义的click
            this.$emit('click')
        }
    },
  };
</script>
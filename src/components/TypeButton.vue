<script>
  import Button from './BaseButton.vue'
  export default{
    name: "type-button",
    render(createElement){
      return createElement(Button,
        {
            class:["info"]
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
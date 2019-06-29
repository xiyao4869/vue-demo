<script>
  export default {
    name: 'test',
    functional: true, // 函数式组件
    props: {
      count: {
        type: Number,
        default: null,
      }
    },
    render(h, ctx){
      console.log(ctx)
      // 传递 ctx.data 外部的class="test"才会出现在组件的根元素上
      return <div {...ctx.data}>hello {ctx.props.count}</div>
    }
  }
</script> 
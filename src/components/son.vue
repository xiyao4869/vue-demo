<script>
  export default {
    data(){
      return {
        msg: 'son  son'
      }
    },
    methods: {
      notify(){
        alert('son')
        this.$emit('say','儿子放学了')
      }
    },
    render(){
      console.log(this.$listeners)
      return (
        <div>
          {this.$scopedSlots.s2({ text: this.msg })}
          <div onClick={this.notify}>我是儿子哦</div>
        </div>
      )
    }
  }
</script>
<script>
  import Son from './son.vue';
  export default {
    name: 'testjsx',
    props: {
      count: {
        type: Number,
        default: null,
      },
      text: {
        type: Number,
        default: null,
      },
    },
    data(){
      return {
        name: 'xiyao',
        nickName: 'lucy',
        message: "ni hao",
        info: '',
      }
    },
    methods: {
      clickHandler(){
        alert('handler');
        this.$emit('update', '我是更新的信息');
      }
    },
    render(){
      return (
        <div>
          hello {this.name}{this.count}
          <span onClick={this.clickHandler}>6677</span>
          {this.$slots.s1}
          {this.$scopedSlots.s3({
            name: this.nickName
          })}
          <Son {...{scopedSlots: { s2: props => <span>{props.text}</span>}, on: { respond: () => {}} }} vOn:say={ info => this.info = info }/>
          <input v-model={this.message} placeholder="please input yeyeye u"/>
          {this.message}
          <div vOn:click={this.clickHandler}>来个煎饼果子</div>
          {this.info}
        </div>
      )
    }
  }
</script> 
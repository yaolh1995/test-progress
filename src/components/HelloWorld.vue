<template>
  <div class="paymentWrapper">
    <div class="number">
    <div class="paied">
     +已缴{{paiedNumber}}户
    </div>
    <div class="unpaied">
      -未缴{{unpaiedNumber}}户
    </div>
    </div>
    <div class="progressBar">
      <div class="paiedBar" ref="paied">{{paiedPercent}}%</div>
      <div class="unpaiedBar" ref="unpaied">{{unpaiedPercent}}%</div>
    </div>
  </div>
</template>

<script>
export default {
  created() {
    this.$nextTick(() => {this.operatewidth()
    })
    },
  data(){
  return{
    paiedNumber:679,
    unpaiedNumber:846,
    paiedPercent:35,
    unpaiedPercent:65
  }
},
  props: {
    msg: String
  },
  methods:{

    operatewidth(){
      let paied=this.$refs.paied.style
      let unpaid=this.$refs.unpaied.style
      console.log(paied.width)
      paied.width=this.paiedPercent+'%';
      console.log(paied.width)
      unpaid.width=this.unpaiedPercent+'%';
      console.log(unpaid.width)
    }
  },
  computed:{

  }
}
</script>
<style  scoped>
.paymentWrapper{
  font-size: 41px;
  background-color: #f1f1f1;
  width: 600px;
}
.number{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.number > .paied{
  padding-left: 55px;
  color: #40b884;
}
.number > .unpaied{
  color: #fe0000;
  padding-right: 55px;
}
.progressBar{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 550px;
}
.progressBar > .paiedBar{
  margin-left: 25px;
  padding-left: 30px;
  background-color: #40b884;
  color: white;
  width: 45%;
}
.progressBar > .unpaiedBar{
  margin-right: 25px;
  padding-right: 30px;
  background-color: #fe0000;
  color: white;
  width: 55%;
}
.progressBar > .unpaiedBar::before{
  content: '';
  width: 100%;
  max-height: 500px;
  color: white;
}
</style>

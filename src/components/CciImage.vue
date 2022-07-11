<template>
  <div>
    <img width='240px' :src="imgSrc" alt="">
    <span class="legende">{{imgLegend}}</span>
  </div>
</template>

<script>
export default {
  name: "CciImage",
  created() {},
  data() {
    return {};
  },  
  props: {
    imgSrc:{
      type:String,
      default:'https://api.arretsurimages.net/api/public/media/raffarin-le-monde-johnny-1/action/show?format=public&t=2017-10-18T12:18:01+02:00'
    },
    imgLegend:{
      type:String,
      default:'no legend'
    }
  },
  methods: {},
};
</script>

<style  scoped>

    img{
    border-radius: 5px;
    margin:0;
  }
  .legende{
    color:black;
    
    font-size:medium;
  }

</style>
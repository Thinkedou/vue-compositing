<template>
   <div id="app"> <!-- app est notre parent dans cette composition  -->
      <div class='row'>
            <div class='col left'>
                <ul>
                    <li>Ici c'est App.vue</li>
                    <li>Parent (nav, button, etc)</li>
                </ul>
            </div>
            <div class='col right'>
              <CciCard v-for='(cours,idx) in coursesInfos'
                    :key='idx'
                    :chapter-title="cours.chapter"
                    :chap-number="cours.chapterNumber"
              />
            </div>
      </div>
  </div>
</template>

<script>
import CciCard from './components/CciCard.vue'

export default {
  name: 'App',
  components: {
    CciCard
    },
   data:()=>({
       coursesInfos:[
           {
               chapter:'Premier cours',
               chapterNumber:2
           },
           {
               chapter:'Quatrième cours',
               chapterNumber:3
           },
           {
               chapter:'Dernier cours',
               chapterNumber:4
           }
       ]
   })
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css?family=Muli&display=swap');
#app{
	display: flex;
	margin-left: 5%;
	margin-top:2%;
	margin-right:5%;

}
.row{
	margin-top:10px;
	width:100%;
	display: flex;

}
.col {
    padding:50px;
    color:cyan;
    font-family: 'Muli', sans-serif;
}
.left{
    width:20%;
    background-color: #065a75;
}
.right{
    width:70%;
}
</style>

<template>
   <div id="app"> <!-- app est notre parent dans cette composition  -->
      <div class='row'>
            <div class='col left'>
                <ul>
                    <li>Ici c'est App.vue</li>
                    <li>Parent (nav, button, etc)</li>
                    <li>{{selectedCourse}}</li>
                </ul>
            </div>
            <div class='col right'>
              <CciCard v-for='(cours,idx) in coursesInfos'
                    :key='idx'
                    :card-id='idx'
                    :chapter-title="cours.chapter"
                    :chap-number="cours.chapterNumber"
                    @onCourseSelected="handleCourseSelected"
              />

              <CciCard >
                  <h2>JavaScript Fundamentals</h2>
                  <img src='https://www.dotcom-monitor.com/blog/wp-content/uploads/sites/3/2020/05/Vue-logo-1.png' />
              </CciCard>

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
       selectedCourse:'',
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
   }),
   methods:{
       handleCourseSelected(payload){
            console.log('%c APP Parent à entendue un evenement depuis Enfant!', 'background: green; color: white; display: block;');
            console.log(payload)
            // object destructuring car pourquoi pas?
            const {cardId}= payload
            // je met à jour la data locale "selectedCourse"
            this.selectedCourse = this.coursesInfos[cardId].chapter
       }
   }
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
    font-size: 24px;
    background-color: #065a75;
}
.right{
    width:70%;
}
</style>

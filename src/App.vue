<template>
  <div id="app">
    <!-- app est notre parent dans cette composition  -->
    <div class="row">
      <div class="col left">
        <ul>
          <li>Ici c'est App.vue</li>
          <li>Parent (nav, button, etc)</li>
          <li
            v-for="cardId in selectedCourse"
            :key='cardId'
          >
          {{coursesInfos[cardId].chapter}}
          </li>
          <li>une modif pour git</li>
        </ul>
        <CciImage
        imgLegend="Kramer l'unique"
        imgSrc="https://m.media-amazon.com/images/M/MV5BY2U4NzRmNmMtNGQ4OC00OTdmLTg0YTAtMGNiODc2OTExYWVkXkEyXkFqcGdeQXVyNTM3MDMyMDQ@._V1_UY98_CR32,0,67,98_AL_.jpg" />
        <CciImage
        imgLegend="Hughie"
        imgSrc="https://www.slashfilm.com/img/gallery/the-big-difference-between-hughies-powers-in-the-boys-show-and-comic-explained/l-intro-1654979525.jpg" />
        <CciImage
        imgLegend="Nkm moment de grace"
        imgSrc="https://media.nouvelobs.com/referentiel/1200x630/6650943.jpg" />

      </div>
      <div class="col right">

        <CciCard
          v-for='(course,id) in coursesInfos'

          :key = 'id'
          :cardId='id'
          :chapterTitle='course.chapter'
          :courseTitle='course.chapterNumber'
          :cardColor = 'course.color'
          @onCourseSelected="handleCourseSelected"
        />

      </div>
    </div>
  </div>
</template>

<script>
//1° import du component
import CciCard  from './components/CciCard.vue'
import CciImage from './components/CciImage.vue';



export default {
  name: "App",
  components: {
    CciCard,
    CciImage
  },
  data: () => ({
    selectedCourse: [],
    coursesInfos: [
      {
        chapter: "Premier cours",
        chapterNumber: 2,
        color: "lime",
      },
      {
        chapter: "Quatrième cours",
        chapterNumber: 3,
        color: "#EBE60E",
      },
      {
        chapter: "Dernier cours",
        chapterNumber: 4,
        color: "#ED6FF5",
      },
    ],
  }),
  methods: {
    handleCourseSelected(datas){
      const {cardId} = datas
      // je regarde d'abord s'il n'est pas déjà dans la liste
      if(!this.selectedCourse.includes(cardId)){
        this.selectedCourse.push(cardId)
      }

      console.log('👨 événément entendu par le parent:', datas)
    }
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=Muli&display=swap");
#app {
  display: flex;
  margin-left: 5%;
  margin-top: 2%;
  margin-right: 5%;
}
.row {
  margin-top: 10px;
  width: 100%;
  display: flex;
}
.col {
  padding: 50px;
  color: cyan;
  font-family: "Muli", sans-serif;
}
.left {
  width: 20%;
  font-size: 24px;
  background-color: #065a75;
}
.right {
  width: 70%;
}

</style>

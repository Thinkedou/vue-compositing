<template>
    <div>
        <div class="courses-container">
            <div class="course">
                <div class="course-preview">
                    <slot>
                        <h6>Course par défaut ({{cardId}})</h6>
                        <h2>H2 du Slot Par défaut</h2>
                    </slot>
                </div>
                <div class="course-info">
                    <h6>Chapter {{chapNumber}}</h6>
                    <h2>{{chapterTitle}}</h2>
                    <button class="btn" @click="selectCourse">Continue</button>
                </div>
            </div>
        </div>
    </div>

</template>

<script>
export default {
  name: 'CciCard',
  props: {
       chapterTitle:{
           type:String,
           default:'Chapitre par défaut'
       },
       chapNumber:{
           type:Number,
           default:0
       },
       cardId:{
           type:Number
       }
  },
  data:()=>({

  }),
  methods:{
      selectCourse(){
          console.log('ça click depuis CciCard ', this.cardId)
          // on déclenche un événément custom
          // son nom est arbitraire et ne correspond pas aux évt Js classiques
          this.$emit('onCourseSelected',{cardId:this.cardId})
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url('https://fonts.googleapis.com/css?family=Muli&display=swap');

.courses-container {
    font-family: 'Muli', sans-serif;
	display: flex;
	align-items: center;
	justify-content: center;
    color:black;
	flex-direction: column;
}

.course {
	background-color: #fff;
	border-radius: 10px;
	box-shadow: 0 10px 10px rgba(0, 0, 0, 0.2);
	display: flex;
	max-width: 100%;
	margin: 20px;
	overflow: hidden;
	width: 700px;
}

.course h6 {
	opacity: 0.6;
	margin: 0;
	letter-spacing: 1px;
	text-transform: uppercase;
}

.course h2 {
	letter-spacing: 1px;
	margin: 10px 0;
}

.course-preview {
	background-color: #2A265F;
	color: #fff;
	padding: 30px;
	max-width: 250px;
}

.course-preview a {
	color: #fff;
	display: inline-block;
	font-size: 12px;
	opacity: 0.6;
	margin-top: 30px;
	text-decoration: none;
}

.course-info {
	padding: 30px;
	position: relative;
	width: 100%;
}



.btn {
	background-color: #2A265F;
	border: 0;
	border-radius: 10px;
	box-shadow: 0 10px 10px rgba(0, 0, 0, 0.2);
	color: #fff;
	font-size: 16px;
	padding: 12px 25px;
	position: absolute;
	bottom: 30px;
	right: 30px;
	letter-spacing: 1px;
}

</style>

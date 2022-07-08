<template>
  <div id="app">
    <!-- app est notre parent dans cette composition  -->
    <div class="row">
      <div class="col left">
        <ul>
          <li>Ici c'est App.vue</li>
          <li>Parent (nav, button, etc)</li>
          <li></li>
        </ul>
      </div>
      <div class="col right">
        <div>
          <div class="courses-container">
            <div class="course">
              <div class="course-preview">
                <h6>Nom du cours</h6>
              </div>
              <div class="course-info">
                <h6>Chapter 2</h6>
                <h2>Title</h2>
                <button class="btn">Select</button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data: () => ({
    selectedCourse: "",
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
  methods: {},
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

.courses-container {
  font-family: "Muli", sans-serif;
  display: flex;
  align-items: center;
  justify-content: center;
  color: black;
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
  color: #fff;
  padding: 30px;
  background-color: #2a265f;
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
  background-color: #2a265f;
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

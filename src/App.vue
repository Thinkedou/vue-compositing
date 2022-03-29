<template>
  <div id="app">
      <div class='row'>
            <div class='col left'>
                <ul>
                    <li>Ici c'est App.vue</li>
                    <li>Parent (nav, button, etc)</li>
                </ul>
            </div>
            <div class='col right'>
              <CciCard />
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
  }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css?family=Muli&display=swap');
.#app{
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

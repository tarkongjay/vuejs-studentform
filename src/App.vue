<template>
  <header>
    <h1>ระบบจัดการนักเรียน</h1>
  </header>
  <FormComponents @save="SaveData"/>
  <section class="student-content" v-if="(stus.length > 0)">
    <h2>ข้อมูลนักเรียน</h2>
    <!-- <FormComponents /> -->
    <ListData :data="stus"/>
  </section>
</template>
  
  <script>
// import FormComponents from "./components/FormComponents.vue";
import ListData from "./components/ListData.vue";
import FormComponents from "./components/FormComponents.vue";
export default {
  name: "App",
  components: {
    FormComponents,
    ListData,
  },
  data(){
    return{
      stus: []
    }
},
methods:{
  SaveData(data){
    this.stus.push(data);
  }
}

};
</script>
  
  <style>
  @import url('https://fonts.googleapis.com/css?family=Kanit');
  *{
    box-sizing: border-box;
    font-family: 'Kanit', sans-serif;
  }
  body{
    margin: 0;
    background-color: whitesmoke;
  }
  header{
    box-shadow: rgba(50, 50, 93, 0.25) 0px 6px 12px -2px, rgba(0, 0, 0, 0.3) 0px 3px 7px -3px;
    margin: 5ex;
    border-radius: 5ex;
    padding: 4ex;
    background-color: cornflowerblue;
    color: white;
    text-align: center;
    font-weight: bold;
  }
  .student-content{
    box-shadow: cornflowerblue 0px 3px 8px;
    margin: 5ex;
    padding: 5ex;
    border-radius: 7ex;
    text-align: center;
  }
  .student-content h2{
    font-weight: bold;
    border-bottom: 3px solid cornflowerblue;
font-size: 4ex;
  }
</style>
  
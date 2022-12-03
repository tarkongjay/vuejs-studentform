<template>
  <Cards>
    <template v-slot:card-name>
      <h1>{{name}}</h1>
    </template>
    <!-- <template v-slot:card-button>
      <button class="b1" @click="showInfor(idList)">ดูรายละเอียด</button>
    <button class="b2" @click="deletefor(idList)">ลบข้อมูล</button>
    </template> -->
    <template v-slot:card-info>
      <transition name="fade">
        <!-- <div v-show="check">
      <p>ห้องเรียน : {{ room }} </p>
      <p>มหาลัยที่ได้ : {{ uni }} สาขา : {{ bra }}</p>
    </div> -->
    <div>
      <p>ห้องเรียน : {{ room }} </p>
      <p>มหาลัยที่ได้ : {{ uni }} สาขา : {{ bra }}</p>
    </div>
  </transition>
    </template>
  </Cards>
</template>

<script>
import Cards from "./Cards.vue";
export default {
  name: "student",
  components:{
    Cards
  }
  ,
  //  data(){
  //   return{
  //     mess: 'ข้อมูลนักเรียน'
  //   }
  //  }
  // props: ["name","room"]
  props: {
    name: {
      type: String,
      required: true,
    },
    room: {
      // type: Number,
      type: String,
      required: true,
      default: "6/2",
    },
    uni: {
      type: String,
      required: true,
    },
    bra: {
      type: String,
      required: true,
    },
    // check: {
    //   type: Boolean,
    // },
    // idList:{
    //   type: Number
    // }
  },
  methods:{
    showInfor(id){
    this.$emit("show",id) //ส่งให้แม่รู้ว่าต้องการเปลี่ยนแปลง
    },
    deletefor(id){
    this.$emit("delete",id) //ส่งให้แม่รู้ว่าต้องการเปลี่ยนแปลง
    }
  }
};
</script>

<style scoped>
h1 {
  font-size: 3.5ex;
  color: white;
}
button{
  margin: 2px;
  padding: 7.5px 16px;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
  border: none;
  font-size: 2ex;
  border-radius: 5ex;
  color:black
}
.b1{
  background-color: rgb(104, 255, 155);
}
.b1:hover{
  background-color: rgb(205, 255, 222);
}
.b2{
  background-color: rgb(255, 144, 125);
}
.b2:hover{
  background-color: rgb(248, 196, 187);
}
p{
  color: white
}
.fade-enter-from{
  opacity: 0;
}
.fade-enter-active{
transition: all 1.0s linear;
}

</style>
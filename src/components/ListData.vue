<template>
  <ul>
    <!-- <Students
      v-for="(item,index) in studentlist"
      :key="index"
      :idList="item.id"
      :check="item.isChack"
      :bra="item.branch"
      :uni="item.university"
      :room="item.roomname"
      :name="item.nickname"
      @show="Toggle"
      @delete="DeleteData"
    /> -->
    <Students
      v-for="(item,index) in data"
      :key="index"
      :bra="item.bra"
      :uni="item.uni"
      :room="item.room"
      :name="item.name"
    />
  </ul>
</template >

<script>
import Students from "./Students.vue";

export default {
  name: "listdata",
  // data() {
  //   return {
  //     studentlist: [
  //       {
  //         id: 1,
  //         nickname: "กีตาร์ สับหลอก",
  //         roomname: "6/2",
  //         university: "มหาลัยศิลปากร",
  //         branch: "วิทยาการคอมพิวเตอร์",
  //         isChack: false,
  //       },
  //       {
  //         id: 2,
  //         nickname: "บอส ไอหลง",
  //         roomname: "6/2",
  //         university: "มหาลัยราชมงคล",
  //         branch: "วิศวกรรมเครื่องกล",
  //         isChack: false,
  //       },
  //       {
  //         id: 3,
  //         nickname: "โจ้ ปั่นป่วน",
  //         roomname: "6/2",
  //         university: "มหาลัยกรุงเทพ",
  //         branch: "นิเทศภาพยนตร์",
  //         isChack: false,
  //       },
  //       {
  //         id: 4,
  //         nickname: "ก้อง ไม่รุ",
  //         university: "มหาลัยกรุงเทพ",
  //         branch: "นิเทศภาพยนตร์",
  //         isChack: false,
  //       },
  //       {
  //         id: 5,
  //         nickname: "ฟ้า รักนะ",
  //         university: "มหาลัยมหิดล",
  //         branch: "วิศวกรรมเคมี",
  //         isChack: false,
  //       },
  //     ],
  //   };
  // },
  props:["data"]
  ,
  // methods: {
  //   Toggle(id) { //ปุ่มแสดงข้อมูล
  //     this.studentlist.map((item) => {
  //       if (item.id == id) {
  //         item.isChack = !item.isChack;
  //       }
  //     });
  //   },
  //   DeleteData(id) { //ปุ่มลบ
  //     this.studentlist = this.studentlist.filter((item) => {
  //       return item.id !== id;
  //     });
  //   },
  // },
  components: { 
    Students,

  
  },
};
</script>

<style scopped>
ul {
  list-style: none;
  margin: 1ex 1;
  padding: 0;
}
/* <style scoped> */
</style>
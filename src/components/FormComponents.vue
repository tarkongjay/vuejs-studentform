<template>
  <form @submit.prevent="formSummit">
    <div class="form-control">
      <label for="form_name">ชื่อนักเรียน : </label>
    <input type="text" v-model.trim="stu.name">
    </div>
    <div class="form-control">
      <label for="form_room">ชั้นเรียน : </label>
    <input type="text" v-model.trim="stu.room">
    </div>
    <div class="form-control">
      <label for="form_selectname">เลือกมหาลัยที่ได้ : </label>
    <select name="form_selectUni" v-model="stu.uni">
    <option value="มหาลัยกรุงเทพ">มหาลัยกรุงเทพ</option>
    <option value="มหาลัยมหิดล">มหาลัยมหิดล</option>
    <option value="มหาลัยราชมงคล">มหาลัยราชมงคล</option>
    <option value="มหาลัยศิลปากร">มหาลัยศิลปากร</option>
</select>
    </div>
    <div class="form-control">
      <label for="form_selectname">เลือกสาขา : </label>
    <select name="form_selectฺBra" v-model="stu.bra">
    <option value="นิเทศภาพยนตร์">นิเทศภาพยนตร์</option>
    <option value="วิทยาการคอมพิวเตอร์">วิทยาการคอมพิวเตอร์</option>
    <option value="วิศวกรรมเคมี">วิศวกรรมเคมี</option>
    <option value="วิศวกรรมเครื่องกล">วิศวกรรมเครื่องกล</option>
</select>
    </div>
    <div class="form-control">
      <label for="form_radio">เลือกเพศ : </label>
      <div>
        <input type="radio" value="เพศชาย" v-model="stu.gender">
        <label for="boy">ชาย</label>
      </div>
      <div>
        <input type="radio" value="เพศหญิง" v-model="stu.gender">
        <label for="girl">หญิง</label>
      </div>
    </div>
    <div class="form-control">
      <label for="form_radio">ทักษะภาษา : </label>
      <div>
        <input type="checkbox" value="ภาษาอังกฤษ" v-model="stu.skill">
        <label for="en">ภาษาอังกฤษ</label>
      </div>
      <div>
        <input type="checkbox" value="ภาษาญี่ปุ่น" v-model="stu.skill">
        <label for="japan">ภาษาญี่ปุ่น</label>
      </div>
      <div>
        <input type="checkbox" value="ภาษาจาวา" v-model="stu.skill">
        <label for="java">ภาษาจาวา</label>
      </div>
    </div>
    <button>บันทึกข้อมูล</button>
  </form>
</template>

<script>
export default {
name: 'formcomponents',
data(){
    return{
      stu: {
        name:"",room:"",uni:"",bra:"",gender:"",skill:[]
      }
    }
},
methods:{
  formSummit(){
    const newStudent={
   name:this.stu.name,
   room:this.stu.room,
   uni:this.stu.uni,
   bra:this.stu.bra,
   gender:this.stu.gender,
   skill:this.stu.skill
}
    this.$emit("save",newStudent)
    this.resetForm()
  },
  resetForm(){
    this.stu.name = "",
   this.stu.room = "",
   this.stu.uni ="มหาลัยกรุงเทพ",
   this.stu.bra ="นิเทศภาพยนตร์",
   this.stu.gender="",
   this.stu.skill=[]
  }
}
}
</script>

<style scoped>
form{
  padding: 1ex;
  margin-left: 5ex;
  margin-right: 5ex;
}
input,select{
  margin:15px 0;
	padding:15px 10px;
	width:100%;
	outline:none;
	border:1px solid #bbb;
	border-radius:20px;
	display:inline-block;
}
input:focus{
  margin:15px 0;
	padding:15px 10px;
	width:100%;
	outline:none;
	border:1px solid cornflowerblue;
	border-radius:20px;
	display:inline-block;
}
button{
  margin: 2px;
  padding: 7.5px 16px;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
  border: none;
  font-size: 2ex;
  border-radius: 5ex;
  background-color: cornflowerblue;
  color: white
}
button:focus{
  margin: 2px;
  padding: 7.5px 16px;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
  border: none;
  font-size: 2ex;
  border-radius: 5ex;
  background-color: rgb(141, 173, 233);
  color: white
}
input[type="radio"],input[type="checkbox"]{
display: inline-block;
width: auto;
margin-right: 2ex;
}
/* input[type="radio"]+label:focus{
color:cornflowerblue
} */
</style>
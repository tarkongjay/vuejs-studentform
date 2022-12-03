<template>
  <li>
    <img src="https://www.pngarts.com/files/11/Avatar-PNG-Download-Image.png" alt="avata">
    <!-- <slot></slot>//ให้มันไปอยู่หน้าทุกครั้ง อารมณ์เหมือน navbar เนื้อหาเราจะต่อจากรูป-->
    <slot name="card-name"></slot>
    <!-- <slot name="card-button"></slot> -->
    <slot name="card-info"></slot>
  </li>
</template>

<script>
export default {

}
</script>

<style scoped>
li{
  background-color: cornflowerblue;
  margin: 5ex;
    padding: 5ex;
    border-radius: 1ex;
    box-shadow: cornflowerblue 0px 5px, rgb(113, 157, 238) 0px 10px, rgb(133, 170, 238) 0px 15px, rgb(152, 181, 235) 0px 20px, rgb(161, 185, 230)0px 25px;
}
img{
    width: 100px;
    height: 100px;
}
</style>
<template>
  <CardBox>
    <template v-slot:card-header>
      <h1>{{ name }}</h1>
    </template>
    <!-- <template v-slot:card-button>
        <button @click="showDescription(id)">ดูรายละเอียด</button> &nbsp;
        <button @click="dropEmployees(id)">ลบข้อมูล</button>        
    </template> -->
    <!-- <template v-slot:card-content>
        <transition name="fade">
        <div v-show="isVisible">
            <p>เงินเดือน : {{ salary }} บาท ตำแหน่งงาน : {{ department }}</p>
        </div>
        </transition>       
    </template> -->
    <template v-slot:card-content>
        <p>เงินเดือน : {{ salary }} บาท, เพศ : {{ gender }}</p>
        <p>ตำแหน่งงาน : {{ department }}</p> 
        <p>ทักษะด้านภาษา : {{ language }}</p> 
        <!-- <div>
        <p>ทักษะภาษา:</p>
            <ul>
                <li v-for="(lang, index) in language" :key="index">{{ lang }}</li>
            </ul>
        </div>   -->
    </template>
  </CardBox>
</template>

<script>
import CardBox from "./CardBox.vue";
export default {
  name: "PersonItem",
  components: {
    CardBox,
  },
  data() {
    return {
      message: "ข้อมูลพนักงาน",
    };
  },
  props: {
    // id: {
    //   type: Number,
    //   required: true,
    // },
    name: {
      type: String,
      required: true,
    },
    salary: {
      type: Number,
      default: 15000,
    },
    department: {
      type: String,
      required: true,
    },
    gender:{
        type:String,
    },
    language:{
        type:String,
    }
    // isVisible: {
    //   type: Boolean,
    // },
  },
//   methods: {
//     showDescription(id) {
//       this.$emit("show", id);
//     },
//     dropEmployees(id) {
//       this.$emit("drop", id);
//     },
//   },
};
</script>

<style scoped>
/* li {
  margin: 1rem 0;
  font-size: 1.25rem;
  font-weight: bold;
  background: rgb(134, 168, 134);
  padding: 0.5rem;
  color: #1f1f1f;
  border-radius: 25px;
} */
button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #a66d6d;
  background: #a66d6d;
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
  border-radius: 25px;
}
.fade-enter-from {
  opacity: 0;
}
.fade-enter-active {
  transition: all 0.5s linear;
}
</style>
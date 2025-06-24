<template>
  <ul>
    <PersonItem
      v-for="(item, index) in employees"
      :key="index"
      :name="item.name"
      :salary="item.salary"
      :id="item.id"
      :department="item.department"
      :gender="item.gender"
      :language="item.language"
    />
  </ul>
</template>

<script>
import PersonItem from "./PersonItem.vue";
export default {
  name: "ListData",
  components: {
    PersonItem
  },
  props:["employees"]
//   data() {
//     return {
//       employees: [
//         { id: 1, name: "Piin", salary: 15000, department: "Developer", isVisible: false}, //ข้อมูลที่เก็บใน array จะเป็น object
//         { id: 2, name: "Fany", salary: 16000, department: "Developer", isVisible: false},
//         { id: 3, name: "Taeyeon", salary: 17000, department: "Developer", isVisible: false},
//         { id: 4, name: "Yoona", salary: 18000, department: "Developer", isVisible: false},
//         { id: 5, name: "Yuri", salary: 19000, department: "Developer", isVisible: false},
//         { id: 6, name: "Sunny", salary: 29000, department: "Developer", isVisible: false},
//       ],
//     };
//   },
//   methods:{
//     toggleVisible(id){
//         this.employees = this.employees.map((item) =>{
//             if(item.id === id){
//                 return {...item,isVisible:!item.isVisible}
//             }
//             return item
//         })
//     },
//     dropEmployees(id) {
//         this.employees = this.employees.filter(item =>{
//             return item.id !== id
//         })
//     }
//   }
    // @show="toggleVisible"
    // @drop="dropEmployees"
    // :isVisible="item.isVisible"
    // :key="item.id"
};
</script>

<style scope>
ul{
    list-style: none;
    margin: 1rem 0;
    padding: 0;
}
</style>
<template>
    <form @submit.prevent="submitForm">
        <div class="form-control">
            <label for="emp-name">ชื่อพนักงาน</label> &nbsp;
            <input type="text" v-model.trim="employee.name"/>
        </div>
        <div class="form-control">
            <label for="emp-salary">เงินเดือน</label> &nbsp;
            <input type="number" v-model="employee.salary"/>
        </div>
        <div class="form-control">
            <label for="department">ตำแหน่งงาน</label> &nbsp;
            <select v-model="employee.department">
                <option value="Developer">Developer</option>
                <option value="Marketing">Marketing</option>
                <option value="Finance">Finance</option>
                <option value="Sales">Sales</option>
            </select>
        </div>
        <div class="form-control">
            <h2>เพศ</h2>
            <div>
                <input type="radio" value="ชาย" v-model="employee.gender" />
                <label for="gender-name">ชาย</label>
            </div>
            <div>
                <input type="radio" value="หญิง" v-model="employee.gender" />
                <label for="gender-name">หญิง</label>
            </div>
            <div>
                <input type="radio" value="ไม่ระบุ" v-model="employee.gender" />
                <label for="gender-name">ไม่ระบุ</label>
            </div>
        </div>
        <div class="form-control">
            <h2>ทักษะด้านภาษา</h2>
            <div>
                <input type="checkbox" value="ภาษาอังกฤษ" v-model="employee.language" />
                <label for="skill">ภาษาอังกฤษ</label>
            </div>
            <div>
                <input type="checkbox" value="ภาษาจีน" v-model="employee.language" />
                <label for="skill">ภาษาจีน</label>
            </div>
            <div>
                <input type="checkbox" value="ภาษาญี่ปุ่น" v-model="employee.language" />
                <label for="skill">ภาษาญี่ปุ่น</label>
            </div>
            <div>
                <input type="checkbox" value="ภาษาเกาหลี" v-model="employee.language" />
                <label for="skill">ภาษาเกาหลี</label>
            </div>
            <div>
                <input type="checkbox" value="ภาษาไทย" v-model="employee.language" />
                <label for="skill">ภาษาไทย</label>
            </div>
        </div>
        <div>
            <button>บันทึกข้อมูล</button>
        </div>
    </form>
</template>

<script>
export default {
    name: "FormComponent",
    data() {
        return {
            employee:{
                name: "",
                salary:0,
                department:"",
                gender:"",
                language:[]
            }
        }
    },
    methods:{
        submitForm(){
            console.log("บันทึกข้อมูลพนักงานเรียบร้อยแล้ว");
            const newEmployee={
                name:this.employee.name,
                salary:this.employee.salary,
                department:this.employee.department,
                gender:this.employee.gender,
                language:this.employee.language
            }
            this.$emit("save",newEmployee)

        }
    }
}
</script>

<style scoped>
form{
    margin: 2rem auto;
    max-width: 40rem;
    border-radius: 12px;
    box-shadow: 2px 5px rgba(0, 0, 0, 0.25);
    padding: 2rem;
    background: #eee4b2;
}
.form-control{
    margin: 0.5rem 0;
}
label{
    font-weight: bolder;
}
input, select{
    display: block;
    width: 100%;
    font: inherit;
    margin-top: 0.5rem;
    background: #e5e4de;
    border-radius: 5px;
}
button{
    font: inherit;
    background: #f59a59;
    border-radius: 5px;
    color: #fff;
    cursor: pointer;
    padding: 0.25rem 0.75rem;
}
input[type="radio"], input[type="checkbox"]{
    display: inline-block;
    width: auto;
    margin-right: 0.3rem;
}
input[type="radio"]+label,
input[type="checkbox"]+label{
    font-weight: normal;
}
h2{
    font-size: 1rem;
    margin: 0.1rem 0;
}
</style>
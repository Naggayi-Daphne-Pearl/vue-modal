<template>
  <form>
      <label> Email</label>
      <input type="email" required v-model="email">
       <label> Password</label>
      <input type="password" required v-model="password">

      <label>Role:</label>
      <select v-model="role">
          <option value="developer">Web developer</option>
          <option value="designer">Web designer</option>
      </select>

      <label> Skills</label>
      <input type="text" v-model="tempSkill" @keyup.alt="addSkill">
      <div v-for="skill in skills" :key="skill" class="pill">
          {{ skill }}

      </div>


       <div>
          <input type="checkbox" value="surname" v-model="names">
          <label>Naggayi</label>
      </div>
      <div>
          <input type="checkbox" value="pearl" v-model="names">
          <label>Pearl</label>
      </div>
      <div>
          <input type="checkbox" value="daphne" v-model="names">
          <label>Daphne</label>
      </div>
      <div class="terms">
          <input type="checkbox" required v-model="terms">
          <label>Accept terms and conditions</label>
      </div>
     
  </form>
  <p>Email: {{ email }}</p>
  <p>Password: {{ password }}</p>
  <p>Role: {{ role }}</p>
  <p>Terms Accepted: {{ terms }}</p>


</template>

<script>
// two  way data binding means data is bound in two ways from the input output and data 
export default {
    data() {
        return {
            email: '', 
            password: '', 
            role: '', 
            terms: false, 
            names: [], 
            tempSkill: '', 
            skills: []


        }
    }, 
    methods: {
        addSkill(e) {
           //console.log(e); 
           if (e.key === ',' && this.tempSkill) {
               // this makes sure the skill selected is not duplicated
               if (!this.skills.includes(this.tempSkill)) {
                   this.skills.push(this.tempSkill) 
               }
              this.tempSkill = ''
           }
        }
    }

}
</script>

<style>
    form {
        max-width: 420px;
        margin: 30px auto;
        background: white;
        text-align: center;
        padding: 40px;
        border-radius: 10px;
    }
    label {
        color: #aaa;
        display: inline-block;
        margin: 25px 0 15px;
        font-size: 0.6rem;
        text-transform: uppercase;
        letter-spacing: 1px;
        font-weight: bold;
    }
    input, select{
        display: block;
        padding: 10px 6px;
        width: 100%;
        box-sizing: border-box;
        color: #5555;
    }
    input[type="checkbox"] {
        display: inline-block;
        width: 16px;
        margin: 0 10px 0 0;
        position: relative;
        top: 2px;
    }
</style>
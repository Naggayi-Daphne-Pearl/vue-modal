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
  </form>
  <p>Email: {{ email }}</p>
  <p>Password: {{ password }}</p>
  <p>Role: {{ role }}</p>

</template>

<script>
// two  way data binding means data is bound in two ways from the input output and data 
export default {
    data() {
        return {
            email: '', 
            password: '', 
            role: ''

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
</style>
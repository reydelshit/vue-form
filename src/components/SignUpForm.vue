<template>
  <form>
      <label for="email">email</label>
        <input v-model="email" type="email" required>
      <label for="password">password</label>
        <input type="password" v-model="password">
      <label for="role">role</label>
        <select name="role" id="role">
            <option value="webdev">web dev</option>
            <option value="webdev">web dev</option>
            <option value="webdev">web dev</option>
            <option value="webdev">web dev</option>
      </select>
      <label for="skills">skills:</label>
        <input type="text">
    <input type="checkbox">
    <label for="accept">terms</label>
  </form>
  <h1>{{email}}</h1>
  <h1>{{password}}</h1>

</template>

<script>
export default {
    data(){
        return{
            email: '',
            password: null
        }
    }
}
</script>

<style scoped>
form {
    max-width: 420px;
    margin: 30px auto;
    background: white;
    text-align: left;
    padding: 40px;
    border-radius: 10px;
  }
label {
    color: #aaa;
    display: inline-block;
    margin: 25px e 15px;
    font-size: 0.6em;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold; 
  }
input {
    display: block;
    padding: 10px 6px;
    width: 100%;
    box-sizing: border-box;
    border: none;
    border-bottom: 1px solid #ddd;
    color: #555;
  }
</style>
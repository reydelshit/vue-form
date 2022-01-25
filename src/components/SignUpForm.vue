<template>
  <form @submit.prevent="signUp">
      <label>email</label>
        <input v-model="email" type="email" required>
      <label>password</label>
        <input type="password" v-model="password">
        <span v-if="passWarning" style="display: block;" class="warning">{{passWarning}}</span>
      <label>role</label>
        <select v-model="role">
            <option value="webdev">web dev</option>
            <option value="ws">ws dev</option>
            <option value="wew">wew dev</option>
            <option value="por">por dev</option>
      </select>
        <label>skills(press alt)</label>
            <input type="text" v-model="temporarySkill" @keyup="bro">
            <p class="warning" >{{warning}}</p>
        <div class="pill" v-for="skill in skill" :key="skill">
            <span @click="removeSkill(skill)">{{skill}}</span>
        </div>

        <div class="terms">
            <input type="checkbox" v-model="terms" required>
            <label>terms</label>
        </div>

    <div class="submit">
        <button>sign up</button>
    </div>
  </form>
</template>

<script>
export default {
    data(){
        return{
            email: '',
            password: null,
            role: '',
            terms: false,
            temporarySkill: '',
            skill: [],

            warning: '',
            passWarning: ''
        }
    },
    methods: {
        bro(e){
            if(e.keyCode === 18){
                if(!this.skill.includes(this.temporarySkill)){
                    this.skill.push(this.temporarySkill) 
                    this.warning = ''
                } else {
                    this.warning = 'u cant add the same shit over and over again'
                }
                    this.temporarySkill = ''

            }
        },
        removeSkill(w) {
            console.log('uy')
            this.skill = this.skill.filter((e) => {
                return e !== w
            })
        },
        signUp(){
            this.passWarning = this.password.length > 8 ? '' : 'password should be long bro';

            if(!this.passWarning){
                console.log(this.email)
                console.log(this.password)
                console.log(this.role)
                console.log(this.terms)
                console.log(this.skill)
            }
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
    margin: 25px 0 15px;
    font-size: 0.6em;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold; 
}
input, select {
    display: block;
    padding: 10px 6px;
    width: 100%;
    box-sizing: border-box;
    border: none;
    border-bottom: 1px solid #ddd;
    color: #555;
}

.skills{
    display: block;

}



input[type="checkbox"] {
    display: inline-block;
    width: 16px;
    margin: 0 10px 0 0;
    position: relative;
    top: 2px;
}

.pill {
  display: inline-block;
  margin: 20px 10px 0 0;
  padding: 6px 12px;
  background: #eee;
  border-radius: 20px;
  font-size: 12px;
  letter-spacing: 1px;
  font-weight: bold;
  color: #777;
  cursor: pointer;
}

button {
  background: #eb6dff;
  border: 0;
  padding: 10px 20px;
  margin-top: 20px;
  color: white;
  border-radius: 20px;
  cursor: pointer;
}
.submit {
  text-align: center;
}

.warning{
    color: red;
    font-size: 1rem;
    margin-top: 5px;
}

</style>
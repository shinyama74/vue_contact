
<template>
  <div id="app">
    <div>
      ・お名前  <input type="text" name="name" v-model = "form.name"><br>
      ・メールアドレス  <input type="text" name="address" v-model = "form.address"><br>
      ・件名  <input type="text" name="subjects" v-model = "form.subjects"><br>
      ・本文  <input type="text" name="text" v-model = "form.text"><br>
      <div v-if="error.name"> 名前を入力してください。</div>
      <div v-if="error.address"> メールアドレスを入力してください。</div>
      <div v-if="error.subjects"> 件名を入力してください。</div>
      <div v-if="error.text"> 本文を入力してください。</div>
    </div>
    <input type="submit" value="送信"　@click="submit">

    <p>{{form.name.length}}/20</p>
  </div>
</template>

<script>
  export default {
    data(){
      return {
        form:{
          name: "",
          address: "",
          subjects: "",
          text: "",

        },
        error: {
          name: false,
          address: false,
          subjects:false,
          text: false,
        }
      }
    },
    methods: {
      submit(e) {
        if(this.form.name.length ==0) {
          this.error.name = true
          e.prevebtDefault()
        }else if(this.form.address.length ==0) {
          this.error.address = true
          e.prevebtDefault()
        }else　if(this.form.subjects.length ==0) {
          this.error.subjects = true
          e.prevebtDefault()
        }else　if(this.form.text.length ==0) {
          this.error.text = true
          e.prevebtDefault()
        }
        else{
          this.error.name = false
        }
      }
    },



    // ナビゲーション編
    methods: {
      scroll(){
        this.$scrollTo("body",500)
    }
  }








  }
</script>

<style>
</style>
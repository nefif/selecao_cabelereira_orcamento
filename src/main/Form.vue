<template>
<div class="main-former">
    <header>{{msg}}</header>
    <div class="form-groups">
        <form action="#" class="form-itens">
            <div class="page"><FormService/></div>
            <div class="page"><FormWho/></div>
            <div class="page"><FormMany/></div>
            <div class="page"><FormWhen/></div>
            <div class="page"><FormAd/></div>           
            <div class="page"><FormUser/></div>   
        </form>
    </div>
</div>
</template>

<script>
import FormService from '../components/FormService.vue'
import FormWho from '../components/FormWho.vue'
import FormMany from '../components/FormMany.vue'
import FormWhen from '../components/FormWhen.vue'
import FormAd from '../components/FormAd.vue'
import FormUser from '../components/FormUser.vue'

export default {
    data() {
        return {
            msg: 'Solicitação de Orçamento' 
        }
    },
    components: { FormService, FormWho, FormMany, FormWhen, FormAd, FormUser },

  

}
</script>

<style>

/* Works on Firefox */
* {
  scrollbar-width: thin;
  scrollbar-color: blue rgb(255, 255, 254);
}

/* Works on Chrome, Edge, and Safari */
*::-webkit-scrollbar {
  width: 12px;
}

*::-webkit-scrollbar-track {
  background: rgb(255, 255, 255);
}

*::-webkit-scrollbar-thumb {
  background-color: blue;
  border: solid transparent
}

*{
  margin: 0;
  padding: 0;
  outline: none;
  font-family: 'Poppins', sans-serif;
}
body{
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(to right, rgb(39, 27, 110), rgb(56, 92, 250), rgb(60,80,236));
}

::selection{
  color: #fff;
  background: #2500cc;
}

.main-former{
  max-width: 330px;
  max-height: 1570px;
  width: auto;
  height: auto;
  background: rgb(241, 207, 14);
  text-align: center;
  border-radius: 5px;
  padding: 50px 35px 10px 35px;
  
}
.main-former header{
  font-size: 35px;
  font-weight: 600;
  margin: 0 0 30px 0;
}

.form-groups form .page{
  width: 100%;
  height: 100%;
}

.main-former .form-groups{
  width: 100%;
}
.form-groups .form-itens .page .title{
  text-align: left;
  font-size: 25px;
  font-weight: 500;
}
.form-groups .form-itens .page .field{
  width: 330px;
  height: 45px;
  margin: 45px 0;
  display: flex;
  position: relative;
}
.form-itens .page .field .label{
  position: absolute;
  top: -30px;
  font-weight: 500;
}

.form-itens .page .field input{
  height: 100%;
  width: 100%;
  border: 1px solid rgb(0, 0, 0);
  border-radius: 5px;
  padding-left: 15px;
  font-size: 18px;
}

.form-itens .page .field select{
  width: 100%;
  padding-left: 10px;
  font-size: 17px;
  font-weight: 500;
  height: 100%;
  width: 100%;
  border: 1px solid rgb(8, 8, 8);
  border-radius: 5px;
  padding-left: 15px;
}

.form-itens .page .field button{
  width: 100%;
  height: calc(100% + 5px);
  border: none;
  background: #2500cc;
  margin-top: -20px;
  border-radius: 5px;
  color: #fff;
  cursor: pointer;
  font-size: 18px;
  font-weight: 500;
  letter-spacing: 1px;
  text-transform: uppercase;
  transition: 0.5s ease;
  box-shadow: 5px 5px rgb(46, 45, 45);
}

.form-itens .page .field button:hover{
  background: #000;
}

.form-itens .page .field button:active{
  background-color: #0fc915;
  color: #fff;
  box-shadow: 5px 5px rgb(46, 45, 45);
  transform: translateY(10px);
}



</style>
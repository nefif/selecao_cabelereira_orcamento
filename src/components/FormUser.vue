<template>
    <div v-bind="getData()">
        <div id="nameUs" class="title">Dados para Contato</div>
            
            <div class="field">
                <div id="label-cep" class="label"/>
                <input type="" placeholder="" required>
            </div>
            <div class="field">
                <div id="label-name" class="label"/>
                <input type="" placeholder="" required>
            </div>
            <div class="field">
                <div id="label-email" class="label"/>
                <input type="email" placeholder="Ex: nome@email.com" required>
            </div>
            <div class="field">
                <div id="label-phone" class="label"/>
                <input type="tel" placeholder="" required>
            </div>
            <div class="field">
                <button type="submit" v-bind:class=btnSubmit>{{btnText}}</button>
            </div>
    </div>
</template>

<script>
export default {

    data() {
        return {
           btnSubmit : 'submit',
           btnText : 'Enviar Solicitação'
        }
    },

    methods: {

        getData() {
           
        fetch('https://raw.githubusercontent.com/matheusliraofficial/teste-vaga-frontend/main/fields.json')
        .then(resp=> resp.json())
        .then(fields=>{
        document.getElementById("label-cep").innerHTML=fields._embedded.user_fields[0].label,
        document.getElementById("label-name").innerHTML=fields._embedded.user_fields[1].label,
        document.getElementById("label-email").innerHTML=fields._embedded.user_fields[2].label,
        document.getElementById("label-phone").innerHTML=fields._embedded.user_fields[3].label;
               
    })
        }
    },

}
</script>

<style>

</style>
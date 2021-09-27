<template>
    <div v-bind="getData()">
        <div id="nameW" class="title"/>
            <div class="field">
                <div id="labelW" class="label"/>
                <select >
                    <option class="iten" value="">{{sltNull}}</option>
                    <option id="crianca" class="iten" value="crianca"/>
                    <option id="homem" class="iten " value="homem"/>
                    <option id="mulher" class="iten " value="mulher"/>
                </select>
        </div>
    </div>
</template>

<script>
export default {

    data() {
            return {
                sltNull: 'Selecione para quem será o serviço',
                btnTxt: 'Próximo'
            }
        },

    methods: {
        getData() {
            
        fetch('https://raw.githubusercontent.com/matheusliraofficial/teste-vaga-frontend/main/fields.json')
        .then(resp=> resp.json())
        .then(fields=>{
        document.getElementById("nameW").innerHTML=fields._embedded.request_fields[1].name,
        document.getElementById("labelW").innerHTML=fields._embedded.request_fields[1].label,
        document.getElementById("crianca").innerHTML=fields._embedded.request_fields[1].values['Criança'],
        document.getElementById("homem").innerHTML=fields._embedded.request_fields[1].values['Homem'],
        document.getElementById("mulher").innerHTML=fields._embedded.request_fields[1].values['Mulher'];        
    })
        }
    }

}
</script>

<style>

</style>
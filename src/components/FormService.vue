<template>
    <div class="slide-page" v-bind="getData()">
        <div id="nameS" class="title"/>
            <div class="field">
                <div id="labelS" class="label"/>
                <select required>
                    <option class="iten" value="">{{sltNull}}</option>
                    <option id="coloracao" class="iten" value="coloracao"/>
                    <option id="corte" class="iten " value="corte"/>
                    <option id="escova" class="iten " value="escova"/>
                    <option id="escova-p" class="iten" value="escova-progressiva"/>
                    <option id="luzes" class="iten" value="luzes"/>
                    <option id="manicure" class="iten" value="manicure"/>
                    <option id="pedicure" class="iten" value="pedicure"/>
                    <option id="penteado" class="iten" value="penteado"/>
                </select>
        </div>
    </div>
</template>

<script>

export default {

    data() {
            return {
                sltNull: 'Selecione um Serviço',
                btnTxt: 'Próximo',
                divClass: 'slide-page',
                btnClass: 'firstNext'
            }
        },

    methods: {

        /* click() {      
           moveTo(120,120)                
        }, */

        /* turnPage() {
            if(this.click()===true){
                alert("clicou")
            }
        }, */

        getData() {
            
        fetch('https://raw.githubusercontent.com/matheusliraofficial/teste-vaga-frontend/main/fields.json')
        .then(resp=> resp.json())
        .then(fields=>{
        document.getElementById("nameS").innerHTML=fields._embedded.request_fields[0].name,
        document.getElementById("labelS").innerHTML=fields._embedded.request_fields[0].label,
        document.getElementById("coloracao").innerHTML=fields._embedded.request_fields[0].values['Coloração'],
        document.getElementById("corte").innerHTML=fields._embedded.request_fields[0].values['Corte'],
        document.getElementById("escova").innerHTML=fields._embedded.request_fields[0].values['Escova '],
        document.getElementById("escova-p").innerHTML=fields._embedded.request_fields[0].values['Escova progressiva/definitiva'],
        document.getElementById("luzes").innerHTML=fields._embedded.request_fields[0].values['Luzes'],
        document.getElementById("manicure").innerHTML=fields._embedded.request_fields[0].values['Manicure'],
        document.getElementById("pedicure").innerHTML=fields._embedded.request_fields[0].values['Pedicure'],
        document.getElementById("penteado").innerHTML=fields._embedded.request_fields[0].values['Penteado'];
        
    })
        }
    },

}
</script>

<style scoped>

</style>
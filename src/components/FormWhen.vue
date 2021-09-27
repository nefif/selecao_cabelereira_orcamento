<template>
    <div v-bind="getData()">
        <div id="nameWh" class="title"/>
            <div class="field">
                <div id="labelWh" class="label"/>
                <select required >
                    <option class="iten" value="">{{msgSelect}} </option>
                    <option class="iten" value="">{{sltNull}}</option>
                    <option id="hoje" class="iten" value="hoje"/>
                    <option id="30d" class="iten " value="30 dias"/>
                    <option id="3m" class="iten " value="3 meses"/>
                    <option id="nd" class="iten " value="nd"/>
                </select>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            msgSelect : 'Quem Irá usar o Serviço?',
            sltNull: 'Selecione Quando Deseja o Serviço',
            btnTxt: 'Próximo'
        }
    },

    methods: {
        getData() {
            
        fetch('https://raw.githubusercontent.com/matheusliraofficial/teste-vaga-frontend/main/fields.json')
        .then(resp=> resp.json())
        .then(fields=>{
        document.getElementById("nameWh").innerHTML=fields._embedded.request_fields[3].name,
        document.getElementById("labelWh").innerHTML=fields._embedded.request_fields[3].label,
        document.getElementById("hoje").innerHTML=fields._embedded.request_fields[3].values['Hoje ou nos próximos dias'],
        document.getElementById("30d").innerHTML=fields._embedded.request_fields[3].values['Nos próximos 30 dias'],
        document.getElementById("3m").innerHTML=fields._embedded.request_fields[3].values['Nos próximos 3 meses'],
        document.getElementById("nd").innerHTML=fields._embedded.request_fields[3].values['Ainda não tenho previsão'];        
    })
        }
    }

}
</script>

<style>

</style>
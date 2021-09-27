<template>
    <div v-bind="getData()">
        <div id="nameM" class="title"/>
            <div class="field">
                <div id="labelM" class="label"/>
                <select >
                    <option class="iten" value="">{{sltNull}}</option>
                    <option id="n1" class="iten" value="1"/>
                    <option id="n2" class="iten " value="2"/>
                    <option id="n3+" class="iten " value="3"/>
                </select>
        </div>
    </div>
</template>

<script>
export default {

    data() {
            return {
                sltNull: 'Quem Irá Usar o Serviço?',
                btnTxt: 'Próximo'

            }
        },
    methods: {
        getData() {
            
        fetch('https://raw.githubusercontent.com/matheusliraofficial/teste-vaga-frontend/main/fields.json')
        .then(resp=> resp.json())
        .then(fields=>{
        document.getElementById("nameM").innerHTML=fields._embedded.request_fields[2].name,
        document.getElementById("labelM").innerHTML=fields._embedded.request_fields[2].label,
        document.getElementById("n1").innerHTML=fields._embedded.request_fields[2].values['1'],
        document.getElementById("n2").innerHTML=fields._embedded.request_fields[2].values['2'],
        document.getElementById("n3+").innerHTML=fields._embedded.request_fields[2].values['Mais de 3'];        
    })
        }
    }

}
</script>

<style>

</style>
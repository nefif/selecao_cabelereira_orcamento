<template>
    <div v-bind="getData()">
        <div id="nameA" class="title"/>
            <div class="field">
                <div id="labelA" class="label"/>
                <textarea id="txtA" rows="10" cols="50" wrap="soft" :placeholder="getData()"></textarea>
        </div>
    </div>
</template>

<script>
export default {

    data() {
            return {
                btnTxt: 'Próximo'

            }
        },

    methods: {
        getData() {
            
        fetch('https://raw.githubusercontent.com/matheusliraofficial/teste-vaga-frontend/main/fields.json')
        .then(resp=> resp.json())
        .then(fields=>{
        document.getElementById("nameA").innerHTML=fields._embedded.request_fields[4].name,
        document.getElementById("labelA").innerHTML=fields._embedded.request_fields[4].label;
        document.getElementById("txtA").innerHTML=fields._embedded.request_fields[4].placeholder;       
    })
        }
    }

}
</script>

<style>
textarea{
    resize: none;
}
</style>
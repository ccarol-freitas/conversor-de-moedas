<template>
    <div class="conversor">
        <h2>{{ moedaA }} para {{ moedaB }}</h2>
        <input class="moedaA" type="text" v-model="moedaA_value" v-bind:placeholder="moedaA" />
        <br />
        <input class="btnCon" type="button" value="Converter" v-on:click="converter" />
        <h2>{{ moedaB_value }}</h2>
    </div>
</template>

<script>
export default {
    name: "Conversor",
    props: ["moedaA", "moedaB"],
    data() {
        return {
            moedaA_value: "",
            moedaB_value: 0
        };
    },
    methods: {
        converter() {
            let de_para = this.moedaA + '_' + this.moedaB;
            let url = 'https://free.currencyconverterapi.com/api/v6/convert?q=' + de_para + '&compact=y&apiKey=9efaf120b22fde4b9a53';
            fetch(url)
                .then(res => {
                    return res.json()
                })
                .then(json => {
                    let cotacao = json[de_para].val;
                    this.moedaB_value = (parseFloat(this.moedaA_value) * cotacao).toFixed(2)
                })
        }
    }
};
</script>

<style scoped>
.conversor {
    padding: 20px;
    max-width: 300px;
    width: 300px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    background: #ffff;
}

.btnCon {
    border-radius: 5px;
    color: #fff;
    background: #94b793;
    border: #94b793;
    height: 40px;
    width: 150px;
    margin: 10px;
    font-size: 18px;
}

.moedaA {
    width: 250px;
    height: 40px;
    border-radius: 3px;
    border: 1px solid #ccc;
    text-align: center;
    font-size: 25px;
}

.moedaA:hover {
    border: 1px solid #94b793;
}
</style>
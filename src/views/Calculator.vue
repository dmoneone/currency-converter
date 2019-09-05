<template>
  <div class="calc" v-bind="getApi">
    <div class="container">
        <div class="calc-wrap">
            <input class="form-control" type="text" id="rate" v-model="val" v-on:keyup="calcRate">
            <select class="browser-default custom-select custom-select-lg mb-3" v-model="selected_rate" v-on:change="calcRate">
              <option disabled value="">Выберите один из вариантов</option>
              <option  v-for="ccy in rates">{{ccy.ccy}}</option>
            </select>
            <span for="uah">{{result}} UAH</span>
        </div>
    </div>
  </div>
</template>


<script>
    export default {
        data(){
            return{
                val:'',
                result:'...',
                rates: [],
                selected_rate: '',
                exhange_rate: {
                    url: "https://api.privatbank.ua/p24api/pubinfo?json&exchange&coursid=5"
                }
            }
        },
        
        computed: {
            getApi(){
                axios.get(this.exhange_rate.url)
                .then(response => {
                    this.rates = response.data;
                    console.log(this.rates);
                })
                .catch(error => console.error(error));
            }
        },
        methods: {
            calcRate(){
                this.rates.forEach(i => {
                    if(i.ccy == this.selected_rate) {
                      this.result = this.val * i.sale;
                    } return;
                })
            }
        }
    }
</script>


<style scoped lang="scss">
    .calc-wrap{
        max-width: 350px;
        width: 100%;
    }
    input,select,span{
        display: block;
        width: 100%;
        font-size: 20px !important;
        margin-top: 5px;
    }
    span{
        border-bottom: 1px solid #ced4da;
        padding-bottom: 5px;
    }
</style>
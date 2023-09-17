<template>
    <Header name="Dashboard"></Header>
    
        <div class="d-flex" :class="[darkmode ? 'darkmode' : '']">
            <div class="col-8">
                <!-- <DashboardChart></DashboardChart> -->

            </div>
            
            
            <div class="col-4 d-flex flex-column p-5">
                <div class="balance">
                    <h4 class="fw-bold">Total Balance :</h4>
                    <h4>{{ data.dashboard[0].balance}}</h4>
                </div>
                <div class="d-flex flex-row justify-content-between mt-5 card_info ">
                    <div class="income "> 
                        <h6 class="fw-bold m-0">Income: </h6>
                        <h6 class="m-0"> {{ data.dashboard[0].income }}</h6>
                    </div>
                    <div class="expenses">
                        <h6 class="fw-bold m-0">Expenses: </h6>
                        <h6 class="m-0">17500</h6>
                    </div>
                    <div class="creadit">
                        <h6 class="fw-bold m-0">Creadit Limit :</h6>
                        <h6 class="m-0">{{ data.dashboard[0].credit }}</h6>
                    </div>
                </div>

            </div>

        </div>

</template>
<script>
import Header from '../components/Header.vue';
import sourceData from '../data.json'
import DashboardChart from '../components/DashboardChart.vue';
export default{
    data(){
        return{
            data : sourceData,
            darkmode : sourceData.darkMode           
        }
    },
    components:{
        Header,
        DashboardChart
    }
}
</script>
<style lang="scss" scoped>
.darkmode , .darkmode >* {
    background-color: #1f1f1f;
    color: #e8e8e8;
    .col-4 > *{
        background-color: inherit;
        color: inherit;
    }
    h4,h6{
        background-color: #1f1f1f;
        color: #e8e8e8;
    }
}
.card_info{
    background-color: inherit;
    color: inherit;
}

    // .darkmode, .darkmode > *{
    //     background-color: #1f1f1f!important;
    //  }

    //  .darkmode > div > .balance,.darkmode > div > .balance > h4  {
    //     background-color: #1f1f1f;
    //     color: #e8e8e8;
    //  }
    //  .darkmode > div > .card_info, .darkmode > div > .card_info > div > h6{
    //     background-color: #1f1f1f;
    //     color: #e8e8e8;
    //     margin: 0;
    //  }
    /* .balance , .balance > * ,.income, .income > * , .expenses , .expenses > * , .creadit , .creadit > *{
        background-color: #1f1f1f;
        color: #e8e8e8;
    } */

</style>
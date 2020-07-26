<template>
    <div class="container">
         <!-- Side navigation -->
         <span class="row">
            <h1 class="col-5">Dashboard</h1>
            <div class="col-7 bg-white mb-2 mt-1 shadow-sm bg-white">
                <a v-b-toggle.collapse-1>
                    <div class="row" style="height:50px" >
                        <div class="col-4 align-self-center">
                            <p class="col small-text my-auto"><img alt="calendar"  
                                height="20px" src="@/assets/calendar.png" class="mr-2">  Period</p>
                        </div>
                        <div class="col-8 align-self-center">
                            <p class="my-auto small-text"> 11 September 2018 - 14 September 2018  <i class="fa fa-angle-down ml-1"></i></p>
                            
                        </div>
                        
                    </div>
                </a>

                <b-collapse id="collapse-1">
                    <div class="row">
                        <div class="col-2">
                        tes
                        
                        </div>
                        <div class="col-5">
                        <b-calendar v-model="value" @context="onContext" width="150px" locale="en-US"></b-calendar>
                        
                        </div>
                        <div class="col-5">
                        <b-calendar v-model="value" @context="onContext" width="150px" locale="en-US"></b-calendar>
                        
                        </div>
                    </div>
                </b-collapse>
            </div>
         </span>

         <span class="row mt-4 p-3" style="background-color: #37B04C">
            <div class="col d-flex h-100" >
                <div class="font-weight-bold text-white">MARKET INSIGHT</div>
            </div> 
         </span>

         <span class="row mt-4">

            <div class="card col-4">
                <div class="card-body">
                    <div class="row card-title">
                        <h6 class="col card-title">Sales Turnover</h6>
                        <img alt="triple_dot" height="25px" src="@/assets/triple_dot.svg">
                    </div>

                    <div class="row card-text">
                        <div class="col-9">
                            <h3 class="">Rp. 3,600,000</h3>
                            <p class="card-text">
                                <img alt="Advotics logo" height="10px" src="@/assets/downarrow.svg">
                                <small class="font-weight-bold text-danger">     13,8% </small>
                                <small class="text-muted">last period in product sold</small>
                            </p>
                        </div>
                        <div class="col-3">
                            <img alt="Advotics logo" height="60px" src="@/assets/sales_turnover.svg">
                        </div>
                    </div>
                </div>
            </div>

         </span>

         <span class="row mt-4">
            <div class="card col-6 mr-3">
                <div class="card-body">
                    <div class="row card-title">
                        <h5 class="col-7 card-title text-dark">AVERAGE PURCHASE VALUE</h5>
                        <div class="col"></div>
                        <img alt="triple_dot" height="25px" src="@/assets/triple_dot.svg">
                    </div>
                    <div class="row card-title">
                        <div class="col-12">
                            <chart :chartdata="chartdata" :options="options" />
                        </div>
                        
                    </div>
                </div>
            </div>


            <div class="card col">
                <div class="card-body">
                    <div class="row card-title">
                        <h5 class="col-11 card-title text-dark">BEST SELLING SKU</h5>
                        <img alt="triple_dot" height="25px" src="@/assets/triple_dot.svg">
                    </div>
                    <objectcard />
                </div>
            </div>
            
            
            <div class="card col ml-3">
                <div class="card-body">
                    <div class="row card-title">
                        <h5 class="col-11 card-title text-dark">TOP COMPETITOR SKU</h5>
                        <img alt="triple_dot" height="25px" src="@/assets/triple_dot.svg">
                    </div>
                    <objectcard />
                </div>
            </div>

         </span>
         
        
    </div>
  
</template>

<script>
import Chart from '@/components/Chart.vue'
import Objectcard from '@/components/Objectcard.vue'

export default {
  name: 'Content',
  components: {
    Chart,
    Objectcard,
  },
  data() {
      return {
            chartdata: {
                labels: ['January'],
                datasets: [
                    {
                        label: 'Data One',
                        backgroundColor: '#f87979',
                        data: [40, 20]
                    }
                ]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false
            },
            value: '',
            context: null,

      }
  },
  methods: {
        onContext(ctx) {
            this.context = ctx
        }
    }
}
</script>

<style scoped>

.small-text {
    font-size: 14px;
}

</style>
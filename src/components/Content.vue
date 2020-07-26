<template>
    <div class="container">
         <!-- Side navigation -->
         <span class="row">
            <h1 class="col-4">Dashboard</h1>
            <div class="col-8 bg-white mb-2 mt-1 shadow-sm bg-white" @click="openCollapse" v-click-outside="closeCollapse">
                <a>
                    <div class="row" style="height:50px" >
                        <div class="col-3 align-self-center">
                            <p class="col small-text my-auto"><img alt="calendar"  
                                height="20px" src="@/assets/calendar.png" class="mr-2">Period</p>
                        </div>
                        <div class="col-9 align-self-center">
                            <p class="my-auto small-text float-right"> 11 September 2018 - 14 September 2018  <i class="fa fa-angle-down ml-1"></i></p>
                            <a @click="closeCollapse"><i class="fa fa-times float-right" aria-hidden="true"></i></a>
                        </div>
                        
                    </div>
                </a>

                <b-collapse id="collapse-1" :visible="visibility" ref="collapseb">
                    <div class="row mb-3 mt-3">
                        <div class="col-3">
                            <div 
                                class="col-12 calendar-button m-auto" 
                                @click="onDay('today')"
                                :class="stateButton == 'today'? 'text-success font-weight-bold':''"
                            >
                                Today
                            </div>
                            <div 
                                class="col-12 calendar-button m-auto" 
                                @click="onDay('yesterday')"
                                :class="stateButton == 'yesterday'? 'text-success font-weight-bold':''"
                            >
                                Yesterday
                            </div>
                            <div 
                                class="col-12 calendar-button m-auto" 
                                @click="onDay('last7')"
                                :class="stateButton == 'last7'? 'text-success font-weight-bold':''"
                            >
                                Last 7 days
                            </div>
                            <div 
                                class="col-12 calendar-button m-auto" 
                                @click="onDay('last30')"
                                :class="stateButton == 'last30'? 'text-success font-weight-bold':''"
                            >
                                Last 30 days
                            </div>
                            <div 
                                class="col-12 calendar-button m-auto" 
                                @click="onDay('month')"
                                :class="stateButton == 'month'? 'text-success font-weight-bold':''"
                            >
                                This Month
                            </div>
                            <div 
                                class="col-12 custom-button m-auto"
                            >
                                Custom
                            </div>
                            <button @click="submitSelectedDate">apply</button>
                        
                        </div>
                        <div class="col">
                            <v-date-picker
                                mode="multiple"   
                                v-model='selectedDate'
                                :max-date="new Date(new Date().setDate(new Date().getDate()-1))"
                                color="green"
                                show-caps
                                is-inline>
                            </v-date-picker>
                        
                        </div>
                        <div class="col">
                            <v-date-picker
                                mode="multiple"
                                v-model='selectedDate'
                                :max-date="new Date(new Date().setDate(new Date().getDate()-1))"
                                color="green"
                                show-caps
                                is-inline>
                            </v-date-picker>
                        
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
import ClickOutside from 'vue-click-outside'

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
            attributes: [
                {
                    key: 'today',
                    highlight: true,
                    dates: new Date()
                }
            ],
            selectedDate: null,
            visibility: false,
            oldSelectedDate: null,
            stateButton: null,
      }
  },
  directives: {
    ClickOutside
  },
  methods: {
        onContext(ctx) {
            this.context = ctx
        },
        closeCollapse() {
            if (this.$refs.collapseb.show == true){
                this.selectedDate = this.oldSelectedDate
                this.$refs.collapseb.show = false
            }
            
        },
        openCollapse() {
            if (this.$refs.collapseb.show == false){
                this.$refs.collapseb.show = true
            }
        },
        submitSelectedDate() {
            this.oldSelectedDate = this.selectedDate
            this.$root.$emit('bv::toggle::collapse', 'collapse-1')

        },
        onDay(value) {
            var moment = require('moment'); // require
            moment().format(); 
            if (value == "today"){
                this.stateButton = 'today'
                this.selectedDate = [
                    new Date(),
                ]
            }
            else if (value == "yesterday"){
                this.stateButton = 'yesterday'
                this.selectedDate = [
                    new Date(new Date().setDate(new Date().getDate()-1)),
                ]
            }
            else if (value == "last7"){
                this.stateButton = 'last7'
                this.selectedDate = [
                    {
                        start: moment().subtract(1, 'days').toDate(),
                        end: moment().subtract(7, 'days').toDate()
                    },
                ]
            }
            else if (value == "last30"){
                this.stateButton = 'last30'
                this.selectedDate = [
                    {
                        start: moment().subtract(1, 'days').toDate(),
                        end: moment().subtract(30, 'days').toDate()
                    },
                ]
            }
            else if (value == "month"){
                this.stateButton = 'month'
                this.selectedDate = [
                    {
                        start: moment().startOf('month').toDate(),
                        end: moment().endOf('month').toDate()
                    },
                ]
            }
        }
    }
}
</script>

<style scoped>

.small-text {
    font-size: 14px;
}

.calendar-button {
    font-size: 12px;
    padding-top: 3px;
    padding-bottom: 7px;
    border-bottom-style: solid;
    border-width: 1px;
    cursor: pointer;
    height: 50px;

}

.custom-button {
    font-size: 12px;
    padding-top: 3px;
    padding-bottom: 7px;
    cursor: pointer;
    height: 50px;

}
</style>
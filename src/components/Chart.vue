<script>
import { Bar } from 'vue-chartjs'
// const { reactiveProp } = mixins

export default {
    extends: Bar,
//   mixins: [reactiveProp],
//   props: ['options'],
    data: () => ({
    chartdata: {
      labels: ['January', 'February', 'March', 'April', 'May', 'June'],
      datasets: [
        {
          label: 'Net Spend',
          backgroundColor: '#37B04C',
          data: [40, 20, 30, 55, 40, 70]
        }
      ]
    },
    options: {
        responsive: true,
        maintainAspectRatio: false,
        scales: {
            yAxes: [{
                ticks: {
                    beginAtZero: true
                },
                gridLines: {
                    display: true
                }
            }],
            xAxes: [{
                ticks: {
                    beginAtZero: true
                },
                gridLines: {
                    display: false
                }
            }]
        },
        legend: {
            position: "bottom"
        }
    }
  }),
  mounted () {
    this.renderChart(this.chartdata, this.options)
  }
}
</script>

<style>
</style>
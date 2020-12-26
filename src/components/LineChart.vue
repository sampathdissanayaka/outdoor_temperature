<script>
import {Line} from "vue-chartjs";

export default {
    extends: Line,
    props: {
        label: {
            type: String
        },
        chartData: {
            type: Array
        },
        option: {
            type: Object
        }
    },
    mounted() {
        const dates = this.chartData.map(singleData => singleData.date).reverse();
        const totals = this.chartData.map(singleData => singleData.total).reverse();

        this.renderChart({
            labelS: dates,
            datasets: [{
                label: this.label,
                data: totals,
            }],
        },
         this.options
         );
    }


};
</script>
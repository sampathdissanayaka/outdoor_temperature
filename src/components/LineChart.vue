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
        const dates = this.chartData.map(d => d.date).reverse();
        const totals = this.chartData.map(d => d.total).reverse();

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
<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator";
import { Line } from "vue-chartjs";

@Component({
  extends: Line,
})
export default class LineChart extends Vue {
  @Prop({ type: Object, default: null }) readonly chartdata!: any | null;
  @Prop({ type: Object, default: null }) readonly options!: any | null;

  mounted() {
    (this as any).renderChart(this.chartdata, this.options);
  }
}
</script>

<style scoped lang="scss"></style>

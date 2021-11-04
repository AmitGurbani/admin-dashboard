<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator";
import { Bar } from "vue-chartjs";

@Component({
  extends: Bar,
})
export default class BarChart extends Vue {
  @Prop({ type: Object, default: null }) readonly chartdata!: any | null;
  @Prop({ type: Object, default: null }) readonly options!: any | null;

  mounted() {
    (this as any).renderChart(this.chartdata, this.options);
  }
}
</script>

<style scoped lang="scss"></style>

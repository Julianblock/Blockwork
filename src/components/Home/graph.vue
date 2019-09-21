<template>
    <div>
        <vue-funnel-graph :width="width" :height="height" :labels="labels"
              :values="values" :colors="colors" :sub-labels="subLabels" :direction="direction"
              :gradient-direction="gradientDirection"
              :animated="true" :display-percentage="true"
        >       
        </vue-funnel-graph>
    </div>
</template>

<script>
import { VueFunnelGraph } from 'vue-funnel-graph-js';

export default {
  name: 'app',
  components: {
      VueFunnelGraph
  },
  data() {
      return {
          labels: ['Impressions', 'Resumes sent', 'Interested Recruiters'],
          subLabels: ['Direct', 'Social Media', 'Ads'],
          values: [
          // with the given Labels and SubLabels here's what the values represent:
          // 
          // Direct, Social, Ads  
          //    |      |     |  
          //    v      v     v
              [3000, 2500, 6500], // Segments of "Impressions" from top to bottom
              [3000, 1700, 1000], // Segments of "Add To Cart"
              [600,  200,  130]   // Segments of "Buy"
          ],
          colors: [
              ['black', 'green'], // color set for "Impressions" segment
              ['green', '#fff'], // color set for "Add To Cart" segment
              ['#A0F9FF', 'green']  // color set for "Buy" segment
          ],
          direction: 'horizontal',
          gradientDirection: 'horizontal',
          height: 300,
          width: 800
      };
  }
}
</script>
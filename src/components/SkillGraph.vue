<template>
  <div id="skillGraph">
  </div>
</template>

<script>
import { setTimeout } from 'timers';

export default {
  name: 'SkillGraph',
  data() {
    return {
      skillTypes: [
        {
          name: 'Backend Dev',
          color: '#6b486b',
          percent: 41.4
        },
        {
          name: 'Cloud Ops',
          color: '#7b6888',
          percent: 27.1
        },
        {
          name: 'Web Dev',
          color: '#ccccee',
          percent: 19.8
        },
        {
          name: 'SQL',
          color: '#dddddd',
          percent: 11.8
        }
      ]
    }
  },
  mounted: function () {
    drawCircleGraph(this.skillTypes);

      //Give animation time to finish
      setTimeout(function(){
        var outer = document.getElementById('skillGraphContainer').offsetWidth;
        var inner = document.getElementById('skillGraph').offsetWidth;

        document.getElementById('skillGraphContainer').scrollLeft = (inner-outer)/2;
      }, 100)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#skillGraph {
  height: 100%;
  width: 550px;
  margin: auto;
  display: none;
}
</style>
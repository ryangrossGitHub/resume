<template>
  <div class="container">
    <div class="row">
      <div class="col">
        <h4>Core Skills</h4>
        <ul class="list-group list-group-flush">
          <li v-for="skill in this.skills" class="list-group-item"> 
            {{ skill }}
          </li>
        </ul>
      </div>
      <div class="col-lg-auto">
        <h4>Time Allocation (Last 5 Years)</h4>
        <div id="skillGraphContainer">
          <SkillGraph />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import SkillGraph from './SkillGraph.vue'

export default {
  name: 'Skills',
  components: {
    SkillGraph
  },
  data() {
    return {
      skills: [
        'Java (Spring Boot, Grails, Hibernate)',
        'Amazon Web Services (Production usage of EC2, ELB, EBS, AutoScaling, RDS, CloudWatch, IAM, STS, SNS)',
        'NodeJS (AWS SDK)',
        'DevOps Tools (Git, GitHub, Jenkins, Swagger, Selenium, AWS Cloudwatch Logs)',
        'SQL (Oracle, MySQL)',
        'HTML & CSS & JavaScript (Angular & Ext JS)',
        'Linux (Bash, Cron)'
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.col {
  margin-top: 2rem;
}
.list-group {
  text-align: left;
}
li {
  border: none;
}
.col-lg-auto {
  min-width: 47%;
  min-height: 350px;
  margin-top: 2rem;
}
#skillGraphContainer {
  width: 100%;
  height: 100%;
  overflow-x: auto;
  overflow-y: hidden;
}
</style>